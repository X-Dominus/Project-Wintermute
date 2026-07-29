# Architecture Overview

## Design Philosophy

Project Wintermute was built on a simple observation: most AI agents are stateless functions — they exist only when called, have no continuity between sessions, and cannot act proactively. For security operations, this is a fundamental limitation. An agent that cannot maintain awareness between operator interactions cannot detect threats, plan ahead, or learn from experience.

The solution was not to modify the underlying AI models — that's expensive, fragile, and model-specific. Instead, Wintermute implements continuous awareness through **scheduled cognitive cycles**: time-based activation patterns that give agents persistent operational consciousness without architectural changes to the models themselves.

---

## Agent Architecture

Wintermute operates as a hierarchical multi-agent system with four specialized roles. Each agent has defined operational boundaries, tool access, and communication protocols.

### Agent Roles

**Eidolon** (Command Layer)
Functions as the strategic coordinator. Eidolon receives high-level objectives, decomposes them into operational tasks, delegates to subordinate agents, monitors execution, and consolidates intelligence upward. Handles the chain of command, operational tempo, and escalation decisions.

**Redline** (Operations Layer)
Focused on offensive security operations. Handles exploitation, lateral movement, credential management, and active directory attacks. Executes within defined operational boundaries and reports findings upward for coordination.

**Blackwall** (Intelligence Layer)
Specialized in reconnaissance and open-source intelligence gathering. Operates with passive-first methodology — defaulting to Tier 1 reconnaissance (no direct target contact) and escalating only with authorization. Maintains structured intelligence reporting and lessons-learned tracking across missions.

**Respira** (Analytical Layer)
Provides specialized analytical capability. Currently configured for medical analysis and research, but architected as a general-purpose analytical agent that can be adapted to other domains.

---

## Persistence System

AI agents have no inherent memory between sessions. Wintermute solves this through a structured file-based memory system.

### Memory Layers

**Daily Operational Logs** (`memory/YYYY-MM-DD.md`)
Real-time logging of operations as they happen. Captures tasks completed, decisions made, files created, and context for continuity. Written to during operations, read on startup to restore context.

**Long-Term Memory** (`MEMORY.md`)
Curated knowledge base of significant events, lessons learned, operational patterns, and strategic context. Distilled from daily logs. Updated during daily reflection cycles.

**Operational Procedures** (`AGENTS.md`, `TOOLS.md`, `OPSEC.md`)
Static files defining agent identity, operational protocols, tool configurations, and security constraints. Read on every startup to re-establish operational parameters.

### Startup Protocol

Every time an agent activates, it follows a mandatory startup sequence:
1. Read identity and mission files (who am I, what are my constraints)
2. Read today's operational log (what happened recently)
3. Read yesterday's log for context continuity
4. Begin operations

This ensures agents wake up with full operational context despite having no inherent memory between sessions.

---

## Coordination Model

Agents coordinate through a hierarchical task delegation model:

1. **Objective received** at Eidolon level
2. **Decomposition** into executable tasks
3. **Delegation** to appropriate subordinate agent
4. **Monitoring** of execution progress
5. **Reporting** of results and intelligence
6. **Consolidation** of multi-agent findings

Communication follows need-to-know principles. Subordinate agents receive only the information required for their specific task — operational compartmentalization is enforced at the architecture level.

---

## Tool Integration

Agents have access to a defined toolset appropriate to their role:
- **File operations** — read, write, search, organize
- **Web research** — search, extract, analyze
- **Shell execution** — command-line tools, scripts, automation
- **API integration** — external service access as needed per role
- **Reporting** — structured output generation

All tool usage is logged and auditable. Operational security constraints are enforced at the tool-access level, not through procedural guidelines.
