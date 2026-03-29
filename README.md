

<h1 align="center">🦗 MantisClaw - First Desktop CUA Agent</h1>

<p align="center">
  <a href="https://mantisclaw.yapzek.ai">
    <img src="https://mantisclaw.yapzek.ai/assets/Screenshots/Architecture.png" alt="MantisClaw Architecture" width="100%" />
  </a>
</p>

<p align="center"><strong>Multi-Platform Autonomous Agent — Control from WhatsApp, Telegram, Slack, and more</strong></p>
<p align="center"><em>The best GUI Computer Use Agent. No complex setup — just download and run. All features are already built-in.</em></p>

<p align="center">
  <a href="https://mantisclaw.yapzek.ai">🌐 Website</a> &nbsp;·&nbsp;
  <a href="https://mantisclaw.yapzek.ai/download" target="_blank">⬇️ Download</a> &nbsp;·&nbsp;
  <a href="#-demo-videos">🎬 Demo Videos</a> &nbsp;·&nbsp;
  <a href="#-platform-screenshots">📸 Screenshots</a>
</p>

---

MantisClaw integrates autonomous agents across multiple channels so your team can command, automate, and supervise real operations from chat. Use direct or group conversations to run tasks, trigger workflows, and keep execution secure with local-first data control.

---

## 🚀 What's New

- WhatsApp, Telegram, Slack, Built-in ChatUI channels
- MantisClaw Blender MCP Control UI
- MCP support for extensible tool discovery
- OpenAI-compatible Tools & Advanced HTTP Call Support
- Workflow — POC (under development)
- 50+ Node Registry POC (under development)
- Templates POC (under development)
- Bug Fixes & Stability Improvements

---

## 🔒 Why MantisClaw Stands Out

| Feature | Details |
|---------|---------|
| **Local Database** | Your accounts & keys never leave your computer |
| **Runtime Key Injection** | Keys injected at runtime, never sent to LLM |
| **Built-in Office Engine** | Word, Excel, PowerPoint & PDF generation |
| **Real Browser** | The only Agent that can use a real browser |
| **Multi-Platform CUA** | First & only GUI Multi-Platform CUA Agent |
| **Token Efficient** | Uses less tokens than competitors |
| **Self-Healing Code** | Writes code, debugs, fixes & self-heals automatically |
| **Auto Skills** | Creates skills & skill settings by itself |
| **Unlimited Agents** | Unlimited Agents & unlimited Scenarios (SOUL) |
| **Account Security** | Sub-accounts for granular access control |
| **Completely Free** | All features included at no cost |

---

## ⚙️ Platform Capabilities

### Autonomous Agent Integrated with Multiple Channels
Run an autonomous agent through chat conversations across channels and keep operations inside real communication flows.

### Control Your Agent from Any Channel
Start tasks, steer behavior, and trigger workflows by messaging your agent from your preferred channel.

### Direct + Group Command Support
Use both direct chats and groups as command surfaces for agent actions and automation routines.

### Code and Task Execution
Ask the agent to write code, run scripts, call APIs, and produce business outputs from channel instructions.

### Secure Runtime Settings
Sensitive values are injected at runtime and kept out of chat prompts whenever possible.

### Local-First Agent Memory
Portable PostgreSQL keeps your operational data local unless you explicitly route data to an external model provider.

---

## 🔄 How MantisClaw Works

From incoming channel message to autonomous action — here is what happens under the hood.

| Step | Phase | Description |
|:----:|-------|-------------|
| **1** | **Message Arrives** | A message from a connected channel reaches MantisClaw. The system identifies the sender, resolves the target agent mapping, and queues the message for processing. |
| **2** | **Context Assembly** | The last 20 messages are loaded from chat history plus the agent's persona/scenario. This context window is sent alongside all available tools to the LLM. |
| **3** | **Tool-Call Loop (25 Turns)** | The AI decides actions in a single loop: run Python code, browse the web, execute skills, create files, or call APIs. Each tool result feeds back into the next decision. |
| **4** | **Self-Healing Execution** | If Python or a skill fails, the AI reads the traceback, fixes the code, auto-installs missing packages, and retries — up to 3 attempts before reporting. |
| **5** | **Output Delivery** | Text responses go back to the source channel. Generated files (Excel, Word, PDF, images) are auto-detected and sent as attachments to the original chat. |
| **6** | **Learn & Schedule** | Skills discovered during execution are saved for reuse. Scheduled tasks run autonomously on cron and deliver results directly to connected channels. |

---

## 🏗️ Agent Architecture

| Component | Description |
|-----------|-------------|
| **Go + Wails** | Desktop runtime with embedded web server and system tray |
| **Embedded PostgreSQL** | Local-first database — no external server required |
| **Playwright + Chromium** | Persistent browser context with cookies across restarts |
| **Python Kernel** | Embedded interpreter with auto pip-install and SETTINGS injection |

