# Changelog — Strong Vibes Protocol

All notable changes to the Strong Vibes Protocol specification are documented
here. Format: [Keep a Changelog](https://keepachangelog.com/en/1.1.0/). The
protocol is versioned independently of any implementation.

## [1.0.0] — 2026-07-04

Initial public release of the canonical Strong Vibes Protocol specification.

### Added
- Two-characteristic BLE GATT design (Vibe Service `0x1221`; Write `0x1225`,
  Notify `0x1227`) with first-byte discrimination (`0x10` = Strong Vibes
  datagram).
- Datagram format (`VER = 0x10`, `SIZE`, payload) and the module/message map:
  Control.Reset; Motor (RepeatingPattern, NonRepeatingPattern, State,
  ErrorEvent, MainIntensityControl); Device.Info.
- Linear / Sine / Gaussian waveform encodings, segment sizes, and per-datagram
  segment limits.
- Device.Info telemetry slots (battery, fault, HW revision, usage, FW version,
  writable device-settings slot, extended serial) with append-only, forward-
  compatible schema evolution.
- Client-side multi-datagram chunking, pattern-interaction rules, reserved
  ranges for forward compatibility, a constants reference, and a Web Bluetooth
  quick-start.

Verified against the reference Europe Magic Wand® firmware. Wire-level
identifiers retain the historical `Vibe` / `VIBE_` names for on-the-wire
compatibility.

[1.0.0]: https://github.com/amok-products/strong-vibes/releases/tag/protocol-v1.0.0
