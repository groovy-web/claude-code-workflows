# Claude Code Workflow Guide

This comprehensive guide explains how to create, use, and share workflows with Claude Code.

## What are Claude Code Workflows?

Workflows are reusable, structured processes that guide Claude Code through common development tasks. They ensure consistency, save time, and encode best practices.

## Workflow Anatomy

### Basic Structure

```markdown
# Workflow Name

> Brief one-line description

## Overview
Detailed explanation of what the workflow does.

## Prerequisites
- Requirement 1
- Requirement 2

## Steps
1. **Step 1**
   - Action
   - Result

2. **Step 2**
   - Action
   - Result

## Usage
```bash
claude-code workflow path/to/workflow.md
```

## Example
Concrete example
```

### Complete Template

```markdown
# [Workflow Name]

> One-line description of the workflow

## Overview
Comprehensive description of:
- What the workflow accomplishes
- Why it's useful
- When to use it
- What makes it different

## When to Use
- [ ] Scenario 1
- [ ] Scenario 2
- [ ] Scenario 3

## Prerequisites
### Required
- [ ] Tool/Library 1 (version X.Y+)
- [ ] Tool/Library 2 (version X.Y+)
- [ ] Configuration file

### Optional
- [ ] Optional tool that enhances functionality
- [ ] Optional configuration

## Steps

### Step 1: [Clear Step Title]
**Purpose**: Why this step matters

**Actions**:
```bash
# Commands to run
command arg1 arg2
```

**Verification**:
```bash
# How to verify the step completed
command --check
```

**Expected Output**:
```
What you should see
```

**Troubleshooting**:
- **Problem**: Common issue
- **Solution**: How to fix it

### Step 2: [Clear Step Title]
... (repeat for all steps)

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

### With Environment Variables
```bash
export VAR=value
claude-code workflow workflows/category/workflow.md
```

## Examples

### Example 1: [Descriptive Title]
**Context**: When to use this example

**Input**:
```bash
claude-code workflow workflows/feature.md --name user-auth
```

**What Happens**:
1. Creates feature branch
2. Generates boilerplate
3. Sets up tests

**Result**:
```
Feature branch created: feature/user-auth
Generated files:
- src/auth/user.ts
- tests/auth/user.test.ts
- docs/auth/user.md
```

### Example 2: [Another Descriptive Title]
...

## Configuration

### Environment Variables
```bash
# Required
export REQUIRED_VAR=value

# Optional
export OPTIONAL_VAR=default_value
```

### Configuration Files
```yaml
# config/workflow-config.yml
setting1: value1
setting2: value2
```

## Troubleshooting

### Issue: [Common Problem]
**Symptoms**: What you see
**Cause**: Why it happens
**Solution**:
```bash
# Fix commands
```

### Issue: [Another Common Problem]
...

## Related Workflows
- [Related Workflow 1](path/to/workflow1.md) - Brief description
- [Related Workflow 2](path/to/workflow2.md) - Brief description

## Resources
- [Resource 1](url)
- [Resource 2](url)
- [Documentation](path/to/docs)
```

## Workflow Categories

### Development Workflows

**Location**: `workflows/development/`

Purpose: Guide development tasks from start to finish

**Examples**:
- `feature.md` - Feature development workflow
- `bugfix.md` - Bug fixing workflow
- `refactoring.md` - Code refactoring workflow
- `optimization.md` - Performance optimization workflow

### Review Workflows

**Location**: `workflows/review/`

Purpose: Ensure code quality and consistency

**Examples**:
- `automated.md` - Automated code review
- `manual.md` - Manual review checklist
- `security.md` - Security review process
- `performance.md` - Performance review

### Testing Workflows

**Location**: `workflows/testing/`

Purpose: Comprehensive testing strategies

**Examples**:
- `tdd.md` - Test-driven development
- `integration.md` - Integration testing
- `e2e.md` - End-to-end testing
- `performance.md` - Performance testing

### Deployment Workflows

**Location**: `workflows/deployment/`

Purpose: Safe and reliable deployment

