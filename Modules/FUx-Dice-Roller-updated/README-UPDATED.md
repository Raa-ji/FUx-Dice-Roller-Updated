# FUx Dice Roller (Updated for Foundry VTT 12)

**Version:** 0.4.3  
**Last Updated:** 2026-10-11  
**Compatibility:** Foundry VTT 10-12

## What's New in This Version

This is an **updated version** of the original FUx Dice Roller module, modified to work with Foundry VTT version 12. The updates include:

- ✅ **Foundry VTT 12 compatibility** (verified)
- ✅ **Fixed deprecated API calls** (`.data` property removal)
- ✅ **Updated combat helper** to use modern combat API
- ✅ All original features preserved

## Description

Dice roller for FreeForm Universal(FU) RPG Classic & v2, Action Tales! RPG, Neon City Overdrive RPG, Earthdawn - Age Of Legend

### Built-in Support for
- Game system Sandbox chat result style
- Dice So Nice (if installed)

The dice roller is not dependent on any specific Foundry game system but can be used in any game system.

### Recommended Foundry Game Systems
- [Sandbox System Builder](https://foundryvtt.com/packages/sandbox)
- [Simple World-Building](https://foundryvtt.com/packages/system/worldbuilding)

## Supported System Variants

### FU v2 (FreeForm Universal v2)
Default mode for most games.

### FU Classic
Classic FreeForm Universal rules with automatic dice reduction.

### Action Tales! RPG
Supports Action Tales! RPG dice mechanics.

### Neon City Overdrive
Supports Neon City Overdrive's Danger Die mechanics.

### Earthdawn - Age Of Legend
Supports Earthdawn Age of Legend dice mechanics.

## Installation

### Method 1: Direct Installation in Foundry
1. Open Foundry VTT
2. Go to **Configuration & Settings** ⚙️
3. Click **Add-on Modules**
4. Click **Install Module**
5. Paste this manifest URL:
   ```
   https://raw.githubusercontent.com/Anderware/Foundry-Vtt-Sandbox-Macros/main/Modules/FUx-Dice-Roller/releases/module.json
   ```
6. Click **Install** next to FUx Dice Roller

### Method 2: Manual Installation
1. Download the latest release: [fux-dice-roller-0.4.3.zip](https://github.com/Anderware/Foundry-Vtt-Sandbox-Macros/raw/main/Modules/FUx-Dice-Roller/releases/0.4.3/fux-dice-roller-0.4.3.zip)
2. In Foundry VTT, go to **Configuration & Settings** ⚙️
3. Click **Add-on Modules**
4. Click **Install Module**
5. Click **Choose File** and select the downloaded zip file
6. Click **Install**

## Usage

### Launching the Dice Roller

**Method 1: Chat Icon**
- Click the **FU icon** 🎲 on the Chat tab in the sidebar

**Method 2: Module Settings**
- Go to **Game Settings** ⚙️
- Click **FUx Dice Roller Settings**
- Click **Open Dice Roller**

### Rolling Dice

1. Select the number of **Action Dice** (bonus dice) by clicking on them
2. Select the number of **Danger Dice** (penalty dice) by clicking on them
3. Click **Roll!** 🎲

### Chat Commands

You can also roll dice using chat commands:

**Format:**
```
/fux [action_dice]a[danger_dice]d
```

**Examples:**
- `/fux 2a1d` - Roll 2 Action Dice and 1 Danger Die
- `/fux 3a` - Roll 3 Action Dice (no danger dice)
- `/fux 2d` - Roll 2 Danger Dice (no action dice)

### Sending Initiative to Combat Tracker

If you have tokens selected in the scene:
1. Check the **"Send result as Initiative to Combat Tracker for selected token(s)"** option
2. Roll the dice
3. The result will be automatically set as initiative for the selected combatants

### Blind Rolls

The module supports blind rolls for GM-only dice rolls. Non-GM users will see a masked result.

## Settings

Access settings via **Game Settings** ⚙️ → **FUx Dice Roller Settings**

### Available Settings

- **Maximum Action Dice Available** - Set the maximum number of action dice shown in the roller
- **System Variant** - Choose which RPG system rules to use
- **Custom Action Die Icon** - Upload a custom icon for action dice
- **Custom Danger Die Icon** - Upload a custom icon for danger dice
- **Hard Mode** - Enable/disable hard mode for certain systems
- **Matching Dice** - Enable matching dice for FU Classic

## Troubleshooting

### Issue: Dice roller doesn't appear
**Solution:** Make sure you're on the Chat tab and look for the FU icon in the bottom-left corner.

### Issue: Character image not showing
**Solution:** Ensure your user has a character assigned and that character has an image set.

### Issue: Initiative not updating in combat
**Solution:** Make sure you have a combat active and tokens selected before rolling.

### Issue: Dice So Nice not working
**Solution:** Ensure the Dice So Nice module is installed and enabled. The FUx Dice Roller will automatically detect it.

## Credits

**Original Developer:** Anders Forslund  
**Original Repository:** [Anderware/Foundry-Vtt-Sandbox-Macros](https://github.com/Anderware/Foundry-Vtt-Sandbox-Macros)  
**Updated by:** AI Assistant (for Foundry VTT 12 compatibility)

## License

This module is provided as-is. Please respect the original author's work and licensing.

## Support

For issues or questions:
1. Check the [original repository](https://github.com/Anderware/Foundry-Vtt-Sandbox-Macros)
2. Report issues on GitHub
3. Check the Foundry VTT forums

---

**Note:** This updated version maintains full backward compatibility with Foundry VTT 10 and 11.
