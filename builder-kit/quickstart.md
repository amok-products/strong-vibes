# Quickstart

Two ways to build a Strong Vibes client — pick one.

## A. Start from the reference app (fastest)

**Strong Vibes Playapp** is a complete Web Bluetooth controller (Vite + React +
TypeScript). It's published as a GitHub **template repo**, so:

1. Open the Strong Vibes Playapp repository and click **Use this template →
   Create a new repository**.
2. Clone your copy, then:
   ```bash
   npm install
   npm run dev
   ```
3. Open the printed URL in **Chrome or Edge** (Web Bluetooth is required; Firefox
   and Safari don't support it). `localhost` counts as a secure context, so local
   dev works over plain HTTP.
4. Connect to your device and go. Modify the UI/patterns to taste.

The app already implements the full Strong Vibes Protocol (datagram building,
Device.Info parsing, reconnection). It ships a synced copy of the protocol spec
in-repo so your AI assistant can read it locally.

## B. Build from the spec (from scratch)

If you'd rather build your own client (a different framework, a mobile app, a CLI
tool):

1. Read the canonical spec:
   [`../protocol/strong-vibes-protocol.md`](../protocol/strong-vibes-protocol.md).
   It is self-contained and ends with a copy-pasteable Web Bluetooth quick-start.
2. Or hand the whole thing to your AI assistant with
   [`PROMPT.md`](PROMPT.md).

## The 30-second mental model

- **Two characteristics.** Write control datagrams to `0x1225`; subscribe for
  state/error notifications on `0x1227`.
- **One datagram shape.** `[0x10, SIZE, ...payload]`, ≤ 121 bytes. First byte is
  always `0x10`.
- **Motor patterns** are lists of waveform segments (linear / sine / gaussian).
  A *repeating* pattern loops; a *non-repeating* one plays once.
- **Live intensity** is a single small datagram — no need to resend the pattern.
- **The device is autonomous.** It keeps running if BLE drops; reflect its
  reported state on reconnect instead of pushing your own.

## Hardware

You need a device that speaks the Strong Vibes Protocol — e.g. a Europe Magic
Wand®, or your own build running the [Strong Vibes Knob
Control](../README.md#reference-implementations) firmware. Mount accessories with
[Strong Vibes Connect](../connect/strong-vibes-connect.md).

Adults only (18+). Test at low intensity. See [`../DISCLAIMER.md`](../DISCLAIMER.md).
