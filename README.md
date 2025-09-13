# Home Assistant Dashboard Default

## dash-ing default

### Because, why isn't this a default feature?

Automatically redirect to your preferred dashboard when opening Home Assistant!

[![GitHub Release][releases-shield]][releases]
[![License][license-shield]](LICENSE.md)
[![hacs_badge](https://img.shields.io/badge/HACS-Custom-blue.svg)](https://github.com/hacs/integration)

![Project Maintenance][maintenance-shield]
[![GitHub Activity][commits-shield]][commits]

## Features

* 🎯 Automatically redirect to your chosen dashboard when accessing Home Assistant
* 🔄 Change your default dashboard anytime via a dropdown helper
* 👥 Updates all devices to default to the same dashboard
* 🏠 Auto-creates helper entities for easy configuration
* ⚡ No manual YAML configuration required

---

## Installation

### Step 1: Install via HACS

1. Open HACS in your Home Assistant instance
2. Click the three dots menu (top right) and select "Custom repositories"
3. Add this repository URL: `https://github.com/shinypancake/dash-ing-default`
4. Select category: "Dashboard"
5. Click "Add"
6. Search "Dashing Default". Choose it
7. Click "Install"

### Step 2: Add as a Lovelace Resource

1. Go to Settings → Dashboards → Resources tab (top right three dots menu)
2. Click "Add Resource"
3. Enter URL: `/hacsfiles/dash-ing-default/default-dashboard.js`
4. Select Resource type: `JavaScript Module`
5. Click "Create"

### Step 3: Initial Setup

1. **Clear your browser cache** (Important!)
2. Navigate to your Home Assistant homepage (`/`)
3. The integration will automatically create two helper entities:
   * `input_select.default_dashboard` (Dropdown helper)
   * `input_boolean.default_dashboard` (Toggle helper)
4. You'll see console messages confirming the helpers were created

### Step 4: Configure Your Default Dashboard

1. Go to Settings → Devices & Services → Helpers
2. Find the "Default Dashboard" dropdown helper (`input_select.default_dashboard`)
3. If it shows "refresh" as the selected option, select it once to populate all available dashboards
4. Reload the page (F5) and go back to the dropdown helper
5. Select your preferred dashboard from the dropdown
6. Ensure the "Default Dashboard" toggle helper (`input_boolean.default_dashboard`) is on
7. Reload your Home Assistant homepage - it will now redirect to your chosen dashboard!
   * If you are asked to log in when refreshing, you will be re-directed to log in a second time. Check `Keep Me Logged In` to avoid this

---

## Usage

### Changing Your Default Dashboard

1. Go to Settings → Devices & Services → Helpers
2. Find "Default Dashboard" dropdown (`input_select.default_dashboard`)
3. Select your preferred dashboard
4. The change will take effect on the next home page reload

### Disabling the Redirect

1. Go to Settings → Devices & Services → Helpers
2. Find "Default Dashboard" toggle
3. Turn it off

---

## Troubleshooting

### Double Login Required

This is a known problem with the current implementation. The redirect happens after Home Assistant loads, which may require re-authentication. There is currently no solution or workaround

### Helpers Not Created Automatically

If the helper entities aren't created automatically:

1. Check the browser console (F12) for error messages
2. Ensure you have admin privileges in Home Assistant
3. Try manually creating the helpers:
   - **Dropdown Helper**: Entity ID must be `input_select.default_dashboard` with one option initially (e.g., "refresh")
   - **Toggle Helper**: Entity ID must be `input_boolean.default_dashboard`

### Dashboard Not Redirecting

1. Ensure the toggle helper is enabled
2. Clear your browser cache
3. Check that the selected dashboard exists and you have access to it
4. Open browser console (F12) and look for "DEFAULT-DASHBOARD" messages

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

For issues, feature requests, or questions, please open an issue on [GitHub](https://github.com/shinypancake/dash-ing-default/issues).

Original project by [@daredoes](https://www.github.com/daredoes)

---

[commits-shield]: https://img.shields.io/github/commit-activity/y/shinypancake/dash-ing-default.svg
[commits]: https://github.com/shinypancake/dash-ing-default/commits/master
[devcontainer]: https://code.visualstudio.com/docs/remote/containers
[license-shield]: https://img.shields.io/github/license/shinypancake/dash-ing-default.svg
[maintenance-shield]: https://img.shields.io/maintenance/yes/2025
[releases-shield]: https://img.shields.io/github/release/shinypancake/dash-ing-default.svg
[releases]: https://github.com/shinypancake/dash-ing-default/releases
