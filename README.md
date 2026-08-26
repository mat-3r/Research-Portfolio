# Undergraduate Research Portfolio: Physics & Astronomy

A collection of computational and observational projects conducted during my undergraduate studies in astronomy at the University of Arizona, with minors in mathematics and physics. This repository showcases my experience with data analysis, numerical modeling, and astrophysical systems, emphasizing both theoretical foundations and practical coding implementations. Work spans N-body simulation analysis, photometric data reduction, and numerical modeling, including approximately 25 hours of observing on the Kuiper 61-inch telescope at Steward Observatory.

**Tools:** Python (NumPy, SciPy, Matplotlib, AstroPy), AstroImageJ, Jupyter, Git, Latex

---

## Projects Overview

### 1. **[Decoding Dark Matter's Secrets Through Galactic Mergers]**
[Code and report ->](https://github.com/mat-3r/astr400B/tree/main/ResearchAssignments/ResearchAssignment7)

- **Objective:** Analyze the final remnant structural evolution of the Dark Matter halo during a major merger by comparing the merged halo’s density profile to Navarro-Frenk-White and Hernquist Profiles to evaluate how accurately these models describe the post merger structure.
- **Methods Used:** N-body simulations, Hernquist and NFW analytical models, R200 computation from critical density, Python, radial density binning, Center of Mass.
- **Key Results:**
  - The NFW profile is close to the simulated density distribution, even at larger radii.
  - A well defined boundary of R200 = 150.7789 kpc was computed for the remnant halo.
  - The inner regions remained dense and stable, while the outer regions was reshaped by the redistribution.
- **Outcome:** Supports the CDM prediction that Dark Matter halos follow a universal density profile even after major mergers. These results move forward our overall understanding of galaxy evolution, emphasizing the vital role of the NFW model in accurately representing post-merger halo structures. It also demonstrates how structural changes during mergers provide the foundation for decoding Dark Matter’s true nature.

---

### 2. **[Photometric Analysis of GALEX J082053.6+000843]**
[Notebook ->](https://github.com/mat-3r/Research-Portfolio/blob/main/sdb-low-mass/sdb_photometry.ipynb)

- **Objective:** Analyze an eclipsing binary system composed of an sdB primary and a brown dwarf companion.
- **Methods Used:** AstroImageJ, multi-aperture photometry, Lomb-Scargle periodogram, Python.
- **Key Results:**
  - Orbital period determined via time-series analysis.
  - Light curve modeling captured reflection effects due to tidal locking.
  - Comparison with MUCHFUSS project benchmarks showed consistency.
- **Outcome:** System modeling yielded a ~3.03% uncertainty and reinforced models of irradiated low-mass companions in short period sdB binaries.

---

### 3. **[Model of Foucault Pendulum: Unlocking the Mysteries of Earth’s Rotation]**
[Report](https://github.com/mat-3r/Research-Portfolio/blob/main/foucault-pendulum-rk4/model-pendulum.pdf)

- **Objective:** Demonstrate Earth's rotation through the numerical modeling of a Foucault pendulum.
- **Methods Used:** 4th Order Runge-Kutta (RK4) method, Python, numerical integration.
- **Key Results:**
  - Precession rates were computed at four latitudes: Equator, New York, Japan, and Antarctica.
  - Modeled values were compared against theoretical predictions using Earth’s angular velocity.
  - Conservation of total mechanical energy was numerically confirmed.
- **Outcome:** Error was reduced to ~18.3%, validating the accuracy of the simulation and confirming Earth’s rotation, debunking flat Earth claims.


---
