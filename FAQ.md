# Frequently Asked Questions

## General

**Did you actually build this, or is it just a concept?**

Phase 1 (Core Infrastructure) is complete and the system was operational in a production security operations environment. The architecture was designed, deployed, tested, and validated over multiple weeks of continuous operation. The results in [RESULTS.md](./RESULTS.md) are from real operations, not projections. Additional phases covering threat detection, active defense, and hardening were planned as part of the phased rollout.

**What platform does this run on?**

The agent orchestration layer runs on Hermes Agent, an open-source AI agent framework. The cognitive architecture (agent identities, memory systems, defense protocols, operational procedures) is custom-built — that is the core contribution of Project Wintermute.

**What LLM does it use?**

Multiple — the system uses model routing based on task complexity. Heartbeat and monitoring cycles use lightweight models for cost efficiency. Deep analysis and strategic planning use more capable reasoning models. The architecture is model-agnostic.

**How is this different from AutoGPT, CrewAI, or similar frameworks?**

Those are general-purpose agent frameworks. Wintermute is a security-specific cognitive architecture. The difference is specialization — Wintermute has built-in OPSEC enforcement, graduated autonomous defense, role-specialized agents for distinct operational domains, and a hierarchical command structure designed for security operations. It solves problems that general agent frameworks don't address: operational security, persistent memory across multi-day operations, and safe autonomous defense.

**How much does it cost to operate?**

Approximately $35-50 per month for 24/7 operation including heartbeat cycles, daily reflections, and all agent activity. See [RESULTS.md](./RESULTS.md) for detailed cost breakdowns.

---

## Technical

**What engineering disciplines are involved in building something like this?**

See the "The Engineering Behind This" section in [README.md](./README.md). In short: system prompt engineering, cognitive architecture design, multi-agent orchestration, and autonomous systems engineering.

**Is this just writing prompts?**

No. Prompt engineering is one component, but the system involves state machine design (the Z.E.R.O. graduated response model), distributed systems concepts (multi-agent coordination, task delegation, compartmentalization), memory architecture (structured persistence across stateless execution contexts), and security engineering (defense-in-depth for autonomous agents). The implementation medium is structured documents and natural language rather than traditional code, but the engineering problems are the same as any distributed autonomous system.

**Can I see an example agent prompt or configuration?**

The specific agent prompts, system instructions, and defense heuristics are not public. They represent the core intellectual property of the system and contain operational patterns that would reduce their effectiveness if disclosed. The architecture documents explain the design principles and capabilities without exposing the implementation details.

**What is Z.E.R.O. and why is it novel?**

Z.E.R.O. (Zone Emergency Response Override) is an autonomous defense system that uses graduated severity thresholds to determine response authority. Most autonomous systems either require human approval for everything (slow) or have full autonomy (dangerous). Z.E.R.O. resolves this by scaling authority based on threat severity — low events are monitored, medium events trigger automatic countermeasures, high events escalate immediately. See [ZERO-DEFENSE-SYSTEM.md](./ZERO-DEFENSE-SYSTEM.md).

**How does the memory system work?**

Wintermute uses a structured file-based persistence system rather than vector databases or specialized memory stores. Daily operational logs capture real-time activity, long-term memory files curate significant events and lessons, and startup protocols ensure agents restore full context from these files on activation. This approach is simpler, cheaper, and more reliable than database-dependent solutions for this use case.

---

## For Recruiters & Hiring Managers

**What does this project demonstrate about the developer's skills?**

- **System design** — Architecting a multi-agent system with role specialization, hierarchical command, and persistent state management
- **Security engineering** — Building autonomous defense systems with graduated response, safety constraints, and operational security enforcement
- **Technical writing** — Documenting complex architecture clearly for different audiences (executive, technical, operational)
- **Independent project delivery** — Taking a concept from design through deployment, testing, and validation without vendor support or team resources
- **Prompt engineering at scale** — Designing structured agent identities and decision-making frameworks that operate reliably across thousands of autonomous cycles

**Is this relevant to a security engineering or AI engineering role?**

Directly. The system demonstrates practical experience with AI agent architecture, autonomous system design, security operations modeling, and operational security — all of which transfer directly to roles involving AI security, red team automation, or security tooling development.

**Will the developer be able to discuss this in an interview?**

Yes. The architecture documents are written by the developer and reflect a thorough understanding of every design decision, tradeoff, and operational outcome. The system was built, tested, and operated by a single individual without external assistance.

**What is the developer's specific role in this project?**

Sole architect, engineer, and operator. Every component of Project Wintermute — from the agent identities and memory systems to the Z.E.R.O. defense framework and deployment infrastructure — was designed, implemented, tested, and documented by the developer.
