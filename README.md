# Codex Sidecar

Keep your AI next to Codex.

No MCP. No tunnel. No connector. No API key.

> The annoying part wasn't copy and paste. It was switching windows.

Codex Sidecar is a tiny, skill-only Codex plugin. It opens an AI web app in Codex's existing in-app Browser, reuses an existing tab when possible, makes the Browser visible, and leaves the tab open for you.

**Version 0.1.0 supports ChatGPT only.** It opens `https://chatgpt.com/`. Other AI web apps are not currently supported.

## Why?

Sometimes the best integration is the simplest one: Codex for building, ChatGPT beside it for thinking, and copy and paste between them when useful.

Codex Sidecar was inspired by [Codex with ChatGPT (C2C)](https://github.com/XiaoDuoYa/codex-with-chatgpt), which showed how useful it is to keep ChatGPT beside Codex. C2C provides a powerful automated planning and review workflow with workspace-aware integration. Codex Sidecar takes only the adjacent-browser idea and intentionally stops there.

## What it does

- Checks whether OpenAI's Browser plugin is available in Codex.
- Reuses an existing `chatgpt.com` tab when one is open.
- Opens one new ChatGPT tab when needed.
- Makes the in-app Browser panel visible.
- Hands the tab back to you and keeps it open where the Browser plugin supports it.

It does not read, type, submit, copy, or summarize ChatGPT conversations.

## What it does not use

- MCP
- Cloudflare
- Connectors
- Node.js CLI
- External or local servers
- OpenAI API or API keys
- Workspace access
- Automatic messages or PLAN/REVIEW loops
- Codex DOM or installation patches
- Bundled Browser plugin code

## Requirements

- Codex with plugin and skill support.
- OpenAI's Browser plugin and its `control-in-app-browser` skill.
- Access to `https://chatgpt.com/`.

The Browser plugin is supplied separately by OpenAI and is not included here. Browser availability, panel placement, tab lifetime, and authentication behavior depend on the installed Codex and Browser plugin versions.

## Install

After this repository is published as `YOUR_GITHUB_USER/codex-sidecar`:

```powershell
codex plugin marketplace add YOUR_GITHUB_USER/codex-sidecar
codex plugin add codex-sidecar@codex-sidecar
```

Start a new Codex task so the newly installed skill is loaded, then ask:

> Open ChatGPT next to Codex.

If ChatGPT asks you to sign in, complete sign-in directly in the visible Browser tab. Codex Sidecar does not read or store your credentials.

## Sidecar and C2C

These projects solve different problems:

| | Codex Sidecar | C2C |
| --- | --- | --- |
| Primary purpose | Keep ChatGPT visible | Automated planning and review |
| ChatGPT beside Codex | Yes | Yes |
| Copy-and-paste workflow | Yes | Yes |
| Automatic PLAN/REVIEW | No | Yes |
| Workspace access | No | Yes, read-only |
| Integration infrastructure | None | MCP and secure connection |

Use C2C when you want ChatGPT to participate in an automated, workspace-aware planning and review loop. Use Codex Sidecar when you only want the website beside your work.

## Privacy and security

Codex Sidecar contains instructions only. It has no server, telemetry, credential store, or workspace integration. Its skill explicitly prohibits inspecting conversations, cookies, storage, credentials, tokens, and browser profiles.

## Acknowledgements

Inspired by [Codex with ChatGPT (C2C)](https://github.com/XiaoDuoYa/codex-with-chatgpt). No C2C source code is included or copied.

## Disclaimer

**Unofficial community project. Not affiliated with or endorsed by OpenAI.**

ChatGPT, Codex, and OpenAI are trademarks of OpenAI. This project does not include or redistribute OpenAI's proprietary Browser plugin.

## License

MIT. See [LICENSE](LICENSE).
