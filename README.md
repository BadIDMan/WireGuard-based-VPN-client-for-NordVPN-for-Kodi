## WireGuard Monitor for Kodi / CoreELEC (NordVPN)

This Kodi service provides a lightweight WireGuard VPN client for NordVPN only, designed for CoreELEC systems.
It automatically installs required dependencies (Entware, WireGuard, curl, jq) and creates a WireGuard configuration template.

The user only needs to supply a **NordVPN WireGuard Private Key.**
On each boot, the service dynamically fetches the optimal NordVPN server, public key, endpoint, and VPN IP, and injects them into the config.

The service monitors:

* LAN connectivity
* WireGuard interface state
* Handshake health
* Internet reachability

It automatically restarts the tunnel if needed and displays Kodi notifications for all important events.
No GUI, no credentials stored, minimal user interaction.

Before using this service, a NordVPN user **must** generate a WireGuard Private Key.

To do this, log in to: https://my.nordaccount.com/dashboard/nordvpn/ 
and in the Access Token section, create a token. After creating the token, the corresponding WireGuard Private Key must be retrieved.

Command to run to retrieve WireGuard NordVPN Private Key:

`curl -s -u token:<ACCESS_TOKEN> https://api.nordvpn.com/v1/users/services/credentials | jq -r .nordlynx_private_key`

To run this command on Windows, _curl_ and _jq_ must be installed. They can be installed easily using:

`winget install curl` and `winget install jq`

Details: https://github.com/BadIDMan/service.wg.monitor/wiki
