# Lumy Widget Development Guide

Complete guide for developing custom widgets for Lumy digital signage platform.

## Table of Contents

1. [Overview](#overview)
2. [Getting Started](#getting-started)
3. [Project Setup](#project-setup)
4. [Implementing Your Widget](#implementing-your-widget)
5. [Configuration Schema](#configuration-schema)
6. [Building and Testing](#building-and-testing)
7. [Sharing Your Widget](#sharing-your-widget)

## Overview

Custom widgets allow you to extend Lumy with your own interactive components using Jetpack Compose. Your widget will be:

- Dynamically loaded at runtime
- Rendered alongside standard media content
- Configurable through a JSON schema

**Key Points:**
- Widgets are built as standalone Android APK files
- They must implement the `CustomWidget` interface
- They're loaded using Android's `DexClassLoader`
- All dependencies must be bundled in your APK

## Getting Started

### 1. Clone the Template

```bash
git clone https://github.com/lumy-signage/lumy-widget-template.git my-widget
cd my-widget
```

### 2. Setup Android SDK

**Quick Setup (Automatic):**
```bash
# Windows (PowerShell or CMD)
.\setup-android-sdk.bat

# Linux/Mac
chmod +x setup-android-sdk.sh
./setup-android-sdk.sh
```

This automatically detects and configures your Android SDK location.

**Manual Setup (if needed):**
```bash
# Copy example file
cp local.properties.example local.properties

# Edit local.properties and set your SDK path:
# Windows: sdk.dir=C\:\\Users\\YourUsername\\AppData\\Local\\Android\\Sdk
# macOS: sdk.dir=/Users/YourUsername/Library/Android/sdk
# Linux: sdk.dir=/home/YourUsername/Android/Sdk
```

### 3. Test Locally First

**Before making any changes, run the test app:**

1. Open the project in Android Studio
2. Select **`test-app`** from the run configuration dropdown
3. Click Run (▶️)
4. See the widget in action instantly!

This test app is your **development environment**. You'll use it to test your widget locally before uploading to Lumy.

### 4. Update Project Configuration

Edit `app/build.gradle.kts`:

- Change `namespace` to your package
- Update `versionName` and `versionCode`

Edit `widget-metadata.json`:

- Update `name`, `description`, `author`
- Update `className` to match your widget class

### 5. Rename and Customize

- Rename widget class to your widget name
- Update package structure
- Implement your widget logic

## Implementing Your Widget

### Required Interface

Your widget class must implement `CustomWidget`:

```kotlin
class MyWidget : CustomWidget {
    override fun getName(): String = "My Widget"
    override fun getVersion(): String = "1.0.0"
    override fun getDescription(): String? = "Widget description"
    
    @Composable
    override fun RenderWidget(config: Map<String, String>) {
        // Your UI here
    }
}
```

### Configuration Schema

Define configuration options using JSON Schema:

```kotlin
override fun getConfigSchema(): String? {
    return """
    {
      "type": "object",
      "properties": {
        "backgroundColor": {
          "type": "string",
          "title": "Background Color",
          "format": "color",
          "default": "#000000"
        },
        "refreshInterval": {
          "type": "integer",
          "title": "Refresh Interval (seconds)",
          "minimum": 10,
          "default": 60
        }
      }
    }
    """.trimIndent()
}
```

## Building and Testing

### Local Testing (Recommended)

**Use the built-in test app for rapid development:**

1. **Run test-app:**
   - Select `test-app` from run configurations
   - Click Run
   - Widget renders instantly
   - **40x faster than build-upload-test cycle!**

2. **Make changes:**
   - Edit your widget code
   - Hot reload (Ctrl+F9 / Cmd+R)
   - See updates in ~15 seconds

3. **Test configurations:**
   - Modify values in MainActivity
   - Test edge cases (empty values, invalid inputs)
   - Verify error handling

**See `test-app/README.md` for detailed instructions.**

### Build APK

**Using Build Scripts (Easiest):**

```bash
# Windows
.\build-widget.bat

# Linux/Mac
chmod +x build-widget.sh
./build-widget.sh
```

This script will:
- Build the release APK
- Copy it with proper naming (`widget-name-vX.X.X.apk`)
- Display file size and configuration
- Show upload instructions

**Manual Build:**

```bash
./gradlew :test-app:assembleRelease
```

APK location: `test-app/build/outputs/apk/release/test-app-release.apk`

### Test in Lumy

After building:

1. Upload APK to Lumy Manager → Custom Widgets
2. Fill in widget details (name, version, class name, permissions)
3. Add to playlist/layout
4. Test on Android player device

## Sharing Your Widget

### Creating Releases for Users

**Important:** Create GitHub Releases with pre-built APKs so non-technical users can download your widget without build tools.

1. **Build your APK:**
   ```bash
   # Windows
   .\build-widget.bat
   
   # Linux/Mac
   ./build-widget.sh
   ```

2. **Tag and create release:**
   ```bash
   git tag -a v1.0.0 -m "Initial release"
   git push origin v1.0.0
   ```

3. **On GitHub:**
   - Go to Releases → Create new release
   - Select tag `v1.0.0`
   - Upload the APK file (e.g., `my-widget-v1.0.0.apk`)
   - Add release notes describing features
   - Publish

### Repository Setup

1. Create a repository in the `lumy-signage` organization (or your account)
2. Include:
   - Source code
   - `README.md` with description, screenshots, build instructions
   - `widget-metadata.json`
   - `.gitignore` (from template)
   - Screenshots or demo GIFs
   - **GitHub Release with APK file** ✨

3. Submit PR to add to organization README, or open an issue to request listing

For complete documentation, see:
- [Widget Template README](https://github.com/lumy-signage/lumy-widget-template/blob/main/README.md)
- [Contributing Guide](https://github.com/lumy-signage/.github/blob/main/CONTRIBUTING.md)
- [Main Project Documentation](https://github.com/lumyproject/lumy/tree/main/docs/widgets)

