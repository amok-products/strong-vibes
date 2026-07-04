# Contributing to Strong Vibes

Thanks for your interest! This repository is the **umbrella** for the Strong
Vibes program: it holds the two open standards (the **Strong Vibes Protocol** and
**Strong Vibes Connect**), the builder kit, community documents, and the landing
page. Reference *implementations* live in their own repositories — contribute
code there; contribute to the **standards and docs** here.

## Where does my change go?

| Change | Repository |
|---|---|
| Protocol spec (`protocol/`) or mechanical standard (`connect/`) | **here** (`amok-products/strong-vibes`) |
| Builder kit, landing page, community docs | **here** |
| Web app behavior | Strong Vibes Playapp |
| Knob firmware behavior | Strong Vibes Knob Control |
| Printable parts / CAD | Strong Vibes Prints |

## Ground rules

- Be respectful — see [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md).
- The standards describe software that drives a **physical motor**. Treat any
  change that affects motor semantics (intensity, timing, safety) with extra
  care and clear rationale.
- Security issues and spec ambiguities that could cause unsafe behavior go
  through the private channel in [`SECURITY.md`](SECURITY.md), **not** public
  issues.

## Changing a standard

The **Strong Vibes Protocol** (`protocol/strong-vibes-protocol.md`) is the
**canonical source**. Reference implementations keep a *synced copy* of it and a
CI check flags divergence — so:

1. Propose the change **here**, with rationale and (for wire changes) a note on
   backward compatibility. The protocol is versioned; append-only, forward-
   compatible changes are strongly preferred (see the spec's reserved-ranges
   section).
2. Update `protocol/CHANGELOG.md` and the version string in the spec header in
   the same PR, and regenerate the checksum:
   `shasum -a 256 protocol/strong-vibes-protocol.md > protocol/strong-vibes-protocol.md.sha256`
   (the `spec-integrity` workflow fails if the committed checksum doesn't match).
3. After merge, each reference implementation re-syncs its mirror from the new
   canonical file.

The **Strong Vibes Connect** standard (`connect/strong-vibes-connect.md`) tracks
the parametric CAD in Strong Vibes Prints (`STANDARD_VERSION` in
`strong_vibes_connect.py` is the source of truth for dimensions). A dimension
change starts there; this document and its `CHANGELOG.md` follow.

## Developer Certificate of Origin (DCO)

This project uses the **DCO** instead of a CLA. By contributing, you certify the
[Developer Certificate of Origin 1.1](https://developercertificate.org/). Sign
off every commit:

```bash
git commit -s -m "your message"
```

which adds a `Signed-off-by: Your Name <you@example.com>` trailer. Use your real
name and a reachable email.

> Note: do **not** add AI co-author trailers to commits (e.g. a `Co-authored-by:`
> line crediting an AI). Mentioning AI vendors, tools, or their APIs in docs is
> fine — the rule is only about commit authorship.

## Branding & trademark constraint

The specs and docs are CC-BY-4.0, but the **names are trademarks** (see
[`TRADEMARK.md`](TRADEMARK.md)). Contributions must not introduce uses of the
"Strong Vibes" or "Europe Magic Wand®" names that conflict with that policy
(e.g. implying a fork is the official project, or marking "Strong Vibes" as a
registered trademark). Factual compatibility statements are fine.
