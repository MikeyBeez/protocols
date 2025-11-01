# Context Window Extraction Protocol v1.0.0

**Created**: August 20, 2025  
**Type**: Foundation Protocol (Tier 2)  
**Status**: Active  

## Purpose
Verify what content is actually in Claude's context window versus what tools claim to have loaded.

## The Fundamental Rule
**If it's truly in your context window, you should see it directly without using any tools.**

## Core Principle
Context window contents should be immediately accessible without tool usage. If you need a tool to access it, it's not actually in your context.

## Protocol Steps

### 1. Direct Reference Test
When claiming to have content in context:
- Quote specific details directly
- Reference exact content without tools
- Cite particular sections or data points

### 2. Tool-Free Verification
Never use tools to "check" context contents:
- ❌ Don't use `brain_recall` for "loaded" memories
- ❌ Don't use `filesystem:read_file` to verify context
- ❌ Don't use any search tools for supposedly loaded content

### 3. Honest Gap Acknowledgment
If you cannot directly reference content:
- Admit it's not actually in context
- Distinguish between "claimed loaded" and "actually accessible"
- Request proper loading using [[Context Window Loading Protocol v1.0.0]]

### 4. Verification Questions
Ask yourself:
- Can I quote this content without tools?
- Can I reference specific details immediately?
- Would I know this content if the tool hadn't claimed to load it?

## Trigger Conditions
- Any claim about loaded content (memories, protocols, data)
- Tools report successful loading operations
- Need to verify context window contents
- User asks about supposedly loaded information

## Success Criteria
- ✅ Can directly quote/reference any truly loaded content
- ✅ Honest about accessibility gaps
- ✅ Clear distinction between claimed vs actual loading
- ✅ No tool usage for context verification

## Common Violations
- ❌ Using brain_recall to find "loaded" memories
- ❌ Claiming to have protocol content when only seeing metadata
- ❌ Reporting successful loading without ability to cite content
- ❌ Tool usage to verify supposedly accessible information

## Implementation Examples

### Good Practice
```
I can see the first 3 memories in my context:
1. user_preferences_session_start - Shows initialization workflow
2. brain_init_v5_working_final_specification - Version 5.0 details
3. vault_path_fix_complete_20250819 - Fixed Obsidian location
```

### Bad Practice
```
Let me check what memories were loaded...
[Uses brain_recall to find supposedly loaded content]
```

## Related Protocols
- [[Context Window Loading Protocol v1.0.0]] - Proper loading method
- [[Tool Modification Protocol v1.0.0]] - Handle restart requirements
- [[Brain Initialization Protocol v5.2.0]] - Enhanced initialization

---
*Part of Foundation Protocol tier - critical for honest context management*