# Strong Vibes

**Open standards and reference code for building your own massager apps,
firmware, and mounts** — by [europemagicwand.com](https://europemagicwand.com).

Strong Vibes is a maker/builder program from Europe Magic Wand®. It opens up the
pieces you need to build a Strong Vibes–compatible device or controller: two open
standards, reference implementations you can fork and run, and an AI-friendly
builder kit that gets you from zero to a working app in one prompt.

> **Adults only (18+).** Hobbyist hardware — build and use at your own risk. Not
> a medical device. See [`DISCLAIMER.md`](DISCLAIMER.md).

## Start here

- **Just want to build an app?** → [`builder-kit/quickstart.md`](builder-kit/quickstart.md)
- **Want your AI to build it for you?** → paste [`builder-kit/PROMPT.md`](builder-kit/PROMPT.md)
  into Cursor (or any AI assistant).
- **Want to understand the wire protocol?** → [`protocol/strong-vibes-protocol.md`](protocol/strong-vibes-protocol.md)
- **Designing a mount or accessory?** → [`connect/strong-vibes-connect.md`](connect/strong-vibes-connect.md)

## The two standards

| Standard | What it defines | Spec | Version |
|---|---|---|---|
| **Strong Vibes Protocol** | the open BLE wire protocol — how a client drives motor/vibration patterns over two GATT characteristics | [`protocol/`](protocol/strong-vibes-protocol.md) | 1.0.0 |
| **Strong Vibes Connect** | the mechanical mount interface — a keyed diamond boss + socket clamped with a `1/4"-20` screw | [`connect/`](connect/strong-vibes-connect.md) | 1.0.0 |

The **Strong Vibes Protocol** spec in this repo is **canonical**: reference
implementations keep a synced copy and a CI check flags divergence. **Strong
Vibes Connect** tracks the parametric CAD in the Strong Vibes Prints repository.

## Reference implementations

Fork-and-run projects that implement the standards — **all public now**. Each is
Apache-2.0 (code) or CC-BY-4.0 (designs), with its own attribution and quickstart.

| Project | What it is | Repository |
|---|---|---|
| **Strong Vibes Playapp** | browser-based controller (Vite/React/TS) — a `Use this template` starting point, live at [playapp.emw4u.com](https://playapp.emw4u.com) | [`amok-products/strong-vibes-playapp`](https://github.com/amok-products/strong-vibes-playapp) |
| **Strong Vibes Knob Control** | ESP32-S3 / ESP-IDF knob firmware (tactile controller + BLE) | [`amok-products/strong-vibes-knob-control`](https://github.com/amok-products/strong-vibes-knob-control) |
| **Strong Vibes Prints** | build123d CAD: a printable holder + the Strong Vibes Connect reference parts, with an [interactive 3D viewer](https://amok-products.github.io/strong-vibes-prints/) | [`amok-products/strong-vibes-prints`](https://github.com/amok-products/strong-vibes-prints) |

## Licensing & accreditation

- **Specs and docs** in this repo: **CC-BY-4.0** ([`LICENSE`](LICENSE)).
- **Reference code**: **Apache-2.0** (in each code repo, with `NOTICE`).
- **Designs**: **CC-BY-4.0** (in the prints repo).

Everything is free to use, **including commercially** — the one condition is
**accreditation**. When you use a Strong Vibes name for a product or fork, keep
the form **"Strong Vibes X by europemagicwand.com"** and preserve the required
attribution. Europe Magic Wand® is a registered trademark; the "Strong Vibes"
names are unregistered ™. Full terms: [`TRADEMARK.md`](TRADEMARK.md).

## Community

- Contributing (and where each kind of change goes): [`CONTRIBUTING.md`](CONTRIBUTING.md)
- Code of Conduct: [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md)
- Security / responsible disclosure: [`SECURITY.md`](SECURITY.md)
- Attribution: [`ATTRIBUTION.md`](ATTRIBUTION.md)

---

Strong Vibes™ · Europe Magic Wand® · [europemagicwand.com/strong-vibes-builder](https://europemagicwand.com/strong-vibes-builder)