**Examples**:
- `staging.md` - Deploy to staging
- `production.md` - Deploy to production
- `rollback.md` - Rollback deployment
- `monitoring.md` - Setup monitoring

## Creating Custom Workflows

### Step 1: Identify the Need

What repetitive task do you perform often?

**Examples**:
- "Every time I create a feature, I do X, Y, Z"
- "I always forget to update documentation"
- "Code reviews take too long"

### Step 2: Document the Process

Write down each step you perform:

```markdown
1. Create branch
2. Update dependencies
3. Generate code
4. Write tests
5. Update docs
6. Create PR
```

### Step 3: Add Details

For each step, add:
- Commands to run
- Files to create
- Verification steps
- Troubleshooting

### Step 4: Test the Workflow

Run through it yourself:

```bash
claude-code workflow workflows/my-new-workflow.md
```

### Step 5: Refine

Improve based on testing:
- Add missing steps
- Clarify instructions
- Add examples
- Fix issues

## Best Practices

### 1. Be Specific

❌ Bad:
```markdown
## Steps
1. Create the files
2. Test it
```

✅ Good:
```markdown
### Step 1: Create Component Files
**Actions**:
```bash
# Create component directory
mkdir src/components/${FEATURE_NAME}

# Create component file
cat > src/components/${FEATURE_NAME}/index.tsx << 'EOF'
// Component template
EOF
```

**Expected Output**:
```
Created: src/components/${FEATURE_NAME}/index.tsx
Created: src/components/${FEATURE_NAME}/styles.css
```
```

### 2. Provide Context

❌ Bad:
```markdown
## Usage
claude-code workflow feature.md
```

✅ Good:
```markdown
## Usage

### Basic Usage
Use this workflow when starting a new feature:

```bash
claude-code workflow workflows/development/feature.md \
  --name "user-authentication"
```

### With Options
Specify additional parameters:

```bash
claude-code workflow workflows/development/feature.md \
  --name "user-authentication" \
  --type "feature" \
  --with-tests
```
```

### 3. Include Examples

❌ Bad:
```markdown
## Examples
Run the workflow to create a feature.
```

✅ Good:
```markdown
## Examples

### Example 1: Creating a Simple Feature
**Context**: Adding a new user profile feature

**Command**:
```bash
claude-code workflow workflows/development/feature.md \
  --name "user-profile" \
  --type "feature"
```

**What Happens**:
1. Creates branch: `feature/user-profile`
2. Generates files:
   ```
   src/features/user-profile/
   ├── index.ts
   ├── UserProfile.tsx
   ├── styles.css
   └── __tests__/
       └── UserProfile.test.tsx
   ```
3. Updates router configuration
4. Creates documentation stub

**Result**: Feature ready for development
```

### 4. Handle Errors

❌ Bad:
```markdown
## Steps
1. Run npm install
2. Run npm test
```

✅ Good:
```markdown
### Step 1: Install Dependencies
**Actions**:
```bash
npm install
```

**Troubleshooting**:

**Problem**: `npm install` fails with peer dependency errors
**Solution**:
```bash
# Use legacy peer deps
npm install --legacy-peer-deps

# Or use force
npm install --force
```

**Problem**: Permission errors
**Solution**:
```bash
# Fix npm permissions
sudo chown -R $(whoami) ~/.npm
```
```

## Workflow Parameters

### Defining Parameters

Workflows can accept parameters:

```markdown
## Parameters

### --name (required)
Feature or project name

### --type (optional)
Type: feature|bugfix|refactor
Default: feature

### --with-tests (optional)
Include test files
Default: true

## Usage
```bash
claude-code workflow workflows/feature.md \
  --name "my-feature" \
  --type "feature" \
  --with-tests
```
```

### Using Parameters in Steps

```markdown
### Step 1: Create Branch
**Actions**:
```bash
# Create feature branch
git checkout -b ${TYPE}/${NAME}
```

**Expected Output**:
```
Switched to a new branch '${TYPE}/${NAME}'
```
```

## Variable Expansion

### Environment Variables

