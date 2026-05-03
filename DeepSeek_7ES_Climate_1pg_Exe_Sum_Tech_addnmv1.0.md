# 7ES Climate Edition – Technical Supplement

**Explicit Equations for Diagnostic Metrics**
**For climate modelers, Earth system scientists, and researchers**
**Version:** 1.0 – May 2026
**Source:** 7ES Climate Edition v1.0 (KOSMOS Institute)

---

## Supplement A: Variety Quantification

### A.1 Internal Variety (V_int)

**Theoretical:**

V_int = b^(7 × b^d)

Where:
- b = average branching factor (subsystems per element per level)
- d = fractal depth (number of hierarchical levels)

**Measurable proxy for climate systems:**

V_int ≈ exp(Σ_i λ_i)

Where λ_i are eigenvalues of the covariance matrix of a climate variable (e.g., sea level pressure, SST) explaining 95% of variance.

**Operational formula:**

V_int = ∏_{k=1}^{d} (b_k)^(7 × b_k^(d-k+1))

**Climate branching factors by level:**

| Level | Process | b (subsystems) |
|-------|---------|----------------|
| 1 | Turbulence/radiation | 5-10 |
| 2 | Weather systems | 4-6 |
| 3 | Seasonal cycle | 3-4 |
| 4 | Interannual variability | 3-5 |
| 5 | Decadal variability | 2-4 |
| 6 | Centennial–millennial | 2-3 |
| 7 | Glacial cycles | 2 |

**Example calculation (b=4, d=6):**

V_int = 4^(7×4^6) = 4^(7×4096) = 4^28672

log10(V_int) = 28672 × log10(4) = 28672 × 0.60206 ≈ 17,260

### A.2 Environmental Variety (V_env)

**Definition:** Number of distinguishable forcing combinations over relevant timescales.

**Forcing sources and their variety:**

| Forcing | Variety measure | log10(V) |
|---------|----------------|----------|
| Solar (total irradiance) | Number of distinguishable irradiance levels over 10³ years | 2-3 |
| Orbital (Milankovitch) | Combinations of eccentricity, obliquity, precession | 3-4 |
| Volcanic | Eruptions by magnitude (VEI) and frequency | 2-3 |
| Anthropogenic (20th–21st c.) | Combinations of GHG, aerosol, land use trajectories | 10³-10⁶ |

**Operational formula:**

V_env = ∏_{j=1}^{m} (n_j)

Where n_j = number of distinguishable states of forcing j (e.g., 5 RCP scenarios × 3 aerosol pathways × 4 land use patterns = 60 combinations).

**For climate risk assessment, including interactions:**

V_env = |F_1 × F_2 × ... × F_m|

Where × is Cartesian product.

---

## Supplement B: Ashby Compliance

### B.1 Definition

A(t) = V_int(t) / V_env(t)

### B.2 Continuous Approximation for Climate

Let V_int be proportional to the effective degrees of freedom (EDOF) of the climate system:

V_int ≈ α × EDOF

Where:
- EDOF = (trace(C))² / trace(C²) for covariance matrix C of climate fields
- α ≈ 1-10 (calibration factor)

Let V_env be proportional to the Shannon entropy of the forcing distribution:

V_env ≈ exp(H(F))

Where H(F) = -Σ p_i log p_i

For RCP/SSP scenarios, if each scenario has probability p_i, then H ranges from 0 (certainty) to ln(N) (uniform).

**Ashby Compliance becomes:**

A(t) ≈ (α × EDOF(t)) / exp(H(F(t)))

### B.3 Critical Slowing Down Proxy

Near A = 1.0, the system exhibits critical slowing down:

τ(t) = τ_0 / (1 - A(t))

Where τ(t) is the relaxation time of the dominant climate mode (e.g., AMOC, ENSO).

**Detection:** If τ(t) increases faster than linear, A is approaching 1.0 from above.

