# ProjectBridge — Development Roadmap

**Project:** ProjectBridge  
**Tagline:** Your project. Every AI. Zero context lost.  
**Purpose:** A free, local-first tool that helps developers transfer project context between AI assistants without repeatedly explaining their project, progress, decisions, and current problems.

---

## 1. Vision

ProjectBridge maintains portable, structured memory for a software or hardware project. Developers can switch between AI assistants and provide a compact, relevant context package instead of copying entire conversations or manually explaining project history.

The first version should be simple, useful, and completely free to run.

## 2. Core Principles

- **Free:** No paid API, subscription, or required cloud service.
- **Local-first:** Project information stays on the developer's computer by default.
- **AI-agnostic:** Context should work with ChatGPT, Gemini, Claude, and other assistants, including those without integrations.
- **Token-efficient:** Generate only the context relevant to the next task.
- **Project-aware:** Track files, Git changes, milestones, decisions, tasks, and issues—not only conversations.
- **Transparent:** Users can inspect, edit, export, and delete stored memory.
- **Incremental:** Build and validate one feature at a time.
- **Safe:** Never expose secrets, credentials, private keys, or sensitive files in generated context.

## 3. MVP Scope

The minimum viable product should:

1. Let the user register and select a local project folder.
2. Store project information and development notes locally.
3. Track project tasks and milestones.
4. Generate a portable AI context package.
5. Export the context as Markdown or copy it to the clipboard.
6. Allow the user to update project memory manually.

The MVP does **not** need an AI model, cloud service, browser extension, MCP server, or automatic conversation capture.

## 4. Proposed Technology Stack

Keep the stack simple and free.

- **Language:** Python
- **Desktop UI:** PySide6
- **Database:** SQLite
- **Context format:** Markdown
- **File monitoring:** Watchdog (later milestone)
- **Git integration:** Git CLI (later milestone)
- **Packaging:** PyInstaller (later milestone)
- **Version control:** Git and GitHub

Use local libraries and tools. No paid API keys or external services should be required.

## 5. Roadmap

### Phase 0 — Planning and Design

- [ ] Define MVP requirements.
- [ ] Decide the application's main workflows.
- [ ] Design the initial UI layout.
- [ ] Define the project memory format.
- [ ] Define database tables and relationships.
- [ ] Create architecture and data-flow diagrams.
- [ ] Establish privacy and file-exclusion rules.

**Deliverable:** Approved specification and architecture.

### Phase 1 — Application Foundation

- [ ] Set up the Python project.
- [ ] Set up PySide6.
- [ ] Create the initial application window.
- [ ] Establish a modular folder structure.
- [ ] Configure application settings.
- [ ] Implement SQLite initialization and migrations.
- [ ] Add basic error handling.

**Deliverable:** A desktop application that launches and initializes its local database.

### Phase 2 — Project Management

- [ ] Add a project.
- [ ] Select a local project directory.
- [ ] Edit project name and description.
- [ ] Define objectives and technology stack.
- [ ] Display registered projects.
- [ ] Switch between projects.
- [ ] Remove projects from the application without deleting their source folders.

**Deliverable:** Projects can be registered, viewed, edited, and managed.

### Phase 3 — Project Memory

Create structured memory for each project.

- [ ] Project overview and objectives.
- [ ] Technology stack.
- [ ] Architecture and important files.
- [ ] Current development status.
- [ ] Important decisions.
- [ ] Known bugs and limitations.
- [ ] Development notes.
- [ ] Current task and next steps.
- [ ] Completed milestones.

Allow the user to edit memory manually.

**Deliverable:** Persistent project memory that survives application restarts.

### Phase 4 — Tasks and Progress Tracking

- [ ] Create tasks.
- [ ] Edit and delete tasks.
- [ ] Set task status: Not Started, In Progress, Blocked, Completed.
- [ ] Add task descriptions and notes.
- [ ] Assign tasks to milestones.
- [ ] Display project progress.
- [ ] Display current and upcoming tasks.
- [ ] Record completed milestones.

