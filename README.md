# Windows desktop Computer Use for Codex

A small, reusable Codex skill for discovering the Computer Use API available in the current Windows session, selecting the intended desktop window, and checking GUI input on screen. App-specific steps belong in each project's own runbook.

## Install

Ask Codex to install this skill with `skill-installer` from:

`https://github.com/nao40031/codex-windows-desktop-computer-use/tree/main/skills/windows-desktop-computer-use`

Then start a new Codex session so the skill appears in its available skills. The repository is small enough for the installer's normal download method.

## Use in a project

Add a short instruction to the project's root `AGENTS.md`:

```md
- Before controlling a Windows desktop app, use the `windows-desktop-computer-use` skill to discover the current API, select the intended window, and verify input on screen. Follow the project's own GUI runbook for app-specific steps.
```

The skill supplements the bundled `computer-use` plugin when that plugin is available; it does not replace the plugin's API reference or confirmation guidance.

## Shared browser operation

For workflows spanning local Windows Codex and ChatGPT Work, see the [shared browser operation guide](docs/browser-operation-workflow.md).

The companion [browser-operation skill](skills/browser-operation) defines the shared entry point and environment adapters. In Codex, install it from:

`https://github.com/nao40031/codex-windows-desktop-computer-use/tree/main/skills/browser-operation`

In ChatGPT Work, use the skill where that Work surface supports installed skills; otherwise paste the guide's [portable task instructions](docs/browser-operation-workflow.md#portable-instructions-for-work). Installation does not connect Work's cloud browser to local Chrome.

When a connected Chrome tab drops during a task, the skill checks the current session again, then tries the same Chrome profile in a new tab if only the original tab fails. It resumes from the last verified state if the connection returns. If the task still cannot use the browser, this user authorizes the skill to reuse or create one browser-capable successor and continue the work there without asking again. For a task requiring the Chrome extension or the user's signed-in Chrome profile, the successor must use local Codex/Codex Remote on the connected host; cloud-only Work browser is a different session and does not qualify. Work qualifies only when local-computer access and Chrome extension are both exposed in that task. The skill cannot enable a Chrome extension in an unavailable execution environment or bypass user-only authentication challenges, site restrictions, or workspace restrictions. For local Codex projects, a short `AGENTS.md` instruction can make this preference explicit:

```md
- For website UI tasks, use `browser-operation` proactively. Before reporting missing browser tools, inspect callable and supported deferred tools and invoke the documented browser/tab inventory; report what was checked. Follow documented recovery once, preserving valid browser bindings when required. If only the original tab fails, try its confirmed URL once in a new tab in the same Chrome profile. If the user requires the Chrome extension or signed-in Chrome profile, use local Codex/Codex Remote on the connected host; a cloud-only Work browser is not a substitute. If capability is still missing, reuse or create one browser-capable task when authorized and supported, then continue the work there; otherwise provide the full ready-to-send handoff prompt. Respect site and workspace restrictions.
- Support capability and completion claims with actual results in the relevant task. Treat screenshots and prior assistant statements as reports until verified, label hypotheses and unverified checks, and reconcile conclusions with earlier success or user corrections.
```
