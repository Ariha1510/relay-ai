# RELAY AI — Functional Hackathon MVP

A browser-based project knowledge handover prototype. It supports document uploads (PDF, DOCX, TXT, MD, CSV, JSON), pasted meeting/chat notes, public GitHub repository activity, source-linked claims, human review, approval, and print-to-PDF export.

## Run locally

This is a static app. Open `index.html` in a modern browser, or serve the folder:

```bash
python -m http.server 8000
```

Then visit http://localhost:8000.

## Deploy so judges can open a link

**GitHub Pages:**
1. Create a public GitHub repository, e.g. `relay-ai-mvp`.
2. Upload `index.html` and `README.md` to the repository root.
3. Open Settings → Pages.
4. Under Build and deployment, choose Deploy from a branch → `main` → `/ (root)` → Save.
5. Wait for deployment. The public app URL will be `https://YOUR-USERNAME.github.io/relay-ai-mvp/`.
6. Open the URL in an incognito window and test the demo before submitting.

You can also deploy the folder using Netlify Drop or Vercel static deployment.

## Judge demo flow

1. Open the public URL.
2. Click **Load demo project**.
3. Open **Handover draft** and inspect the generated sections.
4. Open **Evidence & review**. Every extracted claim displays a source ID, source name and excerpt.
5. Verify each claim using its checkbox (or edit/flag claims). Click **Approve handover** only after all claims are reviewed.
6. Return to the handover and click **Print / Save as PDF**. Choose Save as PDF in the browser print dialog.

## Current MVP scope and limitations

- The demo includes a deterministic extraction/classification pipeline so the core workflow works without an API key. It is not a general-purpose LLM and does not invent missing details.
- PDF and DOCX text extraction use public CDN libraries; an internet connection is needed for those formats.
- GitHub integration reads public repository README, recent commits and open issues via the GitHub REST API. Private repositories and authenticated OAuth are not included in this MVP.
- All processing happens in the browser. The app does not upload sources to a server or persist data after the page is closed/refreshed.
- “Approve all reviewed” is a convenience for demo data. For real use, inspect every source excerpt and edit or flag incorrect claims before approval.
- The MVP intentionally avoids collecting credentials, secrets or payment data.

## Privacy note

Do not upload passwords, API keys, access tokens, private customer data or other sensitive information. The public GitHub API is used only for public repositories. For a production version, add server-side access controls, OAuth scopes, audit logs, retention controls and encrypted storage.
