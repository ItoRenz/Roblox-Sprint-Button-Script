# 🏃‍♂️ Roblox Sprint System with Light Stick Effects

A feature-rich sprint system for Roblox games with rainbow light stick effects, sound effects, and cross-platform support (PC & Mobile).

## ✨ Features

- **Toggle Sprint System** - Easy-to-use toggle button for sprint activation
- **Rainbow Light Stick Effects** - Dynamic color-changing light sticks attached to player's hands
- **Trail Effects** - Beautiful trailing effects following hand movements
- **Sound Effects** - Sprint start/stop sound effects with proper caching
- **Cross-Platform Support** - Works on both PC and Mobile devices
- **Respawn Protection** - Maintains functionality after character death/respawn
- **Speed Multiplier** - 2x speed boost when sprinting
- **Smooth Animations** - Button hover effects and transitions

## 🎮 Controls

### PC
- Click the toggle button on the right side of the screen
- Status displays: "WALK" (normal) or "RUNNING" (sprint)

### Mobile
- Tap the toggle button on the right side of the screen
- Optimized button size for touch devices

## 🎨 Visual Effects

### Light Sticks
- **Location**: Attached to both hands
- **Shape**: Cylindrical neon sticks
- **Colors**: 12-color rainbow cycle (Red → Orange → Yellow → Lime → Green → Cyan → Blue → Purple → Magenta → Pink → White)
- **Trail**: Fading trail effect following hand movements
- **Pulsing**: Dynamic transparency pulsing effect

### Rainbow Color Sequence
1. Bright Red
2. Orange
3. Bright Yellow
4. Lime Green
5. Bright Green
6. Cyan
7. Bright Blue
8. Deep Blue
9. Purple
10. Magenta
11. Bright Pink
12. Brilliant White

## 🔊 Sound Effects

- **Sprint Start Sound**: Plays when activating sprint
- **Sprint Stop Sound**: Plays when deactivating sprint
- **Smart Caching**: Sounds are cached and reloaded after respawn

### Custom Sound IDs
```lua
local SPRINT_START_SOUND_ID = "rbxassetid://111900188409004"
local SPRINT_STOP_SOUND_ID = "rbxassetid://120904325097533"
```

## 📋 Installation

1. Open your Roblox game in Roblox Studio
2. Create a **LocalScript** in `StarterPlayer > StarterPlayerScripts`
3. Copy and paste the entire script code
4. **(Optional)** Replace the sound asset IDs with your own sounds
5. Test in Play Mode

## ⚙️ Configuration

### Speed Settings
```lua
local normalSpeed = 16        -- Default walk speed
local sprintSpeed = normalSpeed * 2  -- Sprint speed (32)
```

### Color Customization
Modify the rainbow color sequence in the `RunService.Heartbeat` section:
```lua
if colorIndex < 1 then
    r = 255; g = 0; b = 0  -- Custom color here
end
```

### Button Position (PC)
```lua
toggleButtonPC.Position = UDim2.new(1, -40, 0.5, -90)
```

### Button Position (Mobile)
```lua
toggleButtonMobile.Position = UDim2.new(1, -38, 0.5, -70)
```

## 🐛 Bug Fixes (v1.1)

### Fixed Issues:
- ✅ Sound effects not working after character respawn
- ✅ Sound cache not updating with new character
- ✅ RootPart reference becoming invalid after death

### Key Improvements:
- Automatic sound reloading on respawn
- Enhanced error handling with validation checks
- Proper cleanup and reinitialization of sound objects

## 🛠️ Technical Details

### Services Used
- `Players` - Player management
- `UserInputService` - Input detection and platform checking
- `RunService` - Frame-by-frame updates for effects
- `TweenService` - Smooth UI animations

### Key Components
1. **Sound Cache System**: Efficient sound management with automatic reload
2. **Platform Detection**: Automatic PC/Mobile detection
3. **Effect Management**: Dynamic light stick creation/destruction
4. **Respawn Handler**: Maintains functionality across character respawns

## 📱 Platform Support

| Platform | Supported | Notes |
|----------|-----------|-------|
| PC | ✅ | Full keyboard and mouse support |
| Mobile | ✅ | Touch-optimized UI |
| Console | ⚠️ | Untested, should work with controller |
| VR | ⚠️ | Not optimized |

## 🎯 Use Cases

- **Racing Games**: Enhanced player movement
- **Role-playing Games**: Immersive character movement
- **Adventure Games**: Quick navigation
- **Showcases**: Stylish player effects
- **Obbies**: Speed boost mechanics

## 📄 Code Structure

```
Script
├── Services & Variables
├── Sound System
│   ├── loadSoundInCache()
│   └── playSprintSound()
├── UI Components
│   ├── PC Toggle Button
│   └── Mobile Toggle Button
├── Core Functions
│   ├── createHandLightSticks()
│   ├── removeHandLightSticks()
│   └── setSprinting()
├── Visual Effects Loop
└── Respawn Handler
```

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

### Areas for Improvement:
- Custom color schemes
- More trail effect options
- Particle effects
- Stamina system
- Animation integration

## 📝 License

This project is free to use and modify for your Roblox games.

## 🔗 Resources

- [Roblox Developer Hub](https://create.roblox.com/docs)
- [Sound Asset Library](https://create.roblox.com/marketplace/audio)

## ⚠️ Known Limitations

- Light sticks attach to hand parts only (R15 avatars work best)
- Sound IDs must be valid and accessible
- Performance may vary with many players

## 📞 Support

If you encounter any issues:
1. Check that sound asset IDs are correct
2. Ensure script is in `StarterPlayerScripts`
3. Verify the script runs as a LocalScript
4. Check output console for error messages

## 🎉 Credits

Created for the Roblox developer community

---

**Version**: 1.1  
**Last Updated**: 2025  
**Status**: Active Development

Made with ❤️ for Roblox developers
