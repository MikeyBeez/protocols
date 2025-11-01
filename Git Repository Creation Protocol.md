# Git Repository Creation Protocol v1.0.0

## Purpose
Systematic procedure for creating, initializing, and publishing new Git repositories with proper setup and GitHub integration.

## Trigger Conditions
- User requests creation of new project/repository
- User says "create a GitHub project/repo"
- User asks to "set up version control" for code
- Starting a new research/development project that needs tracking
- Need to share code/project publicly or with collaborators

## Prerequisites Check
Before starting, verify:
- [ ] Project has a clear name (kebab-case preferred)
- [ ] Project has a description/purpose
- [ ] License type determined (MIT, Apache, GPL, etc.)
- [ ] Target location for local repository (`/Users/bard/Code/` typically)

## Step-by-Step Procedure

### Phase 1: Local Directory Setup

1. **Create Project Structure**
   ```python
   # Use brain:brain_execute to create directories
   import os
   project_path = "/Users/bard/Code/PROJECT_NAME"
   os.makedirs(project_path, exist_ok=True)
   # Create subdirectories as needed
   ```

2. **Initialize Git Repository**
   ```
   Tool: git:git_init
   Parameters:
     - path: /Users/bard/Code/PROJECT_NAME
   ```

### Phase 2: Essential Files Creation

Use `filesystem-enhanced:write_file` for each:

1. **README.md**
   - Project title and description
   - Key features/goals
   - Installation instructions
   - Usage examples
   - License and contact info
   
2. **.gitignore**
   - Language-specific patterns (Python, Node.js, etc.)
   - IDE files (.vscode, .idea, .DS_Store)
   - Build artifacts (dist/, build/, __pycache__/)
   - Secrets and env files (.env, *.key)
   - Large data files
   
3. **LICENSE**
   - Full license text (MIT, Apache 2.0, etc.)
   - Copyright year and name

4. **Additional files as needed**
   - requirements.txt or package.json
   - .env.example
   - CONTRIBUTING.md
   - docs/ structure

### Phase 3: Initial Commit

1. **Stage All Files**
   ```
   Tool: git:git_add
   Parameters:
     - files: ["."]
     - path: /Users/bard/Code/PROJECT_NAME
   ```

2. **Create Initial Commit**
   ```
   Tool: git:git_commit
   Parameters:
     - message: "Initial commit: PROJECT_NAME\n\n[Brief description]"
     - path: /Users/bard/Code/PROJECT_NAME
   ```

3. **Rename Branch to 'main'**
   ```python
   # Use brain:brain_execute
   import subprocess, os
   os.chdir("/Users/bard/Code/PROJECT_NAME")
   subprocess.run(["git", "branch", "-M", "main"], check=True)
   ```

### Phase 4: GitHub Repository Creation

**Option A: Using GitHub CLI (gh) - Preferred**
```python
# Use brain:brain_execute
result = subprocess.run([
    "gh", "repo", "create", "PROJECT_NAME",
    "--public",  # or "--private"
    "--source=.",
    "--remote=origin",
    "--description=PROJECT DESCRIPTION",
    "--push"
], capture_output=True, text=True)
```

**Option B: Manual (if gh not available)**
1. Check for gh CLI availability
2. If not available, provide manual instructions:
   - Go to https://github.com/new
   - Name: PROJECT_NAME
   - Description: [provided]
   - Public/Private: [specified]
   - Don't initialize (we have files)
   - Then: `git remote add origin git@github.com:USERNAME/PROJECT_NAME.git`
   - And: `git push -u origin main`

### Phase 5: Verification

1. **Check Git Status**
   ```
   Tool: git:git_status
   Parameters:
     - path: /Users/bard/Code/PROJECT_NAME
   ```

2. **Verify Remote**
   ```python
   # Use brain:brain_execute
   subprocess.run(["git", "remote", "-v"], check=True)
   ```

3. **Confirm Push**
   - Check that GitHub URL is accessible
   - Verify files are visible on GitHub

## Common Patterns

### Python Project Structure
```
project-name/
├── README.md
├── LICENSE
├── .gitignore
├── requirements.txt
├── setup.py (optional)
├── src/
│   └── project_name/
│       └── __init__.py
├── tests/
├── docs/
└── examples/
```

### Node.js Project Structure
```
project-name/
├── README.md
├── LICENSE
├── .gitignore
├── package.json
├── src/
├── test/
├── docs/
└── examples/
```

### Research Project Structure
```
project-name/
├── README.md
├── LICENSE
├── .gitignore
├── experiments/
├── results/
├── models/
├── notebooks/
├── data/
└── scripts/
```

## .gitignore Templates

### Python
```
__pycache__/
*.py[cod]
*.so
.Python
*.egg-info/
dist/
build/
venv/
.venv
*.log
.DS_Store
```

### Node.js
```
node_modules/
dist/
build/
*.log
.DS_Store
.env
package-lock.json (sometimes)
```

### Research/ML
```
*.pt
*.pth
*.ckpt
data/
logs/
wandb/
.ipynb_checkpoints/
*.log
```

## Error Recovery

### "Repository already exists"
1. Check if local .git exists: `ls -la PROJECT_NAME/.git`
2. If yes, check remote: `git remote -v`
3. Either remove and recreate, or work with existing

### "gh not found"
1. Fall back to manual GitHub creation
2. Provide clear instructions
3. Test with `which gh` first

### "Permission denied"
1. Check SSH keys: `ssh -T git@github.com`
2. If needed, guide through SSH key setup
3. Alternative: use HTTPS with token

### "Nothing to commit"
1. Verify files exist: `ls -la PROJECT_NAME/`
2. Check .gitignore isn't excluding everything
3. Use `git add -f` if necessary

## Quality Checks

Before considering complete:
- [ ] README is informative and well-formatted
- [ ] LICENSE file is present and appropriate
- [ ] .gitignore covers relevant patterns
- [ ] Initial commit is pushed to GitHub
- [ ] Repository URL is accessible
- [ ] Branch is named 'main' (not 'master')
- [ ] Remote is named 'origin'

## Success Indicators
- ✅ Local repository initialized
- ✅ Essential files created
- ✅ Initial commit made
- ✅ GitHub repository created
- ✅ Code pushed successfully
- ✅ Repository accessible at GitHub URL

## Related Protocols
- Development Workflow Protocol (for ongoing work)
- Code Review Protocol (before committing)
- Documentation Protocol (for README/docs)

## Notes
- Always use `filesystem-enhanced:write_file` (not `create_file`)
- Always use git MCP tools (not bash commands when possible)
- Check for gh CLI before attempting GitHub creation
- Prefer descriptive commit messages
- Use semantic versioning for releases

---
**Status**: Active - v1.0.0
**Created**: 2025-11-01
**Last Updated**: 2025-11-01
