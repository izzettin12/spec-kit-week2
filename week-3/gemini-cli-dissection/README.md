# Week 3 — Gemini CLI Dissection

The Gemini CLI track's working copy and submission artifacts are under `work/`. The
baseline test was run before the agent changed the starter files: **2 failed, 12
passed**.

## Installed tooling

Node.js `v26.13.0` and Gemini CLI `0.64.0` are installed. Run `gemini.cmd` from
PowerShell; the `gemini.ps1` shim is blocked by this machine's PowerShell execution
policy. Close and reopen VS Code (or at least its terminal) to refresh PATH, then check
`gemini.cmd --version` prints `0.64.0`.

## Session status

The real session was captured using Gemini CLI `0.64.0` and
`gemini-3.5-flash-lite`. The agent completed its task, and the final suite passed
independently (**22 passed**). The evidence and writeup are under `work/`.

The raw `work\telemetry.log` contains account details and prompt contents. It is local
and must never be committed. Only the redacted prompt export, generated summaries,
run copy, and writeup belong in the submission.
