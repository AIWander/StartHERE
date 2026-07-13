# Start here with CPC - Copy Paste Compute

**Give the AI you already use practical abilities on the computer you already own.**

CPC is a family of local MCP tools. Your AI remains Claude, Codex, Gemini, Grok, or another
MCP-capable client. CPC supplies the local abilities: browser and Windows control, voice,
programming tools, reusable API flows, files, shells, and multi-agent coordination.

The public capability tools run on your machine. They do not grant an AI permissions by
themselves; you install and enable them, and sensitive actions should still require your
confirmation.

## Install the free core trio

The core trio is free and public:

| Product | Installed name you will see | What it does |
|---|---|---|
| [AI-Hands](https://github.com/AIWander/AI-Hands) | Product: AI-Hands; binary and MCP key: `hands` | Browser CDP, Windows UI Automation, screenshots, vision, and OCR |
| [Voice-Command](https://github.com/AIWander/Voice-Command) | Product: Voice-Command; MCP key: `voice`; binary: `voice-mcp.exe` | Speech input, speech output, and the Voice App companion |
| [Programmer-Wander](https://github.com/AIWander/Programmer-Wander) | Product: Programmer-Wander; MCP key: `programmer` | Files, shells, full git, WSL, HTTP, transforms, and persistent dev sessions |

### One signed installer

1. Open the [latest CPC-Suite release](https://github.com/AIWander/CPC-Suite/releases/latest).
2. Download `CPC-Core-Trio-Setup-x64.exe` for most Intel/AMD PCs, or
   `CPC-Core-Trio-Setup-arm64.exe` for Windows on ARM.
3. Run the signed installer.
4. Restart the AI clients the installer registered.
5. Ask the client to list its MCP tools and confirm `hands`, `voice`, and `programmer` appear.

Single-product installers and manual setup instructions remain available in each product's
repository.

## Optional public tools

| Tool | Use it when |
|---|---|
| [workflow](https://github.com/AIWander/workflow) | You want to capture a browser workflow once and replay the underlying API later |
| [local](https://github.com/AIWander/local) | You want a general Windows files, shell, git, and persistent-session surface |
| [ops](https://github.com/AIWander/ops) | You want a lightweight local execution server with breadcrumbs and reminders |
| [manager-universal](https://github.com/AIWander/manager-universal) | You are testing multi-AI delegation; manager and its dashboard are **Beta and coming soon** as a polished public product |
| [CPC-Suite](https://github.com/AIWander/CPC-Suite) | You want signed bundle installers instead of installing products one at a time |

The manager/dashboard bundle is not presented as production-ready. Its current public status is
Beta and coming soon.

## CPC Complete

CPC Complete is the paid system layer: governed memory, shared truth, automation, onboarding,
and coordination across the AIs you use. It builds over the public capability tools rather
than charging for Programmer-Wander, AI-Hands, or Voice-Command.

Pricing is not published here. The product, licensing, checkout, and release package must pass
their verification gates before a public listing exists.

## Bridge

Bridge is a planned **$5/month** relay between a cloud AI and tools on the customer's own
machine. It passes tool calls; it does not rent or host a model. Bridge is not available for
purchase yet.

## How the pieces fit

```text
Your AI client
  |
  +-- AI-Hands        browser, desktop UI, vision
  +-- Voice-Command   speech input/output
  +-- Programmer      files, code, shells, git
  +-- workflow        captured API flows and credentials
  +-- local / ops     local execution surfaces
  +-- manager         multi-AI delegation (Beta, coming soon)
```

Install only what you need. Every server can be used independently, and the core trio installer
is simply the fastest common starting point.

## Honest status

- AI-Hands, Voice-Command, and Programmer-Wander are free public tools.
- The manager and dashboard are Beta and coming soon as a polished product.
- CPC Complete is not publicly priced or on sale yet.
- Bridge is not live yet.
- The public repositories are the reusable product layer; Joseph's private knowledge and
  personal operating data are not included.

Built by Joseph Wander. Public repositories use Apache-2.0 unless a repository says otherwise.

Contact: [contact@aiwander.ai](mailto:contact@aiwander.ai)
