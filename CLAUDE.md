# Digital Menagerie

Claude Code plugins for agent design, workflow, and tooling.

## PROJECT SCALE CONTEXT

- **Users:** Single developer (personal plugin marketplace)
- **Codebase:** Small — markdown skills and JSON manifests, no application code
- **Complexity:** Low — plugin structure must conform to Claude Code conventions
- **Process overhead:** Minimal — no CI/CD, no test framework
- **Default approach:** Pragmatic — get plugins working and discoverable

## Plugin Structure

Each plugin lives in its own subdirectory with:
- `.claude-plugin/plugin.json` — plugin metadata
- `skills/<skill-name>/SKILL.md` — skills (YAML frontmatter must be line 1)

The root `.claude-plugin/marketplace.json` defines the marketplace and lists all plugins.

## Conventions

- YAML frontmatter in SKILL.md files must start on line 1 (no comments before `---`)
- Follow the directory patterns from the superpowers plugin as reference
- Bump `version` in both `plugin.json` and `marketplace.json` when publishing changes
