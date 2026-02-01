# IX-STAR-TA Architecture

## Purpose
IX-STAR-TA is a modular solar-thermal receiver architecture designed to feed a single
controlled thermoacoustic (TA) generator core with a stable hot-side interface.

The engineering intent is simple:
- capture solar flux robustly,
- trap and uniformize it in cavity receivers,
- sum heat into a central hot manifold,
- optionally stabilize that manifold with PCM,
- drive one TA core that is instrumented and testable.

---

## System Blocks (High Level)

### Block A — Receiver Cell Array (N cells)
Each receiver cell provides:
- **capture optics** (non-imaging acceptance-angle friendly geometry)
- **cavity receiver** (flux trapping and reduced sensitivity to hotspots)
- **heat extraction interface** (to manifold via heat pipe or conduction strap)
- **local instrumentation** (temperature at receiver body and outlet)

Cells are designed to be identical modules so scaling does not change the physics,
only the count.

### Block B — Thermal Combining Manifold (Hot Bus)
A central manifold collects heat from all cells and delivers:
- a single hot-side thermal interface to the TA core
- a stable distribution that reduces cell-to-cell mismatch stress
- a place to mount sensors and (optionally) PCM

Key design requirement:
- minimize thermal bottlenecks
- avoid large temperature gradients that create mechanical stress and tuning drift

### Block C — PCM Hot-Side Stabilization (Optional but recommended)
PCM near the manifold:
- absorbs transient fluctuations (clouds, gusts, pointing changes)
- holds the hot-side within a narrower temperature band
- improves repeatability of TA resonance and output

PCM is a stability tool. It is not used to claim extra energy.

### Block D — Thermoacoustic Core (Single TA Engine)
One TA core consists of:
- hot heat exchanger (HHX) coupled to the manifold
- cold heat exchanger (CHX) coupled to a heat rejection system
- resonator / stack geometry (implementation-defined)
- linear alternator (or other transduction) with explicit power accounting

Design objective:
- stable operating point with predictable tuning knobs:
  - gas pressure
  - resonance frequency
  - load impedance
  - HHX/CHX temperature delta

### Block E — Heat Rejection (Cold Side)
TA systems are limited by ΔT and heat rejection.
Cold-side design must be explicit:
- forced convection heatsink for terrestrial prototypes
- liquid loop for higher performance prototypes
- radiator concept only after ground performance is characterized

### Block F — Instrumentation + DAQ
To be taken seriously, the system must log:
- input conditions (estimated flux / aperture temperature proxy)
- receiver temperatures (multiple cells)
- manifold temperature(s)
- TA pressure/acoustic amplitude proxy
- electrical output (V, I, phase) and load
- cold-side temperatures and coolant flow (if used)

---

## Geometry Scaling Strategy

### Recommended scaling approach
Design the architecture as a honeycomb from the beginning, but validate it via modular repetition:
- Define a standard receiver cell mechanical + thermal interface.
- Define a standard manifold interface “port” for each cell.
- Build a 6+1 or 9+1 configuration first using the same interfaces.
- Scale to 19-cell (1 + 6 + 12) by repeating the proven module.

This avoids redesign. It does not avoid testing reality.

---

## What “Success” Means (for this repo)
IX-STAR-TA is considered successful at the proof-of-concept level when:
1) a receiver cell can be characterized (thermal capture and losses),
2) manifold combining behaves predictably as cell count increases,
3) PCM demonstrably reduces hot-side temperature swing,
4) TA core produces repeatable electrical output under controlled conditions,
5) a test report can be reproduced by another engineer from the logs and setup notes.

---

## Claims Boundary
IX-STAR-TA does not claim:
- novel physics,
- extraordinary efficiency,
- performance without test data.

It provides a design and test framework aimed at producing defensible evidence.