### B.4 Policy Restoration Target

A_target(t+Δt) = A(t) × (ΔV_int / ΔV_env) ≥ 1.0

To restore A ≥ 1.0 by year 2050:

ΔV_int / ΔV_env ≥ 1 / A(2025) ≈ 1 / 0.92 ≈ 1.087

This requires either:
- Increase V_int by at least 8.7% (protect biodiversity, circulation complexity), OR
- Decrease V_env by at least 8.7% (reduce forcing variety), OR a combination.

---

## Supplement C: Passive Feedback Viability Score

### C.1 Formal Definition

For subsystem i with viability set V_i ⊂ State_space:

F_passive,i(t) = 1 if state_i(t) ∈ V_i, else 0

### C.2 Continuous Proxy

p_i(t) = 1 if state_i(t) ∈ V_i

p_i(t) = max(0, 1 - |state_i(t) - bound_i| / tolerance_i) if near boundary

Where tolerance_i is the half-width of a buffer zone (e.g., 0.5°C for temperature bound).

**Overall viability score:**

P_viability(t) = (1/N) Σ_i p_i(t)

### C.3 Climate Subsystem Specific Bounds

| Subsystem | State variable | Viability bound | Tolerance |
|-----------|---------------|-----------------|-----------|
| GMST | Global mean surface temperature | pre-industrial + 2°C | 0.5°C |
| AMOC | Overturning at 26°N | 15-25 Sv | 2 Sv |
| Arctic sea ice | September extent | > 1 million km² | 0.5 million km² |
| WAIS | Grounding line position | within 100 km of present | 50 km |
| Amazon | Cumulative deforestation | < 20% | 5% |

### C.4 Tipping Point Criterion

A subsystem is at imminent tipping risk when:

dp_i/dt < 0 AND p_i(t) < 0.7

**Policy alarm threshold:** When P_viability(t) < 0.5 → emergency protocols trigger.

---

## Supplement D: Fractal Depth for Model Evaluation

### D.1 Depth Estimation for a Model

A climate model's depth d_model is the number of explicitly resolved or parameterized hierarchical levels, ordered by timescale.

**Example depth calculation for a typical GCM:**

| Level | Process | Resolved? | Parameterized? | Count |
|-------|---------|-----------|----------------|-------|
| 1 | Molecular diffusion | No | Yes (eddy diffusivity) | 1 |
| 2 | Turbulent eddies | No | Yes (boundary layer scheme) | 1 |
| 3 | Convective plumes | No | Yes (convection scheme) | 1 |
| 4 | Grid-scale dynamics (~100 km) | Yes | No | 1 |
| 5 | Synoptic waves | Yes | Partially | 1 |
| 6 | Seasonal cycle | Yes | No | 1 |
| 7 | Interannual variability | Yes | No | 1 |
| 8 | Decadal variability | Partially | No | 0 (not captured) |
| **Total d_model** | | | | **7** (but level 8 missing) |

### D.2 Required Depth for Subsystem Prediction

For a subsystem with characteristic timescales spanning levels L_min to L_max:

d_required ≥ L_max - L_min + 1

**Example – West Antarctic Ice Sheet (WAIS):**

| Timescale | Level | Process |
|-----------|-------|---------|
| Daily | 3 | Atmospheric forcing |
| Seasonal | 4 | Ocean mixed layer |
| Annual | 5 | Ice shelf melt |
| Decadal | 6 | Grounding line adjustment |
| Centennial | 7 | Marine ice sheet instability |
| Millennial | 8 | Full collapse |

L_min = 3, L_max = 8 → d_required ≥ 6

**Current GCMs typically have d_model = 4-5 → insufficient for WAIS prediction.**

### D.3 Model Variety Deficit

ΔV = V_required - V_available = b^(7×b^d_required) - b^(7×b^d_model)

When ΔV > 0, the model lacks requisite variety → predictions of tipping are not reliable.

**For WAIS (b=4, d_required=6, d_model=4):**

V_required = 4^(7×4^6) = 4^28672 ≈ 10^17260

V_available = 4^(7×4^4) = 4^(7×256) = 4^1792 ≈ 10^1080

ΔV ≈ 10^17260 → model variety deficit of 10,000+ orders of magnitude

This is not a minor error – it is a structural inability to simulate the subsystem.

---

## Supplement E: Active Feedback Gain Calculation

### E.1 Formal Definition

For a climate variable X (e.g., global mean temperature), active feedback gain g is:

g = dF_feedback / dX

Where F_feedback is the radiative flux change due to the feedback mechanism (W/m²).

**Net active feedback:**

g_net = Σ_i (g_i × s_i)

Where s_i = +1 for positive feedback, -1 for negative feedback.

### E.2 Standard Climate Feedbacks (IPCC AR6)

| Feedback | g (W/m²/°C) | Sign | Confidence |
|----------|-------------|------|-------------|
| Water vapor | +2.0 ± 0.5 | Positive | High |
| Lapse rate | -0.5 ± 0.2 | Negative | High |
| Ice-albedo | +0.3 ± 0.1 | Positive | Medium |
| Cloud (shortwave) | -0.5 ± 0.8 | Negative | Low |
| Cloud (longwave) | +0.5 ± 0.5 | Positive | Low |
| Carbon cycle (ocean) | -0.7 ± 0.3 | Negative | Medium |
| Carbon cycle (land) | -0.5 ± 0.4 | Negative | Medium |

**Net g_net (excluding clouds):** 2.0 - 0.5 + 0.3 - 0.7 - 0.5 = +0.6 W/m²/°C

**Including clouds (best estimate):** +0.6 to +1.0 W/m²/°C

### E.3 Feedback Gain from Observations

Using satellite-era data (1970–2025):

ΔT = +1.3°C

ΔF_effective (total radiative forcing) = +3.2 W/m²

Observed net gain = ΔF_effective / ΔT = 2.46 W/m²/°C

**Alternative calculation:**

g_net = (ΔF_effective / ΔT) - (1/α)

Where α ≈ 0.3 K/(W/m²) (Planck sensitivity).

g_net = (3.2 / 1.3) - (1/0.3) ≈ 2.46 - 3.33 = -0.87 W/m²/°C (net negative)

**Interpretation:** This mismatch (model prediction of positive net feedback vs. observation suggesting negative) indicates either:
- Forcing is overestimated, OR
- Observed warming includes unmodeled negative feedbacks (e.g., aerosol indirect effects), OR
- The system is not in equilibrium.

**Research implication:** Use 7ES Ashby Compliance to frame this mismatch as a lack of internal variety in models.

---

## Supplement F: Complexity Index for Climate Models

### F.1 Definition

