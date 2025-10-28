# Neptune FN - Cronus Zen

**Advanced Fortnite enhancement script for Cronus Zen devices with complete performance optimization and a visual overhaul**

## Info

Neptune FN is a heavily enhanced and optimized version of the original Arc Script, completely rewritten and improved by Payson. This GPC (GamePack Code) script provides advanced gaming enhancements for Fortnite players using Cronus Zen devices, featuring a beautiful OLED interface, performance optimizations, and comprehensive customization options.

## Key Features

### **Auto-Tracking**
**What it does:** Automatically adjusts your aim to follow targets with precision tracking
**How it works:** Uses a time-based system running at 25Hz (40ms intervals) that applies subtle left stick adjustments (`set_val(LX, -AutoTrackingPower)` then `set_val(LX, AutoTrackingPower)`) to create smooth tracking movement. Power is configurable from 0-100% and only activates when no manual input is detected.

### **Anti-Recoil** 
**What it does:** Automatically compensates for weapon recoil to maintain accurate aim
**How it works:** Monitors fire button and ADS state, then applies downward right stick movement (`set_val(PS4_RY, AntiRecoilPower)`) to counteract vertical recoil. The system calculates recoil compensation dynamically and stops when manual aim input is detected to prevent conflicts.

### **Pro Enhancers**
**What it does:** Improves controller response and input processing for competitive play
**How it works:** Modifies controller sensitivity curves and response timing through `vm_tctrl(-6)` settings, enhancing stick precision and reducing input lag for more responsive gameplay.

### **Sticky Scope**
**What it does:** Reduces scope sensitivity when aiming down sights for better precision
**How it works:** Applies stick scaling modifications when ADS is active, reducing the effective sensitivity of aim inputs to provide steadier crosshair control during scoped engagements.

### **Aim Assist**
**What it does:** Provides additional aim assistance beyond the game's built-in system
**How it works:** Enhances existing aim assist through subtle stick value modifications and timing adjustments when targets are in proximity, creating stronger magnetism effects.

### **Crouch Shot**
**What it does:** Automatically crouches when firing while aiming for improved accuracy
**How it works:** Monitors for simultaneous fire and ADS inputs (`get_val(Fire) && get_val(ADS)`), then executes a crouch combo with configurable delay timing to reduce recoil and improve shot accuracy.

### **Radar System**
**What it does:** Creates a circular scanning pattern for enhanced enemy detection
**How it works:** Uses polar coordinate mathematics to generate smooth circular movement patterns. Calculates `radar_x` and `radar_y` positions using trigonometric arrays (`PolarArray[radar_angle]`) and applies them to left stick when no manual input is detected. Speed and radius are fully configurable.

### **OLED Interface**
**What it does:** Provides an intuitive menu system with real-time feature status display
**How it works:** Uses bitmap graphics and text rendering functions (`image_oled`, `print`, `rect_oled`) with inverted color scheme (black backgrounds, white text) for better visibility. Features animated logo with falling drop effects and multi-layered menu navigation.

### ⚙️ **Kill Switch**
**What it does:** Instantly enables/disables the entire script for quick toggling
**How it works:** Monitors Xbox+LT combination to disable all features and Xbox+RT to re-enable. Uses RGB lighting (purple for active, red for disabled) and rumble feedback for status confirmation.

## Performance Improvements

- **Audio Glitch Fix**: Moved `vm_tctrl(-6)` to `init()` function to prevent every-frame execution causing audio buffer overflow
- **Optimized Refresh Rates**: Reduced animation frequency from every 5 frames to every 10 frames (50% CPU reduction)
- **Time-Based Auto-Tracking**: Efficient 25Hz tracking system with `AUTO_TRACK_INTERVAL_MS = 40` to minimize input lag
- **Clean Compilation**: Fixed all GPC syntax errors including compound operators (`^=`, `|=`) and floating-point literals

## Visual Enhancements

- **Complete Color Inversion**: Dark theme with inverted OLED colors for better visibility
- **Custom Branding**: Personalized with Payson credits and custom logo
- **Animated Logo**: Smooth falling drop animation effects on startup screen
- **Enhanced Menus**: Three-layer navigation (Container → Main → Edit) with clear status indicators

## Technical Details

- **Language**: GPC (GamePack Code) for Cronus Zen
- **Compatibility**: Xbox/PlayStation controllers with automatic detection
- **Display**: 128x64 OLED with bitmap graphics and text rendering
- **Memory**: Optimized for Cronus Zen hardware limitations (integer-only arithmetic)
- **Performance**: CPU-optimized combo system to prevent audio glitching

## Setup and Usage

1. Load the `.gpc` file into Cronus Zen Studio's Compiler
2. Configure button mappings on lines 82-92 to your preference
3. Upload to your Cronus Zen device
4. **Use Xbox+LT to disable, Xbox+RT to enable features**
5. **Use LT+Menu (3 lines) to open the settings menu**
6. Navigate menus using D-pad and customize settings as needed

## Controls

- **Xbox+LT**: Disable all features (kill switch)
- **Xbox+RT**: Enable all features
- **LT + Menu**: Opens Main Settings Menu
- **LT + D-pad**: Toggle individual features
- **Menu Navigation**: D-pad up/down, shoulder buttons for value adjustment
- **Circle/B (2x tap)**: Enable script when disabled

---

**⚠️ Disclaimer**: This script is for educational purposes. Use responsibly and in accordance with game terms of service.

**🔧 Configuration**: Make sure to configure button mappings on lines 82-92 to match your preferences before use.

**📝 Credits**: Neptune - Made By Payson. Based on the "Arc" script from YewScripts.
