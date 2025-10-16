# 🎵 AudioSampleBuffer

<div align="center">

[![Platform](https://img.shields.io/badge/Platform-iOS-blue.svg)](https://developer.apple.com/ios/)
[![Language](https://img.shields.io/badge/Language-Objective--C%2B%2B-orange.svg)](https://developer.apple.com/library/archive/documentation/Cocoa/Conceptual/ProgrammingWithObjectiveC/Introduction/Introduction.html)
[![Metal](https://img.shields.io/badge/Graphics-Metal-green.svg)](https://developer.apple.com/metal/)
[![License](https://img.shields.io/badge/License-MIT-red.svg)](LICENSE)

**A professional iOS audio visualization & karaoke application with real-time DSP effects**

[English](#english) | [中文](#chinese)

</div>

---

<a name="english"></a>

## ✨ Features

### 🎨 Advanced Visual Effects
- **Metal-Accelerated Rendering**: High-performance GPU-based visualization
  - Galaxy Effect: Stunning space-themed animations
  - Cyberpunk Style: Futuristic neon aesthetics
  - Holographic Display: 3D hologram-like effects
  - Fluid Dynamics: Real-time fluid simulation
  - Lightning & Quantum Effects: Dynamic energy visualization
  - Waveform 3D: Interactive 3D audio waveforms

- **Real-Time Audio Spectrum Analysis**
  - FFT-based frequency spectrum visualization
  - Customizable spectrum bar animations
  - Particle effects synchronized with audio
  - Gradient animations and rotation effects

### 🎤 Karaoke System
- **Professional Karaoke Engine**
  - Segmented recording with BGM playback
  - Real-time vocal monitoring with ear-return
  - Multi-segment recording and editing
  - Playback preview before saving
  - Recording list management

- **Voice Effects Processing**
  - Reverb (Hall/Room/Studio)
  - Echo & Delay effects
  - Pitch shifting (-12 to +12 semitones)
  - Voice gender transformation (Male/Female)
  - Compression & Auto-Gain Control
  - Noise reduction
  - EQ filters (High/Low pass)

### 🎵 Music Library Management
- **Smart Music Organization**
  - Category browsing (All, Recent, Favorites, Genre)
  - File format filtering (MP3, FLAC, NCM)
  - Full-text search (title, artist, album)
  - Multiple sorting options (name, artist, date, play count)
  - Play count tracking
  - Favorite management

- **Multi-Format Support**
  - MP3, M4A, AAC, WAV, FLAC
  - NCM (NetEase Cloud Music) encrypted files
  - Automatic ID3 tag reading
  - Album artwork extraction

### 📝 Lyrics System
- **LRC Lyrics Support**
  - Time-synchronized lyrics display
  - Multiple lyric effect styles
  - Automatic lyrics loading
  - QQ Music & NetEase API integration
  - MP3 ID3 lyrics tag extraction
  - Custom lyrics file support

### 🎛️ Audio Processing
- **Real-Time Audio Engine**
  - Low-latency audio processing
  - AVAudioEngine integration
  - Audio Unit graph architecture
  - Hardware-accelerated DSP

- **Effect Parameters**
  - Independent BGM & vocal volume control
  - Real-time pitch adjustment
  - Playback speed control
  - Professional audio mixing

## 📱 System Requirements

- iOS 13.0+
- Xcode 12.0+
- Devices with A9 chip or later (for Metal effects)
- Microphone permission (for karaoke)

## 🏗️ Architecture

### Core Modules

```
AudioSampleBuffer/
├── Audio/                          # Audio files & resources
├── AudioSampleBuffer/              # Core audio processing
│   ├── AudioSpectrumPlayer.m       # Audio playback & spectrum analysis
│   ├── AudioSpectrumRecorder.m     # Audio recording
│   ├── RealtimeAnalyzer.m          # FFT-based real-time analysis
│   └── SpectrumView.m              # Spectrum visualization view
├── Karaoke/                        # Karaoke system
│   ├── KaraokeAudioEngine.m        # Audio mixing & recording engine
│   ├── VoiceEffectProcessor.mm     # DSP voice effects
│   ├── AudioMixer.m                # Multi-track audio mixing
│   ├── PCMAudioPlayer.m            # PCM audio playback
│   └── DSP/                        # Advanced DSP algorithms
│       ├── DSPBridge.h             # C++/ObjC bridge
│       ├── NoiseReduction.cpp      # Noise reduction algorithm
│       ├── PitchCorrection.cpp     # Pitch correction
│       └── AudioEffect.cpp         # Effect base classes
├── VisualEffects/                  # Metal visual effects
│   ├── VisualEffectManager.m       # Effect management
│   ├── MetalRenderer.m             # Metal rendering engine
│   ├── GalaxyShader.metal          # Galaxy effect shader
│   ├── CyberpunkShader.metal       # Cyberpunk effect shader
│   ├── HolographicShader.metal     # Holographic effect shader
│   ├── FluidShader.metal           # Fluid dynamics shader
│   └── [...]                       # More effect shaders
├── Animations/                     # Animation system
│   ├── AnimationCoordinator.m      # Animation management
│   ├── GradientAnimationManager.m  # Gradient animations
│   ├── ParticleAnimationManager.m  # Particle effects
│   └── SpectrumAnimationManager.m  # Spectrum animations
├── Lyrics/                         # Lyrics system
│   ├── LyricsManager.m             # Lyrics management
│   ├── LRCParser.m                 # LRC file parser
│   ├── LyricsView.m                # Lyrics display view
│   └── QQMusicLyricsAPI.m          # Online lyrics API
├── MusicLibraryManager.m           # Music library management
├── AudioFileFormats.m              # Multi-format audio support
└── ViewController.m                # Main view controller
```

### Key Technologies

- **Audio Processing**
  - AVFoundation framework
  - Audio Unit (AUGraph)
  - Accelerate framework (vDSP)
  - Core Audio

- **Graphics & Rendering**
  - Metal graphics API
  - MetalKit framework
  - Core Animation
  - CALayer & CAEmitterLayer

- **DSP Algorithms**
  - FFT (Fast Fourier Transform)
  - Pitch shifting (PSOLA)
  - Reverb (Comb & All-pass filters)
  - Dynamic range compression
  - Noise gate & reduction

## 🚀 Getting Started

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/AudioSampleBuffer.git
cd AudioSampleBuffer
```

2. Open the project:
```bash
open AudioSampleBuffer.xcodeproj
```

3. Build and run:
   - Select a target device or simulator
   - Press `Cmd + R` to build and run

### Adding Music Files

1. **Via Xcode**: Add MP3/FLAC files to `AudioSampleBuffer/Audio/` folder
2. **Via iTunes**: Use iTunes File Sharing to add files to the app
3. **NCM Files**: Add `.ncm` files and use built-in decryption

### Using Karaoke Mode

1. Tap the **Karaoke** button in the music player
2. Adjust BGM volume and vocal effects
3. Press **Record** to start recording
4. Use **Pause/Resume** for segmented recording
5. Preview your recording before saving
6. Save to the recording list

## 🎛️ Features Guide

### Spectrum Visualization

- **Real-time FFT Analysis**: 60 FPS spectrum updates
- **Multiple Visual Styles**: Bar, line, circular spectrum
- **Customizable Colors**: Gradient and color animations

### Visual Effects

Access advanced visual effects:
1. Tap the effect selector button
2. Choose from 7+ professional effects
3. Adjust parameters in real-time
4. Monitor FPS and performance

**Available Effects:**
- 🌌 Galaxy: Space-themed with stars and nebulae
- 🌃 Cyberpunk: Neon grid and futuristic UI
- 🔮 Holographic: 3D hologram projections
- 💧 Fluid: Interactive fluid dynamics
- ⚡ Lightning: Energy bolts and electricity
- 🌀 Quantum: Quantum field visualization
- 📊 Waveform 3D: Rotating 3D waveforms

### Voice Effects

**Effect Types:**
- **None**: Original voice
- **Hall Reverb**: Large concert hall
- **Room Reverb**: Small room acoustics
- **Echo**: Delay and repeat
- **Robot**: Synthetic voice effect
- **Male Voice**: Lower pitch transformation
- **Female Voice**: Higher pitch transformation
- **Monster**: Deep distorted voice

**Parameters:**
- Reverb Mix: 0-100%
- Echo Delay: 0-1000ms
- Pitch Shift: -12 to +12 semitones
- Mic Volume: 0-200%
- BGM Volume: 0-100%

### Lyrics Display

**Features:**
- Time-synchronized highlighting
- Smooth scrolling animation
- Multiple text effects
- Auto-load from multiple sources

**Priority:**
1. Local `.lrc` files (bundle)
2. Sandbox `.lrc` files
3. ID3 lyrics tags
4. Online API (NetEase/QQ Music)

## 🔧 Configuration

### Performance Settings

Adjust performance in `PerformanceControlPanel`:
- **Target FPS**: 30/60 FPS
- **MSAA**: Off/2x/4x
- **Shader Complexity**: Low/Medium/High

### Audio Settings

Configure in `AudioSpectrumPlayer`:
```objective-c
// Pitch shift (semitones)
player.pitchShift = 0.0;  // -12.0 to +12.0

// Playback rate
player.playbackRate = 1.0;  // 0.5 to 2.0

// Enable lyrics
player.enableLyrics = YES;
```

### Karaoke Settings

Configure in `KaraokeAudioEngine`:
```objective-c
// BGM volume
engine.bgmVolume = 0.5;  // 0.0 to 1.0

// BGM pitch
engine.bgmPitchShift = 0.0;  // -12.0 to +12.0

// Microphone volume
[engine setMicrophoneVolume:1.0];

// Ear-return
[engine setEarReturnEnabled:YES];
[engine setEarReturnVolume:0.5];
```

## 🛠️ Tools

### Lyrics Tools
Located in `Tools/` directory:

- `ncm_lyrics_extractor.py`: Extract lyrics from NCM files
- `decrypt_ncm_to_mp3.py`: Decrypt NCM to MP3
- `lrc_time_adjuster.py`: Adjust LRC timing
- `sync_lyrics_to_sandbox.sh`: Sync lyrics to app sandbox

### Usage Example:
```bash
# Extract lyrics from NCM
python3 Tools/ncm_lyrics_extractor.py /path/to/song.ncm

# Decrypt NCM file
python3 Tools/decrypt_ncm_to_mp3.py /path/to/song.ncm
```

## 📊 Performance

- **Rendering**: 60 FPS on iPhone X and newer
- **Audio Latency**: < 20ms for real-time effects
- **Memory Usage**: ~50-100MB typical
- **Battery Optimization**: Auto-pause Metal rendering in background

## 🐛 Known Issues

- NCM decryption may fail on some protected files
- Metal effects not available on older devices (< A9)
- Some lyrics files may require manual timing adjustment

## 🤝 Contributing

Contributions are welcome! Please feel free to submit issues and pull requests.

### Development Guidelines

1. Follow Objective-C coding conventions
2. Comment code in English or Chinese
3. Test on both iPhone and iPad
4. Ensure performance benchmarks are met
5. Update documentation for new features

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- FFT implementation based on Accelerate framework
- DSP algorithms inspired by classic audio processing papers
- Metal shaders adapted from various open-source projects
- NCM decryption algorithm from community research

## 📮 Contact

For questions or suggestions:
- Create an issue on GitHub
- Email: your.email@example.com

---

<a name="chinese"></a>

# 🎵 AudioSampleBuffer

## ✨ 功能特性

### 🎨 高级视觉效果
- **Metal 加速渲染**：基于 GPU 的高性能可视化
  - 银河效果：惊艳的太空主题动画
  - 赛博朋克风格：未来感霓虹美学
  - 全息显示：3D 全息投影效果
  - 流体动力学：实时流体模拟
  - 闪电与量子效果：动态能量可视化
  - 3D 波形：交互式 3D 音频波形

- **实时音频频谱分析**
  - 基于 FFT 的频率谱可视化
  - 可自定义的频谱条动画
  - 与音频同步的粒子效果
  - 渐变动画和旋转效果

### 🎤 卡拉OK系统
- **专业卡拉OK引擎**
  - 支持 BGM 播放的分段录音
  - 实时人声监听与耳返
  - 多段录音与编辑
  - 保存前预览播放
  - 录音列表管理

- **人声效果处理**
  - 混响（大厅/房间/录音室）
  - 回声与延迟效果
  - 音高变调（-12 到 +12 半音）
  - 变声效果（男声/女声）
  - 压缩器与自动增益控制
  - 降噪处理
  - 均衡器滤波（高/低通）

### 🎵 音乐库管理
- **智能音乐组织**
  - 分类浏览（全部、最近、收藏、流派）
  - 文件格式筛选（MP3、FLAC、NCM）
  - 全文搜索（标题、艺术家、专辑）
  - 多种排序选项（名称、艺术家、日期、播放次数）
  - 播放次数跟踪
  - 收藏管理

- **多格式支持**
  - MP3、M4A、AAC、WAV、FLAC
  - NCM（网易云音乐）加密文件
  - 自动读取 ID3 标签
  - 专辑封面提取

### 📝 歌词系统
- **LRC 歌词支持**
  - 时间同步歌词显示
  - 多种歌词特效样式
  - 自动加载歌词
  - QQ音乐与网易云API集成
  - MP3 ID3 歌词标签提取
  - 自定义歌词文件支持

### 🎛️ 音频处理
- **实时音频引擎**
  - 低延迟音频处理
  - AVAudioEngine 集成
  - Audio Unit 图形架构
  - 硬件加速 DSP

- **效果参数**
  - 独立 BGM 与人声音量控制
  - 实时音高调整
  - 播放速度控制
  - 专业音频混音

## 📱 系统要求

- iOS 13.0+
- Xcode 12.0+
- A9 芯片或更新设备（Metal 效果）
- 麦克风权限（卡拉OK功能）

## 🏗️ 架构说明

### 核心模块

```
AudioSampleBuffer/
├── Audio/                          # 音频文件与资源
├── AudioSampleBuffer/              # 核心音频处理
│   ├── AudioSpectrumPlayer.m       # 音频播放与频谱分析
│   ├── AudioSpectrumRecorder.m     # 音频录制
│   ├── RealtimeAnalyzer.m          # 基于FFT的实时分析
│   └── SpectrumView.m              # 频谱可视化视图
├── Karaoke/                        # 卡拉OK系统
│   ├── KaraokeAudioEngine.m        # 音频混音与录音引擎
│   ├── VoiceEffectProcessor.mm     # DSP人声效果
│   ├── AudioMixer.m                # 多轨音频混音器
│   ├── PCMAudioPlayer.m            # PCM音频播放器
│   └── DSP/                        # 高级DSP算法
│       ├── DSPBridge.h             # C++/ObjC桥接
│       ├── NoiseReduction.cpp      # 降噪算法
│       ├── PitchCorrection.cpp     # 音高校正
│       └── AudioEffect.cpp         # 效果基类
├── VisualEffects/                  # Metal视觉效果
│   ├── VisualEffectManager.m       # 效果管理器
│   ├── MetalRenderer.m             # Metal渲染引擎
│   ├── GalaxyShader.metal          # 银河效果着色器
│   ├── CyberpunkShader.metal       # 赛博朋克着色器
│   ├── HolographicShader.metal     # 全息效果着色器
│   ├── FluidShader.metal           # 流体动力学着色器
│   └── [...]                       # 更多效果着色器
├── Animations/                     # 动画系统
│   ├── AnimationCoordinator.m      # 动画管理器
│   ├── GradientAnimationManager.m  # 渐变动画
│   ├── ParticleAnimationManager.m  # 粒子效果
│   └── SpectrumAnimationManager.m  # 频谱动画
├── Lyrics/                         # 歌词系统
│   ├── LyricsManager.m             # 歌词管理器
│   ├── LRCParser.m                 # LRC文件解析器
│   ├── LyricsView.m                # 歌词显示视图
│   └── QQMusicLyricsAPI.m          # 在线歌词API
├── MusicLibraryManager.m           # 音乐库管理器
├── AudioFileFormats.m              # 多格式音频支持
└── ViewController.m                # 主视图控制器
```

### 关键技术

- **音频处理**
  - AVFoundation 框架
  - Audio Unit (AUGraph)
  - Accelerate 框架 (vDSP)
  - Core Audio

- **图形渲染**
  - Metal 图形API
  - MetalKit 框架
  - Core Animation
  - CALayer & CAEmitterLayer

- **DSP 算法**
  - FFT（快速傅里叶变换）
  - 音高变换（PSOLA）
  - 混响（梳状滤波器与全通滤波器）
  - 动态范围压缩
  - 噪声门与降噪

## 🚀 快速开始

### 安装

1. 克隆仓库：
```bash
git clone https://github.com/yourusername/AudioSampleBuffer.git
cd AudioSampleBuffer
```

2. 打开项目：
```bash
open AudioSampleBuffer.xcodeproj
```

3. 构建并运行：
   - 选择目标设备或模拟器
   - 按 `Cmd + R` 构建并运行

### 添加音乐文件

1. **通过 Xcode**：将 MP3/FLAC 文件添加到 `AudioSampleBuffer/Audio/` 文件夹
2. **通过 iTunes**：使用 iTunes 文件共享添加文件到应用
3. **NCM 文件**：添加 `.ncm` 文件并使用内置解密功能

### 使用卡拉OK模式

1. 在音乐播放器中点击 **卡拉OK** 按钮
2. 调整 BGM 音量和人声效果
3. 按 **录音** 开始录制
4. 使用 **暂停/继续** 进行分段录音
5. 保存前预览您的录音
6. 保存到录音列表

## 🎛️ 功能指南

### 频谱可视化

- **实时 FFT 分析**：60 FPS 频谱更新
- **多种视觉样式**：条形、线形、环形频谱
- **可自定义颜色**：渐变和颜色动画

### 视觉效果

访问高级视觉效果：
1. 点击效果选择器按钮
2. 从 7+ 种专业效果中选择
3. 实时调整参数
4. 监控 FPS 和性能

**可用效果：**
- 🌌 银河：太空主题，带有星星和星云
- 🌃 赛博朋克：霓虹网格和未来感界面
- 🔮 全息：3D 全息投影
- 💧 流体：交互式流体动力学
- ⚡ 闪电：能量闪电和电流
- 🌀 量子：量子场可视化
- 📊 3D波形：旋转的 3D 波形

### 人声效果

**效果类型：**
- **无**：原始声音
- **大厅混响**：大型音乐厅
- **房间混响**：小房间声学
- **回声**：延迟和重复
- **机器人**：合成语音效果
- **男声**：降低音高变换
- **女声**：提高音高变换
- **怪兽**：深沉失真声音

**参数：**
- 混响混合：0-100%
- 回声延迟：0-1000ms
- 音高变调：-12 到 +12 半音
- 麦克风音量：0-200%
- BGM 音量：0-100%

### 歌词显示

**功能：**
- 时间同步高亮
- 平滑滚动动画
- 多种文本效果
- 从多个来源自动加载

**优先级：**
1. 本地 `.lrc` 文件（bundle）
2. 沙盒 `.lrc` 文件
3. ID3 歌词标签
4. 在线 API（网易云/QQ音乐）

## 🔧 配置

### 性能设置

在 `PerformanceControlPanel` 中调整性能：
- **目标 FPS**：30/60 FPS
- **MSAA**：关闭/2x/4x
- **着色器复杂度**：低/中/高

### 音频设置

在 `AudioSpectrumPlayer` 中配置：
```objective-c
// 音高变调（半音数）
player.pitchShift = 0.0;  // -12.0 到 +12.0

// 播放速率
player.playbackRate = 1.0;  // 0.5 到 2.0

// 启用歌词
player.enableLyrics = YES;
```

### 卡拉OK设置

在 `KaraokeAudioEngine` 中配置：
```objective-c
// BGM 音量
engine.bgmVolume = 0.5;  // 0.0 到 1.0

// BGM 音高
engine.bgmPitchShift = 0.0;  // -12.0 到 +12.0

// 麦克风音量
[engine setMicrophoneVolume:1.0];

// 耳返
[engine setEarReturnEnabled:YES];
[engine setEarReturnVolume:0.5];
```

## 🛠️ 工具

### 歌词工具
位于 `Tools/` 目录：

- `ncm_lyrics_extractor.py`：从 NCM 文件提取歌词
- `decrypt_ncm_to_mp3.py`：解密 NCM 到 MP3
- `lrc_time_adjuster.py`：调整 LRC 时间轴
- `sync_lyrics_to_sandbox.sh`：同步歌词到应用沙盒

### 使用示例：
```bash
# 从 NCM 提取歌词
python3 Tools/ncm_lyrics_extractor.py /path/to/song.ncm

# 解密 NCM 文件
python3 Tools/decrypt_ncm_to_mp3.py /path/to/song.ncm
```

## 📊 性能

- **渲染**：iPhone X 及更新设备上 60 FPS
- **音频延迟**：实时效果 < 20ms
- **内存使用**：典型 ~50-100MB
- **电池优化**：后台自动暂停 Metal 渲染

## 🐛 已知问题

- 某些受保护的 NCM 文件解密可能失败
- 旧设备（< A9）不支持 Metal 效果
- 某些歌词文件可能需要手动调整时间轴

## 🤝 贡献

欢迎贡献！请随时提交问题和拉取请求。

### 开发指南

1. 遵循 Objective-C 编码规范
2. 用中文或英文注释代码
3. 在 iPhone 和 iPad 上测试
4. 确保满足性能基准
5. 为新功能更新文档

## 📄 许可证

本项目采用 MIT 许可证 - 详见 [LICENSE](LICENSE) 文件。

## 🙏 致谢

- FFT 实现基于 Accelerate 框架
- DSP 算法受经典音频处理论文启发
- Metal 着色器改编自各种开源项目
- NCM 解密算法来自社区研究

## 📮 联系方式

如有问题或建议：
- 在 GitHub 上创建 issue
- 邮箱：your.email@example.com

---

<div align="center">

**⭐ 如果这个项目对你有帮助，请给一个星标！**

Made with ❤️ by Audio Enthusiasts

</div>
