# Storage System Boundaries Protocol v1.0.0

## Trigger Conditions (MUST ACTIVATE)
- **WHEN**: Creating any new content that might be stored
- **WHEN**: User asks to save, store, or remember information
- **WHEN**: Updating existing protocols or documentation
- **WHEN**: Deciding where to place new knowledge or data
- **WHEN**: Boot process initializes storage systems
- **IMMEDIATE**: Yes - incorrect storage decisions corrupt system integrity
- **PRIORITY**: Critical

## Core Principle
"Every piece of information has a correct storage location based on its purpose, permanence, and scope"

Mixing storage purposes creates:
- Protocol duplication and conflicts
- Loss of canonical authority
- System fragmentation
- Session continuity failures
- Knowledge decay

## Storage System Architecture

### Obsidian Vault - Canonical Knowledge Repository
**Location**: `/Users/bard/Documents/Obsidian/Protocols/`
**Purpose**: Permanent, authoritative, shared knowledge
**Access**: Via MCP server (`protocols:protocol_*` commands)

**ALWAYS Use Obsidian For**:
- ✅ **Protocols**: All protocol content, versions, specifications
- ✅ **Architecture Documentation**: System designs, specifications
- ✅ **Reference Manuals**: User guides, technical documentation  
- ✅ **Standards**: Coding standards, conventions, templates
- ✅ **Knowledge Base**: Permanent, referenceable information
- ✅ **Version-Controlled Content**: Information requiring history
- ✅ **Shareable Content**: Documentation others might access

**Characteristics**:
- Permanent and persistent
- Version controlled (Git)
- Searchable and linkable
- Authoritative source of truth
- Cross-session consistency
- Professional documentation format

### Brain Memory - Session Context Storage
**Purpose**: Session-specific, personal, dynamic data
**Access**: Via `brain:brain_remember` and `brain:brain_recall`

**ALWAYS Use Brain Memory For**:
- ✅ **User Preferences**: Personal settings and configurations
- ✅ **Project Context**: Current work state and progress
- ✅ **Session Continuity**: Data for resuming work
- ✅ **Personal Reminders**: User-specific notes and todos
- ✅ **Learning Insights**: Pattern recognition and adaptation
- ✅ **Cached Results**: Temporary calculations and processing
- ✅ **Dynamic State**: Changing information tied to sessions
- ✅ **Experimental Data**: Draft content being developed

**Characteristics**:
- Session-scoped and personal
- Frequently changing
- Context-dependent
- User-specific preferences
- Temporary or evolving content
- Not requiring formal documentation

## Critical Boundaries

### NEVER Store in Brain Memory
❌ **Protocols**: Always belongs in Obsidian
❌ **Architecture Documentation**: Permanent knowledge only in Obsidian
❌ **System Specifications**: Canonical source in Obsidian
❌ **Reference Materials**: Documentation goes in Obsidian
❌ **Standards and Templates**: Shareable content in Obsidian

### NEVER Store in Obsidian
❌ **User Preferences**: Personal settings in Brain memory
❌ **Session State**: Temporary context in Brain memory  
❌ **Personal Notes**: User-specific content in Brain memory
❌ **Cached Data**: Temporary results in Brain memory
❌ **Experimental Drafts**: Work-in-progress in Brain memory

## Decision Framework

### When Creating New Content, Ask:
1. **Is this permanent knowledge?** → Obsidian
2. **Will others need this?** → Obsidian  
3. **Is this a protocol or specification?** → Obsidian
4. **Is this user-specific?** → Brain Memory
5. **Is this session-temporary?** → Brain Memory
6. **Does this change frequently?** → Brain Memory

### When Updating Existing Content:
1. **Find the canonical location first**
2. **Edit the canonical source, not copies**
3. **For protocols: Always edit Obsidian files**
4. **For user data: Update Brain memory**
5. **Never duplicate across storage systems**

## Protocol Update Workflow

### Correct Protocol Update Process:
1. **Read canonical protocol** via `protocols:protocol_read`
2. **Edit Obsidian file** directly using `filesystem:edit_file`
3. **Test changes** following Implementation First Protocol
4. **Verify via MCP server** that changes are reflected
5. **Document the update** in protocol version history

### NEVER Do This:
❌ Store protocol updates in Brain memory
❌ Create protocol copies in Brain memory
❌ Mix protocol content between storage systems
❌ Edit Brain memory instead of canonical source

## Boot Process Integration

### During System Initialization:
1. **Load storage boundaries** from this protocol
2. **Embed knowledge** in canonical_protocol_locations
3. **Validate access methods** for both storage systems
4. **Prevent cross-contamination** between storage purposes
5. **Enforce boundaries** in all tool operations

### Boot Process Must Know:
- Obsidian = Canonical protocols and documentation
- Brain Memory = Session context and user preferences  
- MCP Server = Reliable protocol access interface
- No protocol content ever goes in Brain memory

## Error Recovery for Boundary Violations

### If Protocol Content Found in Brain Memory:
1. **Stop immediately** - this indicates system corruption
2. **Identify canonical Obsidian source**
3. **Verify canonical content is current**
4. **Delete Brain memory duplicate**
5. **Update all references** to use canonical source
6. **Add prevention measures** to avoid recurrence

### If User Data Found in Obsidian:
1. **Assess if this should be personal**
2. **Move to Brain memory** if user-specific
3. **Keep in Obsidian** if shareable knowledge
4. **Update access patterns** to use correct location

## Tool Integration

### All MCP Tools Must:
- Respect storage boundaries in their operations
- Use `protocols:protocol_*` for protocol access
- Use `brain:brain_*` for session data
- Never cross-store content between systems
- Follow this protocol for storage decisions

### Key Tools and Their Storage Rules:
- **mcp-protocols**: Only accesses Obsidian canonical source
- **brain-manager**: Only stores session context in Brain memory
- **mcp-continuation-notes**: Session-specific, uses appropriate storage
- **filesystem-enhanced**: Can access both but must respect boundaries

## Success Metrics
- Zero protocol duplication between storage systems
- Consistent canonical authority for all protocols
- Clear separation of permanent vs. session data
- Reliable storage system boundaries enforcement
- Reduced confusion about where to find information

## Anti-Patterns to Avoid
🚫 **The Duplicator**: Storing same content in multiple systems
🚫 **The Boundary Blurrer**: Mixing storage purposes
🚫 **The Memory Hoarder**: Storing protocols in Brain memory
🚫 **The Obsidian Overloader**: Putting session data in Obsidian
🚫 **The Canonical Ignorer**: Editing copies instead of source

---
**Status**: Active System Protocol - v1.0.0
**Integration**: Required in boot process for system integrity