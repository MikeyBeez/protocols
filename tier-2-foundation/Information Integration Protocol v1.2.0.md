# Information Integration Protocol v1.2.0 - With Canonical Fallback References

## Canonical Reference Support
This protocol uses canonical references with fallback support.
Format: {{key|fallback}} - Uses canonical form if available, otherwise uses fallback term.
This ensures the protocol works even without the canonical resolver.

## Trigger Conditions (MUST ACTIVATE)
- **WHEN**: Information request requires multiple sources ({{brain|brain-system}} + Obsidian + Web + Files)
- **WHEN**: Conflicting information is detected between any sources
- **WHEN**: Single source is incomplete and user needs comprehensive response
- **WHEN**: User asks for researched, verified, or comprehensive information
- **WHEN**: Combining different information types (structured + unstructured, current + historical)
- **IMMEDIATE**: Yes - information conflicts must be resolved before presenting
- **PRIORITY**: High

## Core Principle
"Multiple sources strengthen truth when integrated systematically, but only when conflicts are resolved explicitly"

Modern AI assistance requires combining:
- {{brain.memory|brain-memories}} (persistent context)
- Obsidian notes via {{brain|brain-system}} (structured knowledge)
- Web search via {{tracked.search|tracked-search}} (current information)
- File contents via {{filesystem|filesystem-enhanced}} (specific data)
- User-provided information (immediate context)
- Internal knowledge (training data)

## Integration Framework

### Step 1: Source Collection Strategy
```
Define information need
├─ Check {{brain.memory|brain-memories}} first (instant access)
├─ Check {{brain.state|state-table}} for project context
├─ Search Obsidian via {{brain|brain-system}} (structured knowledge)
├─ Check uploaded files via {{filesystem|filesystem-enhanced}} (specific data)
├─ Search web via {{tracked.search|tracked-search}} if needed (current/missing info)
├─ Use {{mercury|mercury-evolution}} for knowledge navigation
└─ Apply internal knowledge (fill gaps)
```

### Step 2: Conflict Resolution Matrix

When sources disagree:

| Conflict Type | Resolution Strategy | Tools to Use |
|---------------|-------------------|--------------|
| Version/Recency | Prefer newer source, note temporal difference | {{brain.state|state-table}} for timestamps |
| Authority | Prefer primary source, note secondary source | {{architecture|mcp-architecture}} for authoritative docs |
| Scope | Use source appropriate to user's context | {{brain.manager|mcp-brain-manager}} for context |
| Detail Level | Combine general + specific as appropriate | {{smart.help|mcp-smart-help}} for detail levels |
| Opinion/Preference | Present multiple viewpoints with context | {{contemplation|mcp-contemplation}} for insights |
| Factual Dispute | Research further or acknowledge uncertainty | {{tracked.search|tracked-search}} for verification |

### Step 3: Synthesis Approach

**For Factual Information:**
1. Establish common ground (what all sources agree on)
2. Note significant differences with source attribution
3. Resolve conflicts using reliability ranking from {{protocols|mcp-protocols}}
4. Fill gaps with lower-confidence sources
5. Acknowledge remaining uncertainties
6. Store synthesis in {{brain.state|state-table}}

**For Procedural Information:**
1. Find the most complete procedure in {{architecture|mcp-architecture}}
2. Add details/alternatives from other sources
3. Note important variations or warnings
4. Prioritize based on user's specific context from {{brain.manager|mcp-brain-manager}}
5. Provide fallback approaches
6. Track in {{todo|mcp-todo-manager}} if action needed

**For Opinion/Analysis:**
1. Present the strongest/most relevant perspective first
2. Note alternative viewpoints with brief reasoning
3. Help user understand why perspectives differ
4. Provide framework for making their own decision
5. Use {{cognition|mcp-cognition}} for complex analysis
6. Store insights in {{brain.memory|brain-memories}}

## Source-Specific Integration Rules

### {{brain.memory|brain-memories}} Integration
- **Strengths**: Persistent user context, established preferences, project history
- **Limitations**: May be incomplete or outdated
- **Integration**: Use as primary context, supplement with current sources
- **Conflict handling**: User preferences override general advice
- **Track with**: {{mercury|mercury-evolution}} for usage patterns

### Obsidian Notes Integration (via {{brain|brain-system}})
- **Strengths**: Structured, curated, comprehensive within scope
- **Limitations**: May not cover current topic, could be stale
- **Integration**: Use as authoritative for covered topics
- **Conflict handling**: Obsidian usually wins over web search for established knowledge
- **Navigate with**: {{mercury|mercury-evolution}} heat mapping

