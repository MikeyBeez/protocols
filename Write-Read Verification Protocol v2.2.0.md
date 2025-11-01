# Write-Read Verification Protocol v2.2.0 - With Canonical Fallback References

## Canonical Reference Support
This protocol uses canonical references with fallback support.
Format: {{key|fallback}} - Uses canonical form if available, otherwise uses fallback term.
This ensures the protocol works even without the canonical resolver.

## Trigger Conditions (MUST ACTIVATE)
- **WHEN**: Creating or updating critical system documentation
- **WHEN**: Making changes to protocols, architecture docs, or system configurations
- **WHEN**: Creating continuation notes or session handoff information
- **WHEN**: Updating {{brain.state|state-table}} with important information
- **WHEN**: Any write operation that needs verification for correctness
- **IMMEDIATE**: Yes - verification must happen immediately after writing
- **PRIORITY**: Critical

## Core Principle
"Writing does NOT put content in context - only reading does"

**Critical Discovery**: The LLM context window only contains what has been explicitly read, not what has been written. This means:

1. **Writing ≠ Context Availability**: Writing to {{filesystem|filesystem-enhanced}} doesn't add content to working memory
2. **Reading Required**: Must explicitly read back what was written to verify and access
3. **Context Verification**: Only way to confirm write success is to read the result
4. **Memory Persistence**: Information only persists in session if read after writing

## The Write-Read-Verify Cycle

### Step 1: Strategic Writing
**Write with verification in mind:**
- Use {{filesystem|filesystem-enhanced}} for file operations
- Apply {{smalledit|mcp-smalledit}} for targeted changes
- Store in {{brain.state|state-table}} for persistent data
- Update {{brain.memory|brain-memories}} for pattern storage
- Create {{continuation.note|continuation-note}} for session handoff

### Step 2: Immediate Read-Back
**Read what was written to verify:**
```
Write Operation → Immediate Read → Context Verification
├─ File Write via {{filesystem|filesystem-enhanced}}
├─ Read back via {{filesystem|filesystem-enhanced}} read_file
├─ Verify content in working memory
├─ Check for write errors or corruption
└─ Confirm information now available in context
```

### Step 3: Content Verification
**Verify correctness and completeness:**
- **Accuracy Check**: Does content match intended changes?
- **Completeness Check**: Are all required elements present?
- **Format Check**: Is structure and formatting correct?
- **Integration Check**: Does it work with {{brain|brain-system}} and other tools?

### Step 4: Context Confirmation
**Ensure information is available for use:**
- **Working Memory**: Can I reference the information immediately?
- **Tool Integration**: Do canonical references resolve correctly?
- **Cross-References**: Are links to other systems functional?
- **Pattern Recognition**: Is information properly integrated with existing knowledge?

## Application Patterns by Content Type

### Protocol Documentation
**Enhanced verification for protocols:**
1. **Write Protocol**: Create protocol document via {{filesystem|filesystem-enhanced}}
2. **Read Verification**: Read complete protocol back into context
3. **Canonical Check**: Verify all {{tool|tool-name}} references resolve
4. **Integration Test**: Confirm protocol integrates with {{protocols|mcp-protocols}}
5. **Update Index**: Add to protocol registry and read back confirmation

### Architecture Documentation  
**Systematic verification for architecture:**
1. **Document Creation**: Write via {{filesystem|filesystem-enhanced}}
2. **Read Validation**: Read complete document into working memory
3. **Cross-Reference Check**: Verify links to {{architecture|mcp-architecture}} work
4. **Discovery Test**: Confirm findable via {{smart.help|mcp-smart-help}}
5. **Integration Verification**: Test with {{brain.manager|mcp-brain-manager}}

### State and Memory Updates
**Critical verification for persistent data:**
1. **State Update**: Write to {{brain.state|state-table}}
2. **Read Confirmation**: Read back state to verify persistence
3. **Memory Storage**: Store patterns in {{brain.memory|brain-memories}}
4. **Read Validation**: Read memory to confirm storage
5. **Access Test**: Verify retrieval via {{brain|brain-system}}

