---
name: browser-operation
description: Choose, use, and recover supported browser or desktop surfaces across local Windows Codex and ChatGPT Work. Use for browser access, signed-in sessions, or a disconnected Chrome extension.
---

# Browser operation

Read [the workflow reference](references/workflow.md) before selecting a browser or desktop surface.

1. When the task needs a browser, discover the browser/app controls actually exposed in this task without waiting for a separate request to enable Chrome. Do not infer cross-session availability.
2. Choose the surface using the workflow reference and the user's requested environment.
3. Check the exact website, account, and current page before any action that changes external state.
4. Observe before acting and verify after acting. If a connection fails, follow the reference's recovery steps and resume the pending task when the same surface is restored. Stop when the site, product, or workspace blocks the task.
5. Report the surface used, what you verified, and any boundary or handoff.

For local Windows Codex native-app work, also use the `windows-desktop-computer-use` skill and follow the bundled Computer Use guidance. Do not use native Windows UI automation for terminal commands, authentication dialogs, or security prompts.

Work's cloud browser has separate state from local Chrome. A mobile prompt can use the host's Chrome only through a supported connected-computer route that exposes that browser to the current task. Do not bypass website, product, or workspace restrictions.
