# Repository Update Protocol v1.2.0 - With Canonical Fallback References

## Canonical Reference Support
This protocol uses canonical references with fallback support.
Format: {{key|fallback}} - Uses canonical form if available, otherwise uses fallback term.
This ensures the protocol works even without the canonical resolver.

## Trigger Conditions (MUST ACTIVATE)
- **WHEN**: User requests "update repo", "commit changes", "push changes"
- **WHEN**: Significant development work completed requiring version control
- **WHEN**: Code changes ready for sharing or backup
- **WHEN**: Project milestone reached requiring documentation
- **WHEN**: Integration with {{brain.manager|mcp-brain-manager}} repository workflows
- **IMMEDIATE**: Yes - repository consistency is critical for collaboration
- **PRIORITY**: High

## Core Principle
"Standardize git repository updates with comprehensive documentation and systematic verification"

Repository updates are more than just git commits - they represent:
1. **Progress Milestones**: Meaningful development achievements
2. **Knowledge Preservation**: Code and context for future understanding
3. **Collaboration Foundation**: Clean state for team coordination
4. **System Integration**: Coordination with development ecosystem
5. **Documentation Synchronization**: Keep all project docs current

## Repository Update Workflow

### Phase 1: Pre-Update Assessment
**Comprehensive status evaluation:**
```
Repository Assessment:
├─ Check {{git|mcp-git}} status for changes
├─ Review {{filesystem|filesystem-enhanced}} for modified files
├─ Validate {{system|mcp-system}} for build/test status
├─ Check {{project.finder|mcp-project-finder}} for project structure
└─ Review {{brain.state|state-table}} for project context
```

### Phase 2: Change Analysis and Documentation
**Understanding and documenting changes:**
1. **Change Inventory**: List all modified files via {{filesystem|filesystem-enhanced}}
2. **Impact Assessment**: Analyze changes using {{git|mcp-git}} diff
3. **Documentation Requirements**: Identify docs needing updates
4. **Testing Needs**: Determine validation requirements via {{system|mcp-system}}
5. **Integration Impact**: Assess effect on related systems

### Phase 3: Pre-Commit Validation
**Quality assurance before committing:**
- **Code Review**: Examine changes for quality and consistency
- **Documentation Sync**: Update README, CHANGELOG, architecture docs
- **Testing Execution**: Run tests via {{system|mcp-system}} if applicable
- **Build Verification**: Ensure project builds correctly
- **Integration Check**: Verify with {{tools.registry|mcp-tools-registry}} and related tools

### Phase 4: Commit Creation
**Systematic commit process:**
1. **Stage Changes**: Use {{git|mcp-git}} add for selective staging
2. **Commit Message Creation**: Craft comprehensive, standardized message
3. **Commit Execution**: Create commit via {{git|mcp-git}} with verification
4. **Post-Commit Verification**: Confirm commit success and integrity
5. **State Update**: Record in {{brain.state|state-table}} for tracking

### Phase 5: Documentation and Integration
**Complete the update cycle:**
- **Architecture Updates**: Update {{architecture|mcp-architecture}} docs if needed
- **Project Context**: Update {{brain.manager|mcp-brain-manager}} project status
- **Task Management**: Update {{todo|mcp-todo-manager}} with completed items
- **Knowledge Capture**: Store insights in {{brain.memory|brain-memories}}

## Commit Message Standards

### Conventional Commit Format
**Standardized commit structure:**
```
<type>(<scope>): <description>

<body>

<footer>
```

### Commit Types with Canonical Integration
**Enhanced type classification:**
- **feat**: New features (integrate with {{brain.manager|mcp-brain-manager}} feature tracking)
- **fix**: Bug fixes (coordinate with {{error.recovery|error-recovery-protocol}})
- **docs**: Documentation updates (sync with {{architecture|mcp-architecture}})
- **style**: Code style changes (coordinate with development standards)
- **refactor**: Code refactoring (integrate with {{system|mcp-system}} optimization)
- **test**: Test additions/modifications (coordinate with validation systems)
- **chore**: Maintenance tasks (integrate with {{tools.registry|mcp-tools-registry}})

