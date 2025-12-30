# Contributing to Lumy Widgets

Thank you for contributing to the Lumy widget community!

## Quick Start: Sharing Your Widget

**Easiest way:**
1. Create a public repository on your GitHub account named `lumy-widget-{name}`
2. Push your widget code with a README and `widget-metadata.json`
3. Open an issue at https://github.com/lumy-widgets/.github/issues to request it be added to the gallery

**See detailed steps below ↓**

## How to Contribute

### 1. Create Your Widget

- Start with the [hello-world template](https://github.com/lumy-widgets/lumy-widget-hello-world)
- Follow the [development guide](DEVELOPMENT_GUIDE.md)
- Test thoroughly before sharing

## Local Development & Testing

### ⚠️ Important for Contributors

As a contributor, you **do NOT need access** to the Lumy codebase or backend. The widget template includes everything you need to develop and test locally.

### Development Environment Setup

1. **Clone the hello-world template:**
   ```bash
   git clone https://github.com/lumy-widgets/lumy-widget-hello-world.git my-widget
   cd my-widget
   ```

2. **Open in Android Studio:**
   - File → Open → Select the project folder
   - Wait for Gradle sync to complete

3. **Run the test harness:**
   - Select **`test-app`** from the run configuration dropdown (top toolbar)
   - Click the Run button (▶️)
   - Choose an emulator or connected device

### Testing Your Widget

The template includes a **standalone preview app** (`test-app/`) that lets you:

- ✅ See your widget rendered in real-time
- ✅ Test different configuration values
- ✅ Iterate quickly without uploading
- ✅ Debug issues using logcat
- ✅ Work completely offline

**No Lumy installation required! No backend needed!**

### Development Workflow

```
1. Edit widget code (app/src/.../YourWidget.kt)
       ↓
2. Hot reload in test-app (Ctrl+F9 / Cmd+R)
       ↓
3. Verify it looks correct
       ↓
4. Test different configs
       ↓
5. Build APK (./gradlew :app:assembleRelease)
       ↓
6. Upload to Lumy platform
       ↓
7. Share on GitHub
```

### Preview App Customization

To test your specific widget, edit `test-app/src/main/kotlin/com/lumy/widgettest/MainActivity.kt`:

```kotlin
// Change this line to your widget class:
val widget = remember { YourCustomWidget() }

// Update mock config to match your schema:
var mockConfig by remember {
    mutableStateOf(mapOf(
        "yourOption1" to "value1",
        "yourOption2" to "value2"
    ))
}
```

### Why This Matters

- 🚀 **Faster development** - See changes instantly
- 🔒 **No access needed** - Develop independently
- 🐛 **Easier debugging** - Test in isolation
- ✅ **Higher quality** - Catch issues before upload
- 📦 **Self-contained** - Everything in one repo

### Common Testing Scenarios

**Test different screen sizes:**
- Rotate device (portrait/landscape)
- Test on phone, tablet, and TV emulators

**Test configuration:**
- Empty values
- Invalid values (wrong format, out of range)
- Extreme values (very long text, huge numbers)

**Test performance:**
- Watch for lag/stuttering
- Check memory usage in Android Profiler
- Test with animations/timers

**Test error handling:**
- Remove required config values
- Provide wrong data types
- Simulate network failures (if fetching data)

### When to Upload to Lumy

Only upload your widget APK to Lumy when:

- ✅ Widget displays correctly in test-app
- ✅ All configuration options work
- ✅ No crashes or errors in logcat
- ✅ Tested on different screen sizes
- ✅ Handles invalid config gracefully
- ✅ Performance is acceptable

### Debugging Tips

**View logs while testing:**
```bash
adb logcat | grep -E "HelloWorldWidget|YourWidgetName"
```

**Common issues in test-app:**

| Issue | Solution |
|-------|----------|
| Widget class not found | Update import in MainActivity.kt |
| Compose crash | Check all dependencies are in both modules |
| Config not updating | Trigger recomposition by modifying state |
| Hot reload not working | Do a full rebuild (Build → Rebuild Project) |

### Need Help?

- 📖 Check [DEVELOPMENT_GUIDE.md](DEVELOPMENT_GUIDE.md)
- 💬 Ask in [GitHub Discussions](https://github.com/orgs/lumy-widgets/discussions)
- 🐛 Report issues: https://github.com/lumy-widgets/.github/issues

### 2. Share Your Widget

#### Option A: Create Repository in Your Own GitHub Account (Recommended for New Contributors)

1. **Create a new repository** on your GitHub account:
   - Go to https://github.com/new
   - Repository name: `lumy-widget-{your-widget-name}` (e.g., `lumy-widget-weather`)
   - Make it **Public**
   - **Don't** initialize with README (you already have files)
   - Click "Create repository"

2. **Push your widget code**:
   ```bash
   cd your-widget-directory
   git init
   git add .
   git commit -m "Initial commit: My Lumy widget"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/lumy-widget-NAME.git
   git push -u origin main
   ```

3. **Include required files and request listing**:
   - ✅ Source code (all Kotlin files)
   - ✅ `README.md` with:
     - Widget description and features
     - Configuration options
     - Build instructions
     - Screenshots or demo images
   - ✅ `widget-metadata.json`
   - ✅ `.gitignore` (from template)
   
   Then **open an issue** at https://github.com/lumy-widgets/.github/issues to request your widget be added to the organization gallery:
   - Title: "Add widget: [Your Widget Name]"
   - Include:
     - Link to your repository
     - Brief description
     - Screenshot
   - Organization maintainers will review and add it to the gallery
   - The widget will appear in the [Available Widgets table](https://github.com/lumy-widgets) on the organization profile

#### Option B: Transfer Repository to Organization (For Trusted Contributors)

If you're already a member of the `lumy-widgets` organization:

1. **Create repository** in the organization:
   - Go to https://github.com/organizations/lumy-widgets/repositories/new
   - Or use GitHub CLI: `gh repo create lumy-widgets/lumy-widget-NAME --public`
   - Repository name: `lumy-widget-{your-widget-name}`

2. **Push your code** (same as Option A, step 2)

3. **Submit PR to organization README**:
   - Fork the `.github` repository
   - Edit `.github/profile/README.md`
   - Add your widget to the "Available Widgets" table
   - Submit a pull request

#### Option C: Fork and Customize Template

1. **Fork the template**:
   - Go to https://github.com/lumy-widgets/lumy-widget-hello-world
   - Click "Fork" → Create a new fork
   - Choose your account or the organization (if you have access)

2. **Rename the repository**:
   - Go to Settings → General → Repository name
   - Change to `lumy-widget-{your-name}`

3. **Customize and push** your changes

4. **Follow steps from Option A or B** to get it listed

## Guidelines

- **Code Quality**: Follow Kotlin best practices
- **Documentation**: Include clear README and comments
- **Testing**: Test your widget before sharing
- **Naming**: Use clear, descriptive names (format: `lumy-widget-{name}`)

## Questions?

Open an issue in the [organization discussions](https://github.com/orgs/lumy-widgets/discussions) or contact the maintainers.