---

## 🚦 Agent Control Flow

1. **Create your account** and complete verification.
2. **Connect your channels** securely.
3. **Choose direct chats and groups** as control channels.
4. **Assign those channels** to your autonomous agent.
5. **Control and monitor** agent actions directly from your channels.

---

## ❓ Why MantisClaw?

MantisClaw helps teams manage one autonomous agent across multiple messaging channels. Send commands from chat, monitor every execution step, and receive outcomes in the same conversation flow.

| Pillar | Description |
|--------|-------------|
| **Multi-Channel Control** | Control one agent from WhatsApp, Telegram, Slack, and other communication channels. |
| **Local and Secure Execution** | Sensitive data stays local, while runtime settings keep workflows secure, traceable, and auditable. |
| **Automation and Productivity** | Combine coding, API calls, file generation, and scheduled tasks in one agent to accelerate operations. |

---

## ⚡ See it in Action

Watch how a single channel message flows through the MantisClaw engine — from ingestion through the AI tool-call loop to autonomous execution and response delivery.

| Feature | Details |
|---------|---------|
| **Single Tool-Call Loop** | 25 turns max — the AI sees all tools at once and picks the right action each turn. No multi-stage overhead. |
| **Self-Healing Pipeline** | Python errors auto-trigger fix → retry cycles. Missing pip packages get installed on the fly. |
| **Scheduled Autonomy** | Cron tasks feed directly into the AI Brain. Results are auto-delivered to your channels on schedule. |

---

## 📸 Platform Screenshots

### Accounts
Manage all your connected accounts, credentials, and linked services in one centralized dashboard.

