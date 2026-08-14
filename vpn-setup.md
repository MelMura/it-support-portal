# VPN Client Setup Guide

**Symptom / Situation:** A user needs to connect to a private network remotely — from
home, while travelling, or from a device outside the school's own Wi-Fi — and either
hasn't set up the VPN client yet, or has it installed but can't get it to connect.

> 🇩🇪 **Auf Deutsch:** VPN = *virtuelles privates Netzwerk* · client = *Client* (borrowed
> as-is) · to authenticate = *sich authentifizieren*.

## Likely Causes (for connection failures)

- Wrong server address, username, or password entered in the client.
- The device's own network is blocking the VPN protocol (common on hotel or public Wi-Fi,
  which often blocks non-standard ports).
- The VPN client or the operating system needs an update.
- The account's VPN access hasn't been enabled on the server side yet.

## Step-by-Step Setup

1. **Get the connection details** from whoever administers the network: server address,
   the VPN protocol in use (e.g. OpenVPN, WireGuard, IKEv2), and login credentials.
2. **Install the client.** Most setups use a dedicated app (e.g. OpenVPN Connect,
   WireGuard) rather than typing settings in manually — install the one that matches the
   protocol you were given.
3. **Import the configuration file**, if one was provided (usually a `.ovpn` or `.conf`
   file) — this saves manually entering server, port, and encryption settings.
4. **Enter credentials** when prompted and connect.
5. **Confirm the connection is actually routing traffic**, not just showing "Connected":
   check the device's new IP address (search "what is my IP" or use `curl ifconfig.me`)
   and confirm it matches the VPN's network, not the local one.

## Troubleshooting a Failed Connection

1. Double-check the server address and credentials — the single most common cause.
2. Try a different network (e.g. mobile hotspot instead of hotel Wi-Fi) to rule out local
   blocking of the VPN port.
3. Check the client's log output for the actual error (e.g. "authentication failed" vs.
   "could not reach server" point to very different problems — credentials vs. network).
4. Restart the VPN client and, if that fails, the device itself — this clears a
   surprising number of stuck connection states.
5. Confirm the account has active VPN access on the server side; a correctly configured
   client can't connect to an account that hasn't been provisioned.

## When to Escalate

- Authentication fails consistently with credentials you've confirmed are correct — the
  account itself likely needs to be checked or re-provisioned on the server.
- The client connects but no traffic routes through it (the IP doesn't change) — this
  usually needs a look at routing/firewall rules on the server side.
- More than one user reports the same failure at the same time — likely a server-side
  outage, not a per-device issue.
