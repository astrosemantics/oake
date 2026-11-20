# OAKE v0.1.0 — Ontology Requirements Specification Document (draft)

**Status:** working draft for review; not an approved release.  
**Basis:** `VISION.md`, `MODELLING_PRINCIPLES.md`, `ROADMAP.md`, `docs/competency-questions.md`, `docs/conceptual-model.md`, `docs/vocabulary-reuse.md` in the supplied repository archive.  
**Method:** LOT — specification phase; subsequent design, implementation, evaluation, publication and maintenance remain iterative.

## 1. Purpose and intended users

OAKE provides a shared semantic foundation for **independently maintained knowledge graphs**, connecting amateur astronomy, professional astronomy, citizen science and related organisations. The initial demonstrator targets instrument discovery, observations, space/time context, network participation, data access and provenance. Stakeholders include observers, observatory/network operators, data managers and semantic-web developers. Specific user validation remains to be obtained.

## 2. Scope for v0.1.0

**In scope:** instruments, observations and results; observing sites and time; operational status; instrument operators; networks and participation; associated datasets/services; information provenance. Use AllSky, TESS/STARS4ALL and FRIPON as **candidate demonstration scenarios**, without assuming their source coverage or institutional agreements.

**Deferred:** comprehensive instrument specifications (spectral range, sensitivity, field of view), full astronomical phenomenon taxonomy, detailed quality scoring, dark-sky recognition schemes, exhaustive regional ecosystem, full historical reconciliation and large-scale ingestion. These remain possible future requirements, not rejected requirements.

**Important distinction:** instrument capability, current operational status, actual observation and availability/quality of resulting data are distinct assertions. An instrument's location may change across deployments. The source of a statement and its period of validity are distinct from its ingestion/update dates.

## 3. Functional requirements (selected existing CQ identifiers)

| Requirement | Requirement statement | Source CQs | Priority |
|---|---|---|---|
| FR-01 | Identify observation target, instrument, observing site, time and result. | CQ5–CQ10 | Must |
| FR-02 | Identify instrument type, operator, location, operational status and documented capabilities. | CQ11–CQ15 | Must |
| FR-03 | Identify network participation without conflating membership, coordination, operation and instrument contribution. | CQ31 | Must |
| FR-04 | Describe instrument deployment sites/platforms and periods where documented. | CQ36 | Must (limited example) |
| FR-05 | Discover associated datasets, images or services and documented access information. | CQ38 | Must |
| FR-06 | Trace the source and available update date of statements, distinct from fact validity and graph ingestion. | CQ39 | Must |
| FR-07 | Filter activities and resources spatially and temporally when the source supports it. | CQ2–CQ3, CQ13, CQ35 | Should |
| FR-08 | Relate observations and instrument configurations to relevant amateur/professional scenarios. | CQ6, CQ15, CQ37 | Should (CQ37 partial) |

The existing CQ1–CQ39 remain authoritative in `docs/competency-questions.md`. This ORSD does not renumber or replace them. Selection here is a **proposed release scope**, not a claim that all requirements are implemented.

## 4. Non-functional requirements

| ID | Requirement | Acceptance evidence |
|---|---|---|
| NFR-01 | Reuse-first and minimal core (MP1–MP4, MP9). | Each OAKE-specific term has documented necessity and rejected reuse alternatives. |
| NFR-02 | Controlled classifications (MP5–MP6). | Roles, statuses and phenomenon types use documented concepts; no unverified `owl:sameAs`/`skos:exactMatch`. |
| NFR-03 | Provenance and temporal interpretation. | Source and update information documented where available; unknown dates not invented. |
| NFR-04 | Interoperability. | Candidate mappings assessed against SOSA/SSN, PROV-O, ORG, GeoSPARQL, OWL-Time, DCAT, SKOS; astronomical vocabularies assessed separately. |
| NFR-05 | Validation and reproducibility. | RDF syntax checks, reasoner checks where applicable, SHACL reports and CQ SPARQL expected-result tests. |
| NFR-06 | FAIR publication readiness. | Stable namespace policy, version metadata, human-readable documentation, licence, citation and resolvable publication plan. |
| NFR-07 | Separation of layers (MP6, MP10). | Ontology, controlled vocabularies and real-world knowledge graph instances stored separately. |
| NFR-08 | Multilingual documentation and language-independent IRIs (MP11). | For each OAKE-defined class and property, labels and definitions in `en`, `fr`, `es`; coverage report for eight additional target languages; stable namespace policy and IRI resolution checks. |

### Multilingual and identifier policy for v0.1.0

OAKE targets eleven languages: `en`, `fr`, `es`, `ar`, `zh-Hans`, `ru`, `de`, `it`, `pt`, `ja`, `hi`. English, French and Spanish labels and definitions are release requirements for OAKE-defined classes and properties. Labels in the remaining eight languages are targets, not release blockers; definitions in those languages may be added incrementally. Coverage must be reported explicitly. These choices combine the six official UN languages (Chinese represented here by Simplified Chinese) and additional languages relevant to international astronomy communities; deployment maps alone do not establish users' languages.

Use one stable IRI per concept, independent of language. The proposed namespace is `https://w3id.org/astrosemantics/oake#` (pending registration and resolution verification). Language-tagged RDF literals, not translated IRIs, carry multilingual labels and definitions. Preserve source attribution and review status for translations of external vocabularies.

## 5. Candidate external resources — evaluation, not automatic adoption

- **SOSA/SSN:** sensors, observations, observed properties, results, systems.
- **PROV-O:** agents, activities, entities and derivation/attribution.
- **W3C ORG:** organisations and organisational relations.
- **GeoSPARQL:** places, features and geometry; explicit coordinate reference system and vertical reference for 3D positions.
- **OWL-Time:** intervals and temporal relations; use appropriate datatypes for timestamps.
- **DCAT:** datasets, distributions and access services.
- **SKOS:** roles, statuses and thematic vocabularies.
- **IAU / IVOA / UAT / SPASE / WMO:** candidate domain terminologies; verify actual concept IRIs, definitions, scope and licences before asserting mappings.

## 6. Evaluation scenarios and acceptance criteria

1. **AllSky:** a real installation with verified operator, location, instrument, observation/result or data access; avoid treating illustrative data as measured facts.
2. **TESS:** a verified photometer and its deployment/status/measurements or services, with provenance and source timestamps when known.
3. **FRIPON:** a verified station/network relationship and, if available, an actual observation or data access path.
4. **Cross-network scenario:** distinguish *could observe* from *did observe*; query only operational instruments where status history exists.

For each selected CQ: prepare one positive and one negative test case; document expected query results; validate relevant RDF shapes; record `supported`, `partially supported` or `unresolved` and distinguish modelling gaps from missing data. Avoid inferring historical state from a current snapshot.

## 7. Open decisions

- Register and test the proposed w3id namespace, settle version IRIs, and review whether the current draft Turtle terms should be retained.
- Determine which operational-status vocabulary and responsibility model can be reused.
- Verify actual network and instrument identifiers, source licences and access conditions.
- Agree which phenomenon types are necessary for the first demonstrator and verify reference vocabulary mappings.
- Confirm acceptance with at least one amateur and one professional stakeholder.

## 8. Source-of-truth and change control

Keep competency-question wording and stable IDs in `docs/competency-questions.md`; maintain this ORSD as the release-specific selection and acceptance criteria. Track design decisions and changes through Git; no release status is implied by this draft.
