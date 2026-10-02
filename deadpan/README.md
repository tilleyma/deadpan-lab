# Deadpan Lab

Upload a photo, pick a format, get a deadpan write-up card to share.
Friends-only lab build. Runs on GitHub + Netlify, same as Bindig.

## What's here

| File | What it does |
|---|---|
| `tone-guide.md` | **The voice.** Read by the AI on every request. Edit it, push, and the humour changes. |
| `public/index.html` | The page: upload, format choice, card, share/save |
| `netlify/functions/caption.mjs` | Server function that sends the photo + tone guide to Claude |
| `netlify.toml` | Netlify config |

## Set up (about 10 minutes)

1. Create a new GitHub repo (e.g. `deadpan-lab`) and push this folder to it.
2. In Netlify: **Add new project → Import from Git →** pick the repo. Build settings come from `netlify.toml`.
3. In Netlify **Project configuration → Environment variables**, add:

| Variable | Value |
|---|---|
| `ANTHROPIC_API_KEY` | A key from console.anthropic.com (set a monthly spend limit) |
| `LAB_PASSCODE` | Any word you share with friends, e.g. `kebab` |
| `DEADPAN_MODEL` | Optional. Defaults to `claude-sonnet-5-5` |

4. Redeploy. Send friends the link and the passcode.

## Privacy and guardrails

- Photos are resized in the browser, sent once, and never saved.
- The AI refuses photos that may include under-18s, anything explicit, or distressing scenes.
- Jokes target the scene, never people's looks.

## Cost

Roughly one image request per card. Set a spend cap in the Anthropic console before sharing.

## Lab test

- 10–15 friends, real photos, 2 weeks.
- **Exit test:** do they share cards without being asked?
