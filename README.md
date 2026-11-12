## Relay AI
Knowledge handovers shouldn't mean lose-your-mind context switching.

**Relay AI** is a zero-backend, browser-based prototype built to make project handoffs painless. Instead of digging through months of scattered docs, meeting transcripts, and GitHub issues, Relay pulls everything together into a clean, source-verified handover document that you can actually trust.

 ## Quickstart (Run Locally)
Since Relay AI runs entirely in the browser, getting it up and running takes seconds:

- Clone or download this repository.
- Serve the directory using Python's built-in HTTP server:
- Bash
python -m http.server 8000
Open http://localhost:8000 in any modern web browser.

(Or simply double-click index.html to open it directly!)

## Walkthrough
To see Relay AI in action, follow this quick flow:

- Load Sample Data: Open the app URL and click Load demo project.

- Inspect the Draft: Navigate to the Handover draft tab to see structured sections created from raw project noise.

- Trace the Evidence: Head to Evidence & review. Every generated claim links directly to its source ID, document name, and raw excerpt.

- Audit & Approve: Verify claims using the checkboxes (or edit/flag anything that looks off). Once ready, click Approve handover.

- Export: Hop back to the handover view, click Print / Save as PDF, and save your final handover document.

## Features & Current Capabilities
- Multi-Format Ingestion: Drag and drop PDFs, Word files (.docx), plain text, Markdown, CSV, and JSON.

- GitHub Context: Paste a public repo URL to pull in READMEs, recent commits, and open issues via the GitHub REST API.

- Traceable Claims: Every insight points directly back to its original source sentence so nothing is hallucinated.

- Client-Side Privacy: Zero server uploads. Everything processes right inside your browser session.

## Limitations
Deterministic Extraction: This MVP uses a deterministic extraction pipeline rather than live LLM API calls.

Network Needs: Text extraction for .pdf and .docx files relies on lightweight CDN libraries, so an active internet connection is needed for those formats.

Public GitHub Only: The GitHub integration uses unauthenticated public API calls (private repos and OAuth are out of scope for this prototype).

In-Memory Storage: Data resets when the browser tab is refreshed or closed.

## Privacy & Safety Notice
Relay AI runs 100% locally in your browser — no data or uploaded files leave your device.

## Reminder: Do not paste passwords, secret keys, or sensitive customer records into public hackathon demos. Production iterations will introduce server-side access controls, OAuth scopes, audit logs, and encrypted persistence.
