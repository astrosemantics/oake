# Observation network participation — LOT-003

## Scope

This experimental pattern supports OAKE v0.1.0 use cases for TESS/STARS4ALL, AllSky and FRIPON. It models **documented participation**, not proof of continuous operation, deployment, ownership or live network connectivity.

## Terms used

| Concept | Candidate term | Caveat |
| --- | --- | --- |
| Observing network | `prov:Entity` | Generic identity only; network semantics require further review. |
| Instrument | `sosa:Sensor` | Reused for physical sensor. |
| Participation period | `prov:Activity` | Experimental interpretation; verify against use cases. |
| Participation link | `prov:used` | Query distinguishes instrument/network using RDF types. |
| Dates | `prov:startedAtTime`, `prov:endedAtTime` | Only when known; fixture uses a closed interval. |
| Organisation | `org:Organization`, `prov:Agent` | Separate from network identity. |
| Role | `prov:Association`, `prov:hadRole` | Contextual role; illustrative SKOS concept. |
| Evidence | `prov:wasDerivedFrom` | Link to a source record. |

## Interpretation

A documented participation activity may use an instrument and a network, and may be associated with an operator. A network can exist without a known operator. A deployed instrument need not participate in any network, and membership is not inferred from geographical proximity.

## Boundaries

The query treats participation as **inclusive at start and exclusive at end** (`start <= date < end`). This is a fixture convention, not a general PROV-O axiom. Missing dates and changing network identifiers require additional rules.

## Next steps

1. Test against real metadata from one TESS and one FRIPON station (with source permissions).
2. Compare an `org:Membership` approach for genuine organisational membership.
3. Evaluate SHACL constraints, provenance granularity and an explicit participation relation if the PROV activity pattern proves semantically inadequate.
