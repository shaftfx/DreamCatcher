# Skill: post-recap-issue

Used by `routines/eod.md` and `routines/weekly.md` to publish a recap as a GitHub Issue.

**Input:** title, body markdown, label.
**Output:** an open Issue on `shaftfx/DreamCatcher`. URL logged.

---

## Procedure

### 1. Idempotency check — don't double-post

Before creating, list issues with the same title:

```bash
gh issue list \
  --repo shaftfx/DreamCatcher \
  --state open \
  --search "<EXACT_TITLE> in:title" \
  --json number,title
```

If a result matches the title exactly: instead of creating, post a comment to that issue with a "(re-run note)" prefix. Do not create a duplicate.

### 2. Try `gh` first

```bash
gh issue create \
  --repo shaftfx/DreamCatcher \
  --title "<TITLE>" \
  --label "<LABEL>" \
  --body-file /tmp/recap_body.md
```

Write the body to a file first to avoid escaping nightmares with backticks, code blocks, and pipes:

```bash
cat > /tmp/recap_body.md <<'BODY_EOF'
<the full markdown body, as-is, no shell expansion>
BODY_EOF

gh issue create --repo shaftfx/DreamCatcher \
  --title "<TITLE>" \
  --label "<LABEL>" \
  --body-file /tmp/recap_body.md
```

The single-quoted `'BODY_EOF'` heredoc disables variable expansion — important if the body contains literal `$` (e.g. dollar amounts) or backticks.

### 3. Capture the URL

`gh issue create` prints the issue URL on stdout. Capture and log it.

### 4. Fallback: REST API

If `gh` is not authenticated in the cloud routine environment (run-time check: `gh auth status` returns non-zero), fall back to the GitHub REST API. This requires a `GITHUB_TOKEN` env var — note in `SETUP.md` that the user should provision one with `repo` scope if `gh` isn't available.

```bash
BODY_JSON=$(jq -Rs . < /tmp/recap_body.md)   # safely escape for JSON

curl -s -X POST \
  -H "Authorization: token $GITHUB_TOKEN" \
  -H "Accept: application/vnd.github+json" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/repos/shaftfx/DreamCatcher/issues \
  -d "{\"title\": \"<TITLE>\", \"body\": ${BODY_JSON}, \"labels\": [\"<LABEL>\"]}"
```

### 5. Verify it landed

After creation, fetch the issue's URL from the response and confirm a 201 status. Log to `research_log.md`:

```markdown
- <UTC timestamp> — Issue posted: <URL>
```

If creation failed (non-2xx response): log the failure, do NOT crash the routine. The routine's primary job (orders, memory updates) is more important than the recap. The recap can be re-posted manually if needed.

---

## Title and label conventions (do not deviate)

| Routine | Title format | Label |
|---|---|---|
| `eod.md` | `Recap YYYY-MM-DD` | `daily-recap` |
| `weekly.md` | `Weekly Review YYYY-Www` (ISO week) | `weekly-recap` |
| Kill-switch (any routine) | `🚨 KILL-SWITCH YYYY-MM-DD` | `kill-switch` |

The user filters and reads issues by label. If the labels don't exist on the repo yet, create them once at first run:

```bash
gh label create "daily-recap"   --color "0E8A16" --description "Daily EOD recap"     --repo shaftfx/DreamCatcher 2>/dev/null
gh label create "weekly-recap"  --color "1D76DB" --description "Friday weekly review" --repo shaftfx/DreamCatcher 2>/dev/null
gh label create "kill-switch"   --color "B60205" --description "Drawdown halt — needs human re-arm" --repo shaftfx/DreamCatcher 2>/dev/null
```

(`2>/dev/null` suppresses errors from labels that already exist.)

---

## Body length guidance

- **Daily recap**: target 200–600 words. Tables should be tight. One paragraph for "what I noticed," not three.
- **Weekly recap**: 400–1,000 words. More room for lessons, but still scannable.
- **Kill-switch**: under 200 words, plus the table of liquidated positions. The user sees the title, panics for a second, reads the body — make it crystal clear.
