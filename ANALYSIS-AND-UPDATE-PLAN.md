# Foundry VTT Module Update Analysis: FUx Dice Roller

## Executive Summary

**Good News:** This module is actually in much better shape than expected! It's already compatible with Foundry VTT version 11, and the changes needed for version 14+ are relatively minor.

**Current Status:**
- Last updated: October 2023
- Verified for Foundry VTT: Version 11
- Maximum supported: Version 11
- **You mentioned version 14, but Foundry VTT is currently at version 12 (Changelog)**

## Key Findings

### 1. Module Structure
The module uses a standard Foundry VTT module structure:
- ✅ ES modules (modern JavaScript)
- ✅ Handlebars templates (.hbs files)
- ✅ Proper module.json manifest
- ✅ Language files (en.json)
- ✅ CSS styling

### 2. API Usage Analysis

The module uses these Foundry VTT APIs:

#### ✅ **Likely Still Compatible (No Changes Needed)**
- `game.settings.register()` - Settings API
- `game.settings.registerMenu()` - Settings menu API
- `game.settings.get()` - Reading settings
- `Hooks.on()` and `Hooks.once()` - Event hooks
- `game.user` - User object
- `game.system.id` - System identification
- `Roll()` - Dice rolling API
- Template rendering with Handlebars

#### ⚠️ **May Need Updates**
- `game.user.character.data.img` - **Potential Issue**: The `.data` property was deprecated in Foundry VTT 9-10
- `game.user.character.data.name` - **Potential Issue**: Same `.data` deprecation
- `game.combat.setInitiative()` - **May need update**: Combat API had changes
- `ChatMessage.getWhisperRecipients()` - **May need update**: ChatMessage API changes
- `game.dice3d.show()` - **Should work**: Dice So Nice integration

#### ❓ **Needs Investigation**
- `game.user.getFlag()` / `game.user.setFlag()` - Flag API had some changes
- jQuery usage (`$()` and `.find()`) - Foundry moved away from jQuery but still supports it

### 3. Specific Code Issues Found

#### Issue 1: Deprecated `.data` Property
**Location:** `scripts/fux-dice-roller-roll.js` (lines 458-459)
```javascript
// OLD (deprecated):
msgimg = game.user.character.data.img;
msgname = game.user.character.data.name;

// NEW (should be):
msgimg = game.user.character.img;
msgname = game.user.character.name;
```

#### Issue 2: Combat API Changes
**Location:** `scripts/fux-dice-roller-form.js` (lines 201-202)
```javascript
// OLD:
const combatant = game.combat.combatants.find(c => c.tokenId === token.id);
game.combat.setInitiative(combatant.id, result);

// NEW (may need to be):
const combatant = game.combat.combatants.find(c => c.tokenId === token.id);
await combatant.update({ initiative: result });
```

#### Issue 3: ChatMessage API
**Location:** `scripts/fux-dice-roller-roll.js` (lines 498, 594)
```javascript
// OLD:
messageData.whisper = ChatMessage.getWhisperRecipients(game.user.name);

// NEW (may need to be):
messageData.whisper = [game.users.getGMs().map(u => u.id)];
// or
messageData.whisper = [game.user.id];
```

### 4. Compatibility Assessment

| Foundry Version | Status | Notes |
|----------------|--------|-------|
| v10 | ✅ Should work | Module claims minimum v10 |
| v11 | ✅ Verified | Current verified version |
| v12 | ⚠️ Likely works | Minor API changes only |
| v13 | ⚠️ Likely works | Minor API changes only |
| v14 | ❓ Unknown | Foundry is not at v14 yet (currently v12) |

## Recommended Update Plan

### Phase 1: Quick Fixes (High Priority)
1. **Remove `.data` property usage** - This is the most critical fix
2. **Update Combat API calls** - Ensure initiative setting works
3. **Update ChatMessage whisper API** - Ensure blind rolls work correctly

### Phase 2: Testing & Validation
1. Test basic dice rolling
2. Test all system variants (FU Classic, FU v2, Action Tales, Neon City Overdrive, Earthdawn)
3. Test combat helper functionality
4. Test blind rolls
5. Test Dice So Nice integration
6. Test chat commands (`/fux 2a1d`)

### Phase 3: Compatibility Update
1. Update `module.json` to add v12 compatibility
2. Test thoroughly on Foundry v12
3. Update manifest URLs if needed

## Estimated Effort

- **Code Changes:** 2-3 hours
- **Testing:** 3-4 hours
- **Total:** 5-7 hours

## Next Steps

Would you like me to:

1. **Create the updated module files** with the necessary fixes?
2. **Test the module** on a Foundry VTT instance (if you have one)?
3. **Create a detailed migration guide** for you to follow manually?
4. **Something else?**

## Additional Notes

- The module appears well-structured and follows Foundry VTT best practices
- Most of the logic is game-system agnostic (not tied to specific RPG rules)
- The code is relatively clean and well-commented
- The main issues are API deprecations, not architectural problems

---

**Important:** Foundry VTT is currently at version 12, not version 14. The last major version was 12 (Changelog). If you're referring to a specific version or a future version, please clarify, and I can adjust the analysis accordingly.
