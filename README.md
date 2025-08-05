# Template Registry

This directory contains a comprehensive registry of Claude Code agent templates, commands, and MCP server configurations.

## 📁 Structure

```
templates/
├── registry.json          # Main registry index
├── agents/                # AI agent templates (.md files)
├── commands/              # Development command templates (.md files)
├── mcps/                  # MCP server configurations (.json files)
└── README.md             # This file
```

## 🚀 Usage

### Fetch Registry

```bash
curl -s https://raw.githubusercontent.com/sarkarraj/CCDB/main/docs/templates/registry.json
```

### Search Templates

```javascript
// Example: Find all AI-related templates
const registry = await fetch('https://raw.githubusercontent.com/sarkarraj/CCDB/main/docs/templates/registry.json').then(
  (r) => r.json(),
);

// Search by tags
const aiTemplates = Object.values(registry.categories.agents.subcategories)
  .flatMap((cat) => cat.templates)
  .filter((template) => template.tags.includes('ai'));

// Search by difficulty
const beginnerTemplates = Object.values(registry.categories.agents.subcategories)
  .flatMap((cat) => cat.templates)
  .filter((template) => template.difficulty === 'beginner');
```

### Download Template

```bash
# Download a specific agent template
curl -o prompt-engineer.md "https://raw.githubusercontent.com/sarkarraj/CCDB/main/docs/templates/agents/ai-specialists/prompt-engineer.md"

# Download an MCP configuration
curl -o playwright-mcp.json "https://raw.githubusercontent.com/sarkarraj/CCDB/main/docs/templates/mcps/browser_automation/playwright-mcp-server.json"
```

## 📊 Registry Statistics

- **Total Templates**: 102
- **Agent Templates**: 65
- **Command Templates**: 28
- **MCP Configurations**: 9

## 🏷️ Categories

### Agents

- **ai-specialists**: AI and LLM specialized agents
- **development-team**: Core development specialists
- **data-ai**: Data science and AI engineering
- **devops-infrastructure**: DevOps and infrastructure
- **security**: Security and compliance specialists
- **business-marketing**: Business and marketing experts

### Commands

- **automation**: Workflow automation commands
- **deployment**: Release and deployment processes
- **documentation**: API and technical documentation
- **git-workflow**: Version control workflows
- **performance**: Optimization and monitoring
- **security**: Security auditing and hardening
- **testing**: Test automation and coverage

### MCPs

- **browser_automation**: Browser testing and scraping
- **database**: Database integrations
- **devtools**: Development utilities
- **web**: Web scraping and analysis

## 🔍 Search Filters

Templates can be filtered by:

- **category**: Primary template category
- **tags**: Associated keywords and technologies
- **difficulty**: beginner, intermediate, advanced, expert
- **dependencies**: Required tools or frameworks
- **model**: Recommended Claude model (sonnet, opus)

## 💡 Examples

### Find React Development Templates

```javascript
const reactTemplates = registry.categories.agents.subcategories['development-team'].templates.filter((t) =>
  t.tags.includes('react'),
);
```

### Get All Security-Related Resources

```javascript
const securityResources = [
  ...registry.categories.agents.subcategories.security.templates,
  ...registry.categories.commands.subcategories.security.templates,
];
```

### Filter by Difficulty Level

```javascript
const expertTemplates = Object.values(registry.categories)
  .flatMap((category) => Object.values(category.subcategories))
  .flatMap((subcategory) => subcategory.templates)
  .filter((template) => template.difficulty === 'expert');
```

## 🔗 Integration

This registry is designed to integrate with:

- Claude Code agent management systems
- Template download and installation tools
- Project scaffolding utilities
- Developer productivity platforms

## 🤝 Contributing

To add new templates:

1. Add the template file to the appropriate directory
2. Update `registry.json` with template metadata
3. Include proper tags, dependencies, and related templates
4. Ensure GitHub raw URLs are accessible

## 📄 License

Templates are provided under the same license as the CCManager project.
