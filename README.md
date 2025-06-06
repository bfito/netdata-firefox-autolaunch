# Auto-Launch Netdata Dashboard in Firefox on User Login

This project uses a user-level `systemd` service to automatically launch the Netdata monitoring dashboard in Firefox every time you log into your Linux desktop session.

## Features
- Starts Netdata on boot using `systemctl`
- Launches Firefox to the Netdata dashboard (`http://localhost:19999`)
- Uses a persistent user-level `systemd` service for GUI session control

## Setup

1. Enable Netdata service:
   ```bash
   sudo systemctl enable --now netdata

2. mkdir -p ~/.config/systemd/user
cp firefox-netdata.service ~/.config/systemd/user/

3. Enable and start the service:
systemctl --user daemon-reload
systemctl --user enable firefox-netdata.service
systemctl --user start firefox-netdata.service
