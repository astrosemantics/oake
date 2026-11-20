# LOT-002 — Deployment, platform and temporal location

- **Status:** Proposed (example-level technical validation only)
- **Competency questions:** CQ36; complements CQ37
- **Related decision:** LOT-001 — Instrument composition and dated configurations

## Decision proposed

Use `ssn:Deployment` to describe a time-qualified installation context of an instrument (`sosa:Sensor`) on a hosting `sosa:Platform`. Identify sites independently as `geo:Feature`; associate a site with each deployment using `prov:atLocation` as a candidate. Use an `time:Interval` record for deployment validity. Keep the same physical instrument identifier across moves. Do not introduce new OAKE classes or properties at this stage.

## Alternatives and rationale

A timeless `sensor → site` triple cannot represent relocation without ambiguity. A deployment record can distinguish multiple historical contexts and avoid inferring that the platform was always at the same site. Do not equate deployment validity with operational uptime.

## Validation criteria

1. Turtle parses.
2. A SPARQL query returns site A before the move, site B after the move, and exactly one result on the boundary.
3. Semantic mappings and ontology-version compatibility are reviewed separately before acceptance.

## Follow-up

- Review formal domain/range and semantics of time and location properties.
- Extend query to handle unknown boundaries, uncertain dates and moving platforms.
- Attach statement/source provenance and add SHACL validation.
