# Data Sources — WMD Proliferation Monte Carlo Simulation

Channel parameters in `mc_simulation.py` trace to the sources listed here.
The paper (WMD Proliferation: Capability Diffusion Ceiling) is available on SSRN and contains the full
reference list and §4 calibration narrative.

---

## Channel Sources

### `C1_direct_harm`

$800B/yr expected catastrophic damage; probability-weighted nuclear+bio+chem detonation scenarios (Hellman 2008 annual probability ~1%, Toon et al. 2019 nuclear winter damage ~$50-80T per exchange)

*Full citations: paper §4 (available SSRN).*

### `C2_opportunity_cost`

$500B/yr; WMD-attributable defense spending (nuclear forces ~$300B across 9 states, missile defense ~$100B, CBRN ~$50B, bio-defense ~$50B; SIPRI 2024 total $2.4T)

*Full citations: paper §4 (available SSRN).*

### `C3_geopolitical_externality`

$350B/yr; deterrence posture costs, alliance maintenance, arms race dynamics, proliferation risk externalities across 9 nuclear states

*Full citations: paper §4 (available SSRN).*

### `C4_environmental_damage`

$150B/yr; nuclear testing legacy (2,056 tests), site remediation, cancer burden (173-368K excess cases), contaminated land exclusion zones

*Full citations: paper §4 (available SSRN).*

### `C5_institutional_cost`

$40B/yr; IAEA ($0.6B), CTBTO, OPCW, BWC, national export control regimes, intelligence/verification programs, nonproliferation diplomacy

*Full citations: paper §4 (available SSRN).*

---

## Industry Revenue (Π)

The private payoff Π = $86.4B/yr is global annual industry revenue.
Source: paper §2 and §4. See paper §DA-1 (Decision Audit Field 7) for full
revenue source documentation.

---

## SAPM Framework

- Postnieks, E. (2026). *The Private Pareto Theorem*. SAPM Foundation Paper. SSRN.
- Postnieks, E. (2026). *WMD Proliferation (Capability Diffusion Ceiling)*. SAPM Working Paper. SSRN.

---

## Distribution Methodology

- Iman, R. L., & Conover, W. J. (1982). A distribution-free approach to
  inducing rank correlation among input variables. *Communications in
  Statistics — Simulation and Computation*, 11(3), 311–334.
- Cooke, R. M. (1991). *Experts in Uncertainty*. Oxford University Press.
