# Start here with CPC — Copy Paste Compute

**Give the AI you already use practical abilities on the computer you already own.**

CPC is a family of local MCP servers. Your AI stays whatever you already pay for — Claude, Codex,
Gemini, Grok, or another MCP-capable client. CPC supplies the local abilities: memory that outlives
a chat, browser and Windows control, voice, and a developer toolbox.

These tools run on your machine. They do not grant an AI permissions by themselves — you install
them, you enable them, and sensitive actions should still pass through your confirmation.

---

## The basket

Four products, each useful alone, and noticeably better together.

| | What it gives the AI | MCP key |
|---|---|---|
| **Autonomous by AutoCache** | Memory. Your decisions, procedures and project knowledge as ordinary markdown files it can navigate — so a new session continues instead of restarting. | *private preview* |
| **Programmer-Wander** | A developer toolbox on Windows: files, PowerShell and Command Prompt, WSL, persistent shell sessions, search, transforms. | `programmer` |
| **AI-Hands** | A body: browser control over CDP, Windows UI Automation for native apps, screenshots, vision and OCR. | `hands` |
| **Voice-Command** | Ears and a mouth: you speak, it transcribes locally, and it narrates back while it works. | `voice` |

### Why they compound

Each one covers a different failure of a plain chat window.

- **Memory without hands** knows what you decided last week but cannot act on it.
- **Hands without memory** can act, but relearns your project every session and repeats
  yesterday's mistakes.
- **A toolbox without a browser** handles your files but stalls the moment a task needs a
  logged-in web app.
- **Voice without any of it** is dictation.

Put together, a request like *"pick up the migration where we stopped and check it still deploys"*
becomes one motion: Autonomous restores the goal and the last verified step, Programmer-Wander
runs the build, AI-Hands checks the deploy in a real logged-in browser, and Voice narrates it while
you do something else.

---

## Read this before you install Programmer-Wander

**If your AI already runs on your computer, you probably do not need it.**

Claude Code, Codex CLI, Gemini CLI, Grok's build tooling and similar terminal agents already have
their own shell and file access on the machine they run on. Adding a second local execution layer
underneath them is mostly redundant.

Programmer-Wander earns its place in one specific situation: **when the AI is not on your
computer.** A phone or web assistant — claude.ai, ChatGPT, Grok, Gemini in a browser — has no
process on your PC. It cannot open a file or run a command. Reached over a tunnel, Programmer-Wander
is what turns that hosted AI into something that can work on a real machine.

**The same argument makes AI-Hands valuable remotely** — and arguably more so, since a hosted AI
tunnelled into your Hands install drives *your* real browser with *your* logins, instead of a
throwaway sandbox that is signed in to nothing.

### But Hands and Voice are also purposeful locally

The tunnel argument does not mean these belong only on a remote machine. Two of them are tied to
the hardware they run on:

- **AI-Hands** controls *that* screen, *that* browser profile, and *those* application windows.
  Running it on the computer you are actually sitting at is the normal case, not the fallback.
- **Voice-Command** needs a microphone and speakers. It binds to localhost by design. There is no
  meaningful way to tunnel a microphone — the machine that hears you has to be the machine you are
  near.

So the honest split: **Programmer-Wander is the one whose value is mostly remote.** Hands is good
both ways. Voice is local, full stop.

---

## How the remote case actually works

MCP has two transports. Local servers speak **stdio** — your client launches the server as a child
process and talks over stdin/stdout. Hosted AI products can only speak **HTTP to a public URL**,
because their inference runs in a datacenter with no process on your PC to launch.

A bridge adapts one to the other: it accepts JSON-RPC over HTTPS, writes it to the local server's
stdin, reads the reply from stdout, and sends it back. The local server is unchanged — it still
thinks it is talking to an ordinary local client.

[**stdio-to-HTTP-bridge-universal-template**](https://github.com/AIWander/stdio-to-HTTP-bridge-universal-template)
is the public starting point for that pattern.

Two things are yours to get right, and neither is optional:

1. **A stable public hostname.** Tunnels that mint a new URL on every restart will silently break
   every connector you registered.
2. **Authentication in front of it.** A tunnel does not authenticate anything by itself. An
   unauthenticated public URL pointed at a local MCP server is an open door to your machine.

---

## Install the free core trio

The trio is free and public. One signed installer covers all three:

1. Open the [latest CPC-Suite release](https://github.com/AIWander/CPC-Suite/releases/latest).
2. Download `CPC-Core-Trio-Setup-x64.exe` for most Intel/AMD PCs, or
   `CPC-Core-Trio-Setup-arm64.exe` for Windows on ARM.
3. Run it, then restart the AI clients it registered.
4. Ask the client to list its MCP tools and confirm `hands`, `voice`, and `programmer` appear.

Single-product installers and manual setup live in each product's own repository.

| Product | Repository | Notes |
|---|---|---|
| AI-Hands | [AI-Hands](https://github.com/AIWander/AI-Hands) | Needs Chrome or Edge installed; it drives a browser you already have rather than downloading one |
| Voice-Command | [Voice-Command](https://github.com/AIWander/Voice-Command) | Speech-to-text runs locally; spoken replies use an online voice service |
| Programmer-Wander | [Programmer-Wander](https://github.com/AIWander/Programmer-Wander) | See the note above on whether you need it |

Everything above is **Windows 10/11, x64 and ARM64**.

---

## Also public

| Tool | Use it when |
|---|---|
| [ops](https://github.com/AIWander/ops) | You want a lighter local execution server with breadcrumbs and reminders |
| [CPC-Suite](https://github.com/AIWander/CPC-Suite) | You want signed bundle installers instead of one product at a time |

## In progress — not ready to install

Listed so you know they exist and what state they are actually in.

| | Status |
|---|---|
| [Papple](https://github.com/AIWander/Papple) | macOS port of Programmer-Wander. Its own README says *scaffold, porting from Windows* and untested on hardware. |
| [Happle](https://github.com/AIWander/Happle) | macOS port of AI-Hands. Port in progress, scaffold stage. |
| [Manager Universal](https://aiwander.github.io/Universal-Ops/manager-universal.html) | Multi-AI delegation and dashboard — delegates work to Claude Code, Codex, Gemini CLI or the GPT API through one tool surface. Beta and coming soon; the capability preview lists what it will do. |

CPC is Windows-first today. The macOS ports are real work in progress, not shipping products, and
this page will say so until that changes.

---

## CPC Complete

CPC Complete is the paid system layer: governed memory, shared truth, automation, onboarding, and
coordination across the AIs you use. It builds **over** the public capability tools rather than
charging for them — AI-Hands, Voice-Command and Programmer-Wander stay free.

---

## Questions worth asking before you install anything

**Does this send my data anywhere?** The capability tools run locally. Your model provider still
sees whatever you choose to send it, and Voice-Command's spoken replies are generated by an online
voice service.

**Does installing this give an AI control of my PC?** It gives it the *ability* to ask. You decide
which servers are enabled and which actions need confirmation.

**Do I need all four?** No. Start with the one that fixes your actual complaint — memory if your AI
forgets, Hands if it cannot reach the web app you live in, Voice if you want to stop typing.