### Enhanced Commit Body
**Comprehensive change documentation:**
```
## What Changed
- [Specific changes with file references]
- [Feature additions or modifications]
- [Bug fixes and resolutions]

## Why Changed  
- [Business/technical justification]
- [Problem being solved]
- [Integration requirements]

## Impact Assessment
- [Systems affected]
- [Dependencies modified]
- [Integration points changed]

## Verification
- [Tests run and results]
- [Build verification status]
- [Integration testing completed]
```

## Integration with Development Ecosystem

### Brain System Coordination
**Project management integration:**
- **Project Status**: Update {{brain.manager|mcp-brain-manager}} with progress
- **State Tracking**: Record milestones in {{brain.state|state-table}}
- **Pattern Learning**: Store successful approaches in {{brain.memory|brain-memories}}
- **Knowledge Navigation**: Update {{mercury|mercury-evolution}} with project evolution

### Tool Ecosystem Integration
**Coordinate with development tools:**
- **File Operations**: Use {{filesystem|filesystem-enhanced}} for comprehensive file management
- **System Integration**: Coordinate with {{system|mcp-system}} for build/test integration
- **Documentation**: Update {{architecture|mcp-architecture}} and related docs
- **Task Management**: Update {{todo|mcp-todo-manager}} with completed and new tasks

### Quality Assurance Integration
**Systematic quality control:**
- **Error Handling**: Apply {{error.recovery|error-recovery-protocol}} for failures
- **Verification**: Use {{write.read|write-read-verification}} for documentation updates
- **Testing**: Coordinate with {{system|mcp-system}} for automated testing
- **Integration Testing**: Verify with {{tools.registry|mcp-tools-registry}}

## Repository Operations

### Basic Update Sequence
**Standard repository update:**
1. **Status Check**: {{git|mcp-git}} status to understand current state
2. **Change Review**: Examine diffs and understand modifications
3. **Documentation Update**: Sync docs with code changes
4. **Staging**: {{git|mcp-git}} add appropriate files
5. **Commit**: {{git|mcp-git}} commit with comprehensive message
6. **Verification**: Confirm commit integrity and completeness

### Push and Sharing
**Coordinate with remote repositories:**
1. **Pre-Push Check**: Verify local commit integrity
2. **Remote Sync**: {{git|mcp-git}} pull to sync with remote changes
3. **Conflict Resolution**: Handle merge conflicts if necessary
4. **Push Execution**: {{git|mcp-git}} push to share changes
5. **Post-Push Verification**: Confirm successful remote update

### Branch Management
**Coordinate branching workflows:**
1. **Branch Strategy**: Align with project branching model
2. **Feature Branches**: Create and manage feature development
3. **Integration**: Merge branches with proper documentation
4. **Cleanup**: Remove merged branches and maintain repository health

## Documentation Integration

### Architecture Documentation Sync
**Keep architectural docs current:**
- **ARCHITECTURE.md**: Update project architecture documentation
- **README.md**: Sync with current functionality and setup
- **CHANGELOG.md**: Document user-facing changes
- **Integration Docs**: Update {{architecture|mcp-architecture}} system docs

### Project Documentation Management
**Comprehensive project documentation:**
- **API Documentation**: Update interface specifications
- **Developer Documentation**: Update setup and contribution guides
- **User Documentation**: Update user-facing documentation
- **Integration Documentation**: Update system integration guides

### Knowledge Management Integration
**Preserve development knowledge:**
- **Decision Records**: Document architectural and technical decisions
- **Learning Documentation**: Capture insights and lessons learned
- **Pattern Documentation**: Document reusable patterns and approaches
- **Integration Knowledge**: Document system integration approaches

## Quality Assurance Framework

### Pre-Commit Validation
**Quality gates before committing:**
- ✅ **Code Quality**: Code meets project standards and conventions
- ✅ **Test Coverage**: Adequate test coverage for changes
- ✅ **Documentation Sync**: Documentation reflects code changes
- ✅ **Build Verification**: Project builds successfully with changes
- ✅ **Integration Testing**: Changes don't break system integration

