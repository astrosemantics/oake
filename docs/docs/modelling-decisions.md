# OAKE modelling decisions

## LOT-001 — Instrument composition and dated configurations

- **Status:** Proposed — example and SPARQL test passed; external ontology semantics require final review.
- **Related competency questions:** CQ36 (deployment and location history), CQ37 (instrument components and models at a given date).
- **Scope:** AllSky demonstration, with potential reuse for TESS and FRIPON.

### Decision

1. Identify physical cameras and lenses independently of their commercial models (`schema:Product`, `schema:ProductModel`, `schema:model`). A camera may additionally be a `sosa:Sensor`.
2. Identify each dated *configuration record* as a `prov:Entity`. Associate components using `saref:consistsOf` **provisionally**; this property must be checked against the precise SAREF release and its formal constraints before normative adoption.
3. Attach a validity interval to each configuration record using `time:hasTime` and `time:Interval` with `time:hasBeginning` / `time:hasEnd` and `time:inXSDDateTimeStamp`. In this example `time:hasTime` is used on a `prov:Entity` as a documentation convention, not as an OWL entailment; review its formal domain in the targeted OWL-Time version.
4. Preserve the camera's identity when the lens changes. Do not assert a timeless camera–lens composition.
5. Keep instance descriptions in a separate knowledge graph; do not add OAKE classes or properties until a documented gap is demonstrated.

### Alternatives and limitations

- `ssn:hasSubSystem` is not assumed suitable for a passive lens.
- `sosa:Platform` and `ssn:Deployment` remain candidates for station/deployment modelling; their exact properties and versions must be checked independently before extending this fixture to CQ36.
- The example answers the **component-history portion of CQ37**, not CQ36. It does not assert completeness of the historical record or continuity between intervals.
- For production use, replace demonstration `example.org` IRIs with persistent instance identifiers and attach provenance for each configuration assertion.

### Validation evidence

- `examples/allsky-configurations.ttl` parses as Turtle.
- `queries/instrument-configuration.rq` retrieves the correct lens for the two example dates.
- This is an example-level technical check, **not** final semantic validation.
