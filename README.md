# Agent Skills

A collection of reusable skills for AI coding agents to handle complex, multi-agent workflows.

## Skills

### Packet Orchestration

Plan and execute parallel feature work using atomic file-owned packets, dependency waves, and handoff prompts.

**Use when you need to:**
- Split features, migrations, or refactors into independent subagent tasks
- Run multi-agent work without merge conflicts
- Define clear contracts and boundaries for parallel work
- Review and repair completed work packets

**Key concepts:**
- **File ownership** as the hard boundary between packets
- **Dependency waves** for coordinated parallel execution
- **Atomic packets** that can run independently on the same branch
- **Repair packets** for narrow follow-up fixes

[View full documentation →](packet-orchestration/SKILL.md)

## Structure

```
agent-skills/
├── packet-orchestration/
│   ├── SKILL.md           # Main skill documentation
│   ├── agents/            # Agent configurations
│   └── references/        # Templates and examples
```

## Usage

Each skill directory contains:
- `SKILL.md` - Complete skill documentation and workflow
- `references/` - Templates, prompts, and checklists
- `agents/` - Agent configuration files

## License

This repository is provided as-is for use with AI coding agents.

