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
| [ops](https://github.com/AIWander/ops) | You want a lightweight local execution server with breadcrumbs and reminders |
| Manager (repository not public yet) | You are testing multi-AI delegation; Manager and its dashboard are **in beta** and ship in the CPC-Suite Ops installer |
| [CPC-Suite](https://github.com/AIWander/CPC-Suite) | You want signed bundle installers instead of installing products one at a time |

The Manager/dashboard bundle is not presented as production-ready. Its current public status is
beta.

## Autonomous by AutoCache

Autonomous is the one paid line: a local engine and files you own, so the AI you use can pick up
where it left off across models, agents, and sessions. It is sold through
[autocache.ai](https://autocache.ai) and runs on your machine, not as a hosted service. Everything
else on this page is free.

Autonomous is in private preview, and pricing is not published.

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
- Manager and its dashboard are free and in beta; the repository is not public yet.
- Autonomous by AutoCache is in private preview; pricing is not published.
- The public repositories are the reusable product layer; Joseph's private knowledge and
  personal operating data are not included.

Built by Joseph Wander. Public repositories use Apache-2.0 unless a repository says otherwise.

Contact: [contact@aiwander.ai](mailto:contact@aiwander.ai)
