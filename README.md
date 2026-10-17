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
For workflows spanning local Windows Codex and ChatGPT Work, see the [shared browser operation guide](docs/browser-operation-workflow.md). The companion [browser-operation skill](skills/browser-operation) defines the shared entry point and environment adapters. ChatGPT Work's cloud browser runs remotely and cannot use local Chrome state.
