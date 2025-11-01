# Protocol Creation Protocol v1.0.0
*Created: August 19, 2025*  
*Type: Meta-Protocol (Tier 0)*  
*Purpose: Governs systematic creation of new protocols*

## Overview
This meta-protocol defines the systematic process for creating new protocols based on observed patterns, ensuring proper documentation, indexing, and integration with the existing protocol ecosystem.

## Triggers
- Recurring manual processes identified
- Repeated problem-solving patterns emerge
- New system capabilities require standardization
- Complex workflows need systematization
- User requests for automation of repetitive tasks

## Core Principles
1. **Pattern-First Design**: Create protocols AFTER patterns emerge from actual usage
2. **Reality-Grounded**: Base on real workflows, not theoretical frameworks  
3. **Immediately Practical**: Must solve actual problems instantly
4. **Living Documentation**: Update as patterns evolve

## Protocol Creation Process

### Phase 1: Pattern Recognition
1. **Identify the Pattern**
   - Document recurring steps or decisions
   - Note pain points and inefficiencies
   - Gather examples of the pattern in use
   - Verify pattern occurs ≥3 times

2. **Analyze Triggers**
   - What conditions trigger this pattern?
   - What context clues indicate it's needed?
   - How do users typically phrase related requests?

### Phase 2: Protocol Design
1. **Define Scope**
   - Clear problem statement
   - Specific use cases covered
   - Boundaries and limitations
   - Success criteria

2. **Structure the Protocol**
   - Overview and purpose
   - Triggers and conditions
   - Step-by-step procedures
   - Decision trees for edge cases
   - Tools and commands involved

### Phase 3: Documentation
1. **Create Protocol File**
   - Use standard naming: `Protocol Name vX.Y.Z.md`
   - Store in `/Users/bard/Documents/Obsidian/Protocols/`
   - Include version number and creation date
   - Tag with appropriate tier (0-3)

2. **Required Sections**
   ```markdown
   # Protocol Name vX.Y.Z
   *Created: Date*
   *Type: Tier Level*
   *Purpose: Brief purpose statement*
   
   ## Overview
   ## Triggers  
   ## Procedures
   ## Tools/Commands
   ## Examples
   ## Edge Cases
   ## Related Protocols
   ```

### Phase 4: Integration
1. **Update Master Protocol Index** ⚠️ **CRITICAL STEP**
   - Add protocol to appropriate tier
   - Update count in relevant sections
   - Add to quick access if foundation protocol
   - Include creation date and context

2. **Link Related Protocols**
   - Identify dependencies
   - Note conflicts or overlaps
   - Create bidirectional links
   - Update cross-references

3. **Brain System Integration** (if applicable)
   - Add to fundamental protocols if Tier 2
   - Include in intelligent context discovery
   - Update protocol detection patterns
   - Test loading in brain_init_v5_working

### Phase 5: Testing and Refinement
1. **Validate Protocol**
   - Test with real scenarios
   - Verify all steps work
   - Check tool calls and commands
   - Confirm triggers are accurate

2. **Iterate Based on Usage**
   - Monitor effectiveness
   - Gather feedback
   - Update based on edge cases discovered
   - Version increment for significant changes

## Quality Standards

### Must-Have Elements
- [ ] Clear, specific triggers
- [ ] Step-by-step procedures
- [ ] Tool calls with exact syntax
- [ ] Real examples from actual usage
- [ ] Integration with existing protocols

### Quality Checks
- [ ] Can someone else follow the protocol successfully?
- [ ] Are all tool calls and commands correct?
- [ ] Does it solve the original problem efficiently?
- [ ] Is it properly integrated with the protocol ecosystem?
- [ ] Has the Master Protocol Index been updated?

## Anti-Patterns to Avoid
❌ **Creating protocols for theoretical scenarios**  
❌ **Overcomplicating simple processes**  
❌ **Forgetting to update Master Protocol Index**  
❌ **Creating protocols without testing them**  
❌ **Ignoring existing protocols that might conflict**

## Tools and Commands

### Essential Commands
```bash
# Create new protocol file
touch "/Users/bard/Documents/Obsidian/Protocols/[Protocol Name] v1.0.0.md"

# Edit Master Protocol Index
open "/Users/bard/Documents/Obsidian/Protocols/Master Protocol Index.md"
```

### MCP Protocol Tool
```
protocols:protocol_list            # See existing protocols
protocols:protocol_read <id>       # Study related protocols  
protocols:protocol_search <query>  # Find similar protocols
```

## Versioning System
- **Major (X.0.0)**: Fundamental changes to structure or purpose
- **Minor (X.Y.0)**: New procedures, significant additions
- **Patch (X.Y.Z)**: Bug fixes, clarifications, minor updates

## Related Protocols
- All existing protocols (as they were created using earlier versions of this pattern)
- [[Common Sense Protocol v1.2.0]] - Meta-protocol for avoiding complexity
- [[Storage System Boundaries Protocol v1.0.0]] - Defines where protocols live

## Examples

### Recent Protocol Creation
**Text Replacement Automation Protocol** - Created August 19, 2025
- **Pattern**: User wanted AppleScript automation for text replacements
- **Trigger**: Request to automate macOS system preferences
- **Solution**: Direct plist manipulation protocol
- **Integration**: Added to Tier 3 workflows

## Success Metrics
- Protocol is used within 24 hours of creation
- Reduces manual work by ≥50% for target scenario
- No major bugs or missing steps after initial testing
- Properly indexed and discoverable

---

## Meta-Protocol Note
This protocol governs its own creation and updates. Any changes to protocol creation methodology should be reflected here and versioned appropriately.

**Next Protocol ID**: text-replacement-automation
**Master Index Status**: ⚠️ MUST UPDATE AFTER CREATION
