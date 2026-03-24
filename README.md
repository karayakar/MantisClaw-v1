
<h1>**** Will be open source after 1000 star ****</h1>


<p align="center">
  <img src="https://github.com/karayakar/MantisClaw-v1/blob/main/mantis-claw-logo.png" width="600"/>
</p>
<p align="center">
<a href="https://mantisclaw.yapzek.ai" target="_blank">Download Here</a> 
</p>
<p align="center">


</p>
<p align="center">
  WATCH VIDEO - LEARN - SEE IT  IN ACTION.
</p>


[![Watch MantisClaw Demo](https://github.com/karayakar/MantisClaw-v1/blob/main/c34bb133-da6f-4802-92e6-fdca65281527.png)](https://www.youtube.com/watch?v=Kg5qzgYW6t0)

 
</p>
<p align="center">
  <img src="https://github.com/karayakar/MantisClaw-v1/blob/main/mantisclaw-flow-animated.svg" width="800"/>
</p>

# 🦗 MantisClaw for Windows

**Autonomous agents controlled directly from WhatsApp**

MantisClaw is a Windows-based autonomous agent platform that allows you to **run, control, and supervise AI-driven operations directly from WhatsApp conversations**.

Instead of dashboards or complex control panels, MantisClaw turns **WhatsApp chats into a command interface** for automation, workflows, and real task execution.

Teams can issue commands, trigger workflows, and monitor execution through **direct messages or group chats**.

---

# **COMPREHENSIVE FEATURE DOCUMENTATION: MantisClaw Desktop Application**

**Last Updated:** January 2025  
**Version:** Full Capability Audit  
**Architecture:** Wails v2 (Go backend + React frontend) | Embedded PostgreSQL | Embedded Python Kernel

---

## **EXECUTIVE SUMMARY**

MantisClaw is a sophisticated multi-channel AI automation platform with:
- **4 messaging adapters** (WhatsApp, Telegram, Slack, Web Chat)
- **Full workflow engine** with DAG execution, versioning, and 50+ node types
- **Sandboxed Python kernel** with auto-package installation and filesystem restrictions
- **LLM multi-provider support** (8+ providers including local Ollama)
- **Browser automation** via Playwright with playbook recording & LLM vision
- **3D modeling** via Blender socket bridge
- **Skills engine** with self-healing code fixes
- **Desktop agent** fleet management with SSE
- **Vector memory** (PostgreSQL pgvector planned)

---

## **1. COMMUNICATION CHANNELS & ADAPTERS**

### **1.1 WhatsApp Integration**
- **Core Protocol**: WhatsApp QR pairing, E2E encryption (Signal protocol)
- **Features**:
  - User registration and device management
  - QR code generation for pairing
  - Message sending (text + media)
  - Typing indicators
  - Group membership management
  - Media upload/download with encryption
  - Newsletter (channel) support with unencrypted media
  - Broadcast messaging to contacts
  - Status privacy (whitelist/blacklist/contacts)
  - Media retry on 404/410
  - Chat persistence (groups, directs, history)

**API Routes** (`/api/users/*`, `/api/messages/*`, `/api/chat/*`):
```
POST /api/users/register         — Register new WhatsApp user
POST /api/users/{userId}/connect — Initiate QR pairing
GET  /api/users/{userId}/qr/png  — Fetch QR code
POST /api/messages/send          — Send text message
POST /api/messages/send-media    — Send file/media
POST /api/messages/typing        — Send typing indicator
GET  /api/chat/groups/{userId}   — List user's groups
GET  /api/chat/history/{userId}  — Chat history
GET  /api/chat/conversations/{userId} — Conversations
GET  /api/chat/contacts/{userId} — User contacts
```

### **1.2 Telegram Integration**
- **Adapter Pattern**: HTTP polling or webhook (configurable)
- **Features**:
  - Bot token authentication
  - Chat mapping (Telegram chat ↔ WhatsApp target)
  - Message routing
  - Media forwarding
  - Chat discovery

**API Routes** (`/api/telegram/*`):
```
GET    /api/telegram/status      — Bot connection status & info
POST   /api/telegram/connect     — Configure bot token
POST   /api/telegram/disconnect  — Stop bot
GET    /api/telegram/chats       — List available chats/channels
POST   /api/telegram/mapping     — Save routing rule
DELETE /api/telegram/mapping/{id} — Remove routing
GET    /api/telegram/mappings    — List active mappings
```

### **1.3 Slack Integration**
- **Auth**: OAuth token-based
- **Features**:
  - Channel discovery
  - Message routing to WhatsApp/other channels
  - Bi-directional mapping
  - Channel list with metadata

**API Routes** (`/api/slack/*`):
```
GET    /api/slack/status         — Bot status & workspace info
POST   /api/slack/connect        — Configure OAuth token
POST   /api/slack/disconnect     — Revoke token
GET    /api/slack/channels       — List channels
POST   /api/slack/discover       — Auto-discover channels
POST   /api/slack/mapping        — Save routing
DELETE /api/slack/mapping/{id}   — Remove routing
GET    /api/slack/mappings       — List active mappings
```

### **1.4 Chat UI (Web)**
- **Transport**: WebSocket + HTTP
- **Features**:
  - Persistent conversations (CRUD)
  - Message history (paginated)
  - File upload/download
  - Real-time updates via WebSocket
  - Channel status polling

**API Routes** (`/api/chatui/*`):
```
GET    /api/chatui/ws                              — WebSocket endpoint (auth via query param)
GET    /api/chatui/conversations                   — List user's conversations
POST   /api/chatui/conversations                   — Create new conversation
GET|PUT|DELETE /api/chatui/conversations/{convId}
GET    /api/chatui/conversations/{convId}/messages  — Message history
POST   /api/chatui/conversations/{convId}/messages  — Send message
POST   /api/chatui/conversations/{convId}/upload    — File upload
GET    /api/chatui/files/{msgId}/{filename}         — File serving
GET    /api/channels                                — All connected channel statuses
```

---

## **2. AGENT & AI FEATURES**

### **2.1 Agent Types**
- **My Agents**: User-created agents mapped to specific scenarios
- **Desktop Agents**: Headless agent instances with SSE for task delivery
- **Browser Agent**: LLM-driven Playwright automation with screenshot vision
- **Skill Engine**: Auto-generating Python skills with self-healing

### **2.2 My Agents Management**
```
GET    /api/my-agents      — List user's agents
POST   /api/my-agents      — Create new agent (name + scenario)
PUT    /api/my-agents/{id} — Update agent
DELETE /api/my-agents/{id} — Delete agent
```

### **2.3 Desktop Agents (Headless Execution)**
```
GET    /api/desktop-agents                — List agents with connection status
POST   /api/desktop-agents/generate-key   — Generate auth token
POST   /api/desktop-agents                — Create new agent
POST   /api/desktop-agents/{id}/regenerate-key — Rotate token
DELETE /api/desktop-agents/{id}           — Delete agent
GET    /api/desktop-agents/sse            — Subscribe to task stream (SSE)
```

**Features**:
- Unique token per agent
- Last connection timestamp tracking
- Active/inactive toggle
- Server-Sent Events for task delivery

### **2.4 Scenarios (Agent Blueprints)**
```
GET    /api/scenarios      — List scenarios
POST   /api/scenarios      — Create (name + description)
PUT    /api/scenarios/{id} — Update
DELETE /api/scenarios/{id} — Delete
```

**Use**: Define agent personality, system prompts, default tools

### **2.5 LLM Planning & Execution**
- **Planner**: AI plans workflows using available node types + tools
- **Executor**: DAG runner with event streaming
- **Self-Healing**: Automatic code fixes via AI on Python failures

**Key Services**:
- `yapzek_service.go`: AI planning, tool calling, streaming
- `planner.go`: LLM planner with node type constraints
- `engine/engine.go`: Workflow execution with concurrency control (default 10 concurrent)

---

## **3. WORKFLOW ENGINE**

### **3.1 Core Features**
- **DAG Execution**: Directed Acyclic Graph with versioning
- **Node Types**: 50+ builtin (ComfyUI-style registry)
- **Execution Modes**: Sequential | Parallel
- **Retries & Timeouts**: Per-node configuration
- **Versioning**: Auto-save on update + manual rollback
- **Dry-Run Mode**: Validate without execution

### **3.2 Database Schema**
```sql
workflows          — workflow definitions (JSON)
node_types         — registered node types (builtin + custom)
workflow_runs      — execution records + status
run_nodes          — per-node execution details
workflow_versions  — version history with checksums
```

### **3.3 API Routes** (`/api/workflows/*`):
```
GET    /api/workflows                         — List user's workflows
POST   /api/workflows                         — Create workflow
GET|PUT|DELETE /api/workflows/{id}
PATCH  /api/workflows/{id}/toggle             — Enable/disable
POST   /api/workflows/{id}/duplicate          — Clone
GET    /api/workflows/{id}/versions           — Version history
POST   /api/workflows/{id}/rollback/{version} — Rollback to version
POST   /api/workflows/{id}/run                — Execute workflow
POST   /api/workflows/{id}/validate           — Syntax check
GET    /api/workflows/{id}/runs               — Run history
GET    /api/workflows/{id}/runs/{runId}       — Run details
POST   /api/workflow-runs/{runId}/cancel       — Abort execution
```

### **3.4 Builtin Node Types**
- **start** / **end** — workflow boundaries
- **prompt** — LLM query
- **condition** — branching logic
- **loop** — iteration
- **delay** — sleep/wait
- **http_request** — REST API call
- **code_python** — inline Python
- **skill_run** — execute registered skill
- **schedule** — cron trigger
- **split** / **merge** — parallel execution
- Custom nodes via UI with AI-generated handler code

---

## **4. CODE EXECUTION ENVIRONMENT**

### **4.1 Python Kernel (Embedded)**
- **Protocol**: JSON-RPC over stdin/stdout
- **Sandbox**: Restricted file I/O, blocked modules, guarded os/shutil
- **Working Directory**: Sandboxed temp folder per request (`WORK_DIR`)
- **Auto-Install**: numpy, Pillow, imageio, moviepy, fpdf2, reportlab, openai
- **Pre-loaded Modules**: requests, pandas, PIL, re, json, csv, html2text, etc.

### **4.2 Methods** (via PythonBridge):
```
execute_code      — Run Python code with SETTINGS injection
html_to_md        — Convert HTML to Markdown
get_work_dir      — Path to temp working directory
update_settings   — Update SETTINGS dict (skill configs)
execute_workflow  — Run DAG workflow via Python
```

### **4.3 Kernel Globals (Pre-populated)**
```python
WORK_DIR    = "/tmp/yapzek_kernel_files/req_<id>"
REQUEST_ID  = "req_<timestamp>"
SETTINGS    = {
    "skill_name.config_key": "value",   # from database
    "openai.api_key": "...",            # current AI provider
}
fetch_text(url, encoding)       — Download text with encoding detection
download_image(url, filename)   — Download image to WORK_DIR
os, json, sys, numpy, PIL, requests, pandas, etc. — pre-imported
```

### **4.4 Sandbox Restrictions**
- ✅ Read: Anywhere
- ✅ Write: WORK_DIR + system temp + site-packages
- ❌ Block: os.system, dangerous os/shutil functions on non-WORK_DIR paths
- ❌ Modules: None currently blocked (ctypes allowed for deps)

---

## **5. BLENDER INTEGRATION**

### **5.1 Architecture**
- **Blender Component**: Python addon (`mantis_blender.py`) listening on TCP `127.0.0.1:9877`
- **Desktop Bridge**: `blender_handlers.go` WebSocket hub
- **Command Format**: JSON RPC `{"type": "command", "params": {...}}`

### **5.2 Commands (Builtin)**
```
get_scene_info         — Scene objects, materials count
get_object_info        — Object transform, type, materials
get_viewport_screenshot — PNG screenshot of 3D view
list_objects           — All objects in scene
set_object_transform   — Move/rotate/scale object
create_primitive       — Add cube, sphere, light, etc.
delete_object          — Remove object
execute_code           — Execute Blender Python (bpy)
```

### **5.3 Optional Integrations** (if enabled in addon)
- **Poly Haven**: Asset library (textures, HDRI, models)
- **Hyper3D / Hunyuan3D**: Text-to-3D generation (Rodin API)
- **Sketchfab**: 3D model search & import

### **5.4 API Routes** (`/api/blender/*`):
```
GET  /api/blender/ws         — WebSocket for interactive chat
GET  /api/blender/status     — Connection & scene info
POST /api/blender/connect    — Establish TCP connection
POST /api/blender/disconnect — Close connection
POST /api/blender/send       — Send command & get response
```

### **5.5 Web UI** (`BlenderPage.tsx`)
- Per-user conversation history (in-memory, 40 message limit)
- LLM vision: Screenshot → AI → Blender command JSON
- Real-time status updates (thinking, executing, done, error)

---

## **6. DATABASE** (PostgreSQL Embedded)

### **6.1 Core Tables**

| Table | Purpose |
|-------|---------|
| **app_auth_users** | Login credentials, email/phone verification |
| **users** | App users linked to auth + WhatsApp devices |
| **app_scenarios** | Agent personality blueprints |
| **app_my_agents** | User-created agents mapped to scenarios |
| **ai_provider_settings** | LLM configs (OpenAI, Groq, Ollama, etc.) |
| **workflows** | Workflow definitions (JSON) |
| **node_types** | Registered workflow node types |
| **workflow_runs** | Execution records |
| **run_nodes** | Per-node execution details |
| **scheduled_tasks** | Cron jobs (prompt/skill/pipeline) |
| **skill_configurations** | Runtime configs for skills |
| **browser_playbooks** | Recorded browser automation (JSONL) |
| **custom_tools** | User-defined HTTP tools |
| **mcp_servers** | MCP server registrations |
| **desktop_agents** | Headless agent instances |
| **chat_embeddings** | Vector memory (planned, pgvector) |
| **whatsmeow_*** | WhatsApp E2E keys, contacts, messages (internal) |
| **chatui_conversations** | Web chat conversation metadata |
| **chatui_messages** | Web chat message history |

### **6.2 Features**
- ✅ Embedded single-node PostgreSQL
- ✅ Auto-migration on startup
- ✅ UUID primary keys
- ✅ JSONB columns for configs
- ✅ Trigger-based updated_at timestamps
- 🚧 pgvector extension (planned for semantic search)

---

## **7. LLM PROVIDER SUPPORT**

### **7.1 Supported Providers**

| Provider | Endpoint | Auth | Models |
|----------|----------|------|--------|
| **OpenAI** | `https://api.openai.com/v1` | API Key | gpt-4, gpt-4o, gpt-3.5-turbo, o1, o3, o4 |
| **Groq** | `https://api.groq.com/openai` | API Key | mixtral, llama-3-70b |
| **Together AI** | `https://api.together.xyz` | API Key | Mistral, Llama, Qwen |
| **Fireworks** | `https://api.fireworks.ai/inference` | API Key | Various open models |
| **Mistral** | `https://api.mistral.ai` | API Key | Mistral Small/Medium/Large |
| **OpenRouter** | `https://openrouter.ai/api` | API Key | 200+ models aggregated |
| **LM Studio** | `http://localhost:1234` | None | Local models |
| **Ollama** | `http://localhost:11434` | None | Local models (qwen, llama) |

### **7.2 Configuration**
- **Storage**: `ai_provider_settings` table (UUID, provider_name, model_name, api_key, type: "chat"/"image")
- **Selection**: Latest by updated_at
- **Fallback**: Defaults to gpt-4o-mini

### **7.3 Message Format** (OpenAI-compatible)
```json
{
  "model": "gpt-4o",
  "messages": [
    {"role": "system", "content": "..."},
    {"role": "user", "content": "..."}
  ],
  "temperature": 0.7,
  "tools": [{"type": "function", "function": {...}}],
  "tool_choice": "auto|required"
}
```

### **7.4 Special Paths**
- **Ollama**: Uses JSON format request, `/api/chat` endpoint
- **Image Generation**: Separate type, DALL-E/Mistral Image APIs

---

## **8. TOOL SYSTEM**

### **8.1 Tool Categories**

#### **A. Custom HTTP Tools**
- User-defined REST API wrappers
- Template variables: `{param}` in URL, body, headers
- Input schema from JSON schema
- Approval gates (Always/Once/Never)

```
GET    /api/custom-tools              — List all tools
POST|PUT|DELETE /api/custom-tools/{id} — CRUD
PATCH  /api/custom-tools/{id}/toggle  — Enable/disable
POST   /api/custom-tools/{id}/test    — Execute with sample data
```

#### **B. MCP (Model Context Protocol) Servers**
- Standardized tool server protocol
- HTTP Stream or SSE connection
- Tool discovery
- Dynamic schema composition

```
GET|POST|PUT|DELETE /api/mcp-servers/{id} — Server CRUD
PATCH  /api/mcp-servers/{id}/toggle       — Enable/disable
POST   /api/mcp-servers/{id}/discover     — Fetch available tools
GET    /api/mcp-servers/{id}/tools        — List cached tools
```

#### **C. Browser Tools**
- Exposed to LLM during web research
- Persistent page per request

**Builtin Browser Tools**:
```
browser_open(url)               → content + links + media
browser_search(query)           → DuckDuckGo results
browser_get_links(selector?)    → [{text, href}]
browser_get_images(selector?)   → [{alt, src}]
browser_get_text(selector)      → extracted text
browser_get_html()              → raw HTML
browser_click(selector)
browser_fill(selector, value)
browser_scroll(direction)
browser_press(key)
browser_download_media(urls)    → file paths
browser_screenshot(full_page?)  → PNG path
```

#### **D. Workflow Tools**
- Workflows exposed as tools to LLM planner
- Input/output schema from node definitions
- Executed via ToolRouter

#### **E. Skill Tools**
- Auto-generated from registered skills
- Run via SkillEngine with self-healing
- SETTINGS injection (sensitive configs)

#### **F. Built-in Agent Tools**
```
run_python(code)                              — Execute Python in kernel
run_skill(skill_name, args)                   — Execute skill
send_file(data, filename)                     — Return file to user
send_message(channel, text)                   — Send to WhatsApp/Slack/etc.
create_schedule(task_name, cron, type, payload) — Schedule task
run_playbook(name)                            — Execute browser automation
create_playbook(name, website, content)       — Save JSONL playbook
save_setting(key, value)                      — Persist config
```

### **8.2 Tool Integration Flow**
```
LLM (ask for tools)
  → OpenAI function_calling format
Tool Executor (parse tool_calls)
  → dispatch to handler
Handler (browser_*, skill_run, run_python, etc.)
  → execute
Result (text/JSON/binary)
  → return to LLM
Tool Call Logs
  → persist for audit
```

---

## **9. SELF-HEALING & ERROR RECOVERY**

### **9.1 Skill Self-Healing**
1. **Initial Execution** fails with error
2. **AI Diagnosis**: Send failed code + error to LLM
3. **Code Fix**: LLM regenerates corrected code
4. **Retry**: Execute fixed version
5. **Max Retries**: 3 (configurable)
6. **Discovery Log**: Record all attempts

```
POST /api/skills/{name}/ai-edit — Manual AI code improvement
```

### **9.2 Tool Schema Self-Healing** (callOpenAI)
- If 400 `invalid_function_parameters` error:
  - Extract broken tool name
  - Disable skill in engine
  - Remove from tool list
  - Retry request with updated tools

### **9.3 Media Download Self-Healing**
- First failure: save to error buffer
- On retry request: regenerate upload with `SendMediaRetryReceipt`
- New `DirectPath` provided by WhatsApp
- Download with updated path

### **9.4 Browser Automation Recovery**
- Track step sequence + variables
- On error: analyze screenshot via vision
- Suggest alternate selectors/actions
- Resume from last successful step

---

## **10. SCHEDULING SYSTEM**

### **10.1 Cron-Based Task Scheduler**
- **Engine**: robfig/cron (standard cron expressions)
- **Concurrency**: Single execution per task (prevent overlap)
- **Timeout**: Configurable per task (default 120s)
- **History**: last_run_at, last_status, last_error, run_count tracked

### **10.2 Task Types**

| Type | Execution | Use Case |
|------|-----------|----------|
| **prompt** | Send text to AI planner | Daily summaries, reminders |
| **skill** | Call registered skill directly | Data processing, archiving |
| **pipeline** | Run multiple skills in sequence | Complex workflows |

### **10.3 Task Specification**
```json
{
  "task_name": "Morning Briefing",
  "description": "Send news summary daily at 9am",
  "cron_expr": "0 9 * * *",
  "task_type": "prompt",
  "task_payload": {
    "prompt": "Summarize today's top news"
  },
  "target_jid": "1234567890@s.whatsapp.net",
  "channel": "whatsapp",
  "enabled": true
}
```

### **10.4 Database Schema**
```sql
scheduled_tasks (
  id, owner_user_id, task_name, description,
  cron_expr, task_type, task_payload, target_jid, channel,
  enabled, last_run_at, last_status, last_error, run_count,
  created_at, updated_at
)
```

### **10.5 Lifecycle**
1. **Start()**: Load enabled tasks → register with cron
2. **Register**: Parse cron_expr → create cron entry
3. **Execute** (on tick): Load task → execute by type → save result
4. **Result Delivery**: Send output message to target_jid via WhatsApp/Slack
5. **Update Status**: Save to database

### **10.6 API Routes** (`/api/scheduled-tasks/*`):
```
GET    /api/scheduled-tasks              — List all tasks
POST   /api/scheduled-tasks              — Create
PUT    /api/scheduled-tasks/{id}         — Update (auto-reloads scheduler)
DELETE /api/scheduled-tasks/{id}         — Delete
PATCH  /api/scheduled-tasks/{id}/toggle  — Enable/disable
POST   /api/scheduled-tasks/{id}/run     — Execute immediately
```

### **10.7 Tool Definition** (for Planner)
```
create_schedule(
  task_name: str,
  cron_expr: str,          // e.g., "0 9 * * *"
  task_type: str,          // "prompt" | "skill" | "pipeline"
  prompt: str              // for prompt type
) → Creates recurring task
```

---

## **11. FRONTEND PAGES & UI**

### **11.1 Public Pages**
- `/` — Home (landing)
- `/login` — Login form
- `/signup` — Registration
- `/terms` — Terms of Service
- `/privacy` — Privacy Policy
- `/verify-account` — Email/SMS verification
- `/forgot-password`, `/reset-password` — Password recovery

### **11.2 Account Center** (`/account/*`, Protected)

| Route | Page | Features |
|-------|------|----------|
| `/account/my-accounts` | MyAccountsPage | WhatsApp user registration, QR pairing, connection status |
| `/account/channels` | ChannelsPage | Active adapters (WhatsApp, Telegram, Slack) status |
| `/account/users` | UsersPage | Manage connected WhatsApp numbers |
| `/account/desktop-agents` | DesktopAgentsPage | Create agents, view tokens, connection history, SSE subscriptions |
| `/account/my-agents` | MyAgentsPage | Create agents, assign scenarios, view executions |
| `/account/scenarios` | ScenariosPage | Create agent personas, system prompts |
| `/account/skill-settings` | SkillSettingsPage | Configure skill parameters (API keys, settings per skill) |
| `/account/skills` | SkillRegistryPage | Browse registered skills, view code, toggle, edit, delete |
| `/account/scheduled-tasks` | ScheduledTasksPage | Create cron jobs (daily briefings, automations) with cron descriptor |
| `/account/playbooks` | PlaybooksPage | List browser automations, edit JSONL, record new |
| `/account/workflows` | WorkflowListPage | List workflows, create, view status |
| `/account/workflows/{id}` | WorkflowEditorPage | Visual DAG editor (React Flow), add nodes, connect, validate |
| `/account/workflows/{id}/runs/{runId}` | WorkflowRunDetailPage | View execution details, node by node |
| `/account/workflow-runs` | WorkflowRunsPages | Filter runs by workflow, status, date range |
| `/account/workflow-nodes` | NodeRegistryPage | Browse all node types, create custom nodes |
| `/account/workflow-templates` | TemplateGalleryPage | Pre-built workflows (GitHub/user community) |
| `/account/mcp-tools` | MCPToolsPage | Manage MCP servers, custom tools, discover new tools |
| `/account/chat` | ChatPage | Multi-conversation web chat UI, file uploads |
| `/account/blender` | BlenderPage | 3D scene chat interface (if Blender connected) |
| `/account/settings` | SettingsPage | LLM provider configuration (OpenAI, Groq, Ollama, etc.), model selection |
| `/account/integrations` | IntegrationsPage | System diagnostics, bridge status, database health |

### **11.3 Sidebar Menu Structure** (`AccountShell.tsx`)
```
Management Areas
├─ My Account
├─ Channels
├─ My Scenarios
├─ My Agents
├─ Skill Settings
├─ Skills
├─ Scheduled Tasks
├─ Playbooks
├─ Workflows
├─ Node Registry
├─ Workflow Runs
├─ Templates
├─ MCP & Tools
├─ Chat UI
├─ Blender
├─ LLM Settings
└─ Status / Integrations
```

---

## **12. PLAYBOOKS & BROWSER AUTOMATION**

### **12.1 Playbook Format** (JSONL)
```json
{"action":"goto","url":"https://example.com"}
{"action":"fill","selector":"#search","value":"query"}
{"action":"click","selector":"button[type=submit]"}
{"action":"wait","selector":".results","timeout":5000}
{"action":"get_text","selector":".result-title","set_variable":"$title"}
{"action":"get_links","selector":".results","set_variable":"$links"}
{"action":"take_screenshot"}
```

### **12.2 Playbook Actions**

| Action | Params | Purpose |
|--------|--------|---------|
| `goto` | `url` | Navigate to URL |
| `click` | `selector` | Click element |
| `fill` | `selector, value` | Type into input (supports `{setting.x.y}` placeholders) |
| `fill_element` | `element, value` | Alias for fill |
| `select_option` | `selector, value` | Choose dropdown option |
| `press` | `key` | Press keyboard key (Enter, Tab, etc.) |
| `scroll` | `dir` | Scroll up/down |
| `wait` | `selector?, timeout` | Wait for element or time |
| `get_text` | `selector` → `set_variable` | Extract text content |
| `get_attribute` | `selector, key` → `variable` | Extract HTML attribute (href, data-*, etc.) |
| `get_links` | `selector?` → `$links` | Extract all links `[{text, href}]` |
| `get_page_html` | none → `$html` | Full page HTML |
| `send_llm` | `find or question` | Screenshot → AI vision → xpath/answer |
| `take_screenshot` | none | Save PNG to temp dir |
| `find_element` | `selector` | Store selector for chaining |

### **12.3 Setting Placeholders**
- **Format**: `{setting.skill_name.config_name}`
- **Resolved at**: Execution time (from `skill_configurations` table)
- **Use case**: Passwords, API keys, usernames (NEVER sent to LLM)
- **Example**: `{setting.auth.password}` → resolved before filling form

### **12.4 Browser Recording**
- **Toolbar**: Chrome extension UI appears on every page
- **Capture Methods**:
  - User interactions (clicks, fills, selections) → captured via `__yaRecordAction` binding
  - Tool actions (screenshot, get_links, download_images)
  - Navigation (goto captured automatically)
- **Storage**: JSONL content in `browser_playbooks` table
- **Export**: Playbook can be run via `run_playbook` tool

### **12.5 LLM Vision Integration** (send_llm)
1. Take screenshot
2. Encode to base64
3. Send to OpenAI vision model: "Find the CSS selector for..."
4. AI responds with selector
5. Next action (click, fill, etc.) uses that selector
6. Chain multiple vision calls if needed

### **12.6 Database Schema**
```sql
browser_playbooks (
  id UUID, owner_user_id UUID, name TEXT,
  website TEXT, content TEXT (JSONL),
  enabled BOOLEAN, created_at, updated_at
)
```

### **12.7 Execution via Planner**
- Scheduler can trigger `run_playbook("name")`
- Planner can generate new playbooks via `create_playbook(name, website, content)`
- Playbooks can be chained: playbook → extract data → send result

---

## **13. NODE REGISTRY & WORKFLOW EXTENSIBILITY**

### **13.1 Node Type Model**
```json
{
  "id": "uuid",
  "typeKey": "prompt_llm",
  "displayName": "LLM Prompt",
  "description": "Send message to LLM and get response",
  "category": "ai",
  "icon": "brain-circuit",
  "color": "#4f46e5",
  "inputTypes": {
    "required": {"prompt": "string", "model": "string"},
    "optional": {"temperature": "number"}
  },
  "returnTypes": {"response": "string"},
  "returnNames": ["response"],
  "functionName": "run_prompt_llm",
  "outputNode": false,
  "isBuiltin": true,
  "isActive": true,
  "isDeprecated": false,
  "searchAliases": ["chat", "ai", "completion"],
  "handlerCode": null,
  "aiGenerated": false
}
```

### **13.2 Builtin Node Categories**

| Category | Examples |
|----------|----------|
| **ai** | prompt_llm, image_generate, summarize |
| **data** | json_parse, csv_read, regex_match, aggregate |
| **integration** | http_request, webhook_send, send_message |
| **logic** | condition, loop, switch, delay |
| **media** | image_resize, pdf_extract, video_transcode |
| **custom** | User-created with AI-generated code |

### **13.3 Custom Node Creation**
1. User creates node via UI: displayName, description, input/output schema
2. AI generates Python handler code
3. Handler tested in sandbox
4. Registered in `node_types` table
5. Available for workflows immediately

### **13.4 API Routes**
```
GET  /api/workflows/nodeclasses          — Get all node type schemas
POST /api/workflows/{id}/nodes           — Add node to workflow
PUT  /api/workflows/{id}/nodes/{nodeId}  — Update node config
DELETE /api/workflows/{id}/nodes/{nodeId} — Remove node
```

---

## **14. DESKTOP FEATURES**

### **14.1 Window & Tray**
- **Framework**: Wails v2 (Go + React)
- **Window**: 1440×900 default, hide-on-close option
- **Tray Icon**: Windows only (systray library)
  - **Menu**: Open | Quit
  - Disabled on Linux/macOS (GTK/AppDelegate conflicts with Wails)

### **14.2 Embedded Runtimes**

| Runtime | Technology | Purpose |
|---------|-----------|---------|
| **PostgreSQL** | Native binary (pg_embed) | Database |
| **Python** | python.exe (Windows) / binary (Unix) | Code/Kernel execution |
| **Playwright** | browser-driver + Chromium | Browser automation |
| **Blender Addon** | mantis_blender.py | 3D modeling |

### **14.3 Startup Sequence**
1. **Wails OnStartup hook**: `main.go` → `RunLinuxSetup()` (Linux-specific package install)
2. **PostgreSQL**: `ensurePostgresRuntime()` → start or attach (skip if `SKIP_POSTGRES_BOOTSTRAP`)
3. **Python**: `EnsurePythonRuntime()` → extract, verify, initialize kernel
4. **Playwright**: `EnsurePlaywrightRuntime()` → browser install + BrowserTool init
5. **Blender Addon**: Extract `/blender-embed/` → `~/blender/mantis_blender.py`
6. **API Server**: Start HTTP server on configured port (default 8001)

### **14.4 Cross-Platform Support**

| OS | Status | Tray | Notes |
|----|--------|------|-------|
| **Windows** | ✅ Full | ✅ Systray | All features, system tray working |
| **macOS** | ✅ Partial | ❌ Disabled | Wails native menus, no GTK conflict |
| **Linux** | ✅ Partial | ❌ Disabled | GTK signal handler issue with Wails |

### **14.5 Auto-Setup (Linux)**
```bash
apt update
apt install libgtk-3-dev libwebkit2gtk-4.0-dev libappindicator3-dev
pip install playwright requirements
mkdir -p ~/.local/share/psql
```

---

## **15. SECURITY**

### **15.1 Authentication**
- **JWT Tokens**: Signed with app secret, TTL 24 hours (default)
- **Verification**: Email + SMS optional
- **Password**: PBKDF2 with salt (per-user salt stored in DB)

### **15.2 User Management**

| Endpoint | Purpose |
|----------|---------|
| `POST /api/auth/signup` | Register new account (email, phone, password) |
| `POST /api/auth/login` | Login (username + password) → JWT token |
| `POST /api/auth/verify-email` | Email verification link/code |
| `POST /api/auth/phone/send-code` | SMS code delivery |
| `POST /api/auth/verify-phone` | Verify SMS code |
| `POST /api/auth/forgot-password` | Reset password link |
| `POST /api/auth/reset-password` | Set new password |
| `GET /api/auth/me` | Current user info (requires auth) |
| `GET /api/account/profile` | User profile |
| `PUT /api/account/profile` | Update profile |

### **15.3 Authorization** (@requireAuth middleware)
- All `/api/*` routes except `auth/signup|login|forgot-password` require valid JWT
- Token validated via `parseToken()` → claims extraction
- User ID from claims stored in request context

### **15.4 Data Privacy**
- WhatsApp E2E keys: Encrypted at rest (Signal protocol)
- AI API keys: Stored in `ai_provider_settings`, never logged
- Skill configs: Stored in `skill_configurations`, resolved at execution only
- Chat history: Per-user, accessible only to owner
- Playbooks: Sensitive fields (`{setting.x.y}`) resolved at runtime, not sent to LLM

### **15.5 Sandbox Security**
- Python kernel: Restricted file I/O (WORK_DIR only)
- Browser: Persistent user data dir, no destructive scripts allowed
- Tool execution: Rate limiting on API calls
- Blender: TCP localhost only (127.0.0.1:9877)

---

## **16. HISTORY & MEMORY**

### **16.1 Chat History**
- **Storage**: JSONL files per user (legacy) or database
- **Query**: `GET /api/chat/history/{userId}` → last 100 messages
- **Access**: Requires authentication

### **16.2 Conversation Persistence** (ChatUI)
```sql
chatui_conversations (
  id, owner_user_id, title, context, created_at, updated_at
)
chatui_messages (
  id, conversation_id, role, content, created_at
)
```

### **16.3 Playbook Recording History**
- All playbooks auto-saved with timestamps
- Version tracking via `updated_at`
- Step-by-step execution logs during runs

### **16.4 Workflow Run History**
- Execution records in `workflow_runs` table
- Per-node details in `run_nodes`
- Screenshots taken during browser agent runs
- Searchable by: workflow_id, status, date range

### **16.5 Scheduled Task History**
- `last_run_at`: timestamp of last execution
- `last_status`: "success" | "error" | "never"
- `last_error`: exception message if failed
- `run_count`: total executions

### **16.6 Vector Memory** (Planned)
- **Purpose**: Semantic search of past conversations
- **Implementation**: PostgreSQL pgvector + Nomic Embed v1.5
- **Schema**: `chat_embeddings(owner_jid, chat_jid, role, content, embedding[768])`
- **Query**: Cosine similarity search for context injection
- **Benefit**: LLM can reference relevant old msgs even after 20+ new messages

---

## **17. MEDIA HANDLING**

### **17.1 Upload Pipeline** (WhatsApp)
- **Encryption**: AES-256-CBC with media key
- **Hashing**: SHA256 (plaintext) + HMAC-SHA256 (ciphertext)
- **Upload**: POST to WhatsApp media server with multipart form
- **Response**: Direct path + media key for token generation

### **17.2 Download Pipeline**
- **Media Conn**: Query WhatsApp for download hosts periodic refresh (TTL)
- **Fetch**: HTTPS from `https://{host}{directPath}?hash=...`
- **Decrypt**: AES-256-CBC decrypt using media key
- **Validation**: Verify SHA256 hash
- **Retry**: Up to 5 attempts with exponential backoff on network errors
- **Storage**: File saved locally or returned to user

### **17.3 File Upload (Chat UI)**
```
POST /api/chatui/conversations/{convId}/upload
  → multipart file
  → stored on disk (WORK_DIR)
  → linked to message
```

### **17.4 File Serving**
```
GET /api/chatui/files/{msgId}/{filename}
  → serves file (requires auth)
  → browser download
```

### **17.5 Newsletter Media** (Unencrypted)
- Special path: `UploadNewsletter()`
- No encryption, file hash only
- Media handle returned for send request

---

## **18. NEWSLETTER & BROADCAST**

### **18.1 Newsletter (WhatsApp Channels)**
- **Purpose**: One-way broadcast to subscribers (like Twitter/Telegram channels)
- **Access**: Read-only for subscribers, edit/publish for admin
- **Media**: Unencrypted, handle-based
- **Features**:
  - Reactions (configurable: all, basic, none, blocklist)
  - View counters
  - Reply option (converts to DM to channel admin)

### **18.2 Newsletter API**
```
GET  /api/newsletter/subscribe/{jid}                   — Subscribe to channel
POST /api/newsletter/send/{jid}                        — Publish message
NewsletterMarkViewed()                                 — Count subscriber views
NewsletterSendReaction(jid, serverId, reaction)        — Add emoji reaction
NewsletterSubscribeLiveUpdates(jid) → Duration         — Get live update stream
```

### **18.3 Broadcast (Status)**
- **Purpose**: Personal status similar to WhatsApp status (visible to contacts)
- **Privacy Levels**: Contacts, Whitelist, Blacklist
- **MediaType**: WhatsApp Status Keys (special encryption)
- **Recipient List**: Auto-rebuilt from DB or configured manually

### **18.4 Broadcast API**
```
GetStatusPrivacy(ctx) → []StatusPrivacy — User's settings
SetStatusPrivacy(ctx, privacy)          — Update who sees status
SendMessage(..., targets=statusBroadcast) — Broadcast to all
```

---

## **19. ARCHITECTURE & INFRASTRUCTURE**

### **19.1 Tech Stack**

| Layer | Technology |
|-------|-----------|
| **Desktop App** | Wails v2 (Go backend + React 18 frontend) |
| **Backend** | Go 1.21+ (stdlib http, no heavy frameworks) |
| **Frontend** | React 18, React Router 6, Mantine UI, React Flow (DAG editor) |
| **Database** | PostgreSQL 12+ (embedded single-process) |
| **Code Exec** | Python 3.10+ (embedded, Yapzek Kernel) |
| **Browser** | Playwright (Chromium), persistent user-data dir |
| **3D Modeling** | Blender 3.0+ (via TCP socket addon) |
| **Messaging** | WhatsApp (whatsmeow library), Telegram, Slack |

### **19.2 API Design**
- **Protocol**: RESTful JSON over HTTP
- **Auth**: JWT token in `Authorization: Bearer` header
- **Response Format**: `{"ok": bool, "item|items|error": ...}`
- **Errors**: HTTP status codes (401 auth, 400 validation, 500 server)

### **19.3 Deployment**
- **Target**: Single binary executable (Windows/Mac/Linux)
- **Data**: PostgreSQL database file on disk (portable)
- **Config**: Environment variables (DATABASE_DSN, API_ADDR, etc.)
- **Embedded**: All assets (frontend, blender addon, python stdlib) bundled
- **Startup**: Automatic runtime extraction + initialization

### **19.4 Development**
- Frontend source: `frontend/` dir, built to `web/` embed
- Backend source: `desktop/api/`, `desktop/engine/`, `desktop/py-kernel/`
- Root go run: `wails dev` (hot-reload)
- Build: `wails build` → Windows/Mac/Linux binaries

### **19.5 Concurrency**
- **Workflows**: 10 concurrent executions max (semaphore)
- **Scheduled Tasks**: Single-threaded per task (prevent overlap)
- **WebSocket**: Per-user connection hub (browser chat, Blender)
- **Database**: Connection pool (default 25 conns)
- **Python Kernel**: Single process, JSON-RPC serialized requests

---

## **20. EXECUTION PATTERNS**

### **20.1 Message Processing Flow (Inbound)**
```
WhatsApp Message
  → ParseWebMessage()
  → Router.ProcessInbound()
  → Find agent for sender
  → ChatUI: Store message
  → Yapzek: Ask LLM with tools
    → LLM plans actions
    → Execute tools (browser, skill, code, etc.)
    → Collect results
  → Send reply via adapter
```

### **20.2 Scheduled Task Execution**
```
Cron tick (every 1 min)
  → Load enabled tasks where time matches
  → executeTask(taskId)
    → if type == "prompt": planAndExecute(prompt)
    → if type == "skill": skillEngine.ExecuteWithSelfHeal(skillName, args)
    → if type == "pipeline": loop { executeSkill(...) }
  → sendMessage(outputText, targetJid)
  → updateTaskStatus(taskId, "success"/"error")
```

### **20.3 Workflow Execution**
```
User: Run Workflow
  → Validate DAG
  → Send to Python kernel via streaming bridge
  → Python executes nodes in order (or parallel)
    → Emits node_start, node_complete, node_error, workflow_complete events
  → Go receives events, dispatches to EventHandler
  → WebSocket broadcasts to frontend
  → Final result returned to user
```

### **20.4 Browser Agent Loop**
```
User: "Find the cheapest flight to NYC"
  LLM Tool Loop:
    1. Think: "I should search for flights"
       → browser_search("cheapest flights NYC")
    2. Think: "I see several results, let me click the best one"
       → browser_click("a[href*=expedia]")
    3. Think: "I'm on Expedia, let me extract prices"
       → browser_get_text(".price")
    4. Think: "Found results, done"
       → return final answer
```

---

## **SUMMARY TABLE: Features by Component**

| Component | Features | Count |
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

---

## **KEY METRICS**

- **API Endpoints**: 100+
- **Database Tables**: 25+
- **Frontend Routes**: 22
- **LLM Providers Supported**: 8
- **Tool Categories**: 5
- **Workflow Node Types**: 50+
- **Browser Tool Functions**: 10+
- **Max Concurrent Workflows**: 10
- **Max Skill Self-Heal Retries**: 3
- **Session Token TTL**: 24 hours
- **Desktop Agents Per User**: Unlimited
