# Repo 2 — Canonical System Identity and Size Descriptives

This repository is the first **execution layer** in the Tracking the Sun analytical program.

Its sole purpose is to establish a **defensible, system-level analytical substrate**
from raw Tracking the Sun data, under the constraints defined upstream.

Nothing downstream is permitted to reason about system size, structure, scaling,
or deviation unless it is derived from the canonical outputs of this repository.

---

## Role Within the Program Architecture

This repository operates strictly under:

- **Repo 0** — Program Canon and analytical ordering
- **Repo 1** — Data generation, measurement limits, column roles, and contracts

This repository:
- does not define entities, roles, or assumptions
- does not reinterpret upstream constraints
- does not introduce new analytical structure

It executes only what has been explicitly permitted upstream.

---

## Canonical Entity and Analytical Grain

The canonical analytical entity in this repository is:

**Entity:**  
A physical residential photovoltaic system.

**Canonical identifier:**  
`tts_link_id`

**Analytical grain:**  
Exactly **one row per `tts_link_id`**.

No system-level artifact may be produced unless this grain invariant is satisfied.

Any identifier failing admissibility criteria defined in Repo 1 constitutes
a hard violation and prohibits system-level entity construction.

---

## System-Level Collapse Constraints

Empirical inspection of within-system variability reveals that nearly all
raw columns vary across administrative records for the same `tts_link_id`.
With the exception of internal multiphase linkage fields, the raw dataset
does not contain stable, invariant system-level attributes. As a result,
row-to-system collapse in this repository does **not** attempt to reconcile
or infer physical system characteristics (e.g. size, price, installation date).

Instead, collapse is restricted to the construction of a **minimal
system-level index** that preserves canonical identity and explicitly records
diagnostic indicators of reporting multiplicity and instability. These
diagnostics are retained to support downstream cohort definition, temporal
semantics, and analytically justified exclusions, rather than being resolved
or smoothed at this stage.

---

## Scope and Responsibilities

This repository is responsible for:

- loading raw Tracking the Sun data as reported
- applying raw schema validation
- declaring and enforcing canonical system identity
- collapsing multiple reported rows into one system-level record
- classifying violations and exclusions
- producing **descriptive** system size distributions

This repository is explicitly **not** responsible for:

- defining expected size behavior
- computing deviations or residuals
- assigning regimes
- evaluating abnormality or risk
- making causal or predictive claims

---

## Notebook Structure

Analytical work in this repository is intentionally minimal and strictly ordered.

### 01 — Canonical System Identity and Grain

This notebook:

- loads raw Tracking the Sun data
- applies schema and reporting validity checks
- **formally declares `tts_link_id` as the canonical system identifier**
- validates identifier admissibility using Repo 1 contracts
- groups rows by `tts_link_id` without aggregation assumptions
- reconciles values strictly by column role
- flags irreconcilable systems
- enforces the one-row-per-system grain invariant

Outputs from this notebook represent the **only admissible system-level dataset**
used downstream.

No exploratory analysis occurs here.

---

### 02 — Descriptive System Size Distributions

This notebook:

- consumes the canonical system-level dataset
- describes observed system size distributions by declared context
- computes counts, ranges, and quantiles
- characterizes dispersion and temporal drift

All outputs remain **descriptive**.
No normative, expected, or evaluative interpretation is introduced.

---

## Outputs

Canonical outputs produced by this repository:

- are keyed exclusively by `tts_link_id`
- contain exactly one row per system
- are versioned and immutable once published
- are safe for downstream consumption

Diagnostics and exclusions are retained explicitly for auditability.

---

## Relationship to Downstream Repositories

Downstream repositories may assume:

- system identity is stable and canonical
- analytical grain is enforced
- size descriptives are empirically grounded
- exclusions are intentional and documented

Downstream repositories may not:

- redefine system identity
- alter grain
- reinterpret exclusions
- derive expectations without regime logic

Any change to canonical outputs requires upstream review.

---

## Status

This repository is active.

Canonical artifacts are added only when earned.
Descriptive baselines evolve as understanding improves.
