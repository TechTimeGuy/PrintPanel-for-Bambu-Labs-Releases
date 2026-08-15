# Compatibility

## Hardware-validated configuration

- Windows x64
- Bambu Lab P1S
- Physical Bambu AMS units, including multi-AMS inventory, active-slot tracking, guarded Load/Unload, and reviewed print-time tray mapping
- Local LAN MQTT monitoring/control and implicit FTPS file transfer

The P1S is the only printer model currently hardware-confirmed for controls, file transfer, and print submission. Other detected Bambu Lab models remain useful for monitoring but are placed in monitor-only mode until their command and recovery paths complete hardware validation.

## Deliberate limits

- PrintPanel simultaneously monitors every complete saved printer profile through one independently managed local MQTT session per printer. Each session consumes one client slot from that printer's separate LAN connection budget; the tested P1S practical limit of approximately three clients is per printer, not global.
- Printer-changing actions are routed only to the explicitly selected printer and remain unavailable for monitor-only model tiers.
- External-spool Load/Unload is not implemented.
- Raw motion, filament-metadata editing, AMS reset/maintenance, and unvalidated material operations are not exposed.
- A compatible Microsoft Edge WebView2 runtime is required; supported Windows versions normally provide it through the operating system.

These limits are safety boundaries, not promises that unlisted hardware will fail.
