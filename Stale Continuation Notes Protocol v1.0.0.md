# Stale Continuation Notes Protocol v1.0.0

**Created**: August 20, 2025  
**Type**: Foundation Protocol (Tier 2)  
**Status**: Active  

## Purpose
Preserve continuation notes even when sessions end unexpectedly, preventing total context loss through intelligent staleness detection.

## The Problem with Previous System
- `continuation_read_and_cleanup` deleted notes immediately after reading
- If session ended without writing new note = total context loss  
- Forced every session to write a note or lose continuity
- No graceful degradation for incomplete sessions

## The Stale Note Solution

### Core Principle
**Never delete continuation notes until replaced with new ones.**

### Staleness Classification
- **Fresh**: < 1 hour old ✅
- **Stale**: 1-4 hours old 📜  
- **Very Stale**: > 4 hours old ⚠️

### Enhanced Workflow

#### 1. Session Start
```
1. continuation_check_handoff (shows staleness info)
2. continuation_read_with_staleness (preserves note)
3. Use stale context with appropriate caveats
4. Continue session with available context
```

#### 2. Session End
```
1. continuation_write (automatically cleans up old note)
2. New note replaces old one
3. No manual cleanup needed
```

#### 3. Unexpected Session End
```
1. Old note remains available
2. Next session finds stale but usable context
3. Better than complete context loss
```

## Protocol Steps

### 1. Check for Continuation Notes
Always use `continuation_check_handoff` with staleness detection:
```javascript
continuation_check_handoff({ stale_threshold_hours: 1 })
```

### 2. Read with Staleness Awareness
Use `continuation_read_with_staleness` instead of old cleanup method:
```javascript
continuation_read_with_staleness({ stale_threshold_hours: 1 })
```

### 3. Interpret Staleness Indicators
- ✅ **Fresh**: Use context normally
- 📜 **Stale**: Use with caution, mention age to user
- ⚠️ **Very Stale**: Use only for basic continuity, may be outdated

### 4. Write New Notes
`continuation_write` automatically cleans up old notes before writing new ones.

## User Communication Patterns

### Fresh Context
```
"📋 Continuing from previous session (30 minutes ago)..."
```

### Stale Context  
```
"📜 Found stale context from 2.5 hours ago. Using for basic continuity but some details may be outdated..."
```

### Very Stale Context
```
"⚠️ Found very stale context from 6 hours ago. Using for project identification but recommend updating status..."
```

## Implementation Changes

### New Tools
- `continuation_read_with_staleness` - Staleness-aware reading
- `continuation_cleanup_old` - Manual cleanup if needed
- Enhanced `continuation_check_handoff` - Shows staleness info

### Deprecated Tools
- `continuation_read_and_cleanup` - Still works but deprecated

### Updated User Preferences
```
"FIRST: Check for continuation notes using continuation_check_handoff and read with continuation_read_with_staleness if present (stale notes are preserved)..."
```

## Benefits

### 1. Robust Context Preservation
- Sessions can end unexpectedly without losing all context
- Always have some context available, even if stale
- Graceful degradation instead of complete failure

### 2. Honest Communication
- Clear staleness indicators help user understand context quality
- No false claims about fresh context when using old notes
- Appropriate caveats for aged information

### 3. Automatic Management
- No manual cleanup required
- Old notes cleaned up when new ones written
- Simple workflow for users

## Trigger Conditions
- Any session start (check for continuation notes)
- Unexpected session end (notes preserved automatically)
- Long gaps between sessions (staleness detection active)
- Context recovery needed (use stale notes appropriately)

## Success Criteria
- ✅ No context loss from unexpected session ends
- ✅ Clear staleness communication to users
- ✅ Appropriate use of aged context
- ✅ Automatic cleanup management

## Related Protocols
- [[Context Window Loading Protocol v1.0.0]] - Content preservation methods
- [[Brain Initialization Protocol v5.2.0]] - Session start sequence
- [[User Communication Protocol v1.2.0]] - Staleness communication patterns

---
*Part of Foundation Protocol tier - essential for robust session continuity*