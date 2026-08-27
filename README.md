# Undergraduate Research Portfolio: Physics & Astronomy

A collection of computational and observational projects conducted during my undergraduate studies in astronomy at the University of Arizona, with minors in mathematics and physics. This repository showcases my experience with data analysis, numerical modeling, and astrophysical systems, emphasizing both theoretical foundations and practical coding implementations. Work spans N-body simulation analysis, photometric data reduction, and numerical modeling, including approximately 25 hours of observing on the Kuiper 61-inch telescope at Steward Observatory.

**Tools:** Python (NumPy, SciPy, Matplotlib, AstroPy), AstroImageJ, Jupyter, Git, Latex

---

## Projects Overview

### 1. **Decoding Dark Matter's Secrets Through Galactic Mergers**
[Code and Report](https://github.com/mat-3r/astr400B/tree/main/ResearchAssignments/ResearchAssignment7)

- **Objective:** Analyze the final remnant structural evolution of the Dark Matter halo during a major merger between two galaxies, comparing the merged halo's density profile to Navarro-Frenk-White and Hernquist Profiles to investigate how accurately these analytic models represent Dark Matter behavior.
  
- **Methods:** N-body simulation data (Milky Way–M31, snapshot 779, ~11.1 Gyr), Hernquist and NFW analytical models, Center of Mass determination, radial density binning, R200 computation from critical density. Python.
  
- **Results:**
  - The NFW profile closely tracks the simulated density distribution, holding even at large radii.
  - Computed a well defined remnant halo boundary of R200 = 150.78 kpc.
  - Inner regions remained dense and stable while outer regions experienced the greatest redistribution.
    
- **Outcome:** Supports the Cold Dark Matter prediction that Dark Matter halos retain a universal density profile through a major merger. These results reinforce the role of the NFW model in representing post-merger halo structures. It also demonstrates how structural changes during mergers provide the foundation for decoding Dark Matter’s true nature. Limitations include sensitivity to radial binning and scale radius selection, and the omission of dynamical friction from the analytic models.

*Contains: Python analysis, plots, and full written report.*

---

### 2. **Photometric Analysis of GALEX J082053.6+000843**
[Notebook](https://github.com/mat-3r/Research-Portfolio/blob/main/sdb-low-mass/sdb_photometry.ipynb)

- **Objective:** Determine the orbital period and analyze the structure of the eclipsing binary GALEX J082053.6+000843, a subdwarf B primary with a tidally locked brown dwarf companion, through reflection effects in the light curve.
  
- **Methods:** Reduction of 269 science exposures (80-second exposures, 23 Feb 2025) in AstroImageJ with bias subtraction and flat-field correction; multi-aperture differential photometry against 8 calibration stars; phase folding; Lomb-Scargle periodogram analysis. Python (pandas).
  
- **Results:**
  - Obtained an orbital period of 8046.17 s (0.09312 days), a 3.03% deviation from the theoretical value of 0.09603 days (Geier et al. 2011).
  - Identified three distinct features in the phase-folded light curve: the primary eclipse, the irradiated face of the companion, and the cool face transiting the primary.
  - Light curves generated independently in AstroImageJ and Python produced consistent results, confirming the reliability of the reduction.
    
- **Outcome:** Confirms the brown dwarf companion and reinforces models of irradiated low-mass companions in close sdB binaries. Residual discrepancy attributable to photometric noise and possible reduction error. A known dead column in the CCD detector was assessed as minimal.

*Contains: Jupyter notebook with full reduction and analysis.*

---

### 3. **Model of Foucault Pendulum**
[Report](https://github.com/mat-3r/Research-Portfolio/blob/main/foucault-pendulum-rk4/model-pendulum.pdf)

- **Objective:** Demonstrate Earth's rotation through the numerical modeling of a Foucault pendulum.
- **Methods Used:** 4th Order Runge-Kutta (RK4) method, Python, numerical integration.
- **Key Results:**
  - Precession rates were computed at four latitudes: Equator, New York, Japan, and Antarctica.
  - Modeled values were compared against theoretical predictions using Earth’s angular velocity.
  - Conservation of total mechanical energy was numerically confirmed.
- **Outcome:** Error was reduced to ~18.3%, validating the accuracy of the simulation and confirming Earth’s rotation, debunking flat Earth claims.


---
