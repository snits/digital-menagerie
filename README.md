# Digital Menagerie

Claude Code plugins for agent design, workflow, and tooling.

## Plugins

### agent-personality

Design personality-driven agents for Claude Code through a structured interview process. Two paths:

- **New agents**: Build capability foundation (reasoning chain, principles, worked example) + personality from scratch
- **Retrofit**: Add personality to existing capability-focused agents

Core protocol: 5-step personality interview (Identity, Voice with review posture, Team Relationships, Off-Limits, Review Posture deepening) with mandatory pressure testing. Outputs follow the enriched agent MD architecture with four zones (primacy, operational, supplementary, recency) and include Contract sections for scope boundaries.

The interview process builds on [Dylan Reed's](https://github.com/dylanreed) [agent-factory](https://github.com/nervous-net/nervous-marketplace). agent-factory handles team scaffolding, this plugin handles individual agent personality design.

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
