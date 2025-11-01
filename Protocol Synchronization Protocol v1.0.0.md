# Protocol Synchronization Protocol v1.0.0

## Purpose
Systematic procedure for keeping protocol files synchronized between Obsidian vault and GitHub repository to maintain a single source of truth across all systems.

## Trigger Conditions
- New protocol created or modified in Obsidian
- User requests protocol sync/backup
- Before major protocol updates
- Weekly maintenance routine
- When creating or editing any protocol

## Prerequisites Check
Before starting, verify:
- [ ] Obsidian protocols directory exists: `/Users/bard/Documents/Obsidian/Protocols/`
- [ ] GitHub protocols repository exists: `/Users/bard/Code/protocols`
- [ ] Git repository is properly configured with remote
- [ ] No uncommitted changes in protocols repo (or commit them first)

## Step-by-Step Procedure

### Phase 1: Compare and Identify Changes

1. **Compare Protocol Collections**
   ```python
   # Use brain:brain_execute to compare directories
   import os
   obsidian_protocols = "/Users/bard/Documents/Obsidian/Protocols"
   repo_protocols = "/Users/bard/Code/protocols"
   
   obsidian_files = set(f for f in os.listdir(obsidian_protocols) if f.endswith('.md'))
   repo_files = set(f for f in os.listdir(repo_protocols) if f.endswith('.md') and f != 'README.md')
   
   missing_from_repo = obsidian_files - repo_files
   extra_in_repo = repo_files - obsidian_files
   common_files = obsidian_files & repo_files
   
   print(f"Missing from repo: {len(missing_from_repo)}")
   print(f"Extra in repo: {len(extra_in_repo)}")
   print(f"Common files: {len(common_files)}")
   ```

2. **Check File Timestamps**
   ```python
   # Check which files are newer in Obsidian
   import os
   for file in common_files:
       obs_path = os.path.join(obsidian_protocols, file)
       repo_path = os.path.join(repo_protocols, file)
       
       obs_time = os.path.getmtime(obs_path)
       repo_time = os.path.getmtime(repo_path)
       
       if obs_time > repo_time:
           print(f"Obsidian newer: {file}")
   ```

### Phase 2: Copy Updated Files

1. **Copy New/Updated Protocols**
   ```python
   # Use brain:brain_execute for file operations
   import shutil
   
   # Copy missing files
   for file in missing_from_repo:
       src = os.path.join(obsidian_protocols, file)
       dst = os.path.join(repo_protocols, file)
       shutil.copy2(src, dst)
       print(f"Copied new: {file}")
   
   # Copy updated files (based on timestamp)
   for file in common_files:
       obs_path = os.path.join(obsidian_protocols, file)
       repo_path = os.path.join(repo_protocols, file)
       
       if os.path.getmtime(obs_path) > os.path.getmtime(repo_path):
           shutil.copy2(obs_path, repo_path)
           print(f"Updated: {file}")
   ```

2. **Organize by Tiers (if needed)**
   ```python
   # Ensure proper tier organization
   tier_mapping = {
       "Common Sense Protocol": "tier-0-meta",
       "Protocol Creation Protocol": "tier-0-meta",
       "Systematic Intelligence Cultivation Protocol": "tier-0-meta",
       
       "Brain Initialization Protocol": "tier-1-system",
       "Write-Read Verification Protocol": "tier-1-system",
       "Context Window Management Protocol": "tier-1-system",
       "Architecture First Protocol": "tier-1-system",
       "Internal Documentation Protocol": "tier-1-system",
       "Storage System Boundaries Protocol": "tier-1-system",
       "Continuation Note Management Protocol": "tier-1-system",
       "Repository Update Protocol": "tier-1-system",
       
       "Error Recovery Protocol": "tier-2-foundation",
       "User Communication Protocol": "tier-2-foundation",
       "Task Approach Protocol": "tier-2-foundation",
       "Information Integration Protocol": "tier-2-foundation",
       "Progress Communication Protocol": "tier-2-foundation",
       
       "Implementation First Protocol": "tier-3-workflow",
       "Git Repository Creation Protocol": "tier-3-workflow",
       "Text Replacement Automation Protocol": "tier-3-workflow"
   }
   
   # Copy to appropriate tier directories
   for protocol_prefix, tier_dir in tier_mapping.items():
       for file in os.listdir(repo_protocols):
           if file.startswith(protocol_prefix) and file.endswith('.md'):
               tier_path = os.path.join(repo_protocols, tier_dir)
               os.makedirs(tier_path, exist_ok=True)
               src = os.path.join(repo_protocols, file)
               dst = os.path.join(tier_path, file)
               if not os.path.exists(dst):
                   shutil.copy2(src, dst)
   ```

### Phase 3: Update Master Index