### Commit Quality Standards
**Ensure high-quality commits:**
- ✅ **Atomic Changes**: Each commit represents a single, cohesive change
- ✅ **Clear Messages**: Commit messages clearly explain what and why
- ✅ **Complete Context**: Sufficient information for future understanding
- ✅ **Verification**: Changes verified through testing and review
- ✅ **Documentation**: Appropriate documentation updates included

### Post-Commit Verification
**Confirm successful update:**
- ✅ **Commit Integrity**: Commit properly recorded in repository
- ✅ **History Clarity**: Repository history remains clean and understandable
- ✅ **Integration Status**: System integration remains functional
- ✅ **Documentation Sync**: All documentation properly updated
- ✅ **State Consistency**: {{brain.state|state-table}} reflects current state

## Error Handling and Recovery

### Common Repository Issues
**Systematic issue resolution:**
- **Merge Conflicts**: Use {{git|mcp-git}} and {{error.recovery|error-recovery-protocol}}
- **Push Failures**: Resolve remote synchronization issues
- **Commit Issues**: Handle malformed commits and message problems
- **Documentation Sync**: Resolve documentation inconsistencies

### Recovery Strategies
**Robust error recovery:**
1. **Issue Identification**: Use {{git|mcp-git}} status and log analysis
2. **Impact Assessment**: Understand scope of repository issues
3. **Recovery Planning**: Plan systematic recovery approach
4. **Recovery Execution**: Execute recovery with verification
5. **Prevention Planning**: Update procedures to prevent recurrence

### Integration Recovery
**System coordination recovery:**
- **Tool Integration**: Restore integration with development ecosystem
- **State Consistency**: Restore {{brain.state|state-table}} consistency
- **Documentation Sync**: Restore documentation synchronization
- **Project Context**: Restore {{brain.manager|mcp-brain-manager}} coordination

## Advanced Repository Management

### Automated Integration
**Enhanced automation capabilities:**
- **Pre-Commit Hooks**: Automated quality checks and validation
- **Documentation Generation**: Automated doc updates from code changes
- **Integration Testing**: Automated system integration verification
- **State Synchronization**: Automated {{brain.state|state-table}} updates

### Workflow Optimization
**Efficient repository workflows:**
- **Template Systems**: Standardized commit message templates
- **Automation Scripts**: Streamlined update procedures
- **Integration Patterns**: Optimized tool coordination patterns
- **Quality Automation**: Automated quality assurance processes

### Analytics and Improvement
**Continuous workflow improvement:**
- **Commit Analysis**: Analyze commit patterns for optimization opportunities
- **Documentation Effectiveness**: Measure documentation quality and completeness
- **Integration Success**: Track system integration effectiveness
- **Workflow Efficiency**: Optimize repository update procedures

## Anti-Patterns to Avoid

🚫 **The Commit Dumper**: Making large, unfocused commits with poor messages
🚫 **The Documentation Ignorer**: Committing code changes without updating docs
🚫 **The Test Skipper**: Committing without proper testing and validation
🚫 **The Integration Breaker**: Making changes that break system integration
🚫 **The Message Minimalist**: Using uninformative commit messages
🚫 **The State Ignorer**: Not updating {{brain.state|state-table}} with progress

## Success Metrics

### Repository Quality:
- **Commit Clarity**: Percentage of commits with clear, informative messages
- **Documentation Sync**: Percentage of commits with appropriate doc updates
- **Test Coverage**: Percentage of commits with adequate testing
- **Integration Success**: Percentage of commits that maintain system integration

### Workflow Efficiency:
- **Update Speed**: Time from change completion to repository update
- **Quality Gates**: Success rate of pre-commit quality validation
- **Documentation Quality**: Completeness and accuracy of project documentation
- **Team Coordination**: Effectiveness of repository-based collaboration

## Version History
- v1.2.0: Added canonical fallback references for enhanced tool coordination
- v1.1.0: Enhanced with Brain system integration and automated quality gates
- v1.0.0: Initial protocol with standardized repository update procedures

---
**Status**: Active Workflow Protocol - v1.2.0 with canonical fallback references
**Integration**: Coordinates with entire development ecosystem
**Philosophy**: "Repository updates preserve progress, enable collaboration, and maintain system integrity"