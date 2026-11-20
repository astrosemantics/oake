# LOT-003 — Observation networks and time-qualified participation

- **Status:** Proposed — illustrative RDF/SPARQL tests passed; semantic review pending.
- **Competency questions:** CQ19, CQ31, CQ32, CQ34, CQ35 and CQ39.
- **Related decisions:** LOT-001 (instrument configurations), LOT-002 (deployments).

## Requirement

Distinguish (1) an organisational collaboration, (2) an observing network, (3) an organisation's participation and role, and (4) an instrument's participation. Participation periods must not be inferred from deployment dates or current membership lists.

## Proposed reusable patterns

1. Represent an **organisational network** as `org:Organization` only when it genuinely has organisational semantics; use `org:Membership` with `org:organization`, `org:member` and `org:role` for organisational membership.
2. Represent an **observing network** as a separately identified `prov:Entity` for the example. This is a deliberately generic placeholder, **not** an assertion that all networks are PROV entities of a single specific kind.
3. Represent **documented instrument participation during a period** as a `prov:Activity` using `prov:used` for both the network and sensor; disambiguate by their RDF types. `prov:startedAtTime` and `prov:endedAtTime` qualify the activity's period. This is a *candidate modelling pattern*: membership/affiliation is not necessarily an activity in every source.
4. Use `prov:qualifiedAssociation` / `prov:agent` / `prov:hadRole` for the agent's role in an activity when documented. Do **not** infer instrument ownership or station operation from network participation.
5. Record source provenance using `prov:wasDerivedFrom` on participation records when a source is available.

## Alternatives and open issues

- `org:Membership` is appropriate for organisation/person membership in an organisation, but is not automatically appropriate for a physical sensor joining an observing network.
- `prov:Activity` expresses a temporally bounded process; long-lived membership may instead need a dedicated relationship/participation record. Review against real TESS/FRIPON metadata before approval.
- Avoid introducing `oake:Network`, `oake:NetworkParticipation`, or an OAKE role taxonomy before demonstrating a semantic gap.
- Dates in the fixture are synthetic and must not be interpreted as real network affiliations.

## Validation

- Turtle syntax parses.
- CQ31-like query returns the documented network at a selected date and no affiliation after the recorded end.
- The example preserves separation between the network, sensor, and participating organisation.
- Semantic validation against ontology definitions and actual network records remains outstanding.
