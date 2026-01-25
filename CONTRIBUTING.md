# Contributing to Lumy Widgets

Thank you for contributing to the Lumy widget community!

## Quick Start: Sharing Your Widget

**Easiest way:**
1. Create a public repository on your GitHub account named `lumy-widget-{name}`
2. Push your widget code with a README, `widget-metadata.json`, and `.gitignore`
3. **Create a GitHub Release** with a pre-built APK (so users can download without building)
4. Open an issue at https://github.com/lumy-signage/.github/issues to request it be added to the gallery

**See detailed steps below ↓**

## How to Contribute

### 1. Create Your Widget

- Start with the [lumy-widget-template](https://github.com/lumy-signage/lumy-widget-template) or fork an [internal widget](https://github.com/lumy-signage) as a starting point
- Follow the [development guide](https://github.com/lumy-signage/.github/blob/main/DEVELOPMENT_GUIDE.md)
- **Test locally first** using the built-in test app (40x faster development!)
- Test thoroughly before sharing

### 2. Build Release APK

**Use the automated build script:**

```bash
# Windows
.\build-widget.bat

# Linux/Mac
chmod +x build-widget.sh
./build-widget.sh
```

This generates a properly named APK (e.g., `my-widget-v1.0.0.apk`) with metadata.

### 3. Share Your Widget

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

3. **Create a GitHub Release** (Critical for users!):
   ```bash
   # Tag your version
   git tag -a v1.0.0 -m "Initial release"
   git push origin v1.0.0
   ```
   
   Then on GitHub:
   - Go to your repository → Releases → Create new release
   - Select tag `v1.0.0`
   - **Upload the APK file** (e.g., `my-widget-v1.0.0.apk`)
   - Add release notes describing features and configuration options
   - Publish release
   
   **This allows non-technical users to download and use your widget without build tools!** ✨

4. **Include required files**:
   - ✅ Source code (all Kotlin files)
   - ✅ `README.md` with:
     - Widget description and features
     - Screenshots or demo images
     - Configuration options (if any)
     - Build instructions
     - **Link to Releases for APK download**
   - ✅ `widget-metadata.json`
   - ✅ `.gitignore` (from template)
   - ✅ `setup-android-sdk.bat` and `setup-android-sdk.sh` (from template)
   - ✅ `local.properties.example` (from template)
   - ✅ `build-widget.bat` and `build-widget.sh` (from template)
   
5. **Request listing**:
   Open an issue at https://github.com/lumy-signage/.github/issues:
   - Title: "Add widget: [Your Widget Name]"
   - Include:
     - Link to your repository
     - Brief description
     - Screenshot
     - Link to Releases page (with APK)
   - Organization maintainers will review and add it to the gallery
   - The widget will appear in the [Available Widgets table](https://github.com/lumy-signage) on the organization profile

#### Option B: Transfer Repository to Organization (For Trusted Contributors)

If you're already a member of the `lumy-signage` organization:

1. **Create repository** in the organization:
   - Go to https://github.com/organizations/lumy-signage/repositories/new
   - Or use GitHub CLI: `gh repo create lumy-signage/lumy-widget-NAME --public`
   - Repository name: `lumy-widget-{your-widget-name}`

2. **Push your code** (same as Option A, step 2)

3. **Create GitHub Release** (same as Option A, step 3) ✨

4. **Submit PR to organization README**:
   - Fork the `.github` repository
   - Edit `profile/README.md`
   - Add your widget to the "Available Widgets" table
   - Submit a pull request

#### Option C: Fork Internal Widget as Template

1. **Fork an internal widget**:
   - Go to https://github.com/lumy-signage/lumy-widget-clock (or queue, message-slider)
   - Click "Fork" → Create a new fork
   - Choose your account or the organization (if you have access)

2. **Rename the repository**:
   - Go to Settings → General → Repository name
   - Change to `lumy-widget-{your-name}`

3. **Customize** the widget for your needs

4. **Follow steps from Option A or B** to build, release, and get it listed

## Guidelines

- **Code Quality**: Follow Kotlin best practices and Compose guidelines
- **Documentation**: Include clear README with screenshots and configuration details
- **Testing**: Test thoroughly using the test app before sharing
- **Naming**: Use clear, descriptive names (format: `lumy-widget-{name}`)
- **Releases**: Always create GitHub Releases with pre-built APKs for users
- **Template Structure**: Keep all template files (setup scripts, build scripts, etc.)

## Questions?

Open an issue in the [organization discussions](https://github.com/orgs/lumy-signage/discussions) or contact the maintainers.