![Accounts](https://mantisclaw.yapzek.ai/assets/Screenshots/accounts.png)

---

### Advanced MCP
Configure advanced Model Context Protocol settings for fine-grained control over AI model interactions.

![Advanced MCP](https://mantisclaw.yapzek.ai/assets/Screenshots/Advanced_MCP.png)

---

### Advanced Tools
Access powerful advanced tools including code execution, API testing, and debugging utilities.

![Advanced Tools](https://mantisclaw.yapzek.ai/assets/Screenshots/Advanced_Tools.png)

---

### Advanced Workflows
Design complex multi-step workflows with conditional logic, branching, and parallel execution paths.

![Advanced Workflows](https://mantisclaw.yapzek.ai/assets/Screenshots/advanced_workflows.png)

---

### Agents
Create and configure autonomous agents with custom personas, scenarios, and channel assignments.

![Agents](https://mantisclaw.yapzek.ai/assets/Screenshots/Agents.png)

---

### AI-Assisted Node Registry
Browse and register workflow nodes with AI-powered suggestions and auto-configuration.

![AI-Assisted Node Registry](https://mantisclaw.yapzek.ai/assets/Screenshots/Ai_assisted_node_registry.png)

---

### Architecture
Visual overview of the MantisClaw system architecture showing all integrated components.

![Architecture](https://mantisclaw.yapzek.ai/assets/Screenshots/Architecture.png)

---

### Blender Control via MCP
Control Blender 3D directly from chat using MCP integration for 3D modeling and rendering tasks.

![Blender Control via MCP](https://mantisclaw.yapzek.ai/assets/Screenshots/Blender_control_mcp.png)

---

### Browser Playbooks
Record and replay browser automation sequences as reusable playbooks for web tasks.

![Browser Playbooks](https://mantisclaw.yapzek.ai/assets/Screenshots/Browser_playbooks.png)

---

### Built-in Chat
Use the built-in chat interface to interact with your agent directly from the MantisClaw desktop app.

![Built-in Chat](https://mantisclaw.yapzek.ai/assets/Screenshots/Built-in-chat.png)

---

### Channels
Connect and manage multiple messaging channels — WhatsApp, Telegram, Slack, and more.

![Channels](https://mantisclaw.yapzek.ai/assets/Screenshots/Channels.png)

---

### LLM Settings
Configure language model providers, API keys, temperature, token limits, and model selection.

![LLM Settings](https://mantisclaw.yapzek.ai/assets/Screenshots/LLM_settings.png)

---

### MantisClaw + Blender
See MantisClaw controlling Blender to create 3D scenes and render outputs from chat commands.

![MantisClaw + Blender](https://mantisclaw.yapzek.ai/assets/Screenshots/mantis_blender.png)

---

### Blender Integration Demo
Step-by-step demonstration of Blender 3D integration with MantisClaw agent control.

![Blender Integration Demo](https://mantisclaw.yapzek.ai/assets/Screenshots/mants_blender_01.png)

---

### MCP Configuration
Set up Model Context Protocol servers and tools to extend your agent capabilities.

![MCP Configuration](https://mantisclaw.yapzek.ai/assets/Screenshots/MCP.png)

---

### Node Registry
Browse available workflow nodes, skills, and integrations in the central registry.

![Node Registry](https://mantisclaw.yapzek.ai/assets/Screenshots/Node_registry.png)

---

### Reset Option
Safely reset agent state, clear conversation history, or restore default configurations.

![Reset Option](https://mantisclaw.yapzek.ai/assets/Screenshots/RESET_Option.png)

---

### Scenarios
Define agent scenarios with system prompts, behavior rules, and operational boundaries.

![Scenarios](https://mantisclaw.yapzek.ai/assets/Screenshots/Scenarios.png)

---

### Scheduled Tasks
Set up cron-based scheduled tasks that run autonomously and deliver results to your channels.

![Scheduled Tasks](https://mantisclaw.yapzek.ai/assets/Screenshots/Scheduled_Tasks.png)

---

### Skills
Manage reusable skills — code snippets, API integrations, and automation routines your agent can invoke.

![Skills](https://mantisclaw.yapzek.ai/assets/Screenshots/Skills.png)

---

### Skill Settings
Configure skill parameters, runtime settings, and execution preferences for each registered skill.

![Skill Settings](https://mantisclaw.yapzek.ai/assets/Screenshots/Skill_settings.png)

---

### Tool MCP
View and manage MCP tool definitions available to your agent during execution.

![Tool MCP](https://mantisclaw.yapzek.ai/assets/Screenshots/tool_mcp.png)

---

### Workflow List
Browse all created workflows with status indicators, execution history, and quick actions.

![Workflow List](https://mantisclaw.yapzek.ai/assets/Screenshots/WorkFlowList.png)

---

### Workflows
Visual workflow editor to build, connect, and orchestrate automation pipelines with drag-and-drop.

![Workflows](https://mantisclaw.yapzek.ai/assets/Screenshots/WorkFlows.png)

---

## 💼 Use Cases Across Teams

| Use Case | Description |
|----------|-------------|
| **Daily Task Assistant** | Automate morning checklists, prepare end-of-day summaries, and send daily reminders in team channels. |
| **Routine Task Automation** | Handle repetitive actions like status collection, recurring reports, and regular follow-up pings. |
| **Workflow Orchestration** | Run multi-step workflows across tools: collect input, execute logic, generate outputs, and post results automatically. |
| **Dynamic API and Tool Calls** | Trigger dynamic calls to external APIs, internal services, or scripts based on natural language instructions. |
| **Customer Support** | Create ticket summaries, suggest replies, and push escalations to CRM tools. |
| **Sales Operations** | Qualify leads from chat, prepare follow-up drafts, and update pipeline stages automatically. |
| **Marketing Workflows** | Draft campaign copy, collect feedback from group chats, and generate content variants. |
| **Finance Requests** | Prepare weekly KPI snapshots, reconcile simple reports, and send approval-ready summaries. |
| **Engineering Automation** | Run scripts, inspect logs, create troubleshooting notes, and deliver patch suggestions. |
| **DevOps Coordination** | Trigger operational checks, post incident updates, and automate recurring maintenance routines. |
| **HR and People Ops** | Answer policy questions, automate onboarding reminders, and collect status confirmations. |
| **Project Management** | Convert chat decisions into task lists, sync action items, and publish progress digests. |
| **Executive Reporting** | Aggregate updates from multiple teams and produce concise daily or weekly briefings. |
| **Procurement and Operations** | Track purchase requests, route approvals, and notify stakeholders when vendor milestones are reached. |
| **Compliance and Audit Trails** | Log key decisions, preserve execution history, and generate audit-ready summaries for internal controls. |
| **Knowledge Operations** | Turn chat outcomes into reusable playbooks, FAQs, and process notes for continuous team learning. |
| **Word Documents and Letters** | Generate formal letters, proposals, contracts, and branded Word documents directly from chat prompts. |
| **Excel Sheets and Reports** | Create structured spreadsheets, formulas, budget trackers, KPI tables, and operational report templates. |
| **PowerPoint Presentations** | Prepare meeting decks, investor summaries, training slides, and visual storylines ready for presentation. |
| **PDF Documents** | Export polished PDFs such as invoices, summaries, compliance packs, and client-ready documentation. |

---

## 🎬 Demo Videos

<table>
  <tr>
    <td align="center">
      <a href="https://www.youtube.com/watch?v=Kg5qzgYW6t0">
        <img src="https://img.youtube.com/vi/Kg5qzgYW6t0/maxresdefault.jpg" alt="Demo Video 1" width="400" />
        <br/><strong>▶ Demo Video 1</strong>
      </a>
    </td>
    <td align="center">
      <a href="https://www.youtube.com/watch?v=gIy7jucDP_k">
        <img src="https://img.youtube.com/vi/gIy7jucDP_k/maxresdefault.jpg" alt="Demo Video 2" width="400" />
        <br/><strong>▶ Demo Video 2</strong>
      </a>
    </td>
  </tr>
  <tr>
    <td align="center">
      <a href="https://www.youtube.com/watch?v=TMKbYffzvG8">
        <img src="https://img.youtube.com/vi/TMKbYffzvG8/maxresdefault.jpg" alt="Demo Video 3" width="400" />
        <br/><strong>▶ Demo Video 3</strong>
      </a>
    </td>
    <td align="center">
      <a href="https://www.youtube.com/watch?v=5ZqhoV3WO_0">
        <img src="https://img.youtube.com/vi/5ZqhoV3WO_0/maxresdefault.jpg" alt="Demo Video 4" width="400" />
        <br/><strong>▶ Demo Video 4</strong>
      </a>
    </td>
  </tr>
</table>

---

## ⬇️ Download

Available for **Windows**, **Linux**, **Apple Intel**, and **Apple Silicon**.

| Platform | Download Link |
|----------|---------------|
| **Windows (amd64)** | [MantisClaw_win_amd64.zip](https://mantisclaw.yapzek.ai/MantisClaw_win_amd64.zip) |
| **Linux (amd64)** | [MantisClaw_linux_amd64.zip](https://mantisclaw.yapzek.ai/MantisClaw_linux_amd64.zip) |
| **macOS Intel (amd64)** | [MantisClaw-MacOs_Intel_amd64.zip](https://mantisclaw.yapzek.ai/MantisClaw-MacOs_Intel_amd64.zip) |
| **macOS Silicon (arm64)** | [MantisClaw-MacOs_Silicon_arm64.zip](https://mantisclaw.yapzek.ai/MantisClaw-MacOs_Silicon_arm64.zip) |

> Visit **[mantisclaw.yapzek.ai](https://mantisclaw.yapzek.ai)** for setup instructions, compatibility notes, and latest version details.

---

## 🔧 Comprehensive Feature Summary

| Component | Features | Scope |
|-----------|----------|-------|
| **Communication** | WhatsApp, Telegram, Slack, Web Chat | 4 channels |
| **Agents** | My Agents, Desktop Agents, Browser, Skills | 4 types |
| **Workflows** | DAG execution, 50+ node types, versioning | Full |
| **Code Execution** | Python kernel, sandbox, auto-packages | Full |
| **Blender** | Scene info, objects, materials, asset import | Full |
| **Database** | PostgreSQL, 25+ tables, vector memory planned | Full |
| **LLM** | 8 providers, multi-model support | Full |
| **Tools** | Browser (10+), Skills (custom), HTTP, MCP, Workflow | 50+ tools |
| **Self-Healing** | Skill code fixes, tool schema recovery | Full |
| **Scheduling** | Cron jobs, prompt/skill/pipeline types | Full |
| **Frontend** | 22+ pages, React Flow DAG editor | Full |
| **Playbooks** | JSONL format, recording, LLM vision, 15+ actions | Full |
| **Node Registry** | 50+ builtin, custom creation, AI generation | Full |
| **Desktop** | Wails, system tray, 3 runtimes embedded | Full |
| **Security** | JWT auth, email/SMS verification, sandbox | Full |
| **History** | Chat logs, runs, playbooks, task history, vector search planned | Full |

### Key Metrics

- **API Endpoints**: 100+
- **Database Tables**: 25+
- **Frontend Routes**: 22
- **LLM Providers Supported**: 8
- **Tool Categories**: 5
- **Workflow Node Types**: 50+
- **Browser Tool Functions**: 10+
- **Max Concurrent Workflows**: 10
- **Desktop Agents Per User**: Unlimited

---

## 🖥️ Cross-Platform Support

| OS | Status | System Tray | Notes |
|----|--------|-------------|-------|
| **Windows** | ✅ Full | ✅ | All features, system tray working |
| **macOS** | ✅ Partial | ❌ | Wails native menus, no GTK conflict |
| **Linux** | ✅ Partial | ❌ | GTK signal handler issue with Wails |

---

## 🔗 Links

- 🌐 [Website — mantisclaw.yapzek.ai](https://mantisclaw.yapzek.ai)
- 📊 [MantisClaw vs Competitors](https://mantisclaw.yapzek.ai/comparison.html)
- ⚔️ [OpenClaw vs MantisClaw vs NemoClaw](https://mantisclaw.yapzek.ai/open-mantis-nemo-comparison.html)
- 📜 [Terms of Service](https://mantisclaw.yapzek.ai/terms)
- 🔐 [Privacy Policy](https://mantisclaw.yapzek.ai/privacy)

---

<p align="center">© 2026 MantisClaw — <a href="https://mantisclaw.yapzek.ai">mantisclaw.yapzek.ai</a></p>
