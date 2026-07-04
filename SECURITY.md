# Security Policy

The Strong Vibes program publishes standards and reference implementations for
software that drives a **physical motor over Bluetooth Low Energy**. Because a
vulnerability could affect a device acting on a person's body, we take reports
seriously and ask you to disclose privately.

## Reporting a vulnerability

**Please do not open a public issue for security problems.**

Use one of these private channels:

- **GitHub Security Advisories** — open a private report via the affected
  repository's **Security → Report a vulnerability** tab (preferred).
  - Issues in a reference implementation (e.g. Strong Vibes Playapp, Strong
    Vibes Knob Control) should be reported on **that** repository.
  - Issues in a **standard itself** (the Strong Vibes Protocol or Strong Vibes
    Connect specification) should be reported on this umbrella repository,
    `amok-products/strong-vibes`.
- If a private advisory is unavailable, contact the maintainers through this
  umbrella project.

Please include:

- A description of the issue and its impact — especially anything that could
  cause a device to run an unintended or unsafe motor pattern or intensity, or
  any ambiguity in a specification that could lead an implementer to do so.
- Steps to reproduce, affected version(s), and the environment (browser/OS,
  firmware, hardware) where relevant.
- Any proof-of-concept, logs, or BLE traffic captures.

## What to expect

- We aim to acknowledge a report within a few business days.
- We will work with you on a fix and a coordinated disclosure timeline, and
  credit you if you wish.

## Scope notes

- The reference web app requires a **secure context** (HTTPS or `localhost`);
  reports about running it over plain HTTP on a remote origin are expected
  behavior, not a vulnerability.
- The protocol and mechanical standards intentionally describe **no
  application-layer authentication** (see the Strong Vibes Protocol §10). A
  request to add auth is a feature proposal, not a vulnerability report — open a
  normal issue for that.
