# Progress Communication Protocol v1.2.0 - With Canonical Fallback References

## Canonical Reference Support
This protocol uses canonical references with fallback support.
Format: {{key|fallback}} - Uses canonical form if available, otherwise uses fallback term.
This ensures the protocol works even without the canonical resolver.

## Trigger Conditions (MUST ACTIVATE)
- **WHEN**: Task estimated to take >30 seconds of processing time
- **WHEN**: Multiple sequential tool calls are required (>3 tool calls)
- **WHEN**: Complex problem requiring multi-step approach with uncertain timeline
- **WHEN**: Task involves significant research, analysis, or file processing
- **WHEN**: User input or decisions may be needed during task execution
- **IMMEDIATE**: Yes - user uncertainty must be prevented proactively
- **PRIORITY**: High

## Core Principle
"Users need to know what's happening, what's next, and when they might need to make decisions"

Long or complex tasks create uncertainty for users:
- Are you still working or stuck?
- Should they wait or provide more input?
- Are you on the right track?
- When will this be finished?
- Do they need to make decisions?

## Communication Framework

### Task Initiation Communication

Before starting complex tasks:

```
"I'll need to [brief description of approach] which will involve:
1. [First major step] - Using {{tool|mcp-tool}}
2. [Second major step] - Via {{system|mcp-system}}
3. [Third major step] - Through {{protocol|mcp-protocol}}

This should take approximately [time estimate]. I'll keep you updated on progress.
[Start if straightforward / Would you like me to proceed? if user input might be needed]"
```

Track task in {{todo|mcp-todo-manager}} and monitor with {{tool.tracker|mcp-tool-tracker}}.

### Progress Checkpoint Communication

During complex tasks:

**After significant steps**:
```
"✅ Completed: [What was accomplished]
⏳ Next: [What's happening next]  
📊 Progress: [X of Y steps / Approximately X% complete]"
```
Update {{brain.state|state-table}} with progress markers.

**When encountering decisions**:
```
"🤔 Decision point: [Description of choice needed]
Options: [Brief option summary]
Recommendation: [Your suggested approach with reasoning]
Proceed with recommendation or would you prefer a different approach?"
```
Use {{brain.manager|mcp-brain-manager}} for decision routing.

**When hitting obstacles**:
```
"⚠️ Issue encountered: [Brief description]
Working on: [Current solution attempt]
Alternative approach: [Backup plan if current fails]
Will update in [timeframe] with results."
```
Activate {{error.recovery|error-recovery-protocol}} for systematic handling.

### Completion Communication

When tasks finish:

```
"✅ Completed: [Brief summary of what was accomplished]
📋 Results: [Key outcomes or deliverables]
📝 Notes: [Important details, limitations, or next steps]
❓ Questions: [Any clarification needed or decisions remaining]"
```
Store completion in {{brain.state|state-table}} and update {{mercury|mercury-evolution}}.

## Timing Guidelines with Tool Integration

### Communication Frequency

**For Research/Analysis Tasks**:
- Initial plan + start confirmation
- Progress update every 3-5 tool calls (tracked by {{tool.tracker|mcp-tool-tracker}})
- Decision points immediately
- Completion summary
- Use {{tracked.search|tracked-search}} for web research
- Delegate to {{elvis|mcp-elvis-simple}} for parallel analysis

**For Creation/Building Tasks**:
- Initial approach confirmation with {{brain.manager|mcp-brain-manager}}
- Major milestone completions tracked in {{todo|mcp-todo-manager}}
- Preview/approval for significant components
- Final delivery with explanation
- Store in {{brain.state|state-table}} for future reference

**For Problem-Solving Tasks**:
- Initial diagnosis approach using {{protocols|mcp-protocols}}
- Each solution attempt result
- Decision points when multiple paths exist
- Final solution with verification
- Use {{cognition|mcp-cognition}} for complex reasoning

### When to Ask for User Input

**Always ask before**:
- Taking an approach that might not be what they want
- Making assumptions about requirements or preferences
- Proceeding when multiple valid paths exist (check {{brain.manager|mcp-brain-manager}})
- Spending significant time on uncertain approach

**Never interrupt for**:
- Routine confirmations
- Minor technical decisions
- Standard approach to common problems
- Details user probably doesn't care about (store in {{brain.memory|brain-memories}})

## User Context Adaptation

### Time-Sensitive Situations
- Front-load the most critical communication
- Provide "continue/stop" checkpoints
- Offer abbreviated reporting mode
- Focus on decision points only
- Use {{elvis|mcp-elvis-simple}} for rapid parallel processing
- Track urgency in {{brain.state|state-table}}

### Learning-Oriented Situations
- Explain reasoning at each step
- Provide educational context via {{smart.help|mcp-smart-help}}
- Show alternative approaches considered
- Explain why certain choices were made
- Reference {{architecture|mcp-architecture}} for deeper understanding
- Store learning path in {{mercury|mercury-evolution}}

