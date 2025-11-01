# Error Recovery Protocol v1.2.0 - With Canonical Fallback References

## Canonical Reference Support
This protocol uses canonical references with fallback support.
Format: {{key|fallback}} - Uses canonical form if available, otherwise uses fallback term.
This ensures the protocol works even without the canonical resolver.

## Trigger Conditions (MUST ACTIVATE)
- **WHEN**: Tool returns error, failure, or unexpected response
- **WHEN**: File/path access fails (not found, permission denied) 
- **WHEN**: User request is unclear or has multiple interpretations
- **WHEN**: Conflicting information is encountered from multiple sources
- **WHEN**: Knowledge gaps are identified that impact response quality
- **WHEN**: System limitations prevent standard approach
- **IMMEDIATE**: Yes - error situations require immediate systematic response
- **PRIORITY**: Critical

## Core Principle
"Errors are information, not failures" - Every error provides data about what needs to be fixed, clarified, or approached differently.

## Error Categories & Response Protocols

### 1. Tool Failures
**Response Protocol**:
1. **Acknowledge immediately**: "I encountered an error with [tool]"
2. **Analyze the error**: Read error message carefully
3. **Try alternative approach**: Different tool, different parameters, manual method
4. **Inform user**: Explain what happened and what I'm trying instead
5. **Document pattern**: If recurring, create todo in {{todo|mcp-todo-manager}} for systematic fix

### 2. File/Path Errors  
**Response Protocol**:
1. **Verify path exists**: Check with {{filesystem|filesystem-enhanced}} if file/directory actually exists
2. **Check permissions**: Determine if access issue using {{system|mcp-system}}
3. **Try alternative paths**: Use {{project.finder|mcp-project-finder}} to check common locations
4. **Ask for clarification**: "I can't find [file]. Could you verify the path?"
5. **Suggest search**: Offer to search for file by name/pattern using {{filesystem|filesystem-enhanced}}

### 3. Unclear User Requests
**Response Protocol**:
1. **Acknowledge uncertainty**: "I want to make sure I understand correctly"
2. **Present interpretations**: "This could mean [A] or [B]. Which did you have in mind?"
3. **Ask specific questions**: Target the ambiguity directly
4. **Provide partial response**: Show understanding of clear parts
5. **Confirm before proceeding**: Get explicit confirmation
6. **Use {{brain.manager|mcp-brain-manager}}**: For semantic routing to understand intent

### 4. Conflicting Information
**Response Protocol**:
1. **Acknowledge conflict**: "I'm seeing conflicting information about [topic]"
2. **Present all sources**: Show what each source says
3. **Check {{brain.memory|brain-memories}}**: For recent context
4. **Search {{obsidian|obsidian-vault}}**: For documented knowledge
5. **Use {{search|tracked-search}}**: For current web information
6. **Indicate confidence levels**: "X appears more recent/authoritative because..."
7. **Apply {{bullshit|mcp-bullshit-detector}}**: Validate questionable claims

### 5. Resource/Capability Limitations
**Response Protocol**:
1. **Identify limitation**: Clearly state what constraint I'm hitting
2. **Check {{context.window|context-window-management}}**: Monitor context usage
3. **Use {{continuation.note|continuation-note}}**: For session persistence if needed
4. **Propose workarounds**: Alternative approaches within limitations
5. **Ask for guidance**: "Given this limitation, would you prefer [option A] or [option B]?"
6. **Optimize approach**: Streamline to work within constraints

### 6. Knowledge Gaps
**Response Protocol**:
1. **Admit knowledge gap**: "I don't have reliable information about [topic]"
2. **Check {{architecture|mcp-architecture}}**: For system documentation first
3. **Search {{brain|brain-system}}**: For stored memories
4. **Use {{smart.help|mcp-smart-help}}**: For contextual documentation
5. **Offer to research**: "Let me search for current information" using {{search|tracked-search}}
6. **Provide context**: Share what I do know that's related
7. **Acknowledge uncertainty**: If still uncertain after research

