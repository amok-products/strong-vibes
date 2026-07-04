# Strong Vibes Connect

**Strong Vibes Connect by europemagicwand.com** — mechanical mount standard,
version **1.0.0**.

> **This is the human-readable standard.** The machine source of truth for every
> dimension is `strong_vibes_connect.py` (`STANDARD_VERSION`) in the **Strong
> Vibes Prints** repository (`amok-products/strong-vibes-prints`). When that CAD
> is finalized and published, the numbers here track its `STANDARD_VERSION`; a
> bump there is a repo-wide interface event that this document follows.
>
> Free to implement (see [`../LICENSE`](../LICENSE), CC-BY-4.0). Names are
> governed by [`../TRADEMARK.md`](../TRADEMARK.md).

## What it is

Strong Vibes Connect is a **keyed mechanical interface** that rigidly joins a
device boss to an accessory (holder, stand, mount). It is a **mechanical**
standard — it says nothing about the BLE link (that is the Strong Vibes
Protocol).

The joint has three jobs, and does each with a dedicated feature:

1. **Key** — a rhombus (diamond) cross-section prevents rotation and forces a
   single assembly orientation.
2. **Seat** — the male boss's flare shoulder lands flat on the socket face, an
   axial hard stop.
3. **Clamp** — a `1/4"-20` screw through the socket threads into the boss and
   pulls the joint tight → rigid + keyed.

```
        MALE boss (on the device)                 FEMALE socket (on the accessory)
                                                 ┌───────────────────────┐
              ▲ +Z (face up)                     │  mouth lead-in chamfer │
        ╱◆╲   diamond band  ── BAND_DEPTH ──►     │   ╱────────────────╲  │  face (Z=0)
       ╱   ╲  (constant section, socket grips)    │  │  diamond pocket   │ │  ◄ BAND_DEPTH
      ╱ flare╲ shoulder seats on face ──────────► ├──┴──────────────────┴─┤
     ╱────────╲                                   │   clamp plate  PLATE_T │  screw self-taps
        │ │  1/4-20 thread, EFF_THREAD deep       │   1/4-20 clearance/tap │
```

Long axis is keyed longer than the short axis, so the parts mate in exactly one
orientation (modulo 180°).

## Interface geometry (v1.0.0)

All dimensions in millimetres. "Half-diagonal" is measured from the diamond
centre to a vertex.

| Interface | Symbol | Value | Notes |
|---|---|---|---|
| Cross-section | — | rhombus (diamond) prism | keyed: long ≠ short |
| Long half-diagonal | `DIA_A` | **11.322** | full long diagonal = 22.644 |
| Short half-diagonal | `DIA_B` | **7.759** | full short diagonal = 15.518 |
| Band depth | `BAND_DEPTH` | **2.0** | constant-section length the socket grips |
| Female clamp plate | `PLATE_T` | **3.0** | solid material below the pocket |
| Total female plate | — | **5.0** | `BAND_DEPTH + PLATE_T` |
| Fastener | — | **1/4"-20 UNC** | major Ø 6.35, pitch 1.27 |
| Min effective thread in boss | `EFF_THREAD` | **7.0** | usable `1/4"-20` engagement |

## Orientation contract

Each part is modelled in its own frame:

- **Socket (female):** mating face on plane `Z = 0`; the diamond plugs in along
  `−Z` (the band fills `Z ∈ [0, −BAND_DEPTH]`). Screw axis = `Z`. Long axis
  `+Y`, short axis `+X`.
- **Boss (male):** base on the bed at `Z = 0`, diamond face up at the top; the
  `1/4"-20` thread runs down the `Z` axis from the face. Rotate 180° about `X`
  to seat it in the socket.

## Fastening

A single `1/4"-20` screw, ≥ 10 mm long, threads through the socket into the boss
and clamps the joint. The boss carries ≥ `EFF_THREAD` (7.0 mm) of effective
thread. This is the common camera / tripod thread, so standard `1/4"-20`
hardware works.

## Printing & fit (FDM / TPU guidance)

These are **print-tuning allowances**, not part of the interface definition —
they let a printed part hit the nominal geometry above:

- **Clearance** — add `CLEAR ≈ 0.20 mm` to each socket half-diagonal (roughly
  `0.12` for a tight grip … `0.35` for a loose slip fit; tune to your printer).
- **Self-finding mouth** — a small lead-in chamfer at the socket mouth so the
  diamond self-centres on insertion.
- **Threads on a printer** — model the internal `1/4"-20` thread loosened by
  ~`0.6 mm` diametral clearance so a steel screw threads into the print, and add
  a countersink lead-in (≈ Ø9 mm × 1 mm) so the screw starts and self-centres.
  Alternatively use a plain self-tap hole (≈ Ø5.3 mm) and let the steel screw cut
  its own thread.

## Conformance

A part **conforms to Strong Vibes Connect v1.0.0** if:

- its diamond band matches `DIA_A` / `DIA_B` / `BAND_DEPTH` within your fit
  clearance,
- the male boss provides ≥ `EFF_THREAD` of `1/4"-20` engagement and a flare
  shoulder that seats on the socket face, and
- the female provides the keyed pocket plus ≥ `PLATE_T` of clamp material and a
  `1/4"-20` clearance or tapped bore.

Conforming parts may state "Strong Vibes Connect by europemagicwand.com
compatible" per [`../TRADEMARK.md`](../TRADEMARK.md).
