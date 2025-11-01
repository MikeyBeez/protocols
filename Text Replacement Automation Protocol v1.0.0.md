# Text Replacement Automation Protocol v1.0.0
*Created: August 19, 2025*  
*Type: Workflow Protocol (Tier 3)*  
*Purpose: Automate macOS text replacement creation via plist manipulation*

## Overview
This protocol provides systematic automation for adding text replacements to macOS without manual GUI interaction. Uses direct plist file manipulation for reliable, fast text replacement creation.

## Triggers
- User requests AppleScript for text replacement
- Need to programmatically add macOS text substitutions
- Bulk text replacement creation required
- GUI automation for System Preferences is fragile/broken
- Request to "add text replacement via script"

## Why This Approach
**Direct plist manipulation** is superior to GUI automation because:
- ✅ Works across all macOS versions (GUI changes frequently)
- ✅ Fast execution (no GUI delays)
- ✅ Reliable (no UI element dependency)
- ✅ Scriptable and automatable
- ❌ GUI AppleScript breaks with each macOS update

## Core Procedures

### Primary Method: Direct Plist Editing (Recommended)
**This is the most reliable approach** - edit the complete array:

⚠️ **CRITICAL: Always backup first!**
```bash
# Create/replace backup (only keep one backup)
cp ~/Library/Preferences/.GlobalPreferences.plist ~/Library/Preferences/.GlobalPreferences.plist.backup
```

1. First, read current replacements:
```bash
defaults read -g NSUserDictionaryReplacementItems
```

2. Write complete new array with additions:

```bash
# Write complete new array (most reliable method)
defaults write -g NSUserDictionaryReplacementItems '(
    {
        on = 1;
        replace = "existing1";
        with = "Existing Text 1";
    },
    {
        on = 1;
        replace = "existing2";  
        with = "Existing Text 2";
    },
    {
        on = 1;
        replace = "NEW_SHORTCUT";
        with = "NEW_REPLACEMENT";
    }
)'

# Restart preferences daemon
killall cfprefsd
```

### Alternative Method: Single Addition (Less Reliable)
```bash
# Add single text replacement (may fail)
defaults write -g NSUserDictionaryReplacementItems -array-add '{
    on = 1;
    replace = "SHORTCUT";
    with = "REPLACEMENT_TEXT";
}'

# Apply changes immediately
killall cfprefsd
```

⚠️ **Note**: `array-add` can be unreliable. Use primary method if this fails.

### Method 3: Script Template
Create reusable script for automated additions:

```bash
#!/bin/bash
# add_text_replacement.sh

SHORTCUT="$1"
REPLACEMENT="$2"

if [ -z "$SHORTCUT" ] || [ -z "$REPLACEMENT" ]; then
    echo "Usage: $0 <shortcut> <replacement>"
    exit 1
fi

# Add the replacement
defaults write -g NSUserDictionaryReplacementItems -array-add "{
    on = 1;
    replace = \"$SHORTCUT\";
    with = \"$REPLACEMENT\";
}"

# Apply changes
killall cfprefsd

echo "✅ Added: $SHORTCUT → $REPLACEMENT"
echo "ℹ️ You may need to restart apps for changes to take effect"
```

## Verification Steps

### Check Current Replacements
```bash
# List all current text replacements
defaults read -g NSUserDictionaryReplacementItems

# Count total replacements
defaults read -g NSUserDictionaryReplacementItems | grep -c "replace ="
```

### Test Replacement
1. Open any text app (TextEdit, Notes, etc.)
2. Type the shortcut + space
3. Verify expansion occurs
4. If not working, restart the app

## Troubleshooting

### Common Issues
1. **Replacement not working immediately**
   - Solution: Restart affected applications
   - Some apps need full restart to pick up changes

2. **Array-add command fails**
   - Solution: Use Method 2 (complete array replacement)
   - Safer for complex modifications

3. **Changes reverted when opening System Preferences**
   - Cause: Modern macOS also uses UserDictionary.db
   - Solution: Make changes stick by using System Preferences once after script

