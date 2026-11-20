# Deployment and time-qualified location pattern (LOT-002)

## Scope

Describe where the **same physical instrument** was deployed at a given date, without treating its present location as timeless. This example supports **CQ36** and complements LOT-001 (CQ37).

## Reused resources (candidates)

| Purpose | Term | Notes |
| --- | --- | --- |
| Physical observing instrument | `sosa:Sensor` | Reuse the same IRI in both deployment records. |
| Deployment | `ssn:Deployment` | SOSA/SSN 2017 candidate. |
| Deployed instrument | `ssn:deployedSystem` | Check domain/range and release before normative adoption. |
| Hosting platform | `sosa:Platform`, `ssn:deployedOnPlatform` | Platform may differ between deployments. |
| Site | `geo:Feature` | A location/area resource, not necessarily identical to a platform. |
| Deployment location | `prov:atLocation` | Location of the deployment activity/context; not an eternal station location. |
| Validity interval | `time:Interval`, `time:hasBeginning`, `time:hasEnd` | Half-open intervals `[start, end)` in example queries. |
| Interval attachment | `time:hasTime` | **Provisional** use on `ssn:Deployment`; validate OWL-Time semantics before approval. |

## Interpretation

- A deployment records one installation context. Changing the site or hosting platform creates another deployment; the sensor IRI stays the same.
- Time intervals and locations in this fixture are **fictional** and do not describe the real Kersaint-Plabennec station.
- The site is attached to each deployment, not asserted as a timeless property of a potentially mobile platform.
- An unknown end date should not be interpreted as ongoing operation. This minimal query only handles records with both boundaries.
- The example does **not** imply continuous operation, complete historical coverage, or an exclusive location at any instant.
- Real deployments need source/provenance metadata; timestamps of graph ingestion are distinct from deployment validity.

## Test

Load `examples/allsky-deployments.ttl`, then run `queries/instrument-deployment-at-date.rq`. At 2025-06-01 the expected answer is deployment A / station A / site A; at 2026-06-01 it is B / B / B. At the shared boundary 2026-01-01, only deployment B is selected.

## Remaining semantic review

Before moving LOT-002 from **Proposed** to **Accepted**, review the precise normative definitions of `ssn:deployedSystem`, `ssn:deployedOnPlatform`, `time:hasTime` and `prov:atLocation` against the selected ontology versions. Decide how to represent open-ended intervals and mobile trajectories; add a SHACL check for required date boundaries if needed.
