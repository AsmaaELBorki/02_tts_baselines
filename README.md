# System Size Determinants

This repository is the first execution layer in the Tracking the Sun analytical architecture.

It establishes defensible baselines around system size.  
Nothing downstream is allowed to reason about size without passing through this layer.

---

## Role Within the Architecture

This repository applies the constraints defined in Repo 0.

It does not define schema, roles, or assumptions.  
It operates within them.

The objective is not to explain system behavior.  
The objective is to determine what “system size” means, where it is stable, and under what conditions it can be reasoned about safely.

---

## Scope

This repository is responsible for:

- loading raw Tracking the Sun data  
- applying raw schema validation  
- deriving canonically approved fields  
- classifying violations and exclusions  
- establishing descriptive baselines for system size  

This repository does not:

- make causal claims  
- perform predictive analysis  
- define deviation logic  
- reinterpret upstream constraints  

---

## Notebook Structure

Analytical work is sequenced deliberately.

### 01 — Load and Validate

Establishes trust boundaries.

This notebook:
- loads raw data  
- applies Repo 0 raw schema  
- derives `installation_year`  
- classifies temporal and size-related violations  
- produces diagnostics and canonical outputs  

No exploratory analysis occurs here.

---

### 02 — Size Distributions and Baselines

Describes observed system size behavior under controlled conditions.

This notebook:
- examines size distributions by cohort and context  
- identifies stable reference behavior  
- surfaces distributional irregularities  

Outputs remain descriptive.

---

### 03 — Expected Size Function

Formalizes expectation.

This notebook:
- defines an expected size function based on established baselines  
- produces reference mappings and residuals  
- avoids predictive framing  

The resulting function is intended for downstream use, not interpretation here.

Residuals produced here are reference coordinates only and are not interpreted, thresholded, or evaluated in this repository

---

## Outputs

Outputs are explicit and versioned.

Canonical outputs:
- are stable  
- are reusable  
- may be consumed downstream  

Diagnostics:
- document exclusions and violations  
- are retained for auditability  
- are not hidden or collapsed  

---

## Relationship to Downstream Repositories

Downstream repositories may assume:

- canonical fields defined here are stable  
- size baselines are defensible  
- exclusions are intentional  

Downstream repositories may not:
- redefine size semantics  
- bypass diagnostics  
- reinterpret exclusions  

Any change to canonical outputs requires review.

---

## Status

This repository is active.

Canonical fields are added only when earned.  
Baselines evolve as understanding deepens.


## License
See `LICENSE.md` for usage terms. Source data ownership is documented in `DATA_PROVENANCE.md`.
