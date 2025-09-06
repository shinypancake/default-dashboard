# Default Dashboard

Enforce a default dashboard on every device in Home Assistant!

## Features

- Select a dashboard that will become the default for all users/devices
- Update selected dashboard at any time  
- Retain a per-device default dashboard by loading the home page first, then going to the dashboards tab

## Installation

1. Install through HACS
2. Add as a Lovelace resource:
   - URL: `/hacsfiles/default-dashboard/default-dashboard.js`
   - Resource type: JavaScript Module
3. Create required helper entities (see README for detailed instructions)

## Recent Updates (v1.1.0)

- Fixed duplicate entity creation issue
- Fixed dropdown helper state persistence
- Fixed dashboard reset after restart
- Updated all dependencies to latest versions
- Modernized build tooling

For detailed setup instructions, please see the [README](https://github.com/shinypancake/default-dashboard#readme).