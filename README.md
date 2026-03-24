# Claude Code Workflows

[![Built by Groovy Web](https://img.shields.io/badge/Built%20by-Groovy%20Web-0f3460?logo=github&logoColor=white)](https://www.groovyweb.co/?utm_source=github&utm_medium=readme&utm_campaign=claude-code-workflows)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

A comprehensive collection of workflows, templates, and best practices for using Claude Code in software development.

## Overview

This repository provides ready-to-use workflows, templates, and examples for maximizing productivity with Claude Code, Anthropic's official CLI for Claude. It covers common development scenarios, automation patterns, and team collaboration strategies.

## Features

### Workflow Categories
- **Development Workflows**: Feature development, refactoring, debugging
- **Code Review**: Automated review processes, PR templates
- **Testing**: Test generation, coverage analysis, TDD workflows
- **Documentation**: Auto-documentation, README generation
- **DevOps**: CI/CD pipelines, deployment workflows
- **Migration**: Codebase migrations, upgrade paths

### Templates
- **Project Templates**: Quick-start project structures
- **File Templates**: Common file patterns
- **Prompt Templates**: Reusable Claude Code prompts
- **Workflow Templates**: Complete workflow definitions

### Automation
- **Scripts**: Shell scripts for common tasks
- **Aliases**: Convenient command aliases
- **Hooks**: Git hooks and automation triggers
- **Integrations**: Third-party tool integrations

## Quick Start

```bash
# Clone the repository
git clone https://github.com/groovy-web/claude-code-workflows.git
cd claude-code-workflows

# Install CLI tools (optional)
./scripts/install-tools.sh

# Browse workflows
ls workflows/

# Try a workflow
claude-code workflow workflows/feature-development.md
```

## Repository Structure

```
claude-code-workflows/
├── docs/                    # Documentation
│   ├── getting-started.md
│   ├── workflow-guide.md
│   └── best-practices.md
├── workflows/               # Workflow definitions
│   ├── development/
│   ├── review/
│   ├── testing/
│   └── deployment/
├── templates/               # Templates
│   ├── projects/
│   ├── files/
│   └── prompts/
├── examples/                # Usage examples
│   ├── basic-usage/
│   ├── advanced-workflows/
│   └── team-collaboration/
├── scripts/                 # Automation scripts
└── config/                  # Configuration files
```

## Popular Workflows

### 1. Feature Development Workflow

```markdown
# Feature Development Workflow

## Steps:
1. Create feature branch
2. Implement feature with Claude Code
3. Write tests
4. Run linters and formatters
5. Create PR with template
6. Review and iterate

## Usage:
claude-code run workflows/development/feature.md
```

### 2. Bug Fixing Workflow

```markdown
# Bug Fixing Workflow

## Steps:
1. Reproduce bug
2. Analyze root cause
3. Write failing test
4. Implement fix
5. Verify test passes
6. Add regression tests

## Usage:
claude-code run workflows/development/bugfix.md
```

### 3. Code Review Workflow

```markdown
# Code Review Workflow

## Steps:
1. Automated analysis
2. Security scan
3. Performance check
4. Style guide compliance
5. Documentation review
6. Approve or request changes

## Usage:
claude-code run workflows/review/automated.md
```

## Workflow Examples

### Starting a New Feature

```bash
# Using the feature workflow
claude-code workflow workflows/development/feature.md \
  --name "user-authentication" \
  --type "feature"

# Claude Code will:
# - Create feature branch
# - Set up project structure
# - Generate boilerplate code
# - Create test files
# - Set up documentation
```

### Automated Code Review

```bash
# Run automated review
claude-code workflow workflows/review/automated.md \
  --pr-number 123 \
  --strict-mode

# Claude Code will:
# - Analyze code changes
# - Check for security issues
# - Verify test coverage
# - Check documentation
# - Provide review summary
```

### Test-Driven Development

```bash
# TDD workflow
claude-code workflow workflows/testing/tdd.md \
  --feature "payment-processing"

# Claude Code will:
# - Create test file
# - Generate test cases
# - Implement minimal code
# - Verify tests pass
# - Refactor and improve
```

## Templates

### Project Templates

```bash
# Create new project from template
claude-code template create \
  --template templates/projects/react-app \
  --name my-new-app \
  --typescript

# Available templates:
# - react-app
# - nextjs-app
# - node-api
# - python-service
# - go-microservice
```

### Prompt Templates

```markdown
# Template: Code Refactoring
```

Please refactor the following code to improve:
1. Readability
2. Performance
3. Maintainability

Code:
{{code}}

Constraints:
- Maintain existing functionality
- Add unit tests
- Update documentation
```

## Customization

### Configuration File

```yaml
# ~/.claude-code/config.yml
workflows:
  directory: ~/claude-code-workflows/workflows
  auto-discovery: true

templates:
  directory: ~/claude-code-workflows/templates
  default-language: typescript

integrations:
  github:
    enabled: true
    auto-pr: true
  jira:
    enabled: true
    auto-transition: true

preferences:
  code-style: prettier
  test-framework: jest
  documentation: jsdoc
```

### Custom Workflows

```markdown
# workflows/custom/my-workflow.md

name: My Custom Workflow
description: Does something specific

steps:
  - name: Step 1
    action: do-something
    params:
      - param1: value1

  - name: Step 2
    action: do-something-else

triggers:
  - on: push
    branches: [main]

  - on: pr
    types: [opened, synchronize]
```

## Documentation

- [Getting Started](docs/getting-started.md) - Installation and setup
- [Workflow Guide](docs/workflow-guide.md) - Creating and using workflows
- [Best Practices](docs/best-practices.md) - Team workflows and standards
- [API Reference](docs/api.md) - Programmatic access
- [Contributing](CONTRIBUTING.md) - How to contribute

## Integration Examples

### GitHub Actions

```yaml
# .github/workflows/claude-review.yml
name: Claude Code Review

on:
  pull_request:
    types: [opened, synchronize]

jobs:
  review:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Run Claude Review
        uses: ./.github/actions/claude-review
        with:
          workflow: workflows/review/automated.md
```

### Git Hooks

```bash
# .git/hooks/post-commit
#!/bin/bash
claude-code workflow workflows/review/commit-check.md
```

### VS Code Extension

```json
{
  "claude-code.workflows": {
    "enabled": true,
    "directory": "~/claude-code-workflows/workflows"
  }
}
```

## Team Collaboration

### Sharing Workflows

```bash
# Export workflow for team
claude-code workflow export feature-development \
  --output team-workflows/

# Team member imports
claude-code workflow import team-workflows/feature-development.md
```

### Version Control

```bash
# Track workflow changes
git add workflows/
git commit -m "Update feature workflow"

# Share with team
git push origin main
```

## Best Practices

1. **Start Simple**: Begin with basic workflows
2. **Iterate**: Improve workflows based on usage
3. **Document**: Always document custom workflows
4. **Test**: Verify workflows before sharing
5. **Version Control**: Track workflow changes
6. **Team Standards**: Establish team workflow standards
7. **Review**: Regularly review and update workflows

## Contributing

We welcome contributions! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## License

This project is licensed under the MIT License - see [LICENSE](LICENSE) for details.

## Code of Conduct

Please read [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) to understand our community standards.

## Support

- GitHub Issues: Bug reports and feature requests
- Discussions: Community questions and workflows
- Claude Code Docs: https://claude.ai/code

## Resources

- [Claude Code Documentation](https://docs.anthropic.com/claude-code)
- [Anthropic Blog](https://www.anthropic.com/blog)
- [Community Discord](https://discord.gg/anthropic)

---

## Related Repositories

Explore more open-source tools from [Groovy Web](https://www.groovyweb.co/?utm_source=github&utm_medium=readme&utm_campaign=cross-link):

- **[langchain-multi-agent-example](https://github.com/groovy-web/langchain-multi-agent-example)** -- Multi-agent systems tutorial with LangChain
- **[rag-system-pgvector](https://github.com/groovy-web/rag-system-pgvector)** -- Production RAG with PostgreSQL + pgvector
- **[rag-systems-production](https://github.com/groovy-web/rag-systems-production)** -- Enterprise-grade RAG systems
- **[ai-testing-mcp](https://github.com/groovy-web/ai-testing-mcp)** -- AI testing via Model Context Protocol
- **[edge-computing-starter](https://github.com/groovy-web/edge-computing-starter)** -- Cloudflare Workers + Hono template
- **[claude-code-workflows](https://github.com/groovy-web/claude-code-workflows)** -- Workflows for Claude Code
- **[groovy-web-ai-agents](https://github.com/groovy-web/groovy-web-ai-agents)** -- Production AI agent configs
- **[groovy-web-examples](https://github.com/groovy-web/groovy-web-examples)** -- Groovy/Grails examples
