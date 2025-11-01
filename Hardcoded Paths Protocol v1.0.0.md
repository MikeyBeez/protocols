# Hardcoded Paths Protocol v1.0.0

**Created**: August 20, 2025  
**Type**: Foundation Protocol (Tier 2)  
**Status**: Active  

## Purpose
Essential file paths should be immediately available in Claude's context without requiring search operations.

## The Problem
Claude frequently searches for critical system files that should be instantly accessible, leading to inefficiency and context waste.

## The Fundamental Rule
**Critical system paths must be immediately available in smarts - no search operations allowed.**

## Two-Tier Path System

### Tier 1: Immediate Access (In Smarts)
**Most frequently used paths - must be in brain_init_v5_working context:**
```
/Users/bard/Code/claude-brain/brain_init_v5_working.js  # THE smarts definition file
/Users/bard/Code/claude-brain/index.js                 # Main brain server
/Users/bard/Code/claude-brain/config.js                # Configuration  
/Users/bard/Code/Claude_Data/brain/brain.db            # Brain database
/Users/bard/Documents/Obsidian/                        # Main vault location
/Users/bard/Documents/Obsidian/Protocols/Master Protocol Index.md
/Users/bard/Code/                                      # Projects root
```

### Tier 2: Quick Lookup (In This Protocol Document)
**All other important paths - reference this protocol when needed:**

#### Active Projects
```
/Users/bard/Code/fifth-reboot/                        # Current active project
/Users/bard/Code/mcp-brain-manager/                   # Brain management
/Users/bard/Code/mcp-architecture/                    # Architecture docs
/Users/bard/Code/mcp-filesystem-enhanced/             # Enhanced filesystem
/Users/bard/Code/mcp-protocol-tracker/                # Protocol tracking
/Users/bard/Code/mcp-continuation-notes/              # Continuation system
/Users/bard/Code/mcp-smart-help/                      # Smart help system
/Users/bard/Code/ollama/                              # Ollama experiments
/Users/bard/Code/frontiermath/                        # Math problem solving
/Users/bard/Code/mcp-registry-interface/              # MCP registry
/Users/bard/Code/mcp-github-research/                 # GitHub research tools
```

#### Continuation Notes Specific Files
```
/Users/bard/Code/mcp-continuation-notes/src/index.js  # Main continuation tool implementation
/Users/bard/Code/claude-brain/data/continuation-note-latest.md  # Handoff location
```

#### System Directories
```
/Users/bard/Documents/Obsidian/Protocols/             # Protocol storage
/Users/bard/Code/claude-brain/protocols/              # Protocol development
/Users/bard/Code/Claude_Data/                         # All Claude data
/Users/bard/Code/Claude_Data/logs/                    # System logs
/Users/bard/Code/Claude_Data/brain/                   # Brain data files
```

#### Configuration Files
```
/Users/bard/Code/claude-brain/package.json            # Brain dependencies
/Users/bard/Code/claude-brain/brain_init_v5_working.js.bak  # Backup
/Users/bard/Code/claude-brain/brain_init_v5_working_tool.js # Tool wrapper
```

## Protocol Steps

### 1. Immediate Access
- Tier 1 paths must be in immediate context during brain initialization
- No search operations allowed for Tier 1 paths
- Reference directly when needed for modifications or access

### 2. Quick Lookup
- For Tier 2 paths, reference this protocol document
- Read this protocol when needing less-common paths
- No searching allowed - use protocol lookup instead

### 3. Context Loading
- Include all critical paths in brain_init_v5_working smarts
- Make them available even after context clears
- Cache frequently accessed paths during sessions

### 3. Path Updates
- Update this list when new critical paths are established
- Maintain current list in smarts and protocols
- Ensure new team members have access to path list

### 4. Path Discovery and Protocol Updates
When discovering new important paths during work:
- **Evaluate importance**: Is this path frequently accessed or critical to operations?
- **Update protocol**: Add new paths to Tier 2 (Quick Lookup) section of this protocol
- **Consider promotion**: If used frequently, consider moving to Tier 1 (smarts)
- **Document immediately**: Don't wait - update this protocol as soon as important path is discovered

#### When to Add Paths
- ✅ New project directories that will be worked on regularly
- ✅ Tool configuration files discovered during debugging
- ✅ Important system directories found during troubleshooting
- ✅ Any path that required a search operation to find
- ❌ One-off temporary files or user documents
- ❌ Standard system paths that are universally known

#### How to Add Paths
1. Read this protocol file
2. Add path to appropriate Tier 2 section with descriptive comment
3. Save the updated protocol
4. Consider adding to brain memory for immediate access

### 5. Usage Pattern
When needing a critical file:
```
# Good - Direct reference
filesystem:read_text_file(/Users/bard/Code/claude-brain/brain_init_v5_working.js)

# Bad - Search operation
filesystem:search_files(/Users/bard/Code, "brain_init_v5_working")
```

## Trigger Conditions
- Need to access brain system files
- Modifying core tools or configurations
- Reading Obsidian protocols or documentation
- Working with active projects
- Any reference to "find the file" for critical paths

## Success Criteria
- ✅ Instant access to all critical system paths
- ✅ No search operations for core infrastructure
- ✅ Paths available even after context clears
- ✅ Direct file access without "where is..." questions

## Common Violations
- ❌ Using search_files for critical paths listed above
- ❌ Asking "where is the brain_init_v5_working.js file?"
- ❌ Not knowing Obsidian vault location immediately
- ❌ Searching for project directories that should be known
- ❌ Using locate/find for hardcoded system paths

## Implementation Notes
- These paths should be included in brain_init_v5_working smarts
- Update user preferences to include critical paths
- Consider creating a paths configuration file
- Ensure paths are validated during initialization

## Path Categories

### Never Search (Always Hardcoded)
- Brain system files
- Obsidian vault location
- Core project directories
- Main configuration files

### Search Allowed
- User documents within projects
- Temporary files
- New files created during sessions
- Project-specific assets

## Related Protocols
- [[Brain Initialization Protocol v5.2.0]] - Should load these paths
- [[Context Window Loading Protocol v1.0.0]] - Requires known file locations
- [[Tool Modification Protocol v1.0.0]] - Needs tool file locations

---
*Part of Foundation Protocol tier - essential for efficient system operation*