### Code and Configuration Changes
**Rigorous verification for system changes:**
1. **Code Write**: Update files via {{filesystem|filesystem-enhanced}} or {{smalledit|mcp-smalledit}}
2. **Read Verification**: Read changed files completely
3. **Syntax Check**: Verify code correctness in working memory
4. **Integration Test**: Test with {{git|mcp-git}} and {{system|mcp-system}}
5. **Documentation Update**: Document changes and read back

### Continuation Notes
**Essential verification for session continuity:**
1. **Note Creation**: Write {{continuation.note|continuation-note}}
2. **Complete Read-Back**: Read entire note into working memory
3. **Completeness Check**: Verify all essential information captured
4. **Context Verification**: Confirm note contains sufficient handoff information
5. **Storage Confirmation**: Verify note accessible for next session

## Integration with Canonical Tools

### File System Operations
**Enhanced file verification:**
- **Write**: {{filesystem|filesystem-enhanced}} write_file operations
- **Read-Back**: {{filesystem|filesystem-enhanced}} read_file verification
- **Edit Verification**: {{smalledit|mcp-smalledit}} with immediate read-back
- **Directory Confirmation**: {{filesystem|filesystem-enhanced}} list_directory after changes

### Brain System Coordination
**Memory and state verification:**
- **State Updates**: {{brain.state|state-table}} set operations with get verification
- **Memory Storage**: {{brain.memory|brain-memories}} with retrieval confirmation
- **Pattern Updates**: {{mercury|mercury-evolution}} with access verification
- **Project Context**: {{brain.manager|mcp-brain-manager}} with context confirmation

### Version Control Integration
**Git operations with verification:**
- **Commit Verification**: {{git|mcp-git}} commit followed by status check
- **Branch Operations**: {{git|mcp-git}} branch changes with verification
- **Push Confirmation**: {{git|mcp-git}} push with remote verification
- **Repository State**: {{git|mcp-git}} status after any repository changes

### Documentation Systems
**Documentation with discovery verification:**
- **Architecture Updates**: {{architecture|mcp-architecture}} with search verification
- **Protocol Changes**: {{protocols|mcp-protocols}} with access verification
- **Help System**: {{smart.help|mcp-smart-help}} with discovery confirmation
- **Tool Registry**: {{tools.registry|mcp-tools-registry}} with listing verification

## Error Detection and Recovery

### Common Write-Read Failures
**Systematic failure detection:**

**File System Errors**:
- **Write Failure**: {{filesystem|filesystem-enhanced}} write returns error
- **Read-Back Failure**: Cannot read what was supposedly written
- **Permission Issues**: {{system|mcp-system}} permission problems
- **Path Problems**: {{filesystem|filesystem-enhanced}} path resolution issues

**State System Errors**:
- **State Write Failure**: {{brain.state|state-table}} cannot store data
- **State Read Failure**: Cannot retrieve what was stored
- **Memory Issues**: {{brain.memory|brain-memories}} storage problems
- **Context Loss**: Information not available after write

**Integration Errors**:
- **Tool Reference Failures**: Canonical references don't resolve
- **Cross-System Issues**: {{brain|brain-system}} coordination problems
- **Discovery Failures**: {{smart.help|mcp-smart-help}} cannot find new content
- **Protocol Integration**: {{protocols|mcp-protocols}} access issues

### Recovery Strategies
**Systematic error recovery:**
1. **Immediate Detection**: Recognize failure during read-back step
2. **Error Analysis**: Use {{error.recovery|error-recovery-protocol}} for diagnosis
3. **Alternative Approaches**: Try different tools or methods
4. **Verification Repeat**: Retry write-read cycle with corrections
5. **Fallback Documentation**: Document in {{todo|mcp-todo-manager}} if unresolvable

## Quality Assurance Framework

### Verification Checklists

