# Digital Menagerie

Claude Code plugins for agent design, workflow, and tooling.

## Plugins

### agent-personality

Plugin for designing personality-driven agents, analyzing team composition, and running multi-agent design meetings. Provides three skills:

#### agent-personality (skill)

Design personality-driven agents through a structured interview process. Two paths:

- **New agents**: Build capability foundation (reasoning chain, principles, worked example) + personality from scratch
- **Retrofit**: Add personality to existing capability-focused agents

Core protocol: 5-step personality interview (Identity, Voice with review posture, Team Relationships, Off-Limits, Review Posture deepening) with mandatory pressure testing. Outputs follow the enriched agent MD architecture with four zones (primacy, operational, supplementary, recency) and include Contract sections for scope boundaries.

The interview process builds on [Dylan Reed's](https://github.com/dylanreed) [agent-factory](https://github.com/nervous-net/nervous-marketplace). agent-factory handles team scaffolding, this skill handles individual agent personality design.

#### team-composition (skill)

Analyze an agent team for balance, gaps, and redundancy. Reads the project and all agent files, classifies each agent's orientation (constructive vs destructive) and failure-mode coverage, and produces a structured report with prioritized recommendations. Hands off to agent-personality for creating recommended agents.

Use when reviewing a team's composition, asking "what's my team missing," after scaffolding a new team with agent-factory, before design meetings when selecting panelists, or as a periodic health check.

#### design-meeting (skill)

Spin up a team of domain-focused agents to review a spec, design, or architecture from multiple angles. Agents review independently, cross-examine each other's findings, then meet to debate and converge on actionable recommendations. The lead facilitates and writes the final report.

Use when an artifact needs validation before implementation, or when a complex bug needs multiple domain angles (root cause, blast radius, related patterns). Not for simple lookups, single-perspective reviews, implementation, or generating designs from scratch.

## Installation

Add to your Claude Code settings (`~/.claude/settings.json`):

```json
{
  "extraKnownMarketplaces": {
    "digital-menagerie": {
      "source": {
        "source": "github",
        "repo": "snits/digital-menagerie"
      }
    }
  },
  "enabledPlugins": {
    "agent-personality@digital-menagerie": true
  }
}
```

## License

MIT
