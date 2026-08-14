# Fixing DNS Resolution Issues

**Symptom:** A user reports that websites won't load, with errors like *"This site can't
be reached,"* *"DNS_PROBE_FINISHED_NXDOMAIN,"* or *"Server not found."* Often the
strange part is that some sites load and others don't, or the internet "works" on their
phone but not their laptop — which is the clue that points straight at DNS rather than
the internet connection itself.

> 🇩🇪 **Auf Deutsch:** DNS = *Domain Name System* · resolve = *auflösen* · a "flush" is
> *den Cache leeren*.

## Likely Causes

- The device's cached DNS records are stale or corrupted.
- The DNS server address configured on the device is wrong, unreachable, or set to a
  local router that itself can't resolve names.
- A recently changed network (new Wi-Fi, new VPN, new office) hasn't updated the
  device's DNS settings.
- The actual site is down — always rule this out first so you don't chase a fault that
  isn't there.

## Step-by-Step Fix

1. **Confirm it's DNS, not connectivity.** Try opening a site by its raw IP address
   (e.g. `8.8.8.8` in a browser, or `ping 8.8.8.8` in a terminal). If the IP responds but
   the domain name doesn't, the connection is fine and the problem is DNS resolution.
2. **Flush the local DNS cache.**
   - Windows: open Command Prompt and run `ipconfig /flushdns`
   - macOS: `sudo dscacheutil -flushcache; sudo killall -HUP mDNSResponder`
3. **Check what DNS server the device is actually using.**
   - Windows: `nslookup google.com` — the top of the output shows the DNS server it queried.
   - If it's the router's address (usually `192.168.x.1`) and that's the point of failure,
     try a public resolver instead, e.g. `8.8.8.8` (Google) or `1.1.1.1` (Cloudflare).
4. **Update the DNS setting and reconnect.** Set the new DNS server in the network
   adapter's settings, then disable and re-enable the network adapter (or reconnect to
   Wi-Fi) so the change actually takes effect.
5. **Re-test** with `nslookup` or by reloading the site that originally failed.

## When to Escalate

- The same issue affects **multiple users on the same network** at once — this points to
  the network's DNS server or router, not an individual machine, and needs a network-level
  fix rather than a per-device one.
- Flushing and changing the resolver doesn't help, and `ping`-by-IP also fails — that's a
  connectivity problem, not DNS, and belongs with whoever manages the network hardware.
- The problem follows a specific site only (not the whole internet) — that's usually the
  site itself, not something to keep troubleshooting locally.
