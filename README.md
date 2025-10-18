# 🏃‍♂️ Roblox Sprint Script with Rainbow Light Sticks

A feature-rich sprint system for Roblox with stunning rainbow light stick effects and dual platform support (PC & Mobile).

![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)
![Platform](https://img.shields.io/badge/platform-Roblox-red.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

## ✨ Features

### 🎮 Dual Platform Support
- **PC**: Toggle button (30x30px) - right side, center
- **Mobile**: Compact toggle button (28x28px) - right side, center

### 🌈 Visual Effects
- Rainbow light sticks appear in both hands when sprinting
- 12 vibrant colors cycling smoothly (Red → Orange → Yellow → Lime → Green → Cyan → Blue → Dark Blue → Purple → Magenta → Pink → White)
- Pulsing transparency and brightness effects
- Neon material with dynamic PointLight

### 🎨 UI Elements
- Elegant toggle buttons with shadow effects
- Status labels showing "WALK" or "RUNNING"
- Smooth animations on click and hover
- Color-coded states (Blue = Walk, Pink = Running)
- Modern rounded corners with border strokes

### ⚡ Performance
- Speed multiplier: 2x (16 → 32 walkspeed)
- Optimized with RunService.Heartbeat
- Persistent across character respawns
- Lightweight and lag-free

## 📦 Installation

### Method 1: Direct Copy
1. Open Roblox Studio
2. Navigate to `StarterPlayer` > `StarterCharacterScripts`
3. Create a new `LocalScript`
4. Copy the entire script and paste it
5. Save and test your game!

### Method 2: Insert from File
1. Download the `SprintScript.lua` file
2. In Roblox Studio, right-click on `StarterCharacterScripts`
3. Select "Insert from File"
4. Choose the downloaded script
5. Done!

## 🎯 Usage

### Controls (Both PC & Mobile)
- **Click Toggle Button**: Toggle sprint mode on/off
- Button automatically appears on the right side of the screen
- Status label shows current state (WALK/RUNNING)

### Visual Feedback
- **Blue Button + "WALK" label**: Normal walking speed
- **Pink Button + "RUNNING" label**: Sprint mode active with rainbow light sticks

## 🎨 Customization

### Speed Settings
Adjust the speed values at the top of the script:
```lua
local normalSpeed = 16  -- Default walk speed
local sprintSpeed = normalSpeed * 2  -- Sprint multiplier (change multiplier as needed)
```

### Rainbow Colors
The script cycles through 12 colors. To modify colors, edit the `RunService.Heartbeat` section:
```lua
if colorIndex < 1 then
    r = 255; g = 0; b = 0 -- Red (change RGB values)
elseif colorIndex < 2 then
    r = 255; g = 165; b = 0 -- Orange
-- ... modify other colors
end
```

### UI Position

#### PC Button Position
```lua
toggleButtonPC.Position = UDim2.new(1, -40, 0.5, -90)
-- Format: UDim2.new(X_Scale, X_Offset, Y_Scale, Y_Offset)
-- Adjust Y_Offset to move up/down
```

#### Mobile Button Position
```lua
toggleButtonMobile.Position = UDim2.new(1, -38, 0.5, -70)
-- Adjust Y_Offset to move up/down
```

### Button Size
```lua
-- PC Button
toggleButtonPC.Size = UDim2.new(0, 30, 0, 30)

-- Mobile Button
toggleButtonMobile.Size = UDim2.new(0, 28, 0, 28)
```

### Light Stick Properties
```lua
-- In createHandLightSticks() function
lightStick.Size = Vector3.new(1.5, 0.2, 0.2) -- Length, Width, Height
lightStick.Transparency = 0.1 -- 0 = fully opaque, 1 = fully transparent

light.Brightness = 2 -- Light intensity
light.Range = 10 -- Light reach distance
```

## 🔧 Technical Details

### Services Used
- `Players` - Player and character management
- `UserInputService` - Platform detection and input handling
- `RunService` - Frame-by-frame updates for effects
- `TweenService` - Smooth UI animations

### Key Components
- **Light Sticks**: Cylinder-shaped parts with Neon material
- **WeldConstraint**: Attaches light sticks to player's hands
- **PointLight**: Creates glowing effect around light sticks
- **ScreenGui**: UI container (ResetOnSpawn = false for persistence)

### Character Compatibility
- ✅ Supports both R6 and R15 character rigs
- ✅ Auto-detects hand parts (RightHand, LeftHand, RightLowerArm, LeftLowerArm)
- ✅ Handles character respawn automatically
- ✅ Maintains sprint state after respawn

### Platform Detection
```lua
local isMobile = UserInputService.TouchEnabled and not UserInputService.KeyboardEnabled
local isPC = not isMobile
```
The script automatically detects whether the player is on mobile or PC and shows the appropriate UI.

## 🐛 Troubleshooting

### Light sticks don't appear
**Possible causes:**
- Character doesn't have recognizable hand parts
- Script is not placed in `StarterCharacterScripts`
- Character hasn't fully loaded yet

**Solutions:**
- Verify your character model has hand parts
- Move the script to the correct location
- Wait a few seconds after spawning

### Toggle button not visible
**Possible causes:**
- Another GUI is overlapping the button
- Screen size is too small
- UI was accidentally disabled

**Solutions:**
- Check ZIndex of other GUIs
- Adjust button position for your screen
- Look in `PlayerGui > SprintGui` to verify it exists

### Sprint doesn't work
**Possible causes:**
- Humanoid WalkSpeed is being overridden by another script
- Character died/respawned incorrectly

**Solutions:**
- Check for conflicting scripts
- Try respawning your character
- Verify the script is running (check Output for errors)

### Button position is off-screen
**Solutions:**
- Adjust the position values in the script
- Use UDim2.new() with scale values instead of offset for responsive positioning

## 📝 Script Structure

```
├── Services & Variables
│   ├── Player & Character references
│   ├── Speed settings
│   └── Platform detection
│
├── GUI Creation
│   ├── PC UI
│   │   ├── Toggle Button (30x30)
│   │   ├── Shadow effect
│   │   ├── Status Label
│   │   └── Animations
│   │
│   └── Mobile UI
│       ├── Toggle Button (28x28)
│       ├── Shadow effect
│       ├── Status Label
│       └── Animations
│
├── Core Functions
│   ├── createHandLightSticks()
│   │   ├── Find hand parts
│   │   ├── Create neon cylinders
│   │   ├── Add PointLights
│   │   └── Weld to hands
│   │
│   ├── removeHandLightSticks()
│   │   └── Clean up effects
│   │
│   └── setSprinting(boolean)
│       ├── Update WalkSpeed
│       ├── Toggle light sticks
│       └── Update UI state
│
├── Effects System
│   └── Rainbow Color Cycling
│       ├── 12 color transitions
│       ├── Pulsing transparency
│       └── Dynamic brightness
│
└── Respawn Handler
    └── Character persistence
```

## 🎥 Features Showcase

### Sprint Effects
- ✅ Rainbow light sticks appear instantly in both hands
- ✅ Smooth color transitions through 12 vibrant colors
- ✅ Pulsing brightness creates dynamic visual effect
- ✅ 2x speed boost for faster movement
- ✅ Effects automatically sync with sprint state

### UI Design
- ✅ Compact modern buttons that don't obstruct gameplay
- ✅ Shadow and stroke effects for depth
- ✅ Smooth hover animations for better feedback
- ✅ Color-coded status labels for instant state recognition
- ✅ Platform-specific positioning (PC vs Mobile)

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Report Bugs**: Open an issue with details about the problem
2. **Suggest Features**: Share your ideas for improvements
3. **Submit Pull Requests**: Fork, modify, and submit PRs
4. **Improve Documentation**: Help make the README clearer
5. **Share Examples**: Show off your customizations!

### Development Guidelines
- Keep code clean and commented
- Test on both PC and mobile
- Maintain compatibility with R6 and R15
- Follow Lua best practices

## 📄 License

This project is licensed under the MIT License - feel free to use, modify, and distribute!

See the [LICENSE](LICENSE) file for details.

## 👤 Author

Created with ❤️ for the Roblox community

**Want to contribute or have questions?**
- Open an issue on GitHub
- Share your customizations
- Help improve the documentation

## 🌟 Support the Project

If you find this script helpful:
- ⭐ **Star this repository** to show your support
- 🐛 **Report issues** to help improve the script
- 💡 **Share your ideas** for new features
- 📢 **Tell your friends** and fellow developers
- 🎮 **Use it in your games** and let us know!

## 📚 Version History

### v1.0.0 (2025-10-19)
- ✨ Initial release
- 🎮 Dual platform support (PC & Mobile)
- 🌈 Rainbow light stick effects with 12 colors
- 🎨 Modern UI with toggle buttons
- ⚡ Optimized performance
- 🔄 Respawn persistence
- 📱 Responsive design for different screen sizes

## 🔗 Related Projects

Looking for more Roblox scripts?
- Check out our other repositories
- Join the Roblox developer community
- Share your own creations!

## 📞 Contact & Support

**Need help?**
- Open an issue on GitHub
- Check the troubleshooting section
- Review existing issues for solutions

**Want to showcase your game using this script?**
- We'd love to see it! Share in the discussions

---

**Made for Roblox Studio** | **LocalScript** | **Client-Side Only** | **Free & Open Source**

### Quick Links
- 📖 [Installation Guide](#-installation)
- 🎯 [Usage Instructions](#-usage)
- 🎨 [Customization Options](#-customization)
- 🐛 [Troubleshooting](#-troubleshooting)
- 🤝 [Contributing](#-contributing)
