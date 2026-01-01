** WireGuard Monitor for Kodi / CoreELEC (NordVPN)

This Kodi service provides a lightweight WireGuard VPN client for NordVPN only, designed for CoreELEC systems.
It automatically installs required dependencies (Entware, WireGuard, curl, jq) and creates a WireGuard configuration template.

The user only needs to supply a NordVPN WireGuard Private Key.
On each boot, the service dynamically fetches the optimal NordVPN server, public key, endpoint, and VPN IP, and injects them into the config.

The service monitors:

* LAN connectivity
* WireGuard interface state
* Handshake health
* Internet reachability

It automatically restarts the tunnel if needed and displays Kodi notifications for all important events.
No GUI, no credentials stored, minimal user interaction.