### Web Search Integration (via {{tracked.search|tracked-search}})
- **Strengths**: Current information, broad coverage, official sources
- **Limitations**: Variable quality, may be too general
- **Integration**: Use for current data, verification, gap filling
- **Conflict handling**: Web overrides internal knowledge for current events
- **Track usage**: Automatically tracked by {{tracked.search|tracked-search}}

### File Content Integration (via {{filesystem|filesystem-enhanced}})
- **Strengths**: User's specific data, complete within scope
- **Limitations**: May lack broader context
- **Integration**: Prioritize for user's specific case
- **Conflict handling**: User's data overrides general examples
- **Find with**: {{project.finder|mcp-project-finder}} for project files

### Internal Knowledge Integration
- **Strengths**: Broad, reliable, immediately available
- **Limitations**: Knowledge cutoff, may be outdated
- **Integration**: Use as baseline, supplement with current sources
- **Conflict handling**: Lower priority than verified external sources
- **Enhance with**: {{elvis|mcp-elvis-simple}} for parallel processing

## Multi-System Integration Patterns

### Deep Analysis Pattern
1. Load context with {{brain.init|brain_init_v5}}
2. Gather sources using multiple tools
3. Send to {{cognition|mcp-cognition}} for synthesis
4. Or use {{elvis|mcp-elvis-simple}} for parallel analysis
5. Store results in {{brain.state|state-table}}

### Background Research Pattern
1. Initial quick response from available sources
2. Queue deep research in {{subconscious|async-subconscious}}
3. Or start {{contemplation|mcp-contemplation}} loop
4. Update user when insights emerge
5. Track in {{mercury|mercury-evolution}}

### Conflict Resolution Pattern
1. Identify conflicts between sources
2. Activate {{error.recovery|error-recovery-protocol}} if critical
3. Use {{protocols|mcp-protocols}} for resolution strategy
4. Document decision in {{brain.state|state-table}}
5. Create task in {{todo|mcp-todo-manager}} if unresolved

## Quality Assurance Framework

### Before Presenting Integrated Information:

✅ **Consistency Check**
- Are there any remaining contradictions?
- Have I noted where sources disagree?
- Is the overall narrative coherent?
- Check with {{protocols|mcp-protocols}} standards

✅ **Completeness Check**
- Have I addressed all aspects of the user's question?
- Are there important warnings or caveats to include?
- What additional context would be helpful?
- Verify with {{smart.help|mcp-smart-help}} resources

✅ **Attribution Check**
- Are claims properly attributed to sources?
- Is it clear which information comes from where?
- Have I noted confidence levels appropriately?
- Track in {{tool.tracker|mcp-tool-tracker}}

✅ **User Context Check**
- Is this synthesized information appropriate for their situation?
- Have I prioritized information relevant to their context from {{brain.manager|mcp-brain-manager}}?
- Would this help them succeed at their actual goal?
- Apply {{task.approach|task-approach-protocol}} principles

## Source Priority by Information Type
- **Current Events**: {{tracked.search|tracked-search}} → Internal knowledge
- **User Preferences**: {{brain.memory|brain-memories}} → General guidance
- **Technical Procedures**: {{architecture|mcp-architecture}} → Experience reports → Forums
- **User's Specific Data**: {{filesystem|filesystem-enhanced}} → General examples
- **Established Knowledge**: Obsidian via {{brain|brain-system}} → Internal → Web verification

## Anti-Patterns to Avoid
🚫 **The Source Salad** - Dumping information from all sources without synthesis
🚫 **The False Authority** - Preferring sources based on availability rather than quality
🚫 **The Context Ignorer** - Treating all information as equally relevant to {{brain.manager|mcp-brain-manager}} context
🚫 **The Conflict Avoider** - Hiding disagreements between sources
🚫 **The Over-Confident Synthesizer** - Claiming certainty when sources provide uncertainty
🚫 **The Tool Ignorer** - Not using available integration tools from {{brain|brain-system}}

## Success Metrics
- User receives coherent, accurate information that accounts for relevant sources
- Conflicts are resolved transparently with clear reasoning
- Information quality improves with systematic source integration
- User can make informed decisions based on synthesized information
- Integration patterns stored in {{brain.state|state-table}} for reuse
- Knowledge map updated in {{mercury|mercury-evolution}}

## Version History
- v1.2.0: Added canonical fallback references for consistent terminology
- v1.1.0: Added formal trigger conditions
- v1.0.0: Initial protocol

---
**Status**: Active Foundation Protocol - v1.2.0 with canonical fallback references