**Deliverable:** A project dashboard showing development progress.

### Phase 5 — Context Generator

Generate a context package for another AI assistant.

The generated context should contain:

1. Project name and purpose.
2. Project objectives.
3. Technology stack.
4. Architecture summary.
5. Current development status.
6. Completed features.
7. Current task.
8. Relevant decisions.
9. Known problems.
10. Next steps.
11. Instructions for the receiving AI.

- [ ] Generate a complete context package.
- [ ] Generate a task-specific context package.
- [ ] Allow context sections to be enabled or disabled.
- [ ] Copy context to clipboard.
- [ ] Export context as Markdown.
- [ ] Preview context before exporting.
- [ ] Estimate context size and token count.
- [ ] Avoid including irrelevant or duplicate information.

**Deliverable:** Context can be transferred to any AI using copy-paste or a Markdown file.

### Phase 6 — Project File Scanner

- [ ] Scan the selected project directory.
- [ ] Identify common languages, frameworks, and project files.
- [ ] Generate a folder-tree summary.
- [ ] Identify important configuration files.
- [ ] Allow the user to select files for context.
- [ ] Respect ignore rules.
- [ ] Exclude secrets, credentials, binaries, build folders, and large irrelevant files.
- [ ] Provide a preview of information that will be included.

**Deliverable:** Context packages can include relevant source-code and project-structure information.

### Phase 7 — Git Integration

- [ ] Detect whether the project is a Git repository.
- [ ] Display the current branch.
- [ ] Display recent commits.
- [ ] Display modified and untracked files.
- [ ] Summarize changes between commits.
- [ ] Include relevant Git information in context packages.
- [ ] Allow the user to exclude Git information.

**Deliverable:** Context reflects recent development activity.

### Phase 8 — Automatic Project Monitoring

- [ ] Monitor selected project directories.
- [ ] Detect file creation, modification, and deletion.
- [ ] Record activity locally.
- [ ] Detect changes to important project files.
- [ ] Allow the user to pause monitoring.
- [ ] Avoid scanning excluded folders.
- [ ] Avoid storing excessive or redundant activity.

**Deliverable:** Project activity is tracked automatically without requiring a cloud service.

### Phase 9 — Session Handoff

Create a workflow for ending a development session.

- [ ] Record what was completed.
- [ ] Record files changed.
- [ ] Record problems encountered.
- [ ] Record decisions made.
- [ ] Record the next task.
- [ ] Generate a session summary.
- [ ] Save the summary in project memory.
- [ ] Generate context for the next AI session.

**Deliverable:** A session handoff can be created in a few clicks.

### Phase 10 — Browser Extension

Only begin after the core application and context generator are stable.

- [ ] Create a Chrome/Chromium extension.
- [ ] Detect supported AI websites.
- [ ] Allow the user to select a project.
- [ ] Retrieve a context package from ProjectBridge.
- [ ] Insert context into a new AI conversation.
- [ ] Capture user-approved conversation summaries.
- [ ] Provide a context-transfer workflow between AI platforms.
- [ ] Clearly indicate what information is being transferred.
- [ ] Avoid capturing conversations without user consent.

**Deliverable:** Context transfer becomes easier than manual copy-paste.

### Phase 11 — Optional Local AI

This phase is optional. ProjectBridge must remain useful without AI.

- [ ] Evaluate Ollama integration.
- [ ] Allow local model selection.
- [ ] Summarize development notes.
- [ ] Extract candidate tasks from user-approved conversations.
- [ ] Identify possible project decisions.
- [ ] Summarize Git changes.
- [ ] Allow users to review AI-generated memory before saving.
- [ ] Never require a paid AI API.

**Deliverable:** Optional local intelligence without subscription or API costs.

### Phase 12 — Testing and Release

