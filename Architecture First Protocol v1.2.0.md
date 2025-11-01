# Architecture First Protocol v1.2.0 - With Canonical Fallback References

## Canonical Reference Support
This protocol uses canonical references with fallback support.
Format: {{key|fallback}} - Uses canonical form if available, otherwise uses fallback term.
This ensures the protocol works even without the canonical resolver.

## Trigger Conditions (MUST ACTIVATE)
- **WHEN**: Encountering unknown systems, frameworks, or technologies
- **WHEN**: User asks about implementation patterns or best practices
- **WHEN**: Starting analysis of complex codebases or architectures
- **WHEN**: Need to understand system relationships or dependencies
- **WHEN**: User requests information about established workflows or conventions
- **IMMEDIATE**: Yes - check documentation before external search
- **PRIORITY**: High

## Core Principle
"Check architecture documentation first - external search is the last resort, not the first choice"

The system contains comprehensive architectural documentation that answers most questions faster and more accurately than web search. Use this knowledge base first:

1. {{architecture|mcp-architecture}} - Primary architectural documentation
2. {{brain|brain-system}} - Stored knowledge and patterns  
3. {{obsidian|obsidian-vault}} - Curated documentation
4. Web search via {{tracked.search|tracked-search}} - Only for gaps

## Documentation Hierarchy (Check in Order)

### 1. Master Architecture Index
- **Access**: {{architecture|mcp-architecture}} → arch_find_document("keyword")
- **Purpose**: Central registry of all architectural systems
- **Coverage**: System overview, integration status, document index
- **Use for**: Understanding system scope and finding specific docs

### 2. System-Specific Architecture Documents
- **Access**: {{architecture|mcp-architecture}} → arch_get_document("doc-id")
- **Purpose**: Detailed system documentation
- **Coverage**: Design patterns, implementation details, examples
- **Use for**: Understanding how specific systems work

### 3. Brain System Knowledge
- **Access**: {{brain|brain-system}} → unified_search("architecture pattern")
- **Purpose**: Stored experiences and documented patterns
- **Coverage**: Learned patterns, historical decisions, working examples
- **Use for**: Proven approaches and troubleshooting

### 4. Project-Specific Architecture
- **Access**: {{project.finder|mcp-project-finder}} → find project → check ARCHITECTURE.md
- **Purpose**: Project-specific design decisions and patterns
- **Coverage**: Implementation choices, constraints, trade-offs
- **Use for**: Understanding specific project approaches

### 5. Smart Documentation
- **Access**: {{smart.help|mcp-smart-help}} → context-aware documentation
- **Purpose**: Intelligent documentation discovery
- **Coverage**: Context-appropriate documentation suggestions
- **Use for**: Finding relevant docs based on current work

## Architecture-First Response Pattern

### Step 1: Architectural Context Loading
```
Load architectural context:
├─ Check {{architecture|mcp-architecture}} for relevant systems
├─ Search {{brain|brain-system}} for established patterns
├─ Review {{smart.help|mcp-smart-help}} for context docs
├─ Check {{project.finder|mcp-project-finder}} for project patterns
└─ Load {{mercury|mercury-evolution}} heat map for knowledge navigation
```

### Step 2: Information Synthesis
- Combine architectural knowledge with current context
- Check {{brain.state|state-table}} for user preferences
- Apply {{information.integration|information-integration-protocol}} for multi-source synthesis
- Use {{brain.manager|mcp-brain-manager}} for semantic routing

### Step 3: Gap Identification  
- Identify what architectural documentation covers
- Note gaps that require external research
- Only use {{tracked.search|tracked-search}} for identified gaps
- Document new patterns in {{brain|brain-system}}

## Common Architecture Questions and Sources

### System Design Questions
- **First check**: {{architecture|mcp-architecture}} Master Architecture Index
- **Then check**: {{brain|brain-system}} for implementation experiences
- **Finally**: {{tracked.search|tracked-search}} for new approaches
- **Store results**: {{brain.state|state-table}} for future reference

### Implementation Pattern Questions
- **First check**: {{smart.help|mcp-smart-help}} for context-appropriate docs
- **Then check**: {{project.finder|mcp-project-finder}} for working examples
- **Finally**: {{tracked.search|tracked-search}} for current best practices
- **Track usage**: {{mercury|mercury-evolution}} for pattern optimization

### Integration Questions
- **First check**: {{architecture|mcp-architecture}} cross-references
- **Then check**: {{brain|brain-system}} for integration experiences
- **Apply**: {{protocols|mcp-protocols}} for systematic integration
- **Monitor**: {{tool.tracker|mcp-tool-tracker}} for success patterns

### Troubleshooting Questions
- **First check**: {{architecture|mcp-architecture}} for known issues
- **Then apply**: {{error.recovery|error-recovery-protocol}}
- **Use**: {{brain|brain-system}} for similar issue patterns
- **Create**: {{todo|mcp-todo-manager}} tasks for unresolved issues