**For Critical Documentation**:
- ✅ **Write Successful**: No errors during write operation
- ✅ **Read Complete**: Entire document read back successfully
- ✅ **Content Accurate**: Content matches intended changes
- ✅ **Format Correct**: Structure and formatting preserved
- ✅ **References Functional**: All canonical and standard references work
- ✅ **Integration Verified**: Works with related systems

**For State and Memory Updates**:
- ✅ **State Stored**: {{brain.state|state-table}} write successful
- ✅ **State Retrieved**: Can read back stored state
- ✅ **Memory Recorded**: {{brain.memory|brain-memories}} storage confirmed
- ✅ **Memory Accessible**: Can retrieve stored memories
- ✅ **Pattern Updated**: {{mercury|mercury-evolution}} reflects changes
- ✅ **Context Available**: Information usable in current session

**For Code and Configuration**:
- ✅ **File Updated**: {{filesystem|filesystem-enhanced}} write successful
- ✅ **Syntax Valid**: Code reads correctly and is syntactically valid
- ✅ **Integration Maintained**: Works with {{git|mcp-git}} and build systems
- ✅ **Documentation Current**: Changes documented and verified
- ✅ **Testing Possible**: Code can be tested with {{system|mcp-system}}

## Advanced Verification Techniques

### Multi-Tool Verification
**Cross-system confirmation:**
- **File + State**: Store file paths in {{brain.state|state-table}} and verify access
- **Memory + Discovery**: Store in {{brain.memory|brain-memories}} and test {{smart.help|mcp-smart-help}} discovery
- **Protocol + Registry**: Add to {{protocols|mcp-protocols}} and verify in {{tools.registry|mcp-tools-registry}}
- **Cross-Reference Validation**: Test canonical references across multiple tools

### Temporal Verification
**Time-based confirmation:**
- **Immediate Verification**: Read-back within same tool session
- **Session Verification**: Test access across tool calls
- **Persistence Verification**: Confirm survival across context boundaries
- **Long-term Verification**: Test with {{continuation.note|continuation-note}} across sessions

### Integration Testing
**System-wide verification:**
- **Tool Chain Testing**: Verify information flows through tool ecosystem
- **Protocol Integration**: Test with {{protocols|mcp-protocols}} execution
- **Brain Coordination**: Verify {{brain|brain-system}} integration
- **User Workflow**: Test in real usage scenarios

## Anti-Patterns to Avoid

🚫 **The Blind Writer**: Writing without reading back to verify
🚫 **The Assumption Maker**: Assuming write operations succeeded without verification
🚫 **The Context Ignorer**: Not testing if written information is available in working memory
🚫 **The Tool Truster**: Trusting tool success without explicit verification
🚫 **The Verification Skipper**: Skipping read-back due to time pressure
🚫 **The Single-Tool Believer**: Not testing integration with other tools

## Success Metrics

### Verification Effectiveness:
- **Write Success Rate**: Percentage of write operations that verify correctly
- **Read-Back Success**: Ability to read and use written information immediately
- **Integration Success**: Written information works with related tools
- **Context Persistence**: Information remains available throughout session
- **Error Detection Rate**: Ability to catch write failures through verification

### System Reliability:
- **Data Integrity**: Written information matches intended content
- **Cross-Tool Compatibility**: Information works across tool ecosystem
- **Session Continuity**: {{continuation.note|continuation-note}} enables proper handoff
- **Documentation Quality**: Architecture and protocol docs are accurate and accessible

## Version History
- v2.2.0: Added canonical fallback references for consistent tool coordination
- v2.1.0: Enhanced with multi-tool verification strategies
- v2.0.0: Major revision with systematic verification framework
- v1.0.0: Initial protocol based on context window discovery

---
**Status**: Active Critical Protocol - v2.2.0 with canonical fallback references
**Load Order**: SECOND - Needed for all subsequent operations
**Critical Discovery**: "Writing doesn't create context - only reading does"