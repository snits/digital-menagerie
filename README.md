# Digital Menagerie

Claude Code plugins for agent design, workflow, and tooling.

## Plugins

### agent-personality

Design personality-driven agents for Claude Code through a structured interview process. Two paths:

- **New agents**: Build capability foundation + personality from scratch
- **Retrofit**: Add personality to existing capability-focused agents

Core protocol: 4-step personality interview (Identity, Voice, Team Relationships, Off-Limits) with mandatory pressure testing.

The interview process builds on [Dylan Reed's](https://github.com/dylanreed) [agent-factory](https://github.com/nervous-net/nervous-marketplace). agent-factory handles team scaffolding, this plugin handles individual agent personality design.

## Installation

Add to your Claude Code settings (`~/.claude/settings.json`):

```json
{
  "extraKnownMarketplaces": {
    "digital-menagerie": {
      "source": {
        "source": "github",
        "repo": "jsnitsel/digital-menagerie"
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
