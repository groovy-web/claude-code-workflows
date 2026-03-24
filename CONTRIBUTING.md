# Contributing to Claude Code Workflows

Thank you for your interest in contributing to Claude Code Workflows! This document provides guidelines and instructions for contributing workflows, templates, and examples.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [Contributing Guidelines](#contributing-guidelines)
- [Workflow Creation Guide](#workflow-creation-guide)
- [Pull Request Process](#pull-request-process)
- [Style Guidelines](#style-guidelines)

## Code of Conduct

Please read and follow our [Code of Conduct](CODE_OF_CONDUCT.md).

## Getting Started

### Prerequisites

- Claude Code CLI installed
- Git
- Basic understanding of:
  - Claude Code capabilities
  - Software development workflows
  - Markdown documentation

### Setting Up

1. **Fork and clone**

   ```bash
   git clone https://github.com/groovy-web/claude-code-workflows.git
   cd claude-code-workflows
   ```

2. **Explore existing workflows**

   ```bash
   ls workflows/
   cat workflows/development/feature.md
   ```

3. **Test a workflow**

   ```bash
   claude-code workflow workflows/development/feature.md
   ```

## Contributing Guidelines

### What to Contribute

We welcome contributions in:

- **New Workflows**: Complete workflow definitions
- **Workflow Improvements**: Enhancements to existing workflows
- **Templates**: Project templates, file templates, prompt templates
- **Examples**: Usage examples and demos
- **Documentation**: Guides and tutorials
- **Scripts**: Automation scripts
- **Bug Fixes**: Correcting issues

### Contribution Categories

#### 1. Development Workflows

Workflows for common development tasks:

```
workflows/development/
├── feature.md          # Feature development
├── bugfix.md           # Bug fixing
├── refactoring.md      # Code refactoring
└── testing.md          # Testing workflows
```

#### 2. Review Workflows

Code review and quality workflows:

```
workflows/review/
├── automated.md        # Automated review
├── manual.md           # Manual review checklist
└── security.md         # Security review
```

#### 3. Deployment Workflows

CI/CD and deployment workflows:

```
workflows/deployment/
├── ci-cd.md            # CI/CD pipeline
├── staging.md          # Staging deployment
└── production.md       # Production deployment
```

#### 4. Templates

Reusable templates:

```
templates/
├── projects/           # Project templates
├── files/              # File templates
└── prompts/            # Prompt templates
```

## Workflow Creation Guide

### Workflow Structure

Every workflow should follow this structure:

```markdown
# Workflow Name

## Description
Clear, concise description of what the workflow does and when to use it.

## Prerequisites
- Requirement 1
- Requirement 2

## Steps
1. **Step Name**
   - Action to take
   - Expected outcome

2. **Step Name**
   - Action to take
   - Expected outcome

## Usage
```bash
claude-code workflow path/to/workflow.md [options]
```

## Example
Concrete example of the workflow in action.

## Notes
Additional notes, tips, or considerations.
```

### Workflow Template

```markdown
# [Workflow Name]

> One-line description

## Overview
Detailed description of the workflow's purpose and goals.

## When to Use
- Scenario 1
- Scenario 2
- Scenario 3

## Prerequisites
### Required
- [ ] Tool 1
- [ ] Tool 2

### Optional
- [ ] Optional tool 1

## Steps

### Step 1: [Step Name]
**Description**: What this step does

**Actions**:
```bash
# Commands or actions
```

**Expected Output**:
- Output item 1
- Output item 2

**Verification**:
- How to verify step completed

### Step 2: [Step Name]
... (continue for all steps)

## Usage

### Basic Usage
```bash
claude-code workflow workflows/category/workflow.md
```

### With Options
```bash
claude-code workflow workflows/category/workflow.md \
  --option1 value1 \
  --option2 value2
```

## Examples

### Example 1: [Example Title]
**Context**: Brief context

**Execution**:
```bash
claude-code workflow workflows/category/workflow.md \
  --name "my-feature"
```

**Result**: What was achieved

## Troubleshooting

### Issue 1
**Problem**: Description
**Solution**: How to fix

## Related Workflows
- [Related Workflow 1](path/to/workflow1.md)
- [Related Workflow 2](path/to/workflow2.md)

## Resources
- [Resource 1](url)
- [Resource 2](url)
```

### Best Practices

#### 1. Clear Structure
- Use consistent formatting
- Number steps clearly
- Include code examples
- Provide expected outcomes

#### 2. Complete Information
- List all prerequisites
- Include verification steps
- Add troubleshooting section
- Provide examples

#### 3. Reusability
- Use variables/parameters
- Make steps modular
- Document assumptions
- Include alternatives

#### 4. Testing
- Test workflow locally
- Verify each step
- Document edge cases
- Test in different environments

## Template Creation Guide

### Project Template Structure

```
templates/projects/my-template/
├── README.md           # Template description
├── template.config.json  # Template configuration
├── src/                # Source files
├── tests/              # Test files
└── docs/               # Documentation
```

### Template Configuration

```json
{
  "name": "my-template",
  "description": "Template description",
  "version": "1.0.0",
  "variables": [
    {
      "name": "PROJECT_NAME",
      "description": "Project name",
      "default": "my-project"
    }
  ],
  "files": [
    "src/**/*",
    "tests/**/*"
  ]
}
```

### Prompt Template Structure

```markdown
# Template: [Template Name]

## Description
What this prompt template does

## Variables
- `{{variable1}}`: Description
- `{{variable2}}`: Description

## Template
```
Your prompt template here with {{variables}}
```

## Example Usage
```bash
claude-code prompt templates/prompts/my-template.md \
  --variable1 "value1" \
  --variable2 "value2"
```
```

## Style Guidelines

### Markdown Style

#### Headers
```markdown
# Main Title (H1 - only once)
## Section Title (H2)
### Subsection Title (H3)
#### Detail Title (H4)
```

#### Code Blocks
```markdown
Inline `code` uses backticks

Code blocks use triple backticks:
```bash
command here
```

```typescript
// With language for syntax highlighting
const example = "code";
```
```

#### Lists
```markdown
- Unordered list item
  - Nested item
  - Another nested item

1. Ordered list item
2. Another item
```

#### Emphasis
```markdown
**Bold text** for strong emphasis
*Italic text* for mild emphasis
`Code` for code or commands
```

#### Links
```markdown
[Link text](url)
[Relative link](../other-file.md)
[External link](https://example.com)
```

#### Tables
```markdown
| Column 1 | Column 2 | Column 3 |
|----------|----------|----------|
| Cell 1   | Cell 2   | Cell 3   |
```

### Workflow Style

#### Step Format
```markdown
### Step 1: [Action-Oriented Title]

**Description**: What and why

**Commands**:
```bash
# Commands here
```

**Expected Result**:
- Clear outcome
```

#### Code Examples
```markdown
**Example**:
```typescript
// Always include comments
function example() {
  // Clear code
  return true;
}
```
```

#### Notes and Warnings
```markdown
**Note**: Helpful tip

**Warning**: Important caution

**Tip**: Best practice
```

## Pull Request Process

### 1. Before Creating PR

- [ ] Workflow tested locally
- [ ] All steps work as documented
- [ ] Examples provided
- [ ] Documentation complete
- [ ] Follows style guidelines

### 2. Creating PR

1. **Descriptive title**
   ```
   feat(workflows): add database migration workflow
   ```

2. **Detailed description**
   - What workflow was added
   - Why it's needed
   - How it works
   - Testing performed

3. **Workflow documentation**
   - Complete README
   - Usage examples
   - Prerequisites listed
   - Troubleshooting included

4. **Screenshots/demos**
   - Before/after if applicable
   - Demo of workflow execution

### 3. PR Template

```markdown
## Description
Brief description of workflow added

## Type of Contribution
- [ ] New workflow
- [ ] Workflow improvement
- [ ] New template
- [ ] Documentation
- [ ] Bug fix

## Workflow Details
- **Category**: development/review/testing/deployment
- **Use Case**: When to use this workflow
- **Prerequisites**: List of requirements
- **Steps**: Number of steps

## Testing
- [ ] Tested locally
- [ ] All steps verified
- [ ] Examples tested
- [ ] Edge cases covered

## Documentation
- [ ] Complete README
- [ ] Usage examples
- [ ] Prerequisites listed
- [ ] Troubleshooting included

## Checklist
- [ ] Follows style guide
- [ ] Proper categorization
- [ ] No typos/errors
- [ ] Links work
```

### Review Process

#### What We Review

1. **Clarity**
   - Steps are clear
   - Instructions are precise
   - Examples are helpful

2. **Completeness**
   - All prerequisites listed
   - All steps documented
   - Troubleshooting included

3. **Usability**
   - Works as documented
   - Easy to follow
   - Properly categorized

4. **Quality**
   - No typos or errors
   - Proper formatting
   - Working links

#### Timeline

- Initial review: 1-2 days
- Additional rounds: 1-2 days each
- Complex workflows: 3-5 days

## Testing Your Workflows

### Local Testing

```bash
# Test workflow
claude-code workflow workflows/your-workflow.md

# Test with options
claude-code workflow workflows/your-workflow.md \
  --option value

# Verify each step
# Check expected outcomes
# Document any issues
```

### Validation Checklist

- [ ] All steps work
- [ ] Commands are correct
- [ ] Files created as expected
- [ ] No missing dependencies
- [ ] Error handling works
- [ ] Documentation matches reality

## Examples and Documentation

### Creating Examples

```markdown
## Examples

### Basic Example
**Context**: Simple use case

**Steps**:
1. Do this
2. Do that

**Result**: What happens

### Advanced Example
**Context**: Complex use case

**Configuration**:
```yaml
setting: value
```

**Execution**:
```bash
command
```

**Outcome**: Result
```

### Documentation Standards

- **Be Complete**: Cover all aspects
- **Be Clear**: Use simple language
- **Be Practical**: Provide real examples
- **Be Visual**: Use diagrams where helpful
- **Be Consistent**: Follow formatting rules

## Release Process

Maintainers handle releases:

1. Review merged PRs
2. Update CHANGELOG.md
3. Create git tag
4. Create GitHub release
5. Announce in discussions

## Getting Help

### Resources

- [Claude Code Docs](https://claude.ai/code)
- [Workflow Guide](docs/workflow-guide.md)
- [Examples](examples/)

### Community

- GitHub Issues: Questions, problems
- GitHub Discussions: Ideas, sharing
- Claude Code Community: Link in docs

## Recognition

Contributors will be:
- Listed in CONTRIBUTORS.md
- Mentioned in workflow files
- Credited in release notes

## License

By contributing, you agree that your contributions will be licensed under the MIT License.

## Questions?

- Check existing workflows
- Read documentation
- Open a GitHub discussion

Thank you for contributing to Claude Code Workflows!
