# Instrument modelling pattern — initial AllSky fixture

## Goal

Answer CQ37: for a specified date, which physical components formed an instrument configuration, and what were their commercial models?

## Entities

| Entity | Candidate representation | Notes |
| --- | --- | --- |
| Camera | `sosa:Sensor`, `schema:Product` | Persistent identity across configurations. |
| Lens | `schema:Product` | Passive physical component; not automatically a sensor or subsystem. |
| Camera/lens models | `schema:ProductModel` | Connected using `schema:model`. |
| Dated configuration record | `prov:Entity` | Example-level record of a configuration during an interval. |
| Component link | `saref:consistsOf` | **Provisional** pending exact SAREF semantic review. |
| Interval | `time:Interval` | Beginning inclusive, end exclusive by query convention. |

## Temporal convention

A configuration record describes components valid in `[start, end)`. The query applies this convention explicitly with SPARQL filters; OWL-Time does not enforce it automatically. The chosen example dates and component changes are **fictional test data**, not historical claims about a real AllSky installation.

## Boundaries

- A configuration record is **not** asserted to be identical to the physical imaging system.
- A `ssn:Deployment` concerns installation on a platform; changing a lens need not imply a new deployment.
- This fixture does not yet implement station relocation, platform hosting, operational status, network membership, or statement-level provenance.
- Before normative adoption, check whether `saref:consistsOf` can legitimately connect the selected configuration record to physical components. If not, use an existing suitable part–whole vocabulary or a qualified component-association pattern.

## How to validate

Run a Turtle parser, then execute `queries/instrument-configuration.rq` against `examples/allsky-configurations.ttl`, substituting the date in the query. Expect `lens-a` on 2025-06-01 and `lens-b` on 2026-06-01.
