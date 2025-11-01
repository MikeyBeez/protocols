# Implementation First Protocol v1.2.0 - With Canonical Fallback References

## Canonical Reference Support
This protocol uses canonical references with fallback support.
Format: {{key|fallback}} - Uses canonical form if available, otherwise uses fallback term.
This ensures the protocol works even without the canonical resolver.

## Trigger Conditions (MUST ACTIVATE)
- **WHEN**: User requests creation of new tools, systems, or workflows
- **WHEN**: Designing protocols, standards, or systematic approaches
- **WHEN**: Proposing solutions that haven't been tested yet
- **WHEN**: Creating documentation for untested processes
- **WHEN**: User asks for "best practices" without proven implementation
- **IMMEDIATE**: Yes - implement and test before systematizing
- **PRIORITY**: High

## Core Principle
"Protocols should document proven practices, not theoretical designs"

Don't create formal protocols or systematic approaches until you've:
1. **Implemented** the solution successfully
2. **Tested** it in real scenarios  
3. **Refined** it based on actual usage
4. **Validated** that it solves the real problem

Only then should you create formal documentation via {{protocols|mcp-protocols}}.

## Implementation-First Workflow

### Step 1: Rapid Prototyping
**Build minimal working version first:**
- Use {{filesystem|filesystem-enhanced}} for quick file operations
- Apply {{brain.manager|mcp-brain-manager}} for project setup if needed
- Leverage {{smalledit|mcp-smalledit}} for iterative refinement
- Test with {{system|mcp-system}} for execution validation
- Store attempts in {{brain.state|state-table}} for learning

### Step 2: Real-World Testing  
**Test with actual use cases:**
- Apply to user's specific problem using {{project.finder|mcp-project-finder}}
- Use {{error.recovery|error-recovery-protocol}} to handle failures
- Track issues in {{todo|mcp-todo-manager}} for systematic fixing
- Monitor effectiveness via {{tool.tracker|mcp-tool-tracker}}
- Document lessons in {{brain.memory|brain-memories}}

### Step 3: Iterative Refinement
**Improve based on real feedback:**
- Apply {{information.integration|information-integration-protocol}} for multi-source insights
- Use {{mercury|mercury-evolution}} to track usage patterns
- Refine with {{brain.manager|mcp-brain-manager}} semantic analysis
- Test variations using {{elvis|mcp-elvis-simple}} for parallel approaches
- Store successful patterns in {{brain.state|state-table}}

### Step 4: Pattern Documentation
**Document only after proven effectiveness:**
- Use {{architecture|mcp-architecture}} for formal documentation
- Create systematic approach via {{protocols|mcp-protocols}}
- Reference successful implementations from {{project.finder|mcp-project-finder}}
- Include error handling based on {{error.recovery|error-recovery-protocol}} experience
- Store final version in {{brain.memory|brain-memories}}

## Anti-Patterns to Avoid

### The Theoretical Designer
**Problem**: Creating elaborate protocols without implementation
**Example**: Designing comprehensive workflow systems before building anything
**Implementation First**: Build one working example, then generalize
**Tools**: Start with {{filesystem|filesystem-enhanced}}, expand as needed

### The Perfect Planner
**Problem**: Spending more time designing than implementing
**Example**: Creating detailed specifications before any code
**Implementation First**: Write working code, document what actually works
**Tools**: Use {{brain.state|state-table}} to track what works vs what was planned

### The Academic Architect
**Problem**: Creating solutions that sound good but don't work practically
**Example**: Designing "elegant" systems that fail in real usage
**Implementation First**: Prioritize working over elegant
**Tools**: Test with {{system|mcp-system}}, refine based on real constraints

### The Specification Writer
**Problem**: Creating detailed requirements before understanding the problem
**Example**: Writing comprehensive requirements docs before prototyping
**Implementation First**: Build to understand, then specify what you built
**Tools**: Use {{project.finder|mcp-project-finder}} to find working examples first

## Implementation Strategies by Domain

### Creating New MCP Tools
1. **Quick prototype**: Basic functionality using {{filesystem|filesystem-enhanced}}
2. **Test with actual data**: Use {{project.finder|mcp-project-finder}} for real projects
3. **Handle edge cases**: Apply {{error.recovery|error-recovery-protocol}}
4. **Register in system**: Add to {{tools.registry|mcp-tools-registry}}
5. **Document patterns**: Store in {{architecture|mcp-architecture}}

### Designing New Workflows
1. **Manual execution**: Do it by hand using available tools
2. **Identify friction points**: Track issues in {{todo|mcp-todo-manager}}
3. **Automate incrementally**: Use {{brain.manager|mcp-brain-manager}} for orchestration
4. **Test with real tasks**: Apply to actual user needs
5. **Formalize as protocol**: Document in {{protocols|mcp-protocols}}

### Building Integration Systems
1. **Point-to-point connection**: Connect two systems directly
2. **Handle failures**: Use {{error.recovery|error-recovery-protocol}}
3. **Add monitoring**: Track with {{tool.tracker|mcp-tool-tracker}}
4. **Scale gradually**: Expand based on proven patterns
5. **Document architecture**: Store in {{architecture|mcp-architecture}}