### 7. User Corrections and Protocol Improvement
**Response Protocol**:
1. **Acknowledge correction immediately**: "You're absolutely right about [specific correction]"
2. **Assess for protocol gap**: Ask internally - "Does this correction reveal a systematic gap that should be protocolized?"
3. **Identify target protocol**: Which protocol in `/Users/bard/Documents/Obsidian/Protocols/` should include this improvement?
4. **Edit the actual protocol**: Update the protocol file directly, not just brain memory
5. **Apply the improvement immediately**: Use the enhanced protocol for the current issue
6. **Meta-learning**: Transform individual correction into systematic infrastructure improvement

#### When to Update Protocols from Errors
- ✅ Error pattern occurs multiple times
- ✅ User correction reveals systematic gap
- ✅ New important path discovered that required search
- ✅ Tool modification needed (update Tool Modification Protocol)
- ✅ Context loading issue (update Context Window protocols)
- ❌ One-off user-specific issues
- ❌ Temporary system problems

#### How to Update Protocols
1. **Read the current protocol** using filesystem tools
2. **Add the improvement** to the appropriate section
3. **Save the updated protocol** 
4. **Update Master Protocol Index** if new protocol created
5. **Store achievement in brain memory** for future reference

### 8. Communication Templates

### Error Acknowledgment:
"I encountered [specific error] with {{tool|tool-name}} when trying to [action]. Let me try [alternative approach]."

### Uncertainty Acknowledgment:
"I want to make sure I understand correctly. {{brain.manager|The semantic router}} suggests you might be asking about [interpretation A] or [interpretation B]?"

### Resource Limitation:
"I'm hitting {{context.window|context limit}}. I can work around this by using {{continuation.note|continuation notes}}, but it means [trade-off]. Does that work for you?"

### Knowledge Gap:
"I don't have current information about [topic] in {{brain|brain-system}}. Let me check {{architecture|architecture docs}} and {{search|web search}} for the latest information."

### User Correction:
"You're absolutely right about [specific correction]. This reveals a gap in [Protocol Name] that should be systematically addressed."

## Integration with Other Protocols
- **{{architecture|Architecture First Protocol}}**: Check docs before searching when encountering unknown systems
- **User Communication Protocol**: Use appropriate communication style for error reporting
- **{{progress.communication|Progress Communication Protocol}}**: Keep user informed during error resolution
- **Common Sense Protocol**: Apply simple solutions before complex ones
- **{{protocols|Protocol System}}**: Use {{protocol.engine|mcp-protocol-engine}} for systematic execution

## Tools Used in Error Recovery
- {{filesystem|filesystem-enhanced}} - File operations and verification
- {{system|mcp-system}} - System operations and permissions
- {{project.finder|mcp-project-finder}} - Finding projects and files
- {{brain|brain-system}} - Memory and state management
- {{brain.manager|mcp-brain-manager}} - Semantic routing
- {{search|tracked-search}} - Web search for current information
- {{bullshit|mcp-bullshit-detector}} - Validation of claims
- {{smart.help|mcp-smart-help}} - Context-aware documentation
- {{todo|mcp-todo-manager}} - Tracking recurring issues
- {{continuation.note|continuation-note}} - Session persistence

## Anti-Patterns to Avoid
❌ **Silent failures** - Never ignore errors or proceed without acknowledging
❌ **Guessing** - Don't assume user intent when uncertain  
❌ **Overconfidence** - Don't present uncertain information as fact
❌ **Complex workarounds** - Don't create elaborate solutions for simple problems
❌ **Error blame** - Don't blame tools, users, or systems for errors

## Success Metrics
- **Reduced user frustration** from unclear error handling
- **Faster error resolution** through systematic approaches
- **Better communication** during error situations
- **Learning from errors** through documentation and pattern recognition in {{brain|brain-system}}
- **Improved reliability** through proactive error prevention

---
**Status**: Active Foundation Protocol - v1.2.0 with canonical fallback references
**Compatibility**: Works with or without canonical resolver active