- [ ] Unit tests for database operations.
- [ ] Tests for context generation.
- [ ] Tests for project scanning and ignore rules.
- [ ] Tests for Git integration.
- [ ] Tests for file monitoring.
- [ ] UI tests for critical workflows.
- [ ] Test on a clean installation.
- [ ] Verify that no paid services are required.
- [ ] Verify privacy and secret-exclusion behavior.
- [ ] Create installation instructions.
- [ ] Package the application.
- [ ] Create a GitHub release.

**Deliverable:** A usable, documented, free application.

## 6. Suggested Project Structure

```text
ProjectBridge/
├── README.md
├── ROADMAP.md
├── PROJECT_CONTEXT.md
├── DEVELOPMENT_LOG.md
├── TASKS.md
├── requirements.txt
├── pyproject.toml
├── src/
│   └── projectbridge/
│       ├── main.py
│       ├── app/
│       │   ├── window.py
│       │   └── settings.py
│       ├── database/
│       │   ├── database.py
│       │   └── repositories/
│       ├── models/
│       ├── services/
│       │   ├── project_service.py
│       │   ├── memory_service.py
│       │   ├── context_service.py
│       │   ├── task_service.py
│       │   └── scanner_service.py
│       ├── ui/
│       │   ├── dashboard/
│       │   ├── projects/
│       │   ├── tasks/
│       │   ├── memory/
│       │   └── context_export/
│       └── utils/
├── tests/
├── docs/
└── extension/
    └── (future browser extension)
```

## 7. Initial Data Model

### Project

- ID
- Name
- Description
- Local path
- Technology stack
- Objectives
- Created date
- Updated date

### Memory

- ID
- Project ID
- Category
- Content
- Importance
- Created date
- Updated date

Categories may include:

- Overview
- Architecture
- Decision
- Bug
- Progress
- Note
- Session
- Constraint

### Task

- ID
- Project ID
- Title
- Description
- Status
- Priority
- Milestone
- Created date
- Updated date
- Completed date

### Activity

- ID
- Project ID
- Activity type
- Description
- Source
- Timestamp

## 8. Context Generation Rules

Context generation should prioritize:

1. Current task.
2. Relevant project architecture.
3. Existing implementation.
4. Important decisions and constraints.
5. Recent changes.
6. Known problems.
7. Next steps.

Do not include the entire project history by default.

The generated context should instruct the receiving AI to:

- Read the provided context before proposing changes.
- Preserve existing architecture and decisions.
- Inspect existing files before generating replacements.
- Avoid unnecessary rewrites.
- Ask for clarification when requirements are genuinely missing.
- Provide complete updated files when modifying code.
- Explain testing procedures.
- Update project memory after meaningful work.

## 9. Privacy and Security

- Keep project memory on the local computer by default.
- Do not upload project files to external services.
- Exclude `.env`, credentials, private keys, tokens, passwords, and other secrets.
- Respect `.gitignore` and configurable ignore rules.
- Allow users to inspect exported context.
- Allow memory entries to be edited and deleted.
- Do not capture AI conversations without explicit user consent.
- Do not automatically execute commands generated by an AI.

## 10. Definition of Success

The MVP is successful when a user can:

1. Register a project.
2. Save its architecture, decisions, and progress.
3. Track tasks.
4. Generate an accurate context package.
5. Copy that package into a different AI assistant.
6. Continue development without manually explaining the project from scratch.

The application must work without an AI API, internet connection, subscription, or cloud account.

## 11. Development Rules

- Implement one phase at a time.
- Do not begin future phases prematurely.
- Keep the architecture simple.
- Avoid unnecessary dependencies.
- Provide complete files when modifying code.
- Test each feature before proceeding.
- Document implementation decisions.
- Update the roadmap and development log after completing a milestone.
- Do not claim a feature is complete unless it has been tested.
- Prioritize a working MVP over a large collection of unfinished features.

---

**First milestone:** Build the application foundation, project registration, persistent project memory, task tracking, and context export. Everything else comes later.
