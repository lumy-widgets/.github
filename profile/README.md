# Lumy Widgets

Official and community widgets for the [Lumy](https://lumy.tv) digital signage platform.

> **🎉 NEW: Local Testing Now Available!**  
> Develop widgets with instant feedback - no backend access required!  
> **40x faster** development with our built-in test harness. [Learn more →](https://github.com/lumy-signage/lumy-widget-template/blob/main/README.md)

## 📦 Official Internal Widgets

These widgets are bundled in the Lumy Android app and available to all users:

| Widget | Description | Repository | Download |
|--------|-------------|------------|----------|
| [Clock Widget](https://github.com/lumy-signage/lumy-widget-clock) | Multiple clock styles (digital, analog, word clock, etc.) | [Source](https://github.com/lumy-signage/lumy-widget-clock) | [📥 Releases](https://github.com/lumy-signage/lumy-widget-clock/releases) |
| [Queue Display Widget](https://github.com/lumy-signage/lumy-widget-queue) | Queue management system for service counters | [Source](https://github.com/lumy-signage/lumy-widget-queue) | [📥 Releases](https://github.com/lumy-signage/lumy-widget-queue/releases) |
| [Message Slider Widget](https://github.com/lumy-signage/lumy-widget-message-slider) | Scrolling messages with multiple sources (manual, RSS, JSON) | [Source](https://github.com/lumy-signage/lumy-widget-message-slider) | [📥 Releases](https://github.com/lumy-signage/lumy-widget-message-slider/releases) |

**Internal widgets are:**
- ✅ Compiled directly into the Lumy Android app
- ✅ Available to all users without APK download
- ✅ Optimized for performance
- ✅ Open source under MIT license
- ✅ Maintained by Lumy team and community
- ✅ **Can also be built as standalone APKs** for testing DEX loading or use as examples

## 🎨 Community Custom Widgets

Browse our collection of community-created widgets:

| Widget | Description | Author | Download |
|--------|-------------|--------|----------|
| [Widget Template](https://github.com/lumy-signage/lumy-widget-template) | Complete template with setup scripts, build automation, and test app | Lumy Team | 🔨 Template |

*More widgets coming soon! Share yours by following our [Contributing Guide](https://github.com/lumy-signage/.github/blob/main/CONTRIBUTING.md).*

**Legend:**
- 📥 **Pre-built APK available** - Download and use immediately (no coding required)
- 🔨 **Source only** - Requires Android Studio and build tools (for developers)

## 🚀 Getting Started

### For Users (Non-Technical)

**Want to use widgets without coding?** Download pre-built APKs directly:

1. **Browse widgets** in this organization
2. **Download the APK**:
   - Go to the widget's repository (e.g., [Clock Widget](https://github.com/lumy-signage/lumy-widget-clock))
   - Click on **Releases** (right sidebar)
   - Download the latest `.apk` file
   
   > 💡 **Note:** If no release exists, request a build in the widget's Issues tab.

3. **Upload to Lumy Manager**:
   - Go to Custom Widgets section
   - Click "Upload Widget"
   - Select the downloaded APK file
   - Fill in widget details and upload

**No programming or build tools required!** ✨

---

### For Developers

**🎉 NEW: Test widgets locally before uploading!** No backend access needed.

#### Create Your Own Widget

1. **Start with the template**:
   ```bash
   git clone https://github.com/lumy-signage/lumy-widget-template.git my-widget
   cd my-widget
   ```

2. **Setup Android SDK** (automatic):
   ```bash
   # Windows
   .\setup-android-sdk.bat
   
   # Linux/Mac
   ./setup-android-sdk.sh
   ```

3. **Test locally** (recommended):
   - Open project in Android Studio
   - Select `test-app` from run configurations
   - Click Run ▶️
   - See your widget instantly with live preview!
   - Edit code → Hot reload (Ctrl+F9) → See changes in 15 seconds
   
   **No Lumy installation required! Works completely offline!**

4. **Build when ready**:
   ```bash
   # Windows
   .\build-widget.bat
   
   # Linux/Mac
   chmod +x build-widget.sh
   ./build-widget.sh
   ```

5. **Create a Release** with the built APK:
   - Tag your version (e.g., `v1.0.0`)
   - Create GitHub Release
   - Upload the APK file
   - **This allows non-technical users to download and use your widget!** ✨

6. **Share your widget**:
   - Create a repository (your account or this organization)
   - Open an issue to request it be added to the gallery
   - See [Contributing Guide](https://github.com/lumy-signage/.github/blob/main/CONTRIBUTING.md)

**⚡ Pro tip:** Use the test-app for rapid development (40x faster than build-upload-test cycle)

#### Build APK for Others (Contributors)

Help non-technical users by building widgets:

1. Clone any widget repository
2. Build: `./gradlew :app:assembleRelease`
3. Create a GitHub Release with the APK file
4. Non-technical users can now download without building!

## 🌟 Widget Promotion

High-quality custom widgets can be promoted to internal widgets (bundled in the app)!

**Benefits of promotion:**
- Available to all Lumy users
- Better performance (compiled into app)
- Official support and maintenance
- Recognition as official widget
- Open source contribution

**How to get promoted:**
1. Create a high-quality custom widget
2. Demonstrate usefulness and demand
3. Submit for review (open GitHub issue)
4. Pass quality and security review
5. Agree to open source under MIT license

See the [Widget Promotion Guide](https://github.com/lumy-signage/.github/blob/main/WIDGET_PROMOTION_GUIDE.md) for details.

## 📚 Resources

- [Widget Template](https://github.com/lumy-signage/lumy-widget-template) - Complete template to start developing
- [Widget Development Guide](https://github.com/lumy-signage/.github/blob/main/WIDGET_DEVELOPMENT_GUIDE.md) - Complete guide
- [Widget Promotion Guide](https://github.com/lumy-signage/.github/blob/main/WIDGET_PROMOTION_GUIDE.md) - Promotion process
- [Widget Schema Specification](https://github.com/lumy-signage/.github/blob/main/WIDGET_SCHEMA_SPECIFICATION.md) - Schema format
- [Contributing Guidelines](https://github.com/lumy-signage/.github/blob/main/CONTRIBUTING.md) - How to contribute
- [CustomWidget Interface](https://github.com/lumy-signage/lumy-widget-template/blob/main/app/src/main/kotlin/io/lumy/player/customwidgets/CustomWidget.kt) - Interface reference
- [Lumy Documentation](https://docs.lumy.tv) - Platform docs

## 🤝 Contributing

We welcome contributions! Widget development is now easier than ever with our local test harness.

### Quick Start for New Contributors

1. **Clone the template** → Open in Android Studio → Run `test-app`
2. **See it working instantly** (no Lumy backend needed!)
3. **Edit code** → Hot reload → See changes in 15 seconds
4. **Build APK** when satisfied
5. **Upload to Lumy** and share!

**Total time from zero to first widget: ~15 minutes** ⚡

### Detailed Steps

1. Base your widget on the [lumy-widget-template](https://github.com/lumy-signage/lumy-widget-template)
2. Test locally using the built-in test app (see template README)
3. Follow our [contribution guidelines](https://github.com/lumy-signage/.github/blob/main/CONTRIBUTING.md)
4. Create a repository (your account or this organization)
5. Submit a pull request to update this README

## 📄 License

Each widget maintains its own license. Check individual repositories for license information.

## 🔗 Links

- [Lumy Website](https://lumy.tv)
- [Lumy Documentation](https://docs.lumy.tv)
- [Report Issues](https://github.com/lumy-signage/.github/issues)
