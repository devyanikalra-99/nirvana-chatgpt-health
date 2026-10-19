# Nirvana × ChatGPT Health — prototype flows

Four self-contained pages. No build step, no dependencies. Each folder is one Vercel project with its own public link.

| Folder | Flow | Vercel project name (suggested) |
|---|---|---|
| `flow-1-insurance-wallet/` | Flow 1 — Insurance Wallet in ChatGPT Health | `nirvana-flow-1` |
| `flow-2-symptoms-appointment/` | Flow 2 — Checking Symptoms and Scheduling an Appointment | `nirvana-flow-2` |
| `flow-3-insurance-updates/` | Flow 3 — Insurance Updates Triggered to ChatGPT Users | `nirvana-flow-3` |
| `combined-flow/` | Combined Flow (all three back to back) | `nirvana-combined` |

Each page auto-plays. Clicking inside the phone pauses the video and makes the UI live. Controls under the phone: Back · Pause · Replay · Next.

## One-time setup (about 10 minutes)

### 1. Put this folder on GitHub — once
1. github.com → **New repository** → name it `nirvana-chatgpt-health` → **Create repository**.
2. On the empty-repo page click **uploading an existing file**, drag in the four folders and this README exactly as they are (keep the folder structure), click **Commit changes**.

### 2. Create four Vercel projects from that one repo
Repeat these steps four times, once per folder:
1. vercel.com → **Add New… → Project** → **Import** `nirvana-chatgpt-health`.
2. **Project Name:** e.g. `nirvana-flow-1`.
3. **Root Directory:** click **Edit** and pick the folder (`flow-1-insurance-wallet`).
4. Framework Preset **Other**, Build Command blank, Output Directory blank.
5. **Deploy**. Copy the link Vercel gives you (`https://nirvana-flow-1.vercel.app`).

Do the same with `flow-2-symptoms-appointment` → `nirvana-flow-2`, `flow-3-insurance-updates` → `nirvana-flow-3`, `combined-flow` → `nirvana-combined`.

You end up with four links to share. Future edits: replace the `index.html` in the relevant folder on GitHub; the matching Vercel project redeploys itself.

### Alternative: four separate repos
If you'd rather keep them fully separate, create four repos and upload one folder's contents (`index.html` + `vercel.json`) into each, then import each repo into Vercel with Root Directory left at `./`.

### Terminal alternative
```bash
git init && git add . && git commit -m "Nirvana × ChatGPT Health prototype flows"
git branch -M main && git remote add origin https://github.com/<you>/nirvana-chatgpt-health.git && git push -u origin main
cd flow-1-insurance-wallet && npx vercel --prod && cd ..
cd flow-2-symptoms-appointment && npx vercel --prod && cd ..
cd flow-3-insurance-updates && npx vercel --prod && cd ..
cd combined-flow && npx vercel --prod && cd ..
```
