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
git clone https://github.com/lumy-widgets/lumy-widget-hello-world.git my-widget
cd my-widget
```

### 2. Update Project Configuration

Edit `app/build.gradle.kts`:

- Change `namespace` and `applicationId` to your package
- Update `versionName` and `versionCode`

### 3. Rename and Customize

- Rename `HelloWorldWidget.kt` to your widget name
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
        "option1": {
          "type": "string",
          "title": "Option 1",
          "default": "value"
        }
      }
    }
    """.trimIndent()
}
```

## Building and Testing

### Build APK

```bash
./gradlew assembleRelease
```

### Test Locally

1. Install APK on Android device/emulator
2. Test widget rendering
3. Verify configuration options work

## Sharing Your Widget

1. Create a repository in the `lumy-widgets` organization
2. Include:
   - Source code
   - `README.md` with description
   - `widget-metadata.json`
   - Screenshots

3. Submit PR to add to organization README

For complete documentation, see the [full development guide](https://github.com/lumy-widgets/lumy-widget-hello-world/blob/main/README.md).

