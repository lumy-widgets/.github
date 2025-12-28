# Maintainer Guide - Adding Widgets to Gallery

This guide is for organization maintainers who need to add new widgets to the gallery after a contributor requests it.

## Process: Adding a Widget to the Gallery

When a contributor opens an issue requesting their widget be added to the gallery:

### Step 1: Review the Request

1. Go to the issue: https://github.com/lumy-widgets/.github/issues
2. Check that the widget includes:
   - ✅ Public repository link
   - ✅ Description
   - ✅ Screenshot or demo
   - ✅ Follows naming convention: `lumy-widget-{name}`
   - ✅ Has README.md and widget-metadata.json

### Step 2: Add Widget to Organization Profile

1. **Clone or update the `.github` repository**:
   ```bash
   git clone https://github.com/lumy-widgets/.github.git
   cd .github
   # Or if already cloned:
   git pull origin main
   ```

2. **Edit `profile/README.md`**:
   - Open `profile/README.md`
   - Find the "Available Widgets" table (around line 9)
   - Add a new row with the widget information:

   ```markdown
   | Widget | Description | Author | Status |
   |--------|-------------|--------|--------|
   | [Hello World](lumy-widget-hello-world) | Minimal template widget | Lumy Team | ✅ Template |
   | [Widget Name](repository-link) | Widget description | Author Name | ✅ Active |
   ```

   **Format:**
   - **Widget**: `[Widget Name](repository-link)` - Use relative link if in org, or full URL if external
   - **Description**: Brief description from the issue or README
   - **Author**: GitHub username or name from the issue
   - **Status**: `✅ Active` for community widgets, `✅ Template` for templates

3. **Commit and push**:
   ```bash
   git add profile/README.md
   git commit -m "Add widget: [Widget Name]"
   git push origin main
   ```

### Step 3: (Optional) Transfer Repository to Organization

If the widget repository is in the contributor's personal account and you want it in the organization:

1. **Ask the contributor to transfer the repository**:
   - They go to: Repository Settings → Danger Zone → Transfer ownership
   - Transfer to: `lumy-widgets` organization
   - Or you can add them as a collaborator to the organization repo

2. **If creating in organization directly**:
   ```bash
   gh repo create lumy-widgets/lumy-widget-NAME --public
   ```

### Step 4: Update the Issue

1. Comment on the issue:
   ```
   ✅ Widget added to gallery!
   
   The widget has been added to the organization profile. 
   It will appear at: https://github.com/lumy-widgets
   ```

2. Close the issue

## Quick Reference: Table Format

When adding to the table, use this format:

```markdown
| [Widget Name](repository-link) | Brief description | @username or Name | ✅ Active |
```

**Examples:**
- Widget in organization: `[Weather Widget](lumy-widget-weather)`
- Widget in user's account: `[Weather Widget](https://github.com/username/lumy-widget-weather)`
- External widget: `[Weather Widget](https://github.com/other-org/widget)`

## Repository Location Options

1. **In Organization** (Recommended):
   - Repository: `lumy-widgets/lumy-widget-NAME`
   - Link format: `[Widget Name](lumy-widget-NAME)`

2. **In Contributor's Account**:
   - Repository: `username/lumy-widget-NAME`
   - Link format: `[Widget Name](https://github.com/username/lumy-widget-NAME)`

Both are valid - choose based on whether you want centralized management or community ownership.
