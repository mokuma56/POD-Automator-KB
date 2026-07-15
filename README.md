# POD-Automator-KB

Shared Knowledge Base for the **POD Automator** — Cisco One Experience Lab proctor tool.

## What This Is

This repository stores KB articles that are automatically synced to every proctor's local
POD Automator instance when they click **⬆ Check for Updates** in the dashboard.

Articles cover troubleshooting tips, pipeline failure resolutions, infrastructure notes,
and lab procedures contributed by proctors across sessions.

## How It Works

- `articles.json` — the full KB article database (JSON array)
- On every `Check for Updates`, POD Automator pulls this repo and imports any new articles
  into the local SQLite knowledge base (existing articles are never overwritten)
- Proctors with a GitHub Personal Access Token can publish an article directly from the
  dashboard KB tab → "🌐 Contribute to Shared KB" button

## Contributing an Article

1. Write and publish an article in the POD Automator dashboard (Knowledge Base tab)
2. Click **🌐 Contribute to Shared KB** on the article
3. Enter your GitHub Personal Access Token when prompted (needs `public_repo` scope)
4. The article is committed to this repo automatically
5. Other proctors get it on their next **Check for Updates**

## GitHub Token Setup (One Time)

1. Go to https://github.com/settings/tokens/new
2. Note: `POD Automator KB contributor`
3. Scope: check **`public_repo`** only
4. Copy the token
5. In the POD Automator dashboard → Knowledge Base tab → paste token in the **KB Settings** field

## Repo Access

- **Read** (pull articles) — public, no token needed
- **Write** (push new articles) — requires collaborator access or token with `public_repo` scope
  Contact the lab owner to be added as a collaborator.

## Article Schema

```json
{
  "title": "Article title",
  "body":  "Markdown content",
  "tags":  "comma,separated,tags",
  "category": "general | pipeline-failure | sdwan | infrastructure | dashboard | upgrade",
  "status": "published",
  "created_at": "2026-07-14 17:00:00"
}
```
