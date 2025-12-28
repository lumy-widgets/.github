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

