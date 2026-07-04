# Changelog — Strong Vibes Connect

All notable changes to the Strong Vibes Connect mechanical standard are
documented here. Format: [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).
Dimensions track `STANDARD_VERSION` in `strong_vibes_connect.py` (Strong Vibes
Prints repository), the machine source of truth.

## [1.0.0] — 2026-07-04

Initial public release of the Strong Vibes Connect mechanical mount standard.

### Added
- Keyed rhombus (diamond) boss + socket interface: `DIA_A = 11.322`,
  `DIA_B = 7.759`, `BAND_DEPTH = 2.0` (mm).
- `1/4"-20 UNC` clamp screw with `EFF_THREAD = 7.0 mm` minimum boss engagement;
  female clamp plate `PLATE_T = 3.0` (total plate 5.0 mm).
- Orientation contract, seating/keying/clamp feature roles, and FDM/TPU print
  fit guidance (clearances, mouth lead-in, printable-thread allowances).
- Conformance criteria.

Reference geometry corresponds to `strong_vibes_connect.py` `STANDARD_VERSION =
"1.0.0"`. The mechanical CAD finalizes in the Strong Vibes Prints repository; a
`STANDARD_VERSION` bump there updates this document.

[1.0.0]: https://github.com/amok-products/strong-vibes/releases/tag/connect-v1.0.0
