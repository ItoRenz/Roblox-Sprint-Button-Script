# Roblox Sprint Button

A lightweight and elegant sprint toggle button for Roblox games with smooth animations and customizable settings.

## Features

- ⚡ **Toggle Sprint Button** - Compact 28x28 pixel button positioned at the top right of the screen
- 🎨 **Beautiful UI Design** - Modern design with rounded corners, shadow effects, and stroke borders
- 🔄 **State Persistence** - Sprint state remains active after character respawn/death
- 📱 **Universal Controls** - Works seamlessly on both PC and mobile devices
- ✨ **Smooth Animations** - 360° rotation effect on click and glow hover effects
- 🎯 **Speed Control** - Default sprint speed is 2x the normal walking speed (32 units/s)
- 📊 **Status Display** - Real-time status label showing "READY" or "RUNNING"

## Installation

1. Open your Roblox game in Roblox Studio
2. Navigate to `StarterPlayer > StarterPlayerScripts`
3. Create a new `LocalScript`
4. Copy and paste the entire script from `sprint-button.lua`
5. Save and test your game!

## Configuration

You can customize these values in the script:

```lua
local normalSpeed = 16          -- Normal walking speed (default Roblox)
local sprintSpeed = normalSpeed * 2  -- Sprint speed (2x normal speed)
```

### UI Colors

Toggle Button Colors:
- **Ready State**: Blue (`Color3.fromRGB(100, 200, 255)`)
- **Running State**: Pink/Red (`Color3.fromRGB(255, 100, 150)`)

Status Label Colors:
- **Ready**: Blue text
- **Running**: Pink/Red text

Change these RGB values to customize the appearance:

```lua
toggleButton.BackgroundColor3 = Color3.fromRGB(100, 200, 255)  -- Ready color
stroke.Color = Color3.fromRGB(200, 230, 255)  -- Ready border color
```

## Usage

### Desktop (PC)
- **Click** the toggle button to start/stop sprinting
- **Hover** over the button to see the glow effect

### Mobile
- **Tap** the toggle button to start/stop sprinting
- The button provides visual feedback with color changes and status text

## Button Behavior

| State | Button Color | Icon | Label |
|-------|--------------|------|-------|
| Ready | Blue | ▶ | READY |
| Running | Pink/Red | ⏸ | RUNNING |

## Animations

1. **Click Animation** - Button rotates 360° smoothly when clicked
2. **Hover Animation** - Border thickness increases from 3 to 5 pixels on hover
3. **State Changes** - Instant color and icon changes when toggling sprint

## Technical Details

- **Script Type**: LocalScript
- **Location**: StarterPlayer > StarterPlayerScripts
- **Services Used**: 
  - Players
  - UserInputService
  - RunService
  - TweenService
- **GUI Library**: Roblox ScreenGui with UICorner and UIStroke

## Known Features

- Sprint state persists across character respawns
- Button remains visible and functional at all times
- No stamina system - infinite sprint capability
- Button does not interfere with other GUI elements
- Smooth performance with minimal overhead

## File Structure

```
roblox-sprint-button/
├── README.md
├── sprint-button.lua
└── .gitignore
```

## License

This project is open source and available under the MIT License.

## Contributing

Feel free to fork this repository and submit pull requests for any improvements!

## Support

If you encounter any issues or have suggestions, please create an issue in the repository.

---

**Version**: 1.0.0  
**Last Updated**: October 2025  
**Roblox Studio Compatibility**: All versions
