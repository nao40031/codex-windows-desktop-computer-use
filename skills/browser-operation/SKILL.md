---
name: browser-operation
description: Choose and operate supported browser or desktop surfaces across local Windows Codex and ChatGPT Work. Use for browser access, signed-in sessions, or diagnosing a missing browser surface.
---

# Browser operation

Apply the shared rules in [the workflow guide](../../docs/browser-operation-workflow.md) before choosing a browser or desktop surface.

1. Discover the browser/app controls actually exposed in this task. Do not infer cross-session availability.
2. Choose the surface using the guide's decision order and the user's requested environment.
3. Check the exact website, account, and current page before any action that changes external state.
4. Observe before acting and verify after acting. Stop when the site, product, or workspace blocks the task.
5. Report the surface used, what you verified, and any boundary or handoff.

For local Windows Codex native-app work, also use the `windows-desktop-computer-use` skill and follow the bundled Computer Use guidance. Do not use native Windows UI automation for terminal commands, authentication dialogs, or security prompts.

Work's remote cloud browser is a separate computer. Never claim it can use local Chrome cookies, extensions, tabs, or desktop apps. Do not bypass website, product, or workspace restrictions.
