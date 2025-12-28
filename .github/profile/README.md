# Lumy Custom Widgets

A community-driven collection of custom widgets for [Lumy](https://lumy.tv) digital signage platform.

## 📦 Available Widgets

Browse our collection of community-created widgets:

| Widget | Description | Author | Status |
|--------|-------------|--------|--------|
| [Hello World](lumy-widget-hello-world) | Minimal template widget | Lumy Team | ✅ Template |

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

1. **Start with the template**:
   ```bash
   git clone https://github.com/lumy-widgets/lumy-widget-hello-world.git
   cd lumy-widget-hello-world
   ```

2. **Follow the [Development Guide](https://github.com/lumy-widgets/.github/blob/main/.github/DEVELOPMENT_GUIDE.md)**

3. **Share your widget**:
   - Create a new repository in this organization
   - Submit a pull request to add it to the list above

## 📚 Resources

- [Widget Development Guide](https://github.com/lumy-widgets/.github/blob/main/.github/DEVELOPMENT_GUIDE.md)
- [CustomWidget Interface](https://github.com/lumy-widgets/lumy-widget-hello-world/blob/main/app/src/main/kotlin/io/lumy/player/customwidgets/CustomWidget.kt)
- [Lumy Documentation](https://docs.lumy.tv)

## 🤝 Contributing

We welcome contributions! To add your widget:

1. Create a new repository in this organization
2. Base it on the [hello-world template](lumy-widget-hello-world)
3. Follow our [contribution guidelines](https://github.com/lumy-widgets/.github/blob/main/.github/CONTRIBUTING.md)
4. Submit a pull request to update this README

## 📄 License

Each widget maintains its own license. Check individual repositories for license information.

## 🔗 Links

- [Lumy Website](https://lumy.tv)
- [Lumy Documentation](https://docs.lumy.tv)
- [Report Issues](https://github.com/lumy-widgets/.github/issues)

