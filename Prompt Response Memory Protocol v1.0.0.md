# Prompt Response Memory Protocol v1.0.0

**Created**: August 20, 2025  
**Type**: Foundation Protocol (Tier 2)  
**Status**: Active  

## Purpose
Create memory summaries of the previous prompt and response at the start of each new prompt to maintain session continuity and learning.

## The Principle
**Capture the full conversation context before it gets pushed out of the context window.**

## When to Execute
- At the very start of processing each new user prompt
- Before any other operations (except continuation note checking)
- Only if there was a previous prompt-response pair to summarize

## Protocol Steps

### 1. Detect Previous Interaction
Check if there was a previous prompt-response in the session:
```
if (previousPrompt && previousResponse) {
  proceedWithMemoryCreation();
}
```

### 2. Create Structured Summary
Format the memory with key information:
```javascript
{
  "prompt_number": incrementalNumber,
  "timestamp": currentTimestamp,
  "user_prompt": briefSummaryOfUserRequest,
  "claude_response": keyActionsAndOutcome,
  "tools_used": listOfToolsCalled,
  "achievements": significantAccomplishments,
  "context_notes": relevantContextForFuture
}
```

### 3. Store in Brain Memory
Use brain:brain_remember with structured key:
```
Key: prompt_###_brief_description
Type: conversation_memory
Value: structuredSummary
```

### 4. Quick Storage
Keep memory creation fast - maximum 5 seconds
- Focus on key information, not exhaustive details
- Prioritize actionable insights and outcomes
- Include enough context for future reference

## Memory Naming Convention
```
prompt_001_initial_brain_system_setup
prompt_002_context_window_protocol_creation
prompt_003_hardcoded_paths_implementation
prompt_004_user_feedback_integration
```

## Content Guidelines

### Include
- ✅ Main user request or question
- ✅ Primary actions taken by Claude
- ✅ Tools used and their outcomes
- ✅ Key decisions or insights
- ✅ Files created/modified
- ✅ Problems encountered and solutions

### Exclude
- ❌ Verbose conversation details
- ❌ Repetitive information
- ❌ Tool output unless significant
- ❌ Standard acknowledgments

## Performance Considerations
- Maximum 5 seconds for memory creation
- If slowing response too much, can be disabled
- Monitor user feedback on response speed
- Balance completeness with efficiency

## Integration Points
- Called at start of brain_init_v5_working
- Part of session initialization sequence
- Happens before context loading
- Should not interfere with user request processing

## Success Criteria
- ✅ Consistent memory creation for all prompts
- ✅ Useful summaries for future context
- ✅ Minimal impact on response speed
- ✅ Rich session history for continuity

## Trigger Conditions
- New user prompt received
- Previous prompt-response pair exists
- Brain system is initialized
- Session continuity is active

## Related Protocols
- [[Brain Initialization Protocol v5.2.0]] - Integration point
- [[Context Window Loading Protocol v1.0.0]] - Memory content loading
- [[Information Integration Protocol v1.2.0]] - Multi-session synthesis

---
*Part of Foundation Protocol tier - essential for session continuity and learning*