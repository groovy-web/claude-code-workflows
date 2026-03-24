# Basic Claude Code Workflow Usage

A simple example demonstrating how to create and use Claude Code workflows.

## Overview

This example shows the basics of:
1. Creating a workflow file
2. Running workflows with Claude Code
3. Customizing workflows
4. Sharing workflows

## Prerequisites

- Claude Code CLI installed
- Basic understanding of markdown
- Git (for version control)

## Project Structure

```
basic-usage/
├── workflows/
│   ├── simple-task.md
│   ├── code-review.md
│   └── bug-fix.md
└── README.md
```

## Quick Start

### 1. Create Your First Workflow

Create `workflows/simple-task.md`:

```markdown
# Simple Task Workflow

> A basic workflow for completing simple development tasks

## Overview
This workflow guides you through completing a simple development task from start to finish.

## When to Use
- [ ] Small bug fixes
- [ ] Simple feature additions
- [ ] Documentation updates
- [ ] Code refactoring

## Prerequisites
- Claude Code installed
- Git repository initialized
- Editor configured

## Steps

### Step 1: Create Branch
**Purpose**: Isolate your changes

**Actions**:
```bash
# Create a new branch
git checkout -b feature/my-task

# Verify branch
git branch
```

**Expected Output**:
```
* feature/my-task
  main
```

### Step 2: Make Changes
**Purpose**: Implement your task

**Actions**:
```bash
# Edit files as needed
# Use your editor or IDE
```

**Verification**:
```bash
# See what changed
git status
```

### Step 3: Commit Changes
**Purpose**: Save your work

**Actions**:
```bash
# Add files
git add .

# Commit with message
git commit -m "feat: add my task"
```

**Expected Output**:
```
[feature/my-task abc1234] feat: add my task
 1 file changed, 5 insertions(+)
```

### Step 4: Push to Remote
**Purpose**: Share your changes

**Actions**:
```bash
# Push branch
git push -u origin feature/my-task
```

### Step 5: Create Pull Request
**Purpose**: Request code review

**Actions**:
- Go to GitHub/GitLab
- Click "New Pull Request"
- Fill in PR template
- Request reviewers

## Usage

```bash
# Using Claude Code
claude-code workflow workflows/simple-task.md

# Or with options
claude-code workflow workflows/simple-task.md \
  --task-name "Add user login" \
  --branch-name "feature/user-login"
```

## Example

**Input**:
```bash
claude-code workflow workflows/simple-task.md \
  --task-name "Fix navigation bug"
```

**What Happens**:
1. Creates branch: `feature/fix-navigation-bug`
2. Opens editor for changes
3. Guides through commit process
4. Helps create PR

**Result**: Clean PR ready for review
```

## Running Workflows

### Command Line

```bash
# Basic usage
claude-code workflow path/to/workflow.md

# With parameters
claude-code workflow path/to/workflow.md \
  --param1 value1 \
  --param2 value2

# Verbose mode
claude-code workflow path/to/workflow.md --verbose

# Dry run (see what would happen)
claude-code workflow path/to/workflow.md --dry-run
```

### Interactive Mode

```bash
# Claude Code will prompt for missing parameters
claude-code workflow workflows/simple-task.md

# Output:
# Enter task name: My new feature
# Enter branch name: feature/my-new-feature
# Creating branch...
# Done!
```

## Workflow Examples

### Code Review Workflow

**File**: `workflows/code-review.md`

```markdown
# Code Review Workflow

> Systematic code review process

## Overview
This workflow ensures thorough, consistent code reviews.

## Steps

### Step 1: Understand Context
**Purpose**: Understand what the code does

**Actions**:
- Read PR description
- Check linked issues
- Review requirements

### Step 2: Review Implementation
**Purpose**: Check code quality

**Checklist**:
- [ ] Code is readable
- [ ] Follows style guide
- [ ] Has tests
- [ ] Has documentation
- [ ] No security issues
- [ ] No performance issues

### Step 3: Test Locally
**Purpose**: Verify code works

**Actions**:
```bash
# Checkout PR branch
git checkout pr-branch

# Run tests
npm test

# Run linter
npm run lint

# Build project
npm run build
```

### Step 4: Provide Feedback
**Purpose**: Help author improve

**Actions**:
- Leave specific comments
- Suggest improvements
- Ask questions
- Approve or request changes

## Usage
```bash
claude-code workflow workflows/code-review.md --pr-url <url>
```
```

### Bug Fix Workflow

**File**: `workflows/bug-fix.md`

```markdown
# Bug Fix Workflow

> Systematic approach to fixing bugs

## Overview
This workflow helps you fix bugs systematically.

## Steps

### Step 1: Reproduce Bug
**Purpose**: Confirm the bug exists

**Actions**:
- Write down steps to reproduce
- Note expected vs actual behavior
- Capture screenshots

### Step 2: Identify Root Cause
**Purpose**: Find what's causing the bug

**Actions**:
```bash
# Add debug logging
console.log('Debug: Variable =', variable);

# Run in debug mode
npm run debug

# Check error logs
tail -f logs/error.log
```

### Step 3: Write Failing Test
**Purpose**: Ensure bug is caught

**Actions**:
```bash
# Create test file
touch tests/bug-test.spec.js

