# Context Window Loading Protocol v1.0.0

**Created**: August 20, 2025  
**Type**: Foundation Protocol (Tier 2)  
**Status**: Active  

## Purpose
Ensure that content claimed to be "loaded" by tools actually gets into Claude's context window through explicit file operations.

## Problem Statement
Tools frequently report "loaded 25 memories" or similar, but this content is not actually accessible in Claude's context window unless explicitly read through filesystem operations.

## The Fundamental Rule
**To get content into Claude's context window: Write to file → Read file → Delete file**

## Protocol Steps

### 1. Content Generation
Tool writes content to temporary file:
```javascript
const tempFile = `/tmp/context_${sessionId}.txt`;
fs.writeFileSync(tempFile, contentToLoad);
```

### 2. File Path Return
Tool returns file path in response:
```javascript
return {
  // ... other response data
  contextFilePath: tempFile
};
```

### 3. Explicit Reading
Claude reads file using filesystem tools:
```
filesystem:read_text_file(tempFile)
```

### 4. Cleanup
Claude deletes temporary file:
```
filesystem:move_file(tempFile, '/dev/null')
```

## Trigger Conditions
- Any tool claims to "load" content for context
- Need to verify what's actually in context window
- Tools report loading memories, protocols, or other content
- Context window verification required

## Success Criteria
- ✅ Content is directly visible in Claude's context without additional tools
- ✅ Can quote/reference loaded content immediately
- ✅ No discrepancy between "loaded" claims and accessible content

## Common Violations
- ❌ Tools reporting "loaded" without file operations
- ❌ Claude claiming to have content without being able to quote it
- ❌ Using brain_recall to access "loaded" memories
- ❌ Accepting loading claims without verification

## Implementation Notes
- Temporary files should use unique identifiers (timestamps, session IDs)
- Cleanup is essential to avoid file system clutter
- File paths must be in allowed directories for Claude

## Related Protocols
- [[Context Window Extraction Protocol v1.0.0]] - Verify what's in context
- [[Tool Modification Protocol v1.0.0]] - Handle tool changes
- [[Brain Initialization Protocol v5.2.0]] - Enhanced context loading

---
*Part of Foundation Protocol tier - essential for reliable context management*