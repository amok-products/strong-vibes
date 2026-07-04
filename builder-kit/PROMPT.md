# Builder Kit — paste this to your AI

Copy everything in the block below into your AI coding assistant (Cursor, or any
agent that can read a URL and write code). It points the assistant at the
canonical Strong Vibes Protocol spec and asks it to build you a working Web
Bluetooth client from scratch. Swap in what you want to build.

---

```
You are helping me build a client for the **Strong Vibes Protocol** — an open
BLE (Bluetooth Low Energy) protocol for driving motor/vibration patterns on
devices like the Europe Magic Wand. The full, self-contained specification is
here:

  https://raw.githubusercontent.com/amok-products/strong-vibes/main/protocol/strong-vibes-protocol.md

Read that spec end to end first. It is complete: two GATT characteristics, a
compact datagram format (first byte 0x10), motor waveform encodings (linear /
sine / gaussian), live intensity, and Device.Info telemetry. It includes a Web
Bluetooth quick-start you can build on.

Then build me the following:

  <describe what you want — e.g. "a single-page Chrome web app that connects to
  my device, has a start/stop button, an intensity slider (0–100), and three
  preset patterns: gentle wave, steady, and pulse">

Requirements:
- Use the Web Bluetooth API (Chrome/Edge). It needs a secure context
  (HTTPS or localhost) and a user gesture to connect.
- Service UUID 00001221-1313-71be-1221-785dfeabc321; write to 0x1225, subscribe
  to notifications on 0x1227. Every message you send must start with 0x10 and be
  ≤ 121 bytes.
- Keep the device autonomous: if the BLE link drops, do NOT push my cached state
  back on reconnect — read the device's reported state and reflect it.
- Explain the datagram bytes you send so I can learn the protocol.

Start by summarizing the spec back to me in a few lines, then scaffold the app.
```

---

## Notes

- The **reference implementation** is [Strong Vibes Playapp](../README.md#reference-implementations)
  — a full Vite/React web app you can fork as a `Use this template`
  starting point instead of building from zero. See
  [`quickstart.md`](quickstart.md).
- Anything you build is yours under the spec's CC-BY-4.0 license. If you use the
  "Strong Vibes" name for a product or fork, follow
  [`../TRADEMARK.md`](../TRADEMARK.md) (keep the "by europemagicwand.com"
  accreditation; "Strong Vibes" is an unregistered ™, Europe Magic Wand® is
  registered).
- Adults only (18+). Test at low intensity. See [`../DISCLAIMER.md`](../DISCLAIMER.md).