# Write test that fails
# (shows the bug)
```

### Step 4: Implement Fix
**Purpose**: Fix the bug

**Actions**:
- Modify code
- Run test until it passes
- Don't break existing tests

### Step 5: Verify Fix
**Purpose**: Ensure bug is gone

**Actions**:
```bash
# Run all tests
npm test

# Test manually
# (follow reproduction steps)

# Check for regressions
npm run test:regression
```

## Usage
```bash
claude-code workflow workflows/bug-fix.md \
  --bug-description "Login fails on Firefox"
```
```

## Customizing Workflows

### Adding Parameters

Define parameters in your workflow:

```markdown
## Parameters

### --task-name (required)
Name of the task or feature

### --branch-type (optional)
Type: feature|bugfix|hotfix
Default: feature

### --with-tests (optional)
Include test files
Default: true

## Usage
```bash
claude-code workflow workflows/my-workflow.md \
  --task-name "Add auth" \
  --branch-type feature \
  --with-tests true
```
```

### Using Parameters

```markdown
### Step 1: Create Branch
**Actions**:
```bash
# Use parameter
git checkout -b ${BRANCH_TYPE}/${TASK_NAME}
```

**Expected Output**:
```
Switched to a new branch '${BRANCH_TYPE}/${TASK_NAME}'
```
```

### Conditional Steps

```markdown
### Step 2: Setup Tests
**Actions**:
```bash
if [ "${WITH_TESTS}" = "true" ]; then
  # Create test file
  touch tests/${TASK_NAME}.test.js
fi
```
```

## Best Practices

### 1. Be Specific

❌ Bad:
```markdown
## Steps
1. Do the thing
2. Test it
```

✅ Good:
```markdown
### Step 1: Run Tests
**Purpose**: Verify code works

**Actions**:
```bash
npm test
```

**Expected Output**:
```
PASS  src/app.test.js
  ✓ renders without crashing (5ms)
```
```

### 2. Provide Context

❌ Bad:
```markdown
Just run the workflow.
```

✅ Good:
```markdown
## When to Use
Use this workflow when:
- Adding a new feature
- Fixing a bug
- Refactoring code

## Prerequisites
- Node.js installed
- Tests passing on main
- No merge conflicts
```

### 3. Include Examples

❌ Bad:
```markdown
## Example
Run it with parameters.
```

✅ Good:
```markdown
## Example

**Scenario**: Adding user authentication

**Command**:
```bash
claude-code workflow workflows/feature.md \
  --name "user-auth" \
  --type "feature"
```

**What Happens**:
1. Creates branch: `feature/user-auth`
2. Generates files:
   - `src/auth/user.js`
   - `tests/auth/user.test.js`
3. Runs tests: ✓ PASS
4. Opens PR: #123

**Result**: Feature ready for development
```

## Sharing Workflows

### With Your Team

1. **Commit to repository**
   ```bash
   git add workflows/my-workflow.md
   git commit -m "Add my workflow"
   git push
   ```

2. **Update documentation**
   ```markdown
   # In README.md
   ## Available Workflows
   - [My Workflow](workflows/my-workflow.md) - Description
   ```

3. **Share in team chat**
   ```
   Hey team! I created a new workflow for X.
   Check it out: workflows/my-workflow.md
   ```

### Versioning Workflows

```markdown
# My Workflow

> Description

## Version: 1.2.0
## Last Updated: 2026-01-30

## Changelog
### 1.2.0 (2026-01-30)
- Added security scanning step
- Improved error handling

### 1.1.0 (2026-01-15)
- Added Docker support
- Updated examples
```

## Testing Workflows

### Manual Testing

```bash
# Dry run (see what would happen)
claude-code workflow workflows/my-workflow.md --dry-run

# Verbose mode (see detailed output)
claude-code workflow workflows/my-workflow.md --verbose

# Check mode (validate workflow)
claude-code workflow workflows/my-workflow.md --check
```

### Testing Checklist

- [ ] Workflow runs without errors
- [ ] All steps execute correctly
- [ ] Expected outputs match
- [ ] Parameters work as expected
- [ ] Error messages are helpful

## Troubleshooting

### Workflow Not Found

```
Error: Workflow not found
```

**Solution**:
```bash
# Check path is correct
ls workflows/my-workflow.md

# Use absolute path
claude-code workflow /full/path/to/workflows/my-workflow.md
```

### Parameter Issues

```
Error: Missing required parameter: --task-name
```

**Solution**:
```bash
# Provide required parameter
claude-code workflow workflows/my-workflow.md \
  --task-name "My Task"
```

### Step Failures

```
Error: Command failed at Step 3
```

**Solution**:
- Check the step's commands
- Verify prerequisites are met
- Run commands manually to debug
- Check error logs

## Next Steps

1. Create custom workflows for your team
2. Add workflow parameters
3. Integrate with CI/CD
4. Share with community
5. Monitor workflow usage

## Related Examples

- [Feature Development](../../workflows/development/feature.md)
- [Code Review](../../workflows/review/automated.md)
- [Testing](../../workflows/testing/tdd.md)

## Resources

- [Workflow Guide](../../docs/workflow-guide.md)
- [Best Practices](../../docs/best-practices.md)
- [Claude Code Docs](https://claude.ai/code)

## License

This example is part of Claude Code Workflows and is licensed under the MIT License.
