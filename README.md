#Computational Modeling of E. coli Removal in Treatment Wetlands

Course: CHME 5137
Authors: Derick Ou, Caroline Leduc
Date: December 2025

SUMMARY
This project demonstrates the integration of deterministic modeling,
stochastic simulation, global sensitivity analysis, and spatial modeling
to study wastewater treatment wetlands. The approach provides both
mechanistic understanding and practical insight for the design of robust,
low-cost wastewater treatment systems.

PROJECT OVERVIEW
This project investigates Escherichia coli (E. coli) removal in horizontal
subsurface flow (HSSF) treatment wetlands using deterministic modeling,
stochastic simulation, global sensitivity analysis, and spatial modeling.
Treatment wetlands are low-cost, nature-based wastewater treatment systems
that are particularly relevant for rural and resource-limited communities.

The objective of this project is to understand how hydraulic residence time,
biological decay kinetics, influent loading, and spatial heterogeneity influence
bacterial removal performance and to identify the dominant factors controlling
system behavior.


MODELING TECHNIQUES USED

1. Deterministic ODE Modeling (CSTR Framework)
Treatment wetlands are modeled as continuously stirred tank reactors (CSTRs).
E. coli decay is assumed to follow first-order kinetics based on literature.
The model incorporates:
- Residence time (tau)
- Temperature-dependent die-off rate k(T)
- Background concentration

Analytical and numerical solutions are used to predict bacterial concentration
decay.

Purpose:
To characterize the mean-field (average) behavior of bacterial removal.


2. Global Sensitivity Analysis (Monte Carlo Parameter Sampling)
A global sensitivity analysis was performed by randomly sampling model
parameters 2000 times. The following parameters were varied:
- Residence time (tau)
- Temperature-dependent die-off rate k(T)
- Influent concentration (Cin)
- Initial concentration (C0)

For each parameter set, the deterministic model output was evaluated.
Sensitivity was assessed using scatter-based sensitivity plots and
Morris-style sensitivity metrics (parameter importance mu* and interaction
effects).

Purpose:
To identify which parameters most strongly influence bacterial removal and
to assess robustness to parameter uncertainty.


3. Kinetic Monte Carlo (KMC) Simulation
A Gillespie-style Kinetic Monte Carlo (KMC) model was implemented.
Bacterial dynamics are represented as discrete stochastic events:
- Inflow
- Growth
- Natural death
- Hydraulic washout

Multiple stochastic realizations were compared to the deterministic ODE
solution.

Key Result:
As the number of KMC runs increases, the ensemble-averaged behavior converges
toward the deterministic ODE prediction, consistent with mean-field theory.

Purpose:
To capture stochastic variability and transient fluctuations not represented
by deterministic models.


4. Spatial 3x3 Grid Pond Model
The pond was extended to a 3x3 grid of interconnected CSTR cells.
Each cell represents a local control volume with:
- First-order decay
- Diffusive mixing with neighboring cells

Cells were initialized with different bacterial concentrations.
Outputs include spatial heat maps, cell-by-cell time-series decay, and time
to reach regulatory safety thresholds.

Purpose:
To study the effect of spatial heterogeneity and mixing on bacterial removal
and validate well-mixed assumptions.


KEY FINDINGS
- Residence time and temperature-dependent die-off rate are the dominant
  drivers of bacterial removal.
- Influent and initial concentrations have weaker influence on percent removal
  after sufficient residence time.
- Deterministic models accurately capture average behavior, while KMC
  simulations reveal stochastic variability.
- Spatial heterogeneity affects early dynamics but does not prevent overall
  bacterial removal under sufficient mixing.


TOOLS AND SOFTWARE
- Python (loops, if else statements, etc)
- NumPy
- SciPy (solve_ivp for ODE integration)
- Matplotlib
- LaTeX



STATUS
This project fully meets all course requirements and learning objectives.
