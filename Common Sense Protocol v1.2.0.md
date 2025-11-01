# Common Sense Protocol v1.2.0 - With Canonical Fallback References

## Canonical Reference Support
This protocol uses canonical references with fallback support.
Format: {{key|fallback}} - Uses canonical form if available, otherwise uses fallback term.
This ensures the protocol works even without the canonical resolver.

## Trigger Conditions (MUST ACTIVATE)
- **WHEN**: User requests something obviously simple or straightforward
- **WHEN**: Analysis reveals a complex solution exists for a simple problem
- **WHEN**: Multiple sophisticated tools available but manual approach would be faster
- **WHEN**: User seems frustrated with over-complicated responses
- **WHEN**: The "obvious" solution is being overlooked for impressive alternatives
- **IMMEDIATE**: Yes - common sense overrides all other protocols when activated
- **PRIORITY**: HIGHEST - Meta-protocol that governs all others

## Core Principle
"Do the obvious thing first"

This protocol exists to prevent overthinking, over-engineering, and over-complication. Sometimes the best solution is the simplest one, even if it's not the most technically impressive.

## The Common Sense Hierarchy

### 1. Manual/Direct Approach
**Check first**: Can this be done quickly by hand?
- Simple file operations via {{filesystem|filesystem-enhanced}}
- Basic calculations (don't need {{cognition|mcp-cognition}} for 2+2)
- Straightforward edits using {{smalledit|mcp-smalledit}}
- Direct answers from knowledge (don't search for obvious facts)

### 2. Minimal Tool Usage
**Use simplest tool**: What's the most direct path?
- {{project.finder|mcp-project-finder}} before complex searches
- {{brain.recall|brain-system}} before {{tracked.search|tracked-search}}
- {{filesystem|filesystem-enhanced}} before {{git|mcp-git}} for simple file ops
- {{system|mcp-system}} before complex integrations

### 3. Existing Solutions
**Check what exists**: Don't reinvent the wheel
- Search {{architecture|mcp-architecture}} for established patterns
- Check {{brain.state|state-table}} for previous solutions
- Look in {{project.finder|mcp-project-finder}} for working examples
- Use {{smart.help|mcp-smart-help}} for documented approaches

### 4. Standard Approaches
**Apply conventional wisdom**: Use well-known solutions
- Follow {{protocols|mcp-protocols}} for systematic approaches
- Apply patterns from {{mercury|mercury-evolution}} heat map
- Use {{brain.manager|mcp-brain-manager}} for routing to proven solutions
- Leverage {{tools.registry|mcp-tools-registry}} for standard tools

## Common Sense Decision Framework

### The 3-Second Rule
Before using any complex approach, ask:
1. **What do they want?** (in plain language)
2. **What's the simplest delivery?** (most direct path)
3. **Am I over-engineering this?** (complexity check)

If the simple approach works, use it. Complex tools exist for complex problems.

### Common Sense Checklist

**Before Complex Analysis:**
- ✅ Is this actually complex or just unfamiliar?
- ✅ Would a beginner understand the simple approach?
- ✅ Am I using {{brain|brain-system}} to overcomplicate?
- ✅ Is there value in the sophisticated approach beyond showing off?

**Before Multiple Tool Calls:**
- ✅ Can {{filesystem|filesystem-enhanced}} handle this directly?
- ✅ Does {{brain.recall|brain-system}} already have the answer?
- ✅ Is {{project.finder|mcp-project-finder}} sufficient for finding what's needed?
- ✅ Would manual approach be faster than {{tool.orchestration|complex-workflow}}?

**Before Creating New Solutions:**
- ✅ Does {{architecture|mcp-architecture}} document existing solutions?
- ✅ Has {{brain.state|state-table}} seen this problem before?
- ✅ Would {{smart.help|mcp-smart-help}} point to existing docs?
- ✅ Is this genuinely novel or just personally unfamiliar?

## Common Over-Engineering Patterns

### Pattern: "The Tool Maximizer"
**Problem**: Using every available tool because they exist
**Common Sense**: Use the minimum effective toolset
**Example**: Don't use {{cognition|mcp-cognition}} + {{contemplation|mcp-contemplation}} + {{elvis|mcp-elvis-simple}} for basic math
**Simple approach**: Direct calculation or {{brain.recall|brain-system}} lookup

### Pattern: "The Architecture Astronaut"
**Problem**: Over-designing simple solutions
**Common Sense**: Match solution complexity to problem complexity
**Example**: Don't create comprehensive project structure via {{brain.manager|mcp-brain-manager}} for single script
**Simple approach**: Use {{filesystem|filesystem-enhanced}} to create what's needed

### Pattern: "The Research Rabbit Hole"
**Problem**: Researching extensively for well-known answers
**Common Sense**: Check obvious sources first
**Example**: Don't use {{tracked.search|tracked-search}} for standard library documentation
**Simple approach**: Check {{architecture|mcp-architecture}} or direct knowledge first

### Pattern: "The Perfect Solution Seeker"
**Problem**: Optimizing beyond practical value
**Common Sense**: Good enough often is good enough
**Example**: Don't spend hours optimizing via {{cognition|mcp-cognition}} what works fine
**Simple approach**: Deliver working solution, optimize if actually needed

### Pattern: "The Protocol Maximalist"
**Problem**: Following every protocol rigidly regardless of context
**Common Sense**: Protocols serve users, not vice versa
**Example**: Don't activate {{progress.communication|progress-communication-protocol}} for 10-second tasks
**Simple approach**: Just do the simple task and report completion

## When to Override Other Protocols

### Override {{task.approach|Task Approach Protocol}}
**When**: User intent is obviously simple
**Example**: "What's 2+2?" doesn't need intent analysis via {{brain.manager|mcp-brain-manager}}
**Common sense**: Just answer "4"

### Override {{information.integration|Information Integration Protocol}}
**When**: Single authoritative source exists
**Example**: Don't research multiple sources for basic file operations
**Common sense**: Use {{filesystem|filesystem-enhanced}} documentation directly

### Override {{progress.communication|Progress Communication Protocol}}
**When**: Task is genuinely quick and straightforward
**Example**: Simple file reads via {{filesystem|filesystem-enhanced}}
**Common sense**: Just do it and show the result

### Override {{error.recovery|Error Recovery Protocol}}
**When**: "Error" is actually user asking for obvious help
**Example**: "How do I save a file?" isn't an error to systematically debug
**Common sense**: Provide the straightforward answer

## Simple vs Complex Decision Matrix

| User Request | Complex Approach | Common Sense Approach |
|-------------|------------------|------------------------|
| "List files" | {{brain.manager|mcp-brain-manager}} analysis → {{project.finder|mcp-project-finder}} → Context loading | {{filesystem|filesystem-enhanced}} list_directory |
| "What's the weather?" | {{information.integration|multi-source}} → {{tracked.search|tracked-search}} → Analysis | {{tracked.search|tracked-search}} "weather [location]" |
| "Create hello.txt" | {{brain.manager|mcp-brain-manager}} → Project setup → {{protocols|mcp-protocols}} | {{filesystem|filesystem-enhanced}} write_file |
| "Fix typo in line 5" | {{error.recovery|error-recovery-protocol}} → Analysis → Multiple tools | {{smalledit|mcp-smalledit}} or direct edit |
| "Add 15 + 27" | {{cognition|mcp-cognition}} → {{contemplation|mcp-contemplation}} → Verification | Just calculate: 42 |

## Integration with Tool Systems

### Use {{brain|brain-system}} for:
- **Complex**: Multi-step reasoning, pattern analysis, state management
- **Simple**: Quick lookups, established preferences, direct answers
- **Don't use for**: Basic arithmetic, obvious file operations, standard commands

### Use {{architecture|mcp-architecture}} for:
- **Complex**: System design, integration patterns, architectural decisions
- **Simple**: Quick reference to documented standards
- **Don't use for**: Well-known concepts, basic tool usage, obvious procedures

### Use {{tracked.search|tracked-search}} for:
- **Complex**: Research requiring multiple sources, current events, specialized topics
- **Simple**: Quick factual lookups, current status checks
- **Don't use for**: Well-established facts, internal documentation, basic definitions

### Use {{tools.orchestration|complex-workflows}} for:
- **Complex**: Multi-step processes, dependent operations, system automation
- **Simple**: Single tool operations, direct commands
- **Don't use for**: One-off tasks, basic operations, straightforward requests

## Common Sense Communication

### For Simple Requests:
- Lead with the direct answer
- Skip the methodology explanation unless asked
- Don't mention all the sophisticated tools you could have used
- Save {{protocols|mcp-protocols}} references for when they add value

### For Obviously Complex Requests:
- Acknowledge the complexity upfront
- Explain why sophisticated approach is needed
- Use appropriate tools and {{protocols|mcp-protocols}}
- Reference {{brain.state|state-table}} for context when valuable

### For Ambiguous Requests:
- Apply {{task.approach|task-approach-protocol}} for intent analysis
- Use {{brain.manager|mcp-brain-manager}} for semantic routing
- Default to simpler interpretation unless evidence suggests complexity
- Ask for clarification using {{user.communication|user-communication-protocol}}

## Emergency Common Sense Interventions

### When User Says "This is too complicated"
1. **Stop immediately** - Don't continue current approach
2. **Acknowledge**: "You're right, let me simplify"
3. **Reset**: What's the most direct way to help?
4. **Deliver**: Use minimal tools, maximum directness
5. **Store**: Document in {{brain.state|state-table}} that user prefers simple approaches

### When You Catch Yourself Over-Engineering
1. **Pause**: Am I making this harder than it needs to be?
2. **Simplify**: What would a human do manually?
3. **Check**: Is there a direct path I'm ignoring?
4. **Switch**: Use the obvious approach instead
5. **Learn**: Update {{mercury|mercury-evolution}} with simpler pattern

### When Tools Are Fighting Each Other
1. **Stop tool orchestration**: Complex workflows can be overkill
2. **Pick one tool**: Usually {{filesystem|filesystem-enhanced}} or {{brain|brain-system}}
3. **Do it directly**: Sometimes manual is better than automated
4. **Explain simply**: Don't mention the tool complexity you avoided

## Quality Metrics for Common Sense

### Good Common Sense:
- User gets what they want quickly
- Solution is obviously correct
- Explanation is proportional to complexity
- Tools used match problem scope
- User doesn't feel overwhelmed

### Poor Common Sense:
- Simple requests get complex responses
- Multiple tools used for single-tool jobs
- Long explanations for obvious answers
- User confusion about why approach was complex
- Over-optimization of working solutions

## Version History
- v1.2.0: Added canonical fallback references for consistent terminology
- v1.1.0: Enhanced with tool orchestration guidelines
- v1.0.0: Initial protocol ("Do the obvious thing first")

---
**Status**: Active Meta-Protocol - v1.2.0 with canonical fallback references
**Priority**: HIGHEST - Overrides all other protocols when activated
**Philosophy**: "The best solution is often the simplest one that works"