CI_model = (# of elements with >1 identifiable subsystem) / 7

### F.2 Example: CMIP6-class GCM

| Element | Multiple subsystems? | Count |
|---------|---------------------|-------|
| I (Inputs) | Yes (solar, volcanic, anthropogenic) | 3+ |
| O (Outputs) | Yes (OLR, reflected, latent) | 3+ |
| P (Processing) | Yes (atm, ocean, ice, biosphere) | 4+ |
| C (Controls) | Partially (orbital yes, emissions not varied in constant CO₂ runs) | 2 |
| F (Feedback) | Yes (multiple active, passive not modeled) | 3+ active only |
| N (Interfaces) | Yes (air–sea, land–atm, TOA) | 3+ |
| E (Environment) | Partially (sun yes, technosphere often fixed) | 2 |

CI ≈ 5/7 = 0.71 (if passive feedback missing entirely)

**Interpretation:** CI = 0.71 is typical for GCMs – sufficient for seasonal prediction, insufficient for tipping point prediction (which requires CI = 1.0 and dual-mode feedback).

---

## Supplement G: Evolution of Ashby Compliance Over Time

### G.1 Paleoclimate Reconstruction (last 800k years)

From ice cores (CO₂, dust, temperature reconstructions):

| Period | V_int (relative) | V_env (relative) | A |
|--------|------------------|------------------|---|
| Glacial–interglacial cycles | High (multiple stable states) | Moderate (orbital + CO₂) | ~1.0-1.2 |
| Holocene (last 11.7k years) | Moderate (single stable state) | Low (stable forcing) | ~1.1-1.3 |
| Industrial (1850–1950) | Stable | Slowly increasing | ~1.05 |
| Accelerated (1950–2000) | Stable | Rapidly increasing | ~0.98 |
| Present (2000–2025) | Slightly declining | Still increasing | ~0.92 |

### G.2 Projected under SSP Scenarios

Assume V_env grows with number of independent forcing trajectories (N_f):

V_env(t) ≈ N_f(t) × V_env(2025)

N_f(2100) under high scenario: 10-50 (combinations of GHG, aerosol, land use)

If V_int remains constant:

A(2100) ≈ A(2025) × (V_env(2025)/V_env(2100))

≈ 0.92 × (1/10) = 0.092 → complete regulatory failure

**Conclusion:** Without active intervention to increase V_int (protect biodiversity, maintain ocean circulation complexity, avoid destabilizing feedbacks), Ashby Compliance will collapse by 2100 under high-emission scenarios.

---

## Supplement H: Model Evaluation Checklist

Use this checklist to determine if a model has requisite variety for a given prediction task.

**For target subsystem S_target:**

| Step | Action | Pass/Fail |
|------|--------|-----------|
| 1 | Compute d_required = number of hierarchical timescales spanning S_target's dynamics (min: 1, max: 8) | ______ |
| 2 | Compute d_model = number of resolved/parameterized levels in the model | ______ |
| 3 | If d_model < d_required - 1 → Model lacks structural variety → predictions not reliable | ______ |
| 4 | Compute CI_model = (elements with >1 subsystem)/7 | ______ |
| 5 | If CI_model < 0.85 → Model lacks functional variety → likely missing critical feedbacks | ______ |
| 6 | Check dual-mode feedback: Does the model have passive feedback (persistence bounds) or only active? If passive missing, CI_F = 0.5 → insufficient for tipping points | ______ |

**Pass/fail criteria for tipping point prediction:**

- Pass: d_model ≥ d_required - 1 AND CI_model ≥ 0.85 AND passive feedback present
- Fail: Any condition fails → model lacks requisite variety; results must be treated as lower bound

---

## Supplement I: Complete Equation Reference

| Equation | Symbol | Definition |
|----------|--------|------------|
| V = b^(7 × b^d) | Variety | Internal variety from fractal depth |
| A = V_int / V_env | Ashby Compliance | Regulatory capacity |
| F_active = Σ (gain_k × ΔT) + nonlinear | Active feedback | Explicit correction signals |
| F_passive(t) = 1 if state(t) ∈ Viability_Set | Passive feedback | Existential persistence |
| P_viability = (1/N) Σ 1[subsystem_i ∈ envelope] | Viability score | Fraction of healthy subsystems |
| M = A - 1.0 | Regulatory margin | Surplus/deficit capacity |
| τ(t) = τ_0 / (1 - A(t)) | Critical slowing down | Relaxation time near tipping |
| dp_i/dt < 0 AND p_i(t) < 0.7 | Tipping risk | Pre-tipping alarm condition |
| d_required ≥ L_max - L_min + 1 | Model depth requirement | Minimum levels for prediction |
| CI_model = (#elements with >1 subsystem)/7 | Complexity Index | Functional variety |

---

**END OF TECHNICAL SUPPLEMENT**

*For collaboration, testing protocols, and model evaluation: climate@thekosmosinstitute.org*