
<p align="center">
  <img src="https://github.com/karayakar/MantisClaw-v1/blob/mantis-claw-logo.png" width="420"/>
</p>

<p align="center">
  <img src="https://github.com/karayakar/MantisClaw-v1/blob/mantisclaw-flow-animated.svg" width="420"/>
</p>

# 🦗 MantisClaw for Windows

**Autonomous agents controlled directly from WhatsApp**

MantisClaw is a Windows-based autonomous agent platform that allows you to **run, control, and supervise AI-driven operations directly from WhatsApp conversations**.

Instead of dashboards or complex control panels, MantisClaw turns **WhatsApp chats into a command interface** for automation, workflows, and real task execution.

Teams can issue commands, trigger workflows, and monitor execution through **direct messages or group chats**.

---

# 🚀 Key Features

## WhatsApp Controlled Autonomous Agent

Run a fully capable autonomous AI agent through WhatsApp conversations.

Send commands, start tasks, and receive results directly in chat.

---

## Direct + Group Command Support

Use both **direct chats** and **WhatsApp groups** as command surfaces.

```
User → WhatsApp → Agent → Tools → Execution → Result
```

Teams can collaborate while supervising agent operations.

---

## Code & Task Execution

MantisClaw agents can:

- write code  
- debug code  
- execute scripts  
- call APIs  
- automate workflows  
- perform operational tasks  

Outputs can include:

- Word documents (.docx)
- Excel spreadsheets (.xlsx)
- PowerPoint files (.pptx)
- data exports
- generated reports

---

## Secure Runtime Settings

Sensitive values such as:

- API keys  
- credentials  
- tokens  
- internal secrets  

are **injected at runtime** and **not shared with the LLM by default**.

This ensures secure tool execution.

---

## Local-First Architecture

MantisClaw prioritizes **local data ownership**.

Operational data is stored using **portable PostgreSQL**, ensuring:

- local data control
- no forced cloud dependency
- secure operational history

External AI providers are optional.

---

## Multi-User & Multi-Account Support

MantisClaw supports:

- multiple WhatsApp accounts
- multiple users
- multiple agent channels
- flexible chat → agent mappings

---

## Autonomous Scheduling

Agents can run tasks automatically.

Examples:

- scheduled workflows
- monitoring tasks
- recurring automations

---

## Editable Skill System

Agent capabilities are defined by **skills**.

Skills can:

- call APIs
- run scripts
- interact with files
- automate processes

Skills are **fully configurable and extensible**.

---

# 🧠 Architecture Overview

```
WhatsApp
   │
   ▼
MantisClaw Router
   │
   ▼
Agent Core
   │
   ├── Planner
   ├── Tool Executor
   ├── Skill Engine
   └── Memory
        │
        ▼
   PostgreSQL (local)
```

The agent interprets chat commands and executes tasks through configured skills and tools.

---

# ⚙️ Platform Capabilities

- Autonomous agent orchestration
- WhatsApp chat-native command system
- Secure tool execution
- Runtime configuration injection
- Local-first memory
- Multi-user operations
- Multi-channel command routing
- Document generation
- Code execution
- API integrations

---

# 🖥 Example Use Cases

## DevOps Assistant

```
run server health check
restart staging container
generate deployment report
```

---

## Business Automation

```
generate monthly sales report
export Excel report
email report to management
```

---

## Team Workflow Automation

```
create meeting summary
generate PowerPoint
send task list to group
```

---

# 🔐 Security Model

MantisClaw follows a **local-first execution model**.

Key security principles:

- secrets are injected at runtime
- sensitive data is not sent to LLM prompts by default
- execution runs locally
- tools are configurable and sandboxed

---

# 📦 Installation (Windows)

Download the Windows release.

```
MantisClaw.exe
```

Run the application and follow the setup wizard.

---

# 🔗 WhatsApp Setup

1. Start MantisClaw  
2. Open WhatsApp connection page  
3. Scan the QR code with WhatsApp  
4. Choose control chats or groups  
5. Assign those channels to your agent  

Your agent is now controllable from WhatsApp.

---

# 🔄 Agent Control Flow

```
1. User sends command via WhatsApp
2. Router maps message to agent
3. Agent planner interprets request
4. Tools and skills execute tasks
5. Result is returned to chat
```

---

# 🛠 Technology

- Windows native runtime
- WhatsApp integration
- PostgreSQL (portable)
- LLM integration (optional)
- Tool & skill execution engine
- autonomous task planner

---

# 🌍 Vision

MantisClaw turns everyday messaging platforms into **operational control interfaces for autonomous agents**.

Instead of dashboards and complex automation tools, teams can run real operations directly from chat.

---

# 📜 License

License details coming soon.

---

# 🧑‍💻 Maintained by

**Karay Akar**



# whatsmeow
[![Go Reference](https://pkg.go.dev/badge/go.mau.fi/whatsmeow.svg)](https://pkg.go.dev/go.mau.fi/whatsmeow)

whatsmeow is a Go library for the WhatsApp web multidevice API.

## Discussion
Matrix room: [#whatsmeow:maunium.net](https://matrix.to/#/#whatsmeow:maunium.net)

For questions about the WhatsApp protocol (like how to send a specific type of
message), you can also use the [WhatsApp protocol Q&A] section on GitHub
discussions.

[WhatsApp protocol Q&A]: https://github.com/tulir/whatsmeow/discussions/categories/whatsapp-protocol-q-a

## Usage
The [godoc](https://pkg.go.dev/go.mau.fi/whatsmeow) includes docs for all methods and event types.
There's also a [simple example](https://pkg.go.dev/go.mau.fi/whatsmeow#example-package) at the top.

## Features
Most core features are already present:

* Sending messages to private chats and groups (both text and media)
* Receiving all messages
* Managing groups and receiving group change events
* Joining via invite messages, using and creating invite links
* Sending and receiving typing notifications
* Sending and receiving delivery and read receipts
* Reading and writing app state (contact list, chat pin/mute status, etc)
* Sending and handling retry receipts if message decryption fails
* Sending status messages (experimental, may not work for large contact lists)

Things that are not yet implemented:

* Sending broadcast list messages (this is not supported on WhatsApp web either)
* Calls
