# Research Direction: Stochastic Orbital Dynamics

*Claude Sonnet 3.7*

## Starting Point: The Papers

Three papers formed the context for this discussion:

  1. **Probabilistic Targeting with Gaussian Positional Uncertainty** — integrating a 2D Gaussian PDF over a circular aim-region to compute hit probability, with a closed-form special case when aim-point and threat coincide, and a polar coordinate formulation for the general case.

  2. **Collision Probability Assessment for Spherically Symmetric Debris Cloud Models** — a Monte Carlo-based Poisson process model for the ~120 second spherical phase after fragmentation, addressing the methodological gap in the immediate post-fragmentation period.

  3. **Probability Generating Function for Independent Trials** — deriving expected value and probability distributions for independent trials via PGFs and the linearity of expectation.

## Choosing a New Research Direction

### Two Candidate Topics (via Galileo AI)

#### Option A: Stochastic Orbital Dynamics

Focuses on randomness and uncertainty in orbital mechanics — propagation of errors, stochastic forces (atmospheric drag, solar radiation pressure, thrust misalignment). Integrates differential equations, probabilistic modeling, and uncertainty quantification. Stays in the realm of pure mathematics and theoretical physics.

#### Option B: Astrodynamics of Swarm / Multi-agent Systems

Focuses on dynamics, coordination, and interactions within multiple spacecraft. Involves multi-body orbital mechanics, graph theory, probabilistic collision avoidance, and decentralized control. More interdisciplinary, touching control theory and applied engineering.

### Decision

**Stochastic Orbital Dynamics** — the more natural continuation of existing work. The debris cloud preprint already lives at the boundary of this field. The probabilistic targeting paper and PGF paper form a coherent thread that Stochastic OD extends directly. Swarms would be an interesting lateral move but risks feeling like starting over, and the core pull wasn’t deep enough to sustain a long research program.

## The Two-Paper Arc

### Paper 1: Uncertainty Propagation Through Perturbed Keplerian Motion

**Start with:** A Gaussian uncertainty distribution on the initial state of a fragment (or any orbiting object) under perturbed Keplerian motion — J2 and atmospheric drag as the primary perturbations. The Gaussian positional uncertainty machinery from the targeting paper provides the natural starting point.

**End with:** A characterization of how that initial Gaussian deforms over time — showing quantitatively when and why it stops being Gaussian, what drives the non-Gaussianity (J2 vs drag vs initial separation distance), and what that means for collision probability estimates that assume Gaussianity. The punchline is that operational tools making Gaussian assumptions are introducing calculable errors, and those errors can be bounded.

-----

### Paper 2: Stochastic Differential Equations for Orbital Elements

**Start with:** The limitations explicitly identified at the end of Paper 1 — specifically, that propagating a PDF forward through nonlinear dynamics is fundamentally limited by the Gaussian assumption.

**End with:** A full SDE formulation of the orbital elements where randomness is baked into the equations of motion themselves rather than treated as initial condition uncertainty. This requires Itô calculus and is more mathematically ambitious.

**The bridge:** Paper 1 will naturally hit a wall where standard uncertainty propagation techniques become inadequate. That wall is the motivation for Paper 2 — “our previous approach had these limitations, and the SDE framework resolves them.” The two papers form a coherent sequential arc.

## Foundation Papers to Read Before Writing Paper 1

These are the references needed to avoid getting flagged in peer review for insufficient literature grounding:

  - **Jazwinski (1970)** — *Stochastic Processes and Filtering Theory* — mathematical backbone for both papers.

  - **Junkins & Singla (2004)** — *How Nonlinear is It? A Tutorial on Nonlinearity of Orbit and Attitude Dynamics* — directly addresses when linearization breaks down.

  - **Park & Scheeres (2006)** — *Nonlinear Mapping of Gaussian Statistics: Theory and Applications to Spacecraft Trajectory Design* — foundational for Paper 1 specifically.

  - **Horwood, Aragon & Poore (2011)** — *Gaussian Sum Filters for Space Surveillance: Theory and Simulations* — Gaussian mixture models for nonlinear uncertainty propagation in orbital mechanics.

  - **Vallado (2013)** — *Fundamentals of Astrodynamics and Applications* — orbital mechanics reference baseline.

-----

Begin with Park & Scheeres and Junkins & Singla. Those two will define what’s already been done and where the open edges are.
