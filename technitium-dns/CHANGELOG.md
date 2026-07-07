First add-on release on the new **CalVer** scheme (`YYYY.M.PATCH`), decoupled from the upstream Technitium version so add-on-only fixes can ship. Bundles **Technitium DNS Server 15.3.0**.

### 🐛 Fixes
- **Ingress web UI now works with host networking.** The panel previously showed *"refused to connect"*; host-network add-ons need a dynamic ingress port, which wasn't set. Added an nginx reverse proxy on the Supervisor-assigned port → Technitium on 5380. Direct access at `http://<host>:5380` still works. Verified end-to-end in a HA Supervisor. (#42)

### 👷 Maintenance
- Hardened auto-release (SHA-pinned checkout, `make_latest`, release token) (#39)
- Reliable Renovate auto-upgrades; single bot, SHA-pinned actions (#40, #43)

> Note: the add-on version is now date-based; the Technitium version is shown in the Technitium console. This avoids version-scheme conflicts with upstream.