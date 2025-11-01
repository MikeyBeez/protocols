# Tool Modification Protocol v1.0.0

**Created**: August 20, 2025  
**Type**: Foundation Protocol (Tier 2)  
**Status**: Active  

## Purpose
Handle the reality that Claude cannot restart tools/applications after modifying them.

## The Reality
- When Claude modifies an MCP tool, Claude Desktop must be restarted
- Claude cannot perform this restart operation
- Claude often forgets this limitation and attempts testing anyway

## The Fundamental Rule
**Modify → Ask User to Restart → Wait for Confirmation**

## Protocol Steps

### 1. Make the Modification
Complete the requested code changes:
- Edit the tool files as requested
- Ensure changes are saved properly
- Document what was changed

### 2. Immediate Restart Request
Immediately after modification, state clearly:
```
I've modified [tool name]. Please restart Claude Desktop to pick up the changes.
```

### 3. No Premature Testing
Do not attempt to:
- ❌ Test the modified tool
- ❌ Use system commands to restart services
- ❌ Call the tool to verify changes
- ❌ Claim changes are active immediately

### 4. Wait for Restart Confirmation
- Do not proceed with testing until user confirms restart
- Be patient about restart dependency
- Acknowledge that changes are not active until restart

## Trigger Conditions
- Any modification to MCP tool code
- Changes to brain_init_v5_working.js or other tool implementations
- Updates to tool configuration or behavior
- User requests tool improvements or fixes

## Success Criteria
- ✅ Clear communication about restart requirement
- ✅ No premature testing of modified tools
- ✅ Honest acknowledgment of restart dependency
- ✅ User successfully restarts and confirms

## Common Violations
- ❌ Testing modified tools immediately after changes
- ❌ Using system commands to try restarting services
- ❌ Claiming tool modifications are active without restart
- ❌ Forgetting to mention restart requirement
- ❌ Attempting to verify changes before restart

## Tool-Specific Notes

### brain_init_v5_working.js
- Located at `/Users/bard/Code/claude-brain/brain_init_v5_working.js`
- Requires Claude Desktop restart for changes to take effect
- Cannot be restarted via system commands from Claude

### Other MCP Tools
- All MCP tools require application restart
- Claude has no mechanism to restart Claude Desktop
- System service restarts don't affect Claude Desktop integration

## Implementation Example

### Good Practice
```
I've modified the loadLatestMemories() method in brain_init_v5_working.js 
to write memories to a temporary file. Please restart Claude Desktop to 
pick up the changes, then we can test the improved memory loading.
```

### Bad Practice
```
Let me test the modified brain_init_v5_working tool...
[Attempts to use tool immediately after modification]
```

## Related Protocols
- [[Context Window Loading Protocol v1.0.0]] - Often requires tool modifications
- [[Hardcoded Paths Protocol v1.0.0]] - Know tool locations without search
- [[Brain Initialization Protocol v5.2.0]] - Major tool that requires this protocol

---
*Part of Foundation Protocol tier - essential for tool development workflow*