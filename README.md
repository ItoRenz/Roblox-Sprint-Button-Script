# 🏃‍♂️ Roblox Sprint Light Stick

A stylish sprint system for Roblox with animated rainbow light stick effects that appear in your character's hands when sprinting.

## ✨ Features

- **Toggle Sprint System**: Easy-to-use button to toggle sprint on/off
- **Rainbow Light Sticks**: Glowing cylindrical light sticks appear vertically in both hands when sprinting
- **Smooth Animations**: Pulsing transparency and brightness effects
- **12 Color Rainbow Effect**: Cycles through vibrant colors (Red, Orange, Yellow, Lime, Green, Cyan, Blue, Purple, Magenta, Pink, White)
- **Modern UI**: Compact toggle button with hover effects and status indicator
- **Speed Boost**: 2x walking speed when sprinting
- **Respawn Compatible**: Maintains sprint state across character respawns

## 🎮 How to Use

1. Copy the script from `sprint_lightstick.lua`
2. In Roblox Studio, create a **LocalScript** inside `StarterPlayer > StarterPlayerScripts`
3. Paste the script code
4. Test in Play mode

### Controls

- Click the **toggle button** (▶) on the right side of the screen to activate sprint
- Click again (⏸) to deactivate sprint
- Status indicator shows:
  - **WALK** - Normal walking mode
  - **RUNNING** - Sprint mode active

## ⚙️ Customization

You can easily customize the script by modifying these variables:

```lua
local normalSpeed = 16 -- Normal walking speed
local sprintSpeed = normalSpeed * 2 -- Sprint speed multiplier
```

### Light Stick Properties
```lua
lightStick.Size = Vector3.new(1.5, 0.2, 0.2) -- Length and diameter
lightStick.Material = Enum.Material.Neon -- Material type
lightStick.CFrame = hand.CFrame * CFrame.Angles(0, math.rad(90), 0) -- Vertical position
```

### Color Speed
```lua
local time = tick() * 3 -- Change the multiplier to adjust color transition speed
```

## 🎨 UI Customization

The toggle button position can be adjusted:
```lua
toggleButton.Position = UDim2.new(1, -40, 0.5, -70) -- X and Y position
```

## 📋 Requirements

- Roblox Studio
- LocalScript execution (works in local player scripts)
- Character with `HumanoidRootPart`, `Humanoid`, and hand parts

## 🔧 Technical Details

- Uses `RunService.Heartbeat` for smooth color transitions
- Implements `WeldConstraint` for stable light stick attachment
- `PointLight` objects provide realistic glow effects
- TweenService for button animations
- Persistent across character respawns
- Vertical cylinder orientation for realistic light stick appearance

## 🐛 Troubleshooting

**Light sticks not appearing?**
- Ensure your character has `RightHand` and `LeftHand` parts
- Check that the script is in a LocalScript
- Verify the character is fully loaded

**UI not showing?**
- Check PlayerGui is accessible
- Ensure ScreenGui is not being reset on spawn

**Light sticks in wrong position?**
- Adjust the rotation in `CFrame.Angles(0, math.rad(90), 0)` to change orientation

## 📝 License

This project is open source and available for free use and modification.

## 🤝 Contributing

Feel free to fork this project and submit pull requests with improvements!

## ⭐ Credits

Created for Roblox developers who want to add stylish sprint mechanics to their games.

---

**Enjoy your rainbow sprint! 🌈**
