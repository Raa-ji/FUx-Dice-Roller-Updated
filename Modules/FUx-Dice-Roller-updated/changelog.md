# FUx Dice Roller - Version 0.4.3

## Changes in this version

### Compatibility Updates
- **Updated compatibility** to Foundry VTT version 12 (verified)
- **Fixed deprecated API usage**: Removed `.data` property access from `game.user.character`
  - Changed `game.user.character.data.img` to `game.user.character.img`
  - Changed `game.user.character.data.name` to `game.user.character.name`
- **Updated combat API**: Changed `game.combat.setInitiative()` to `combatant.update({ initiative: result })`

### Bug Fixes
- Fixed character image and name display in chat messages
- Improved combat helper initiative setting compatibility

### Notes
- All existing features remain unchanged
- No changes to dice rolling mechanics or system variants
- Backward compatible with Foundry VTT 10 and 11

---

## Original Changelog (v0.4.2)

### Version 0.4.2
- Updated for Foundry VTT 11

### Version 0.4.0
- Added support for Earthdawn - Age Of Legend system variant

### Version 0.3.0
- Added support for Neon City Overdrive system variant

### Version 0.2.0
- Added support for Action Tales! RPG system variant

### Version 0.1.0
- Initial release with support for FreeForm Universal v2