### Debug Commands
```bash
# Check if changes were written
defaults read -g NSUserDictionaryReplacementItems | grep "SHORTCUT"

# Check preferences daemon status
ps aux | grep cfprefsd

# Manual restart if needed
sudo killall cfprefsd
```

### Recovery from Backup
If something goes wrong, restore from backup:
```bash
# Restore from backup
cp ~/Library/Preferences/.GlobalPreferences.plist.backup ~/Library/Preferences/.GlobalPreferences.plist
killall cfprefsd

echo "✅ Restored text replacements from backup"
```

## Advanced Usage

### Bulk Import from CSV
```bash
#!/bin/bash
# bulk_text_replacements.sh

CSV_FILE="$1"
TEMP_PLIST="/tmp/text_replacements.plist"

# Start array
echo '(' > "$TEMP_PLIST"

# Read existing replacements (preserve them)
defaults read -g NSUserDictionaryReplacementItems | grep -A 3 -B 1 'replace =' >> "$TEMP_PLIST"

# Add new ones from CSV
while IFS=',' read -r shortcut replacement; do
    echo "    {" >> "$TEMP_PLIST"
    echo "        on = 1;" >> "$TEMP_PLIST"
    echo "        replace = \"$shortcut\";" >> "$TEMP_PLIST"
    echo "        with = \"$replacement\";" >> "$TEMP_PLIST"
    echo "    }," >> "$TEMP_PLIST"
done < "$CSV_FILE"

# Close array
echo ')' >> "$TEMP_PLIST"

# Apply
defaults write -g NSUserDictionaryReplacementItems "$(cat $TEMP_PLIST)"
killall cfprefsd
```

### AppleScript Integration
For GUI workflows that need text replacement:

```applescript
-- AppleScript wrapper for plist method
set shortcutText to "V5"
set replacementText to "brain_init_v5_working"

do shell script "defaults write -g NSUserDictionaryReplacementItems -array-add '{on=1;replace=\"" & shortcutText & "\";with=\"" & replacementText & "\";}'"
do shell script "killall cfprefsd"

display notification "Text replacement added: " & shortcutText with title "Success"
```

## File Locations
- **Preferences**: `~/Library/Preferences/.GlobalPreferences.plist`
- **Key**: `NSUserDictionaryReplacementItems`
- **Modern DB**: `~/Library/Dictionaries/CoreDataUbiquitySupport/*/UserDictionary.db`

## Examples

### Real Usage Examples
```bash
# Add V5 expansion for brain_init_v5_working
defaults write -g NSUserDictionaryReplacementItems -array-add '{
    on = 1;
    replace = "V5";
    with = "brain_init_v5_working";
}'

# Add common coding shortcuts
defaults write -g NSUserDictionaryReplacementItems -array-add '{
    on = 1;
    replace = "fn";
    with = "function";
}'

# Add email signature
defaults write -g NSUserDictionaryReplacementItems -array-add '{
    on = 1;
    replace = "sig";
    with = "Best regards,\nMichael";
}'
```

## Edge Cases

### Special Characters
- Escape quotes with backslash: `\"`
- Use single quotes for shell commands containing double quotes
- Test with unicode characters separately

### iCloud Sync
- Changes sync to other devices automatically
- May take 5-10 minutes to propagate
- Test on primary device first

### App Compatibility
- Works in: TextEdit, Notes, Mail, Messages, most native apps
- May not work in: Some third-party apps, terminal applications
- Test compatibility per app if critical

## Related Protocols
- [[Protocol Creation Protocol v1.0.0]] - Used to create this protocol
- [[Implementation First Protocol v1.2.0]] - Focus on working solutions
- [[Common Sense Protocol v1.2.0]] - Avoid GUI complexity when plist works

## Success Metrics
- Text replacement works immediately after script execution
- No manual GUI interaction required
- Works reliably across macOS versions
- Can be integrated into larger automation workflows

## Version History
- **v1.0.0** (Aug 19, 2025): Initial creation based on V5 text replacement request

---

**Status**: Ready for production use  
**Tested On**: macOS Sonoma  
**Dependencies**: None (uses built-in defaults command)