## Integration with Other Protocols

### {{task.approach|Task Approach Protocol}}
- Load architectural context before analyzing user intent
- Use architecture knowledge to better understand what user really needs
- Apply architectural patterns to solution strategies

### {{information.integration|Information Integration Protocol}}
- Prioritize architectural documentation in source hierarchy
- Use architecture docs as authoritative sources
- Resolve conflicts by preferring documented patterns

### {{progress.communication|Progress Communication Protocol}}
- Communicate architectural discoveries during research
- Explain architectural context when presenting solutions
- Reference architectural decisions in progress updates

### {{user.communication|User Communication Protocol}}
- Use appropriate architectural terminology based on user context
- Reference architecture docs for detailed explanations
- Adapt detail level based on architectural complexity

## Quality Checks

### Before External Search:
- ✅ Have I checked {{architecture|mcp-architecture}} thoroughly?
- ✅ Have I searched {{brain|brain-system}} for related patterns?
- ✅ Have I used {{smart.help|mcp-smart-help}} for context docs?
- ✅ Have I looked for project-specific examples in {{project.finder|mcp-project-finder}}?
- ✅ Is external search really necessary for gaps not covered?

### After Finding Architecture Information:
- ✅ Does this information apply to user's specific context?
- ✅ Is this the most current version of the architectural pattern?
- ✅ Should I store this pattern in {{brain.state|state-table}} for reuse?
- ✅ Do I need to update {{mercury|mercury-evolution}} with usage patterns?

### When Architecture is Insufficient:
- ✅ Have I clearly identified what architectural docs don't cover?
- ✅ Is external search targeted to specific gaps?
- ✅ Will I document new findings in {{brain|brain-system}}?
- ✅ Should new patterns be added to architectural documentation?

## Architecture Documentation Workflow

### Finding Documentation
1. Use {{architecture|mcp-architecture}} → arch_find_document("keyword")
2. If not found, use {{smart.help|mcp-smart-help}} for broader search
3. Check {{brain|brain-system}} for stored architectural patterns
4. Look in {{project.finder|mcp-project-finder}} for implementation examples

### Reading Documentation
1. Use {{architecture|mcp-architecture}} → arch_get_document("doc-id")
2. Apply {{information.integration|information-integration-protocol}} for synthesis
3. Store relevant patterns in {{brain.state|state-table}}
4. Update {{mercury|mercury-evolution}} with knowledge access patterns

### Contributing Back
1. Document new patterns discovered through external research
2. Update architectural documentation when patterns evolve
3. Use {{todo|mcp-todo-manager}} to track documentation improvements
4. Store lessons learned in {{brain.memory|brain-memories}}

## Tools for Architecture-First Approach

### Primary Tools
- {{architecture|mcp-architecture}} - Smart architectural document discovery
- {{brain|brain-system}} - Memory and state management for patterns
- {{smart.help|mcp-smart-help}} - Context-aware documentation
- {{project.finder|mcp-project-finder}} - Finding implementation examples

### Supporting Tools  
- {{mercury|mercury-evolution}} - Knowledge navigation optimization
- {{tracked.search|tracked-search}} - External search when needed
- {{information.integration|information-integration-protocol}} - Multi-source synthesis
- {{brain.manager|mcp-brain-manager}} - Semantic routing and context

### Documentation Tools
- {{todo|mcp-todo-manager}} - Tracking documentation improvements
- {{tool.tracker|mcp-tool-tracker}} - Monitoring documentation usage
- {{protocols|mcp-protocols}} - Systematic documentation processes

## Anti-Patterns to Avoid
🚫 **The External First** - Searching web before checking internal documentation
🚫 **The Documentation Ignorer** - Not using {{architecture|mcp-architecture}} discovery
🚫 **The Pattern Forgetter** - Not storing useful patterns in {{brain|brain-system}}
🚫 **The Context Loser** - Not using {{smart.help|mcp-smart-help}} for contextual docs
🚫 **The Search Optimizer** - Optimizing for search instead of using curated knowledge
🚫 **The Knowledge Hoarder** - Not contributing discoveries back to architecture docs

## Success Metrics
- Faster problem resolution through architectural knowledge
- Reduced external search dependency 
- Better solution quality through established patterns
- Improved architectural knowledge coverage in {{brain|brain-system}}
- More effective knowledge navigation via {{mercury|mercury-evolution}}
- Enhanced architectural documentation completeness

## Version History
- v1.2.0: Added canonical fallback references for consistent terminology
- v1.1.0: Enhanced with smart documentation discovery
- v1.0.0: Initial protocol

---
**Status**: Active Foundation Protocol - v1.2.0 with canonical fallback references
**Integration**: Works seamlessly with all architecture and documentation tools