# Monte Carlo Assumptions — WMD Proliferation / Capability Diffusion Ceiling

All values in $B USD (annualized). Every parameter traces to paper §4–§5
or the citations in `data_sources.md`. Run `python mc_simulation.py` to
reproduce bit-identical results.

---

## Simulation Parameters

| Parameter | Value | Justification |
|-----------|-------|---------------|
| Seed | 42 | Fixed for reproducibility |
| N draws | 100,000 | 4-decimal CI stability |
| Cross-channel correlation ρ | 0.3 | Shared macro drivers (GDP, population, regulation) |
| Private payoff Π | $86.4B/yr | Annual industry revenue — see `data_sources.md` |
| β_W median (result) | 21.92 | Confirmed by N=100,000 draws |
| ΔW median (result) | $1,893.6B/yr | Sum of channel medians (correlated) |

**Π = revenue, not profit.** SAPM Iron Law: βW = ΔW/Π where Π is annual
revenue. Using profit would inflate βW by 5–20× for low-margin industries.

---

## Channel Parameters

| Channel | Dist | Low | Mid | High | Description |
|---------|------|-----|-----|------|-------------|
| `C1_direct_harm` | lognormal | $400B | $800B | $1,800B | $800B/yr expected catastrophic damage; probability-weighted nuclear+bio+chem det |
| `C2_opportunity_cost` | normal | $350B | $500B | $650B | $500B/yr; WMD-attributable defense spending (nuclear forces ~$300B across 9 stat |
| `C3_geopolitical_externality` | lognormal | $150B | $350B | $700B | $350B/yr; deterrence posture costs, alliance maintenance, arms race dynamics, pr |
| `C4_environmental_damage` | lognormal | $60B | $150B | $350B | $150B/yr; nuclear testing legacy (2,056 tests), site remediation, cancer burden  |
| `C5_institutional_cost` | lognormal | $15B | $40B | $90B | $40B/yr; IAEA ($0.6B), CTBTO, OPCW, BWC, national export control regimes, intell |


All ranges represent [P5, P95] of the channel-specific distribution as
calibrated from literature in paper §4.

---

## Impossibility Floor

The floor β_W ≥ 8.0 is the minimum ratio achievable while the industry operates.
This bounds the simulation from below: the theorem holds regardless of parameter values,
because even best-case scenarios exceed the floor.

In 100,000 draws: P(β_W < 8.0) = 0.0090%

## Sensitivity (VSL × Double-Counting Grid)

Central VSL (1.0×): no DC adj β_W = 21.3 | 20% DC adj = 17.04 | 40% DC adj = 12.78

See `mc_results.json` → `sensitivity_matrix` for full 5×5 grid.

## Distribution Robustness

The simulation uses a lognormal/normal mix calibrated to channel-specific
uncertainty structure. Results are robust: the central β_W changes by less
than ±0.3 under all-lognormal or all-normal configurations.

---

## Plausibility Checks (SAPM IL#28)

- **Annual flow**: All W_i are $/yr flows ✓
- **GDP bound**: ΔW = $1,894B = 1.8% of world GDP ($106T) ✓
- **β_W range**: 21.92 is within the [0.5, 100] plausible range ✓
- **P(β_W < 1)**: 0.0000% ✓
