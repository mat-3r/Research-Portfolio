# Undergraduate Research Portfolio: Physics & Astronomy

A collection of computational and observational projects conducted during my undergraduate studies in astronomy at the University of Arizona, with minors in mathematics. This repository showcases my experience with data analysis, numerical modeling, and astrophysical systems, emphasizing both theoretical foundations and practical coding implementations. Work spans N-body simulation analysis, photometric data reduction, and numerical modeling, including approximately 25 hours of observing on the Kuiper 61-inch telescope at Steward Observatory.

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
[Code and Report](https://github.com/mat-3r/Research-Portfolio/blob/main/foucault-pendulum-rk4/model-pendulum.pdf)

- **Objective:** Model the motion and precession of a Foucault pendulum numerically and compare the computed precession rates against theoretical values derived from Earth's rotational dynamics. Latitudes modeled: equator (0°), Japan (36.2048°), New York (40.7128°), Antarctica (82.8628°).
  
- **Methods:** Fourth-order Runge-Kutta (RK4) used to numerically solve the equations of motion under Coriolis forcing. Timestep (dt) = 0.0003 s, pendulum length (L) = 64 m, mass (m) = 10 kg. Total mechanical energy evaluated numerically at each step to confirm energy was conserved throughout. Python (NumPy, Matplotlib).
  
- **Results:**
  - Modeled precession rates match theoretical values to 0.000% error at all four latitudes.
  - Higher latitudes showed greater precession while the equator showed none, consistent with the Coriolis force depending on sin(φ).
  - Total mechanical energy remained constant to within 0.02% across all simulations, confirming the model remained stable.
    
- **Outcome:** The model reproduces Earth's rotational dynamics across latitude. The original version of this analysis reported an 18.3% discrepancy, consistent at every latitude. That constant offset was traced to the measurement step rather than to the model itself.

- **Note on measurement:** The pendulum's natural period is 16.0567 s. The original run time of T = 100 s ends after 6.23 periods, leaving the pendulum mid-swing at the final timestep. The measured angle arctan(y/x) contains both the precession of the oscillation plane and the pendulum's own position within its swing, so stopping halfway through a swing gives an inaccurate result. The size of the error tracks the size of the precession, which is why every latitude returned the same 18.3%. When the run stops at a whole number of swings, the modeled and theoretical values agree exactly.
  
*Contains: Python model and full written report.*

---
