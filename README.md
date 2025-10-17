# 🏃‍♂️ Roblox Sprint Script with Light Stick Effects

A stylish sprint script for Roblox that adds rainbow light stick effects to your character's hands while running at double speed.

## ✨ Features

- **Sprint Toggle**: Easy-to-use toggle button to enable/disable sprint mode
- **Double Speed**: Run at 2x normal walking speed (32 studs/second)
- **Rainbow Light Sticks**: Beautiful color-changing light sticks held in both hands
- **Neon Effects**: Eye-catching neon material with pulsing transparency
- **Point Light**: Dynamic lighting effects that illuminate the surroundings
- **Compact UI**: Minimalist button design positioned on the right side of the screen
- **Status Indicator**: Shows current sprint status (READY/RUNNING)
- **Respawn Support**: Maintains sprint state even after character respawn

## 🎨 Visual Effects

- **12 Color Rainbow Cycle**: Transitions through Red → Orange → Yellow → Lime → Green → Cyan → Blue → Dark Blue → Purple → Magenta → Pink → White
- **Pulsing Animation**: Light sticks pulse with breathing effect
- **Dynamic Brightness**: Point lights adjust brightness in sync with the animation
- **Block Shape**: Light sticks are shaped as rectangular blocks (0.2 x 0.2 x 1.5 studs)

## 📥 Installation

1. Open Roblox Studio
2. Create a new LocalScript in `StarterPlayer > StarterPlayerScripts`
3. Copy the entire script code into the LocalScript
4. Test in Play mode

## 🎮 Usage

1. **Click the Toggle Button**: Press the ▶ button on the right side of your screen
2. **Sprint Mode Active**: Button changes to ⏸ and status shows "RUNNING"
3. **Light Sticks Appear**: Rainbow light sticks spawn in both hands
4. **Click Again to Stop**: Returns to normal walking speed

## ⚙️ Configuration

You can customize these values at the top of the script:

```lua
local normalSpeed = 16        -- Normal walking speed
local sprintSpeed = normalSpeed * 2  -- Sprint speed multiplier
```

### Light Stick Customization
```lua
lightStick.Size = Vector3.new(0.2, 0.2, 1.5)  -- Width, Height, Length
```

### Color Speed
```lua
local time = tick() * 3  -- Increase multiplier for faster color changes
```

## 🎯 UI Elements

- **Toggle Button**: 28x28 pixel button with rounded corners
- **Shadow Effect**: Subtle drop shadow for depth
- **Border Stroke**: Glowing border that responds to hover
- **Status Label**: Shows "READY" or "RUNNING" with matching colors
- **Hover Animation**: Button border expands on mouse hover
- **Click Animation**: 360° rotation animation on click

## 🔧 Technical Details

- **Services Used**: Players, UserInputService, RunService, TweenService
- **GUI Type**: ScreenGui with ResetOnSpawn disabled
- **Effect Type**: Welded Part with WeldConstraint
- **Material**: Neon for maximum visibility
- **Update Frequency**: RunService.Heartbeat for smooth animations

## 🐛 Troubleshooting

### Light sticks not appearing?
- Make sure your character model has "RightHand" and "LeftHand" parts
- For R6 characters, it will attempt to use "RightLowerArm" and "LeftLowerArm"

### Script not working?
- Ensure it's placed in a LocalScript (not a regular Script)
- Check that it's in StarterPlayerScripts or StarterCharacterScripts
- Verify that your game allows client-side scripts

### Sprint not persisting after respawn?
- The script automatically handles respawns via CharacterAdded event
- Sprint state is preserved across deaths

## 📋 Requirements

- Roblox Studio
- LocalScript execution enabled
- Character with hand parts

## 🤝 Contributing

Feel free to fork this project and submit pull requests for any improvements!

## 📄 License

This script is free to use and modify for your Roblox games.

## 🎉 Credits

Created for enhancing Roblox gameplay with stylish visual effects.

---

**Note**: This script is intended for use in your own Roblox games. Always respect game rules and guidelines when using custom scripts.
