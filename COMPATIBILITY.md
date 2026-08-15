# Compatibility

## Hardware-validated configuration

- Windows x64
- Bambu Lab P1S
- Physical Bambu AMS units, including multi-AMS inventory, active-slot tracking, guarded Load/Unload, and reviewed print-time tray mapping
- Local LAN MQTT monitoring/control and implicit FTPS file transfer

The P1S is the only printer model currently hardware-confirmed for controls, file transfer, and print submission. Other detected Bambu Lab models remain useful for monitoring but are placed in monitor-only mode until their command and recovery paths complete hardware validation.

## Deliberate limits

- PrintPanel currently maintains one live printer connection and switches that connection between saved printer profiles. Future simultaneous monitoring remains planned using independently managed per-printer sessions; each session consumes one client slot from that printer's separate LAN MQTT connection budget.
- External-spool Load/Unload is not implemented.
- Raw motion, filament-metadata editing, AMS reset/maintenance, and unvalidated material operations are not exposed.
- A compatible Microsoft Edge WebView2 runtime is required; supported Windows versions normally provide it through the operating system.

These limits are safety boundaries, not promises that unlisted hardware will fail.
