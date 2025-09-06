# Default Dashboard

Automatically redirect to your preferred dashboard when opening Home Assistant!

[![GitHub Release][releases-shield]][releases]
[![License][license-shield]](LICENSE.md)
[![hacs_badge](https://img.shields.io/badge/HACS-Custom-blue.svg)](https://github.com/hacs/integration)

![Project Maintenance][maintenance-shield]
[![GitHub Activity][commits-shield]][commits]

## Features

* 🎯 Automatically redirect to your chosen dashboard when accessing Home Assistant
* 🔄 Change your default dashboard anytime via a dropdown helper
* 👥 Works per-device (each device remembers its own preference)
* 🏠 Auto-creates helper entities for easy configuration
* ⚡ No manual YAML configuration required

---

## Installation

### Step 1: Install via HACS

1. Open HACS in your Home Assistant instance
2. Click on "Frontend" section
3. Click the three dots menu (top right) and select "Custom repositories"
4. Add this repository URL: `https://github.com/shinypancake/default-dashboard`
5. Select category: "Dashboard"
6. Click "Add"
7. Find "Default Dashboard" in the list and click "Install"
8. Click "Install" again in the popup window

### Step 2: Add as a Lovelace Resource

1. Go to Settings → Dashboards → Resources tab (top right three dots menu)
2. Click "Add Resource"
3. Enter URL: `/hacsfiles/default-dashboard/default-dashboard.js`
4. Select Resource type: `JavaScript Module`
5. Click "Create"

### Step 3: Initial Setup

1. **Clear your browser cache** (Important!)
2. Navigate to your Home Assistant homepage (`/`)
3. The integration will automatically create two helper entities:
   - `input_select.default_dashboard` (Dropdown helper)
   - `input_boolean.default_dashboard` (Toggle helper)
4. You'll see console messages confirming the helpers were created

### Step 4: Configure Your Default Dashboard

1. Go to Settings → Devices & Services → Helpers
2. Find the "Default Dashboard" dropdown helper
3. If it shows "refresh" as the selected option, select it once to populate all available dashboards
4. Reload the page (F5)
5. Select your preferred dashboard from the dropdown
6. Enable the "Default Dashboard" toggle helper
7. Reload your Home Assistant homepage - it will now redirect to your chosen dashboard!

---

## Usage

### Changing Your Default Dashboard

1. Go to Settings → Devices & Services → Helpers
2. Find "Default Dashboard" dropdown
3. Select your preferred dashboard
4. The change will take effect on the next page reload

### Disabling the Redirect

1. Go to Settings → Devices & Services → Helpers
2. Find "Default Dashboard" toggle
3. Turn it OFF
4. The redirect will be disabled immediately

### Per-Device Settings

Each device/browser stores its own preference locally. To set different defaults on different devices:

1. On each device, navigate to the Home Assistant homepage
2. Select the preferred dashboard for that device in the dropdown helper
3. The preference is saved in that browser's local storage

---

## Troubleshooting

### Helpers Not Created Automatically

If the helper entities aren't created automatically:

1. Check the browser console (F12) for error messages
2. Ensure you have admin privileges in Home Assistant
3. Try manually creating the helpers:
   - **Dropdown Helper**: Entity ID must be `input_select.default_dashboard` with at least one option (e.g., "refresh")
   - **Toggle Helper**: Entity ID must be `input_boolean.default_dashboard`

### Dashboard Not Redirecting

1. Ensure the toggle helper is enabled
2. Clear your browser cache
3. Check that the selected dashboard exists and you have access to it
4. Open browser console (F12) and look for "DEFAULT-DASHBOARD" messages

### Double Login Required

This is a known issue with the current implementation. The redirect happens after Home Assistant loads, which may require re-authentication. We're working on a fix.

### Setting Different Defaults Per Device

You can override the default on a specific device:
1. Load the home page first (this loads the module)
2. Navigate to Settings → Dashboards
3. Click "SET AS DEFAULT ON THIS DEVICE" for your preferred dashboard
4. This device will now use its own default instead of the global setting

### Resetting to Default Behavior

1. Disable the "Default Dashboard" toggle helper
2. Clear your browser's local storage for your Home Assistant URL
3. Reload the page

---

## How It Works

This integration works by:
1. Creating two helper entities to store your preferences
2. Loading a JavaScript module with your Home Assistant frontend
3. Checking your preference when you navigate to the root URL (`/`)
4. Automatically redirecting to your chosen dashboard
5. Storing the preference locally in your browser

---

## Support

For issues, feature requests, or questions, please open an issue on [GitHub](https://github.com/shinypancake/default-dashboard/issues).

Original project by [@daredoes](https://www.github.com/daredoes)

---

[commits-shield]: https://img.shields.io/github/commit-activity/y/daredoes/default-dashboard.svg
[commits]: https://github.com/daredoes/default-dashboard/commits/master
[devcontainer]: https://code.visualstudio.com/docs/remote/containers
[license-shield]: https://img.shields.io/github/license/daredoes/default-dashboard.svg
[maintenance-shield]: https://img.shields.io/maintenance/yes/2025
[releases-shield]: https://img.shields.io/github/release/daredoes/default-dashboard.svg
[releases]: https://github.com/daredoes/default-dashboard/releases
