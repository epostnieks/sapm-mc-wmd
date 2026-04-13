# SAPM Monte Carlo — WMD Proliferation / Capability Diffusion Ceiling

**Public replication repository for quantitative results in:**

> Postnieks, E. (2026). *WMD Proliferation (Capability Diffusion Ceiling).* SAPM Working Paper. SSRN.

This repository provides everything needed to independently reproduce, audit,
and extend the Monte Carlo simulation underlying the paper's core results.
The paper is available on SSRN.

---

## Results (N = 100,000 draws, seed = 42)

| Statistic | Value |
|-----------|-------|
| **β_W median** | **21.92** |
| β_W mean | 23.15 |
| β_W std | 7.29 |
| **90% CI** | **[13.8, 36.6]** |
| 99% CI | [11.4, 46.2] |
| P(β_W < 1) | 0.0000% |
| **ΔW median** | **$1,893.6B/yr** |
| Π (revenue) | $86.4B/yr |

**β_W = 21.92** means the wmd proliferation industry destroys **$21.92 in system
welfare for every $1.00 in revenue** — across 5 channels and 100,000 Monte Carlo draws.

**Classification**: Class 1 — Impossibility

---

## What Is β_W?

```
β_W = ΔW / Π
```

- **ΔW** = total annualized welfare destruction ($B/yr) across all channels
- **Π** = annual industry **revenue** ($B/yr) — not profit

β_W > 1: industry destroys more welfare than it captures in revenue.
β_W > 3: Strong Intractability threshold — reform requires structural replacement.

---

## Quick Start

```bash
git clone https://github.com/epostnieks/sapm-mc-wmd.git
cd sapm-mc-wmd
pip install numpy scipy
python mc_simulation.py
```

Expected output: `β_W median : 21.92` and `ΔW median : $1,893.6B/yr`

---

## Welfare Channels

| Channel | Median ($B/yr) | 90% CI | Distribution |
|---------|---------------|--------|--------------|
| C1_direct_harm | $798.4B | [$354.7B, $1,787.2B] | Lognormal |
| C2_opportunity_cost | $499.8B | [$350.0B, $650.2B] | Normal |
| C3_geopolitical_externality | $349.6B | [$174.7B, $698.7B] | Lognormal |
| C4_environmental_damage | $150.0B | [$64.4B, $350.5B] | Lognormal |
| C5_institutional_cost | $40.0B | [$17.7B, $89.8B] | Lognormal |
| **Total ΔW** | **$1,893.6B** | **[$1,188.3B, $3,165.1B]** | Correlated (ρ=0.3) |

---

## Impossibility Floor

The floor β_W ≥ 8.0 cannot be breached by any policy while the
industry continues to operate. In 100,000 draws, only **0.0090%**
fall below this floor — confirming the structural constraint.

## Repository Contents

| File | Description |
|------|-------------|
| `mc_simulation.py` | Self-contained simulation — no private pipeline imports |
| `mc_results.json` | Pre-run results (100K draws, seed=42) — matches paper |
| `mc_histogram.json` | Binned β_W distribution (80 bins) for companion chart |
| `assumptions.md` | Every parameter: value, derivation, source |
| `data_sources.md` | Full citation list for all empirical inputs |

---

## Replication Notes

Results are seeded and deterministic. Tested with:
```
numpy==1.26.4  scipy==1.12.0  Python 3.11.9
```

The `median` and `ci_90` (to 1 decimal) match exactly across compatible versions.

---

## License

CC BY 4.0. Cite as:

> Postnieks, E. (2026). *SAPM Monte Carlo — WMD Proliferation (Capability Diffusion Ceiling)*.
> GitHub: epostnieks/sapm-mc-wmd.
> https://github.com/epostnieks/sapm-mc-wmd
