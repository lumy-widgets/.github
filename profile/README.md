# Lumy Custom Widgets

A community-driven collection of custom widgets for [Lumy](https://lumy.tv) digital signage platform.

> **🎉 NEW: Local Testing Now Available!**  
> Develop widgets with instant feedback - no backend access required!  
> **40x faster** development with our built-in test harness. [Learn more →](https://github.com/lumy-widgets/lumy-widget-hello-world/blob/main/QUICK_START.md)

## 📦 Available Widgets

Browse our collection of community-created widgets:

| Widget | Description | Author | Status |
|--------|-------------|--------|--------|
| [Hello World](https://github.com/lumy-widgets/lumy-widget-hello-world) | Minimal template widget | Lumy Team | ✅ Template |

*More widgets coming soon!*

## 🚀 Getting Started

### For Users

1. **Browse widgets** in this organization
2. **Clone** a widget repository:
   ```bash
   git clone https://github.com/lumy-widgets/widget-name.git
   ```
3. **Build the APK**:
   ```bash
   cd widget-name
   ./gradlew assembleRelease
   ```
4. **Upload to Lumy Manager**:
   - Go to Custom Widgets section
   - Click "Upload Widget"
   - Select the APK from `app/build/outputs/apk/release/app-release.apk`
   - Fill in widget details and upload

### For Developers

**🎉 NEW: Test widgets locally before uploading!** No backend access needed.

1. **Start with the template**:
   ```bash
   git clone https://github.com/lumy-widgets/lumy-widget-hello-world.git
   cd lumy-widget-hello-world
   ```

2. **Test locally** (recommended):
   - Open project in Android Studio
   - Select `test-app` from run configurations
   - Click Run ▶️
   - See your widget instantly with live preview!
   - Edit code → Hot reload (Ctrl+F9) → See changes in 15 seconds
   
   **No Lumy installation required! Works completely offline!**

3. **Build when ready**:
   ```bash
   ./gradlew :app:assembleRelease
   ```

4. **Follow the [Development Guide](https://github.com/lumy-widgets/.github/blob/main/DEVELOPMENT_GUIDE.md)**

5. **Share your widget**:
   - Create a new repository in this organization
   - Submit a pull request to add it to the list above

**⚡ Pro tip:** Use the test-app for rapid development (40x faster than build-upload-test cycle)

## 📚 Resources

- [Quick Start Guide](https://github.com/lumy-widgets/lumy-widget-hello-world/blob/main/QUICK_START.md) - 5-minute setup
- [Widget Development Guide](https://github.com/lumy-widgets/.github/blob/main/DEVELOPMENT_GUIDE.md) - Complete guide
- [Local Testing Guide](https://github.com/lumy-widgets/lumy-widget-hello-world/blob/main/test-app/VISUAL_GUIDE.md) - Test harness walkthrough
- [Contributing Guidelines](https://github.com/lumy-widgets/.github/blob/main/CONTRIBUTING.md) - How to contribute
- [CustomWidget Interface](https://github.com/lumy-widgets/lumy-widget-hello-world/blob/main/app/src/main/kotlin/io/lumy/player/customwidgets/CustomWidget.kt) - Interface reference
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

1. Base your widget on the [hello-world template](https://github.com/lumy-widgets/lumy-widget-hello-world)
2. Test locally using the built-in preview app (see [Quick Start](https://github.com/lumy-widgets/lumy-widget-hello-world/blob/main/QUICK_START.md))
3. Follow our [contribution guidelines](https://github.com/lumy-widgets/.github/blob/main/CONTRIBUTING.md)
4. Create a repository (your account or this organization)
5. Submit a pull request to update this README

## 📄 License

Each widget maintains its own license. Check individual repositories for license information.

## 🔗 Links

- [Lumy Website](https://lumy.tv)
- [Lumy Documentation](https://docs.lumy.tv)
- [Report Issues](https://github.com/lumy-widgets/.github/issues)
