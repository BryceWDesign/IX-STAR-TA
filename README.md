# IX-STAR-TA — Solar-Thermal Array Receiver → ThermoAcoustic

IX-STAR-TA is an evaluation-focused, measurement-first concept for converting concentrated solar heat into electrical power using a **modular cavity-receiver array** feeding a **single controlled thermoacoustic core**, with optional **PCM hot-side stabilization** to improve repeatability.

This repo is written for engineers. It avoids hype and defines what can be built, measured, falsified, and improved.

## What it is
- A **modular solar-thermal receiver architecture**:
  - multiple identical “receiver cells” (non-imaging capture + cavity receiver)
  - thermal combining into a central hot manifold
  - a single thermoacoustic resonator + alternator stage
  - an instrumentation plan that produces audit-grade evidence

## What it is not
- Not a “free energy” claim.
- Not an antigravity/propulsion claim.
- Not a finished product.
- Not a substitute for a full safety review (high temps, pressure, optics hazards).

## Why this architecture is interesting (real reasons)
- **Cavity receivers** can improve absorption and flux uniformity vs simple flat absorbers.
- **Non-imaging concentrators** can increase acceptance angle (less pointing sensitivity).
- **PCM buffering** can reduce hot-side temperature swings that destabilize thermoacoustic operation.
- **One controlled TA core** simplifies tuning and instrumentation vs many small engines.

## Core concept (one sentence)
A **honeycomb-like receiver array** concentrates and traps solar flux in cavity receivers, sums heat into a stabilized hot manifold, and drives a single thermoacoustic generator that is instrumented to produce repeatable power accounting.

## Repository structure
- `docs/` — architecture, receiver physics, manifold + PCM, TA core interfaces, measurement plan, safety.
- `hardware/` — module specs, BOMs, mechanical concepts, sensor placement, assembly notes.
- `tests/` — test plans, acceptance criteria, and reporting templates.
- `reports/` — PoC report template (no fabricated data).

## License
Evaluation-only, no commercial use. See `LICENSE`.