1. **Sync Master Protocol Index**
   ```python
   # Always copy the Master Protocol Index as it's the authoritative source
   master_index_src = os.path.join(obsidian_protocols, "Master Protocol Index.md")
   master_index_dst = os.path.join(repo_protocols, "Master Protocol Index.md")
   
   if os.path.exists(master_index_src):
       shutil.copy2(master_index_src, master_index_dst)
       print("Updated Master Protocol Index")
   ```

### Phase 4: Git Operations

1. **Check Git Status**
   ```
   Tool: git:git_status
   Parameters:
     - path: /Users/bard/Code/protocols
   ```

2. **Add Changes**
   ```
   Tool: git:git_add
   Parameters:
     - files: ["."]
     - path: /Users/bard/Code/protocols
   ```

3. **Commit Changes**
   ```
   Tool: git:git_commit
   Parameters:
     - message: "Sync protocols from Obsidian vault\n\n- Updated: [list files]\n- Added: [list files]\n- Synced at: [timestamp]"
     - path: /Users/bard/Code/protocols
   ```

4. **Push to GitHub**
   ```
   Tool: git:git_push
   Parameters:
     - path: /Users/bard/Code/protocols
   ```

### Phase 5: Verification

1. **Verify File Counts Match**
   ```python
   # Final verification
   final_obsidian = len([f for f in os.listdir(obsidian_protocols) if f.endswith('.md')])
   final_repo = len([f for f in os.listdir(repo_protocols) if f.endswith('.md') and f != 'README.md'])
   
   print(f"Obsidian protocols: {final_obsidian}")
   print(f"Repo protocols: {final_repo}")
   print(f"Match: {final_obsidian == final_repo}")
   ```

2. **Check GitHub Repository**
   - Visit https://github.com/MikeyBeez/protocols
   - Verify files are visible and up to date
   - Check commit history shows sync

## Automation Scripts

### Quick Sync Command
```python
# brain:brain_execute - Quick protocol sync
import os, shutil, subprocess

def sync_protocols():
    obsidian_dir = "/Users/bard/Documents/Obsidian/Protocols"
    repo_dir = "/Users/bard/Code/protocols"
    
    # Copy all .md files except README
    for file in os.listdir(obsidian_dir):
        if file.endswith('.md'):
            src = os.path.join(obsidian_dir, file)
            dst = os.path.join(repo_dir, file)
            shutil.copy2(src, dst)
    
    # Git operations
    os.chdir(repo_dir)
    subprocess.run(["git", "add", "."])
    subprocess.run(["git", "commit", "-m", f"Auto-sync protocols from Obsidian"])
    subprocess.run(["git", "push"])
    
    print("Protocol sync complete!")

sync_protocols()
```

## Scheduled Maintenance

### Weekly Sync (Recommended)
- Run full sync procedure
- Review any conflicts or issues
- Update README if structure changes
- Verify GitHub repository accessibility

### After Protocol Changes
- Immediate sync after creating/editing protocols
- Include change description in commit message
- Tag major protocol updates

## Error Recovery

### "Files out of sync"
1. Compare timestamps manually
2. Use `git diff` to see specific changes
3. Choose source of truth (usually Obsidian for content)
4. Re-run sync procedure

### "Git conflicts"
1. Check for uncommitted changes: `git status`
2. Commit or stash changes first
3. Pull latest from GitHub: `git pull`
4. Resolve conflicts manually
5. Re-run sync

### "Permission denied"
1. Check GitHub SSH keys: `ssh -T git@github.com`
2. Verify repository permissions
3. Use HTTPS if SSH fails

### "Missing files"
1. Verify Obsidian vault location
2. Check if files were moved/renamed
3. Manual copy if automated sync fails

## Quality Checks

Before considering sync complete:
- [ ] All protocol .md files copied from Obsidian to repo
- [ ] Master Protocol Index is up to date
- [ ] No uncommitted changes in git
- [ ] Latest commit pushed to GitHub
- [ ] GitHub repository shows current content
- [ ] File counts match between Obsidian and repo
- [ ] No permission or access errors

## Success Indicators
- ✅ All protocols synchronized
- ✅ Git repository clean
- ✅ GitHub shows latest commit
- ✅ File counts match
- ✅ No sync errors reported

## Related Protocols
- Git Repository Creation Protocol (for initial setup)
- Repository Update Protocol (for ongoing maintenance)
- Internal Documentation Protocol (for documentation sync)

## Notes
- Always treat Obsidian vault as source of truth for protocol content
- GitHub repo serves as backup and public access point
- Tier organization helps categorize protocols but all should be in root too
- Include meaningful commit messages describing what changed
- Consider branch protection for master to prevent accidental overwrites

---
**Status**: Active - v1.0.0
**Created**: 2025-11-01
**Last Updated**: 2025-11-01
