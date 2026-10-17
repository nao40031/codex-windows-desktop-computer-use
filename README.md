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

In ChatGPT Work, use the skill where that Work surface supports installed skills; otherwise apply the guide's environment adapter in the task instructions. Installation does not connect Work's cloud browser to local Chrome.

When a connected Chrome tab drops during a task, the skill checks the current session again and resumes from the last verified state if the connection returns. It cannot enable a Chrome extension in an unavailable or remote execution environment. For local Codex projects, a short `AGENTS.md` instruction can make this preference explicit:

```md
- For tasks needing a browser, use the `browser-operation` skill to discover and choose an available surface proactively. Recheck a dropped Chrome connection once through documented tools, then resume from the last verified state or report the actual blocker.
```
