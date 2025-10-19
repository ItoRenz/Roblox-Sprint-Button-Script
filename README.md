# Sprint System with Light Trail Effects

A dynamic Roblox sprint system with stunning visual effects featuring rainbow-colored light trails on glowing sticks held in player's hands.

## Features

✨ **Visual Effects**
- Rainbow-colored neon light sticks held in both hands during sprint
- Smooth light trail effects following stick movements
- Pulsing transparency animation for dynamic appearance
- Clean visual design without environmental light pollution

🎮 **Platform Support**
- PC and Mobile compatibility
- Dedicated UI buttons for each platform
- Responsive toggle button with smooth animations
- Platform-specific input handling

⚡ **Performance**
- Optimized rendering with heartbeat-based updates
- Proper cleanup on respawn
- Lightweight trail system
- No PointLight for better performance

🎨 **Customization**
- Rainbow color cycling through 12 vibrant colors
- Adjustable sprint speed multiplier
- Configurable trail lifetime and effects
- Dynamic UI with status labels

## Installation

1. Copy the main script to your game
2. Place it in `ServerScriptService` or `StarterPlayer/StarterPlayerScripts`
3. The script automatically handles GUI creation and character management

## Controls

### PC
- Click the **▶ Play Button** (top-right corner) to toggle sprint
- Button shows current status: "WALK" or "RUNNING"
- Visual feedback with color changes and animations
- Smooth rotation animation on button click

### Mobile
- Tap the **▶ Play Button** (compact version, top-right corner)
- Same functionality as PC with optimized touch feedback
- Smooth scale animation on button tap

## Configuration

Edit these values in the script to customize behavior:

```lua
local normalSpeed = 16              -- Default walking speed
local sprintSpeed = normalSpeed * 2 -- Sprint speed (2x multiplier)
```

### Trail Customization

Modify trail properties in the `createHandLightSticks()` function:

```lua
trail.Lifetime = 0.5        -- Duration of light trail (increase for longer trails)
trail.MaxLength = 0         -- Max trail length (0 = unlimited)
```

### Color Cycling

The light stick cycles through 12 colors in sequence:
- Red → Orange → Yellow → Lime Green → Green → Cyan → Light Blue → Dark Blue → Purple → Magenta → Pink → White

Adjust the speed by modifying this line:
```lua
local time = tick() * 3     -- Change 3 to increase/decrease cycle speed
```

### Light Stick Size

Customize the light stick dimensions:

```lua
lightStick.Size = Vector3.new(1.5, 0.2, 0.2)  -- Length, Height, Width
```

## File Structure

```
Sprint-System/
├── sprint-system.lua       # Main script
└── README.md              # This file
```

## Technical Details

### Components

- **Light Stick**: Neon cylinder part welded to player's hand
- **Trail Effect**: Uses Roblox Trail object for visual feedback with smooth fade
- **Attachment Points**: Define trail start and end positions on the stick
- **Weld Constraint**: Keeps light stick attached to player's hand

### How It Works

1. When sprint is activated, two light sticks are created (one per hand)
2. Trail objects connect attachment points to create glowing trails
3. Colors cycle through rainbow spectrum at fixed intervals
4. Transparency pulses for dynamic effect
5. On respawn, old effects are cleaned up automatically
6. UI buttons toggle sprint state and update visual indicators

### Color Animation

The system uses a time-based sine wave for smooth pulsing:
```lua
local pulse = math.sin(time * 8) * 0.15 + 0.2
effect.stick.Transparency = pulse
```

## Performance Tips

- Trail lifetime is set to 0.5 seconds for optimal performance
- Adjust if experiencing frame drops on lower-end devices
- Reduced complexity by removing PointLight
- Efficient attachment-based trail system

## Requirements

- Roblox Studio or Roblox game environment
- Character model with RightHand and LeftHand parts
- Modern Roblox engine with Trail support

## Troubleshooting

**Light sticks not appearing?**
- Ensure character has RightHand and LeftHand parts
- Check script is running in correct service
- Verify part names exactly match (case-sensitive)

**Trail not showing?**
- Verify Attachment objects are created properly
- Check Trail Lifetime is greater than 0
- Ensure parts are not filtered or hidden

**Button not responding?**
- Verify UserInputService is accessible
- Check PlayerGui is available in player
- Ensure script has proper permissions

**Performance issues?**
- Reduce Trail.Lifetime value
- Lower color cycling speed (reduce tick() multiplier)
- Increase update frequency threshold

## Customization Examples

### Increase Trail Length
```lua
trail.Lifetime = 1.0  -- Double the trail duration
```

### Change Sprint Speed
```lua
local sprintSpeed = normalSpeed * 3  -- Triple speed sprint
```

### Modify Light Stick Color
```lua
lightStick.Color = Color3.fromRGB(255, 0, 0)  -- Set initial color
```

### Adjust Trail Transparency
```lua
trail.Transparency = NumberSequence.new({
    NumberSequenceKeypoint.new(0, 0),      -- Fully visible at start
    NumberSequenceKeypoint.new(0.5, 0.5),  -- Semi-transparent in middle
    NumberSequenceKeypoint.new(1, 1)       -- Fully transparent at end
})
```

## Features Comparison

| Feature | Status |
|---------|--------|
| Rainbow Color Cycling | ✅ Enabled |
| Light Trail Effects | ✅ Enabled |
| Pulsing Animation | ✅ Enabled |
| PointLight | ✖️ Disabled |
| PC UI Button | ✅ Enabled |
| Mobile UI Button | ✅ Enabled |
| Sprint Speed Boost | ✅ Enabled |
| Character Respawn Handling | ✅ Enabled |

## Future Enhancements

- [ ] Sound effects during sprint
- [ ] Different trail styles (straight, spiral, wave)
- [ ] Customizable color schemes
- [ ] Stamina system with cooldown
- [ ] Glow intensity adjustment
- [ ] Custom trail thickness options

## API Reference

### Main Functions

```lua
function setSprinting(value: boolean)
  -- Toggle sprint state
  -- Parameters:
  --   value: true to start sprinting, false to stop
```

```lua
function createHandLightSticks()
  -- Creates light sticks with trail effects
  -- Called automatically when sprint is activated
```

```lua
function removeHandLightSticks()
  -- Removes all light stick effects
  -- Called automatically when sprint is deactivated
```

## License

Free to use and modify for your Roblox games.

## Support

For issues or suggestions:
- Ensure all parts are properly named (RightHand, LeftHand)
- Verify script permissions in game settings
- Test in Studio before publishing to production
- Check console for any error messages

---

**Version**: 1.1.0  
**Last Updated**: 2025-10-20  
**Status**: Production Ready