```markdown
### Step 1: Use Environment Variable
**Actions**:
```bash
# Use environment variable
echo "Project: ${PROJECT_NAME}"
echo "Author: ${GIT_AUTHOR_NAME}"
```
```

### Dynamic Values

```markdown
### Step 2: Generate Timestamp
**Actions**:
```bash
# Generate timestamp
TIMESTAMP=$(date +%Y%m%d-%H%M%S)
echo "Created at: ${TIMESTAMP}"
```
```

## Conditional Logic

### If/Else in Workflows

```markdown
### Step 3: Configure Based on Type
**Actions**:
```bash
if [ "${TYPE}" = "feature" ]; then
  # Feature-specific setup
  echo "Setting up feature..."
elif [ "${TYPE}" = "bugfix" ]; then
  # Bugfix-specific setup
  echo "Setting up bugfix..."
fi
```
```

## Workflow Composition

### Reusable Components

Create reusable workflow snippets:

```markdown
<!-- workflows/snippets/create-branch.md -->
### Create Branch
**Actions**:
```bash
git checkout -b ${TYPE}/${NAME}
```
```

Then include in main workflows:

```markdown
## Steps

<snippet workflows/snippets/create-branch.md>

<snippet workflows/snippets/run-tests.md>
```

## Versioning Workflows

### Semantic Versioning

```markdown
# Workflow Name

> Description

## Version: 1.2.0
## Last Updated: 2026-01-30

## Changelog
### 1.2.0 (2026-01-30)
- Added new step for security scanning
- Improved error handling

### 1.1.0 (2026-01-15)
- Added support for TypeScript
- Updated examples
```

## Testing Workflows

### Manual Testing Checklist

- [ ] Workflow completes without errors
- [ ] All files are created correctly
- [ ] Generated code is valid
- [ ] Documentation is accurate
- [ ] Examples work as described

### Automated Testing

```bash
# Test workflow
claude-code workflow workflows/test.md --dry-run

# Validate workflow
claude-code workflow workflows/test.md --validate
```

## Sharing Workflows

### With Your Team

1. **Add to repository**
   ```bash
   git add workflows/my-workflow.md
   git commit -m "Add my workflow"
   git push
   ```

2. **Update documentation**
   ```markdown
   # Add to docs/workflows.md
   - [My Workflow](workflows/my-workflow.md) - Description
   ```

3. **Announce to team**
   - Slack message with workflow description
   - Demo at team meeting
   - Add to team documentation

### Publishing Publicly

1. **Ensure workflow is generic**
   - Remove company-specific details
   - Use placeholder values
   - Add comprehensive documentation

2. **Add license**
   ```markdown
   ## License
   This workflow is licensed under the MIT License
   ```

3. **Share in community**
   - Post on GitHub Discussions
   - Share on social media
   - Submit to workflow directories

## Advanced Techniques

### Parallel Steps

```markdown
## Steps

### Step 1: Run in Parallel
**Actions**:
```bash
# Run multiple commands in parallel
npm run lint &
npm run type-check &
npm run test &
wait  # Wait for all to complete
```
```

### Loops

```markdown
### Step 2: Process Multiple Files
**Actions**:
```bash
# Loop through files
for file in src/**/*.ts; do
  echo "Processing $file"
  # Process file
done
```
```

### Error Handling

```markdown
### Step 3: Handle Errors Gracefully
**Actions**:
```bash
# Run with error handling
if ! npm run build; then
  echo "Build failed, cleaning up..."
  npm run clean
  exit 1
fi
```
```

## Workflow Templates

### Minimal Template

```markdown
# [Workflow Name]

> Description

## Overview
What this workflow does

## Prerequisites
- Requirement 1
- Requirement 2

## Steps
1. **Step 1**
   - Action
   - Result

## Usage
```bash
claude-code workflow path/to/workflow.md
```
```

### Comprehensive Template

See "Complete Template" section above for full template.

## Resources

- [Claude Code Documentation](https://claude.ai/code)
- [Example Workflows](../examples/)
- [Workflow Templates](../templates/)
- [Community Workflows](https://github.com/claude-code-workflows/community)