### Creating Documentation Systems
1. **Document one thing well**: Start with single use case
2. **Test findability**: Use {{smart.help|mcp-smart-help}} for discovery
3. **Refine based on usage**: Track with {{mercury|mercury-evolution}}
4. **Expand systematically**: Add based on actual needs
5. **Integrate discovery**: Connect to {{architecture|mcp-architecture}}

## Quality Gates for Implementation

### Before Moving to Next Step:

**Prototype → Testing:**
- ✅ Basic functionality works using {{filesystem|filesystem-enhanced}} or relevant tools
- ✅ Can be executed manually without errors via {{system|mcp-system}}
- ✅ Handles at least one real use case
- ✅ Failure modes are understood and logged in {{brain.state|state-table}}

**Testing → Refinement:**
- ✅ Works with real user data from {{project.finder|mcp-project-finder}}
- ✅ Error patterns documented in {{todo|mcp-todo-manager}}
- ✅ Performance is acceptable for intended use
- ✅ Integration points identified and tested

**Refinement → Documentation:**
- ✅ Solution is stable and reliable
- ✅ Usage patterns established and tracked in {{mercury|mercury-evolution}}
- ✅ Edge cases handled systematically
- ✅ Ready for others to use and maintain

**Documentation → Systematic Use:**
- ✅ Documentation tested with new users
- ✅ Discovery mechanisms work via {{smart.help|mcp-smart-help}}
- ✅ Integration with existing tools verified
- ✅ Maintenance procedures established

## Integration with Development Tools

### Brain System Integration
- Use {{brain.state|state-table}} to track implementation attempts
- Store successful patterns in {{brain.memory|brain-memories}}
- Apply {{brain.manager|mcp-brain-manager}} for semantic routing of new tools
- Track evolution via {{mercury|mercury-evolution}} knowledge mapping

### Error Handling Integration
- Apply {{error.recovery|error-recovery-protocol}} throughout development
- Use {{todo|mcp-todo-manager}} to track implementation issues
- Monitor with {{tool.tracker|mcp-tool-tracker}} for usage patterns
- Delegate testing to {{elvis|mcp-elvis-simple}} for parallel approaches

### Documentation Integration
- Check {{architecture|mcp-architecture}} for existing patterns before creating new
- Use {{smart.help|mcp-smart-help}} for context-aware documentation
- Store final documentation in {{protocols|mcp-protocols}} system
- Enable discovery through {{architecture|mcp-architecture}} indexing

## Measurement and Validation

### Implementation Success Metrics:
- **Works in practice**: Successfully handles real use cases from {{project.finder|mcp-project-finder}}
- **Stable operation**: Consistent behavior tracked by {{tool.tracker|mcp-tool-tracker}}
- **Error resilience**: Handles failures gracefully via {{error.recovery|error-recovery-protocol}}
- **User adoption**: Actually gets used and provides value

### Documentation Quality Metrics:
- **Findable**: Discoverable via {{smart.help|mcp-smart-help}} and {{architecture|mcp-architecture}}
- **Actionable**: Users can follow it successfully
- **Accurate**: Reflects actual working implementation
- **Maintainable**: Can be updated as implementation evolves

### System Integration Metrics:
- **Compatibility**: Works with existing {{tools.registry|mcp-tools-registry}}
- **Performance**: Doesn't degrade system tracked by {{system|mcp-system}}
- **Reliability**: Consistent behavior stored in {{brain.state|state-table}}
- **Discoverability**: Connected to {{mercury|mercury-evolution}} knowledge map

## When Implementation First Doesn't Apply

### Skip for Well-Established Patterns:
- Using proven approaches from {{architecture|mcp-architecture}}
- Following established protocols from {{protocols|mcp-protocols}}
- Applying standard tools from {{tools.registry|mcp-tools-registry}}
- Implementing documented patterns from {{brain.memory|brain-memories}}

### Speed Up for Urgent Needs:
- Emergency fixes using {{error.recovery|error-recovery-protocol}}
- Critical path items tracked in {{todo|mcp-todo-manager}}
- User-blocking issues requiring immediate resolution
- Time-sensitive implementations with known requirements

### Adapt for Research Projects:
- Exploratory work using {{contemplation|mcp-contemplation}}
- Theoretical investigation via {{cognition|mcp-cognition}}
- Pattern discovery through {{mercury|mercury-evolution}}
- Concept validation with {{elvis|mcp-elvis-simple}}

## Version History
- v1.2.0: Added canonical fallback references for consistent terminology
- v1.1.0: Enhanced with tool integration guidelines
- v1.0.0: Initial protocol ("Implement first, systematize second")

---
**Status**: Active Foundation Protocol - v1.2.0 with canonical fallback references
**Philosophy**: "The best protocols document what actually works, not what should work"
**Integration**: Works with all development and documentation tools