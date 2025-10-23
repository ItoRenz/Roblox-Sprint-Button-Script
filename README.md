# 🏃 Roblox Sprint System

A comprehensive sprint system for Roblox with rainbow lightstick effects and cross-platform support (PC & Mobile).

## 👤 Author

**ItoRenz00**

## ✨ Features

- 🎮 **Cross-Platform Support** - Works seamlessly on PC and Mobile devices
- ⚡ **Toggle Sprint** - Easy-to-use button interface for sprint control
- 🌈 **Rainbow Lightstick Effect** - Dynamic color-changing lightsticks while sprinting
- 🎵 **Sound Effects** - Start and stop sprint sounds for better feedback
- 💨 **Trail Effects** - Beautiful particle trails following the lightsticks
- 🔄 **State Persistence** - Sprint state persists through respawns
- 🎨 **Smooth Animations** - Polished UI animations and transitions
- 📱 **Responsive UI** - Platform-specific UI optimizations

## 🚀 Installation

### 1. Server Setup

1. Create a new `Script` in `ServerScriptService`
2. Name it `SprintServer`
3. Copy the contents from `SprintServer.lua`

### 2. Client Setup

1. Create a new `LocalScript` in `StarterPlayer > StarterPlayerScripts`
2. Name it `SprintClient`
3. Copy the contents from `SprintClient.lua`

### 3. Remote Events

The system automatically creates the required `RemoteEvents` in `ReplicatedStorage`:
- `SprintRemotes/ToggleSprint` - Handles sprint state changes
- `SprintRemotes/UpdateColor` - Syncs lightstick colors

## 🎮 Usage

### For Players

**PC Controls:**
- Click the sprint button (▶) on the right side of the screen
- Status label shows current state (WALK/RUNNING)

**Mobile Controls:**
- Tap the sprint button (▶) on the right side of the screen
- Status label shows current state (WALK/RUNNING)

### For Developers

#### Configuration

**Server (SprintServer.lua):**
```lua
local NORMAL_SPEED = 20
local SPRINT_MULTIPLIER = 2
local LIGHTSTICK_CONFIG = {
    Size = Vector3.new(1.5, 0.2, 0.2),
    DefaultColor = Color3.fromRGB(255, 0, 0),
    DefaultTransparency = 0.1,
    TrailLifetime = 2.0
}
```

**Client (SprintClient.lua):**
```lua
local SPRINT_START_SOUND_ID = "rbxassetid://111900188409004"
local SPRINT_STOP_SOUND_ID = "rbxassetid://120904325097533"
local SOUND_VOLUME = 0.5
local COLOR_UPDATE_INTERVAL = 0.1
```

## 🛠️ Technical Details

### Architecture

The system uses a client-server architecture:

**Client Side:**
- Platform detection (PC/Mobile)
- GUI creation and management
- Sound effect playback
- Rainbow color calculation
- Local visual feedback

**Server Side:**
- Sprint state management
- Speed modification
- Lightstick creation and destruction
- Color synchronization across all clients
- Player state persistence

### Components

#### SprintClient.lua
- Handles user input and UI interactions
- Manages sound effects locally
- Calculates rainbow colors
- Sends state updates to server

#### SprintServer.lua
- Validates and applies sprint states
- Creates/destroys lightsticks
- Manages player walk speed
- Handles respawn logic

## 🎨 Customization

### Changing Sprint Speed

Modify the multiplier in `SprintServer.lua`:
```lua
local SPRINT_MULTIPLIER = 2  -- Change this value (default: 2x speed)
```

### Changing Lightstick Appearance

Edit the `LIGHTSTICK_CONFIG` table in `SprintServer.lua`:
```lua
local LIGHTSTICK_CONFIG = {
    Size = Vector3.new(1.5, 0.2, 0.2),  -- Lightstick dimensions
    DefaultColor = Color3.fromRGB(255, 0, 0),  -- Starting color
    DefaultTransparency = 0.1,  -- 0 = opaque, 1 = invisible
    TrailLifetime = 2.0  -- Trail duration in seconds
}
```

### Changing Sound Effects

Replace the sound IDs in `SprintClient.lua`:
```lua
local SPRINT_START_SOUND_ID = "rbxassetid://YOUR_SOUND_ID"
local SPRINT_STOP_SOUND_ID = "rbxassetid://YOUR_SOUND_ID"
```

### Modifying Rainbow Colors

Edit the `getRainbowColor()` function in `SprintClient.lua` to customize the color sequence.

## 📋 Requirements

- Roblox Studio
- Basic understanding of Lua scripting
- R15 or R6 character rig (both supported)

## 🐛 Troubleshooting

**Lightsticks not appearing:**
- Ensure the character has loaded properly
- Check that the script is in the correct location
- Verify RemoteEvents exist in ReplicatedStorage

**Sound not playing:**
- Check that sound asset IDs are valid
- Verify sound volume settings
- Ensure sounds are loaded in Content

**Sprint not working:**
- Check Humanoid exists in character
- Verify RemoteEvents are firing correctly
- Check server output for errors

## 📝 License

This project is open source and available for personal and commercial use.

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

## 📧 Contact

For questions or support, please open an issue on the repository.

---

**Made with ❤️ by ItoRenz00**
