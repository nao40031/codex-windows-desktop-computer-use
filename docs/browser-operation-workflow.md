# Shared browser operation workflow

This guide describes the supported browser and desktop routes across local Windows Codex and ChatGPT Work.

The canonical workflow is bundled with the [browser-operation skill](../skills/browser-operation/SKILL.md), including its [environment adapters and operating rules](../skills/browser-operation/references/workflow.md). The skill folder includes the reference so the guide remains available after the skill is installed.

ChatGPT Work's cloud browser has separate state from local Chrome. Mobile access to a connected computer follows either Codex/Remote or, where enabled, a new eligible Work Cloud task with local computer access. Browser controls must still be discovered in that task. A site or workspace block must be respected.

## Portable instructions for Work

Local skill installation does not guarantee that a Work task loads the skill. If the task cannot read it, paste the following instructions alongside the task's goal. These instructions guide tool discovery and recovery; they cannot add a capability that the product does not expose.

```text
Continue the work already authorized in this conversation. Before saying browser tools are unavailable, inspect the current task's callable tools and any supported deferred-tool discovery, read the available browser integration's instructions, and invoke its browser/tab inventory. Report the discovery evidence; do not infer availability from a visible Chrome window, an @Chrome mention, or another conversation.

If the Chrome tool is available, use the current inventory and verify the target URL and account. For a connection failure, follow the integration's documented recovery once, preserving a valid browser binding when required. If only the original tab fails, leave it open and try the confirmed target URL once in a new tab in the same Chrome profile. Check the actual state before repeating any uncertain write.

If no supported browser tool is callable or recovery fails, use an already working successor task, or create one on a browser-capable host when task creation is available and authorized. Give it the goal, source conversation, confirmed state, target URL, pending work, constraints, and uncertain actions; exclude secrets. Verify the successor's browser capability before continuing, and do not create a chain of failing tasks.

If you cannot create a task, output the complete ready-to-send handoff prompt and the supported Codex/Work destination in the same response. Continue independent work. Do not stop with only "check the browser connection in Work." Respect site, permission, and workspace restrictions.

Before answering, tie each capability or completion claim to an actual tool result or observation in the relevant task. Clearly separate directly verified facts, another task's or assistant's report, hypotheses, and unverified points. A screenshot of an assistant's claim does not establish its truth. If a check was not executed, say it is unverified; do not claim it passed or invent a cause. Reconcile any conclusion with earlier success and user corrections, and correct unsupported earlier statements explicitly.
```
