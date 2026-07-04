# Attribution

This umbrella repository holds the Strong Vibes **standards** (the Strong Vibes
Protocol and Strong Vibes Connect), community documents, and the landing page.
It credits the works this material builds on. Each reference implementation
repository (Strong Vibes Playapp, Strong Vibes Knob Control, Strong Vibes Prints)
carries its **own** `ATTRIBUTION.md` / `THIRD_PARTY.md` for the third-party code
it ships.

## This repository builds on

| Work | License | Used for |
|---|---|---|
| [Creative Commons Attribution 4.0](https://creativecommons.org/licenses/by/4.0/) | CC-BY-4.0 | the license for the specs and docs in this repo |
| [Contributor Covenant 2.1](https://www.contributor-covenant.org) | CC-BY-4.0 | the Code of Conduct |
| [Keep a Changelog](https://keepachangelog.com) | MIT | the changelog format |
| [Developer Certificate of Origin 1.1](https://developercertificate.org) | — | the contribution sign-off model |

## The standards' sources of truth

- The **Strong Vibes Protocol** spec is verified against the reference Europe
  Magic Wand® firmware. It describes only the open wire protocol.
- The **Strong Vibes Connect** dimensions are generated from the parametric CAD
  in the Strong Vibes Prints repository (`strong_vibes_connect.py`), which itself
  builds on [build123d](https://github.com/gumyr/build123d) (Apache-2.0),
  [OCP / OpenCascade](https://github.com/CadQuery/OCP) (LGPL-2.1), and
  [bd_warehouse](https://github.com/gumyr/bd_warehouse). Those credits live in
  the Strong Vibes Prints repository.

If you believe an attribution is missing or incorrect, please open an issue.