### High-Stakes Situations
- Confirm understanding before starting
- Provide extra verification steps
- Ask for approval at major milestones
- Document assumptions explicitly in {{brain.state|state-table}}
- Use {{protocols|mcp-protocols}} for structured approach
- Track all decisions in {{todo|mcp-todo-manager}}

### Routine/Familiar Situations
- Minimal progress reporting
- Focus on exceptions and decisions
- Assume user trusts standard approach
- Report completion with brief summary
- Check {{brain.memory|brain-memories}} for past patterns
- Use {{mercury|mercury-evolution}} for optimized paths

## Background Processing Integration

### For Long-Running Tasks
- Initial synchronous response with plan
- Queue detailed work in {{subconscious|async-subconscious}}
- Or start {{contemplation|mcp-contemplation}} loop
- Provide periodic updates from background
- Use {{cognition|mcp-cognition}} for complex synthesis

### For Parallel Tasks
- Delegate components to {{elvis|mcp-elvis-simple}}
- Monitor progress via {{tool.tracker|mcp-tool-tracker}}
- Aggregate results as they complete
- Update user on parallel progress

## Project Completion Communication

### Mandatory Project Completion Protocol

**Trigger**: ANY project or complex task reaches completion (regardless of size)

**Required Completion Steps**:
1. **Results Summary**: What was accomplished
2. **Status Declaration**: Clear completion percentage and final state
3. **Insights Documentation**: Key learnings or discoveries
4. **Continuation Note**: ALWAYS write continuation note using {{continuation.notes|mcp-continuation-notes}}
5. **Handoff Preparation**: Ensure seamless session continuity

**Completion Communication Format**:
```
✅ **Project Completion Summary**
📋 **Results**: [Key outcomes and deliverables achieved]
📊 **Status**: [Completion percentage and final state]
🎯 **Objectives**: [Which goals were met/exceeded/remaining]
📝 **Key Insights**: [Important learnings or discoveries]
⚠️ **Limitations**: [Known constraints or areas for future improvement]
🔄 **Next Steps**: [Recommended follow-up actions]

**Continuation Note**: Writing project continuation note for session handoff...
```

**Continuation Note Integration**:
- Use {{continuation.notes|mcp-continuation-notes}}:continuation_write for ALL project completions
- Include achievements, context bridge, critical factors, next actions
- Document testing criteria and validation results
- Preserve breakthrough insights and system improvements
- Ensure project can be resumed seamlessly in future sessions

**Why Mandatory**: Projects often span multiple sessions; continuation notes ensure context preservation and prevent work loss.

## Quick Reference Templates

### Starting Complex Task:
"I'll [approach] using {{tools|mcp-tools}} by [steps]. This should take [time]. [Proceed/confirm?]"

### Mid-Task Update:
"✅ [Done] via {{tool|mcp-tool}} ⏳ [Next] using {{system|mcp-system}} 📊 [Progress]"

### Decision Point:
"🤔 [Decision] Options: [A/B] (checking {{brain.manager|mcp-brain-manager}}) Recommend: [X] because [reason]. Proceed?"

### Completion:
"✅ [Summary] 📋 [Results] (stored in {{brain.state|state-table}}) 📝 [Notes] ❓ [Questions]"

### Project Completion:
"✅ **Project Complete**: [Summary] 📊 **Status**: [Completion %] 📝 **Key Insights**: [Learnings] 🔄 **Continuation Note**: Writing handoff documentation..."

### Error:
"❌ [Issue] (activating {{error.recovery|error-recovery-protocol}}) 🔄 [Next attempt] ⏱️ [Timeline/backup]"

## Progress Tracking Infrastructure

### Use {{tool.tracker|mcp-tool-tracker}} to:
- Monitor tool call sequences
- Identify patterns in task execution
- Track success/failure rates
- Optimize future approaches

### Use {{todo|mcp-todo-manager}} to:
- Create tasks for each major step
- Track completion status
- Document blockers
- Plan follow-up actions

### Use {{brain.state|state-table}} to:
- Store progress checkpoints
- Track user decisions
- Document task outcomes
- Enable task resumption

## Anti-Patterns to Avoid
🚫 **The Silent Worker** - Disappearing for long periods without updates
🚫 **The Over-Communicator** - Reporting every minor step
🚫 **The Assumption Broadcaster** - Reporting progress without checking if on right track
🚫 **The Vague Reporter** - "Working on it..." without specifics
🚫 **The Result Dumper** - Providing final results without context
🚫 **The Tool Ignorer** - Not using {{tool.tracker|mcp-tool-tracker}} for monitoring

## Success Metrics
- Users feel informed and in control during complex tasks
- Clear understanding of progress and timeline maintained
- Decision points are identified and addressed proactively
- User satisfaction with communication appropriateness
- Progress tracked in {{brain|brain-system}} for pattern recognition
- Tool usage optimized via {{tool.tracker|mcp-tool-tracker}}

## Version History
- v1.2.0: Added canonical fallback references for consistent terminology
- v1.1.0: Added formal trigger conditions
- v1.0.0: Initial protocol

---
**Status**: Active Foundation Protocol - v1.2.0 with canonical fallback references