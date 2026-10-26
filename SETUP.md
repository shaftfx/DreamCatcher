# SETUP — going from this repo to a running bot

You have to do this once. After it's done, the bot runs hands-off on a cron schedule.

Total time: **~30 minutes**, mostly waiting for Alpaca to verify your account.

---

## Prerequisites

- A GitHub account with push access to `shaftfx/DreamCatcher` (you, the owner)
- A paid Claude plan ($20/mo Pro or any Max tier) — required for **routines** (cloud-scheduled Claude Code runs)
- The **Claude Desktop App** installed (not the CLI you've been using to build this — the desktop app is where routines are managed)

---

## Step 1 — Alpaca paper account

1. Go to **alpaca.markets** → "Sign Up" → choose **Trading API**.
2. After signing up, you'll be in the dashboard. By default you have a paper account with $100,000 simulated balance.
3. **(Optional)** Reset the paper balance to $10,000 to match your intended live capital: dashboard → Paper Trading → "Reset Account" → set initial deposit to $10,000.
4. On the right side of the dashboard, click **"Generate New Keys"** under the Paper Trading section.
5. Copy both values **right now**:
   - `API Key ID` — this becomes `ALPACA_API_KEY`
   - `Secret Key` — this becomes `ALPACA_SECRET_KEY`

   The secret is shown **once**. If you lose it, regenerate.

The base URL for paper trading is `https://paper-api.alpaca.markets/v2`.

---

## Step 2 — Perplexity API key

> **Note (2026-10-26):** Perplexity is no longer used — routines use WebSearch instead. You can skip this step. Do not add `PERPLEXITY_API_KEY` to the Trading environment.

---

## Step 3 — Install Claude Desktop App

1. Download from **claude.com/download** for your OS.
2. Sign in with the same account that has the paid plan.
3. Confirm you see the **"Routines"** option in the left sidebar of a new session. If not, your plan doesn't include routines — upgrade.

---

## Step 4 — Create the "trading" cloud environment

Cloud environments hold your secrets so they're available to remote routines without committing them to the repo.

1. In the desktop app: **New Routine** → at the top, switch to **Remote** (not Local).
2. Click **Cloud Environments** → **Add One**.
3. Name it: **`trading`**.
4. **Network access**: full (the routine needs to reach Alpaca and GitHub).
5. **Environment variables** — add exactly these (case-sensitive):

   | Name | Value |
   |---|---|
   | `ALPACA_API_KEY` | (from Step 1) |
   | `ALPACA_SECRET_KEY` | (from Step 1) |
   | `ALPACA_BASE_URL` | `https://paper-api.alpaca.markets/v2` |
   | `ALPACA_DATA_URL` | `https://data.alpaca.markets/v2` |

   ⚠️ A single typo or extra space in a variable name will break the routine silently. Double-check.

6. Save the environment.

---

## Step 5 — `GITHUB_TOKEN` (required for Issue creation fallback)

The routines post daily recap Issues via the built-in GitHub MCP connector (installed automatically). `GITHUB_TOKEN` is a fallback for the `gh` CLI inside the container.

> **Known issue (2026-10-26):** `gh auth status` in the cloud container returns "Failed to log in to github.com using token (GITHUB_TOKEN)" even when the token is set. Issues are posted successfully via the built-in connector instead. The `GITHUB_TOKEN` fallback path in `skills/post-recap-issue.md` is not currently working. To fix: regenerate the token with `repo` scope at github.com → Settings → Developer settings → Personal access tokens → Tokens (classic), and update the Trading environment variable.

To add or replace the token:
1. Go to **github.com → Settings → Developer settings → Personal access tokens → Tokens (classic)**.
2. **Generate new token (classic)** with scope: `repo`.
3. Copy the token. Add to the `trading` cloud environment as `GITHUB_TOKEN`.

---

## Step 6 — Create the 5 routines

For each of the 5 files in `routines/`, create a routine in the desktop app:

| Routine name | Cron | File | Timezone |
|---|---|---|---|
| `bull-premarket` | `0 6 * * 1-5` | `routines/premarket.md` | `America/New_York` |
| `bull-open` | `35 9 * * 1-5` | `routines/open.md` | `America/New_York` |
| `bull-midday` | `30 12 * * 1-5` | `routines/midday.md` | `America/New_York` |
| `bull-eod` | `15 16 * * 1-5` | `routines/eod.md` | `America/New_York` |
| `bull-weekly` | `0 17 * * 5` | `routines/weekly.md` | `America/New_York` |

For each routine:

1. **New Routine** → **Remote**
2. **Schedule** → cron string from the table → timezone `America/New_York`
3. **Repository** → `shaftfx/DreamCatcher`, branch `main`
4. **Cloud environment** → `trading` (the one you made in Step 4)
5. **Model** → **Claude Opus 5.5**
6. **Prompt** → paste the entire contents of the corresponding `routines/*.md` file. The full file IS the prompt.
7. **Permissions** → toggle **"allow unrestricted branch pushes" ON** ⚠️ (critical — without it, Claude can only push to `claude/*` branches and the next routine won't see updates)
8. Save.

---

## Step 7 — Smoke test

Don't wait until 6am Monday to find out a typo broke everything.

1. Click on `bull-weekly` (any routine works for a smoke test, but weekly is cheapest — no orders, just a recap).
2. Click **Run Now**.
3. Watch the live execution view. You should see Claude:
   - Read the boot files
   - Pull Alpaca account state (verifies all 3 Alpaca env vars work)
   - Compute a (mostly empty) weekly review
   - Open a GitHub Issue (verifies GitHub connector works)
   - Push to `main` (verifies the unrestricted-pushes permission)
4. Go to **github.com/shaftfx/DreamCatcher/issues** — you should see the issue.
5. Go to **github.com/shaftfx/DreamCatcher/commits** — you should see a new commit on `main` from the routine.

If any step fails, the live view shows the error. Common issues:

| Symptom | Fix |
|---|---|
| `401 Unauthorized` from Alpaca | Re-check `ALPACA_API_KEY` / `ALPACA_SECRET_KEY` in the cloud env (no leading/trailing spaces) |
| Push fails with permission error | Toggle "allow unrestricted branch pushes" ON for the routine |
| Issue creation fails | Check that the Claude GitHub App is installed on `shaftfx/DreamCatcher` (github.com/apps/claude/installations/select_target) |
| `gh` returns "Failed to log in" | Known issue — see Step 5. Issue creation still works via built-in connector. |

---

## Step 8 — Watch the bot run

Once the smoke test passes, the cron takes over. Tomorrow morning at 6am ET, the premarket routine fires automatically.

Where to watch:

- **GitHub Issues** (`shaftfx/DreamCatcher/issues`) — daily and weekly recaps land here. GitHub emails you on each.
- **`memory/portfolio.md` on `main`** — current state, refreshed every routine.
- **`memory/trade_log.md` on `main`** — every fill ever.
- **Commit history on `main`** — every routine run leaves a commit. Healthy bot = ~5 commits per weekday.

---

## Switching from paper to live

When you're confident the bot is performing (paper bake-in of at least **3 months recommended**), switch:

1. Open a real-money trading account on Alpaca (verification can take a few days).
2. Generate **live** API keys from Alpaca.
3. In the `trading` cloud environment, **change**:
   - `ALPACA_API_KEY` → live key
   - `ALPACA_SECRET_KEY` → live secret
   - `ALPACA_BASE_URL` → `https://api.alpaca.markets/v2` (no `paper-api`)
4. Save the env. The routines pick up the new values on their next run.
5. Open a GitHub Issue manually titled `"Going live YYYY-MM-DD"` so the journal records the transition.

⚠️ Strongly recommended: when going live, start by lowering `RULES.md` P1 to 2% (instead of 5%) and P3 to 0.5% (instead of 1.5%) for the first 30 days. Bigger drawdowns are real money now.

---

## Killing the bot

To pause: in the desktop app, **disable** each routine. They stop firing. Re-enable to resume.

To stop entirely: delete the routines.

To recover from a kill-switch (when `halt_until_human: YES` is set in `portfolio.md`):
1. Read the kill-switch GitHub Issue. Understand why it triggered.
2. Manually edit `memory/portfolio.md` on `main`: set `halt_until_human: NO`.
3. Decide if you want to also tighten rules (e.g. lower position size cap) before re-arming.
4. Commit the change. The next scheduled routine resumes.

---

## Tweaking strategy or rules

Edit `RULES.md` or `STRATEGY.md` directly on `main`. The next routine reads them. Commit with a clear message — git history becomes your strategy changelog.

`memory/learnings.md` accumulates over time. Read it monthly. The patterns it surfaces are the most valuable output of this entire system.
