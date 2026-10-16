# Codex UI operations

Reusable skills for choosing and using the interface needed by a Codex task. The existing Windows desktop skill remains available for Computer Use; the new routing skill covers browser and desktop tasks together. App-specific steps belong in each project's runbook.

## Skills

- [`codex-ui-operations`](skills/codex-ui-operations/SKILL.md): chooses a connected tool, Browser, Chrome, or desktop surface; confirms the target; verifies the result.
- [`windows-desktop-computer-use`](skills/windows-desktop-computer-use/SKILL.md): discovers the current Windows Computer Use API, selects a desktop window, and checks GUI input on screen.

These skills describe workflows. They do not install Browser, Chrome, Computer Use, or a service connector, and they do not replace those tools' API references or access requirements. The Windows skill can still be installed and used by itself.

## Install

Ask Codex to install each skill with `skill-installer` from:

```text
https://github.com/nao40031/codex-windows-desktop-computer-use/tree/main/skills/codex-ui-operations
https://github.com/nao40031/codex-windows-desktop-computer-use/tree/main/skills/windows-desktop-computer-use
```

Start a new Codex session so the installed skills appear in its available skills. Install the browser and desktop integrations needed for the tasks you intend to run.

## Use in a project

Add this short instruction to the project's root `AGENTS.md` when its work includes UI operations:

```md
- When a task requires browser or desktop UI interaction, use the `codex-ui-operations` skill to select the available surface, confirm the target, and verify the result. Use `windows-desktop-computer-use` for Windows app procedures. Follow this project's app-specific runbook.
```

The routing skill can also be invoked directly without adding project instructions. A repository `AGENTS.md` applies to work in that repository; this example is for the project where Codex will operate.

## Adoption

1. Keep existing Windows workflows on `windows-desktop-computer-use` while installing the routing skill for browser tasks.
2. Try read-only tasks on an in-app Browser tab, an existing Chrome tab, and a native Windows window. Confirm the selected URL or window and the observed result in each case.
3. Try a controlled navigation and input task on each surface, following the relevant tool's permission requirements. Check that a missing connection or unverifiable URL produces a clear stop and report.
4. Add the `AGENTS.md` instruction to projects whose runbooks and available integrations are ready. Refine the skills from observed failures without adding application-specific paths to the shared rules.

For the product's surface distinctions, see OpenAI's [Computer, Browser, and Chrome walkthrough](https://developers.openai.com/training/walkthroughs/using-your-computer-and-browser).
