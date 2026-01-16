# MPV Configuration Collection

A comprehensive MPV player configuration tailored for high-quality video playback with advanced upscaling, HDR support, and intuitive controls.

## ✨ Features

### 🎬 **Video Enhancement**
- **Multiple Upscaling Profiles**: NNEDI3, FSRCNNX, Ravu-Zoom, Anime4K optimized for different content types
- **HDR Support**: Automatic HDR detection and tone mapping with customizable parameters
- **Smart Downscaling**: 4K to 1080p downscaling using SSIM-based algorithms
- **Debanding**: Configurable debanding filters with medium/strong presets
- **GPU Acceleration**: Vulkan/OpenGL support with hardware decoding (vaapi)

### 🔊 **Audio Processing**
- **Automatic Normalization**: Dialogue enhancement and volume normalization
- **Channel Downmixing**: Intelligent 5.1/7.1 to stereo conversion
- **Audio Pitch Correction**: Maintains pitch during speed changes
- **Multi-language Support**: Automatic English subtitle/audio preference

### 📋 **UI & Controls**
- **uosc Integration**: Modern on-screen controls with intuitive menus
- **Custom Keybindings**: Logical shortcuts for common actions
- **Subtitle Styling**: Clear Sans font with Nordic color scheme
- **OSD Customization**: JetBrains Mono font with bold styling

## 🚀 Quick Start

1. **Clone or download** this configuration
2. **Place files** in your MPV config directory:
   - Linux: `~/.config/mpv/`
   - Windows: `%APPDATA%/mpv/`
   - macOS: `~/.config/mpv/`
3. **Download shaders** (optional but recommended):
   - Place in `~~/shaders/` directory
   - Recommended: FSRCNNX, NNEDI3, Anime4K variants

## 📁 File Structure

mpv/
├── input.conf          # Keybindings and shortcuts
├── mpv.conf           # Main configuration
├── fonts.conf         # Font configuration
├── profiles.conf      # Video/audio profiles
├── shaders/           # GLSL shaders directory
│   ├── F8.glsl
│   ├── F16.glsl
│   ├── nnedi3_*.glsl
│   └── ...
└── cache/             # Cache directories
    ├── watch_later/
    └── shaders_cache/

## 🎮 Keybindings

### Basic Controls
- `SPACE` / `MBTN_LEFT` - Play/Pause
- `LEFT`/`RIGHT` - Seek 5 seconds
- `UP`/`DOWN` - Volume control
- `ESC` - Toggle fullscreen
- `TAB` - Toggle UI visibility
- `q` - Exit and save position

### Menu Navigation
- `F4` - Open menu
- `F5` - Audio menu
- `F6` - Subtitles menu
- `F7` - Video shaders
- `F8` - Toggle deblocking
- `F9` - Auto-deinterlace

### Shader Profiles (Quick Toggle)
- `CTRL+1` - FSRCNNX (HD live action)
- `CTRL+2` - FSRCNNX+ (SD live action)
- `CTRL+3` - Ravu-Zoom
- `CTRL+4` - Ani4K (Anime)
- `CTRL+5` - AniSD (SD Anime)
- `CTRL+6` - Anime4K
- `CTRL+7` - NNEDI3
- `CTRL+8` - NNEDI3+

### Subtitle Controls
- `y` - Load subtitles
- `Y` - Select subtitle track
- `z`/`x` - Adjust subtitle timing
- `CTRL++`/`CTRL+-` - Subtitle size

## 🎨 Profiles

### Upscaling Profiles
1. **NNEDI3** - General purpose, balanced quality
2. **FSRCNNX** - HD live action content
3. **Ravu-Zoom** - Zoom interpolation
4. **Anime4K Variants** - Anime-specific optimization

### Conditional Profiles
- **HDR**: Automatic HDR tone mapping
- **4k-Downscaling**: High-quality downscaling from 4K
- **Audio Downmixing**: 5.1/7.1 to stereo conversion

## ⚙️ Configuration Notes

### GPU Backend
Default is Vulkan (`gpu-api=vulkan`). If experiencing issues:
# Change to OpenGL:
gpu-api=opengl

### Hardware Decoding
Uses `vaapi-copy` for stability. If your hardware supports it, you can try:
hwdec=vaapi

### Cache Management
- Watch later positions: `~~/cache/watch_later/`
- Shader cache: `~~/cache/shaders_cache/`

## 🎯 Recommended Shaders

Download these for full functionality:
- **FSRCNNX** (`F8.glsl`, `F16.glsl`) - Best for live action
- **NNEDI3** (`nnedi3_*.glsl`) - General upscaling
- **Anime4K** variants - Anime optimization
- **SSIM** (`ssimsr.glsl`, `ssimds.glsl`) - Scaling algorithms

## 🔧 Troubleshooting

### Common Issues

1. **Shader errors**: Ensure shaders are in `~~/shaders/` directory
2. **HDR washed out**: Check display supports HDR, adjust `target-peak`
3. **Audio distortion**: Try different downmixing profiles
4. **Performance issues**: 
   - Switch to OpenGL if Vulkan unstable
   - Reduce debanding iterations
   - Use lighter shader profiles

### Debugging
- Press `/` to open console
- Check `mpv.log` for detailed errors
- Disable profiles one by one to isolate issues

## 🤝 Contributing

Feel free to:
1. Report issues with specific media types
2. Suggest new shader combinations
3. Improve existing profiles
4. Add documentation for your hardware setup

## 📄 License

This configuration is provided as-is. MPV is licensed under GPL. Shaders have their own respective licenses.

## 🙏 Credits

- MPV Developers for an amazing player
- uosc developers for modern UI
- Various shader authors (FSRCNNX, NNEDI3, Anime4K communities)
- FontConfig for system font management

---

**Note**: This configuration is optimized for a 1440p display with HDR support. Adjust `display_width`, `display_height`, and HDR parameters for your specific setup.
