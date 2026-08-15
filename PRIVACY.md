# Privacy

PrintPanel is local-first. It does not require a TechTimeGuy Designs account and does not send printer telemetry, project details, credentials, or usage analytics to a TechTimeGuy Designs service.

## Data stored on the PC

- Printer profile details and optional-feature preferences are stored in the current Windows account's application-data area.
- LAN access codes are stored separately through Windows Credential Manager.
- Bounded print history, thumbnail cache, and sanitized guarded-action outcomes may be retained locally.
- Non-secret settings exports contain printer names, LAN addresses, serial numbers, and feature choices, but never access codes, histories, thumbnails, project names, or printer payloads.

## Network use

PrintPanel connects directly to configured printers over the local network for MQTT monitoring/control and FTPS file operations. Bambu printers use a device-local MQTT certificate that is not part of the Windows public trust chain, so the certificate exception is isolated to the configured local printer connection. It is not used for websites, releases, or updates.

When the signed updater channel is enabled, update checks connect only to the published update endpoint. Support reports are generated locally and are shared only when the user deliberately copies or saves them.

## Removal

Normal uninstall retains local settings for reinstall. The installer removal flow also provides an explicit option to delete application data. Protected credentials can be removed with their printer profile or through the full application-data removal option.
