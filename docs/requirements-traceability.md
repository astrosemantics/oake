# OAKE v0.1.0 — Requirements traceability (draft)

This matrix maps **proposed** v0.1.0 requirements to the existing stable competency-question identifiers. The implementation columns are *candidate mappings*, not evidence that classes/properties already exist in the repository. No test has been executed as part of this document.

| Requirement | CQs | Candidate reused terms / pattern | Candidate demonstration | Test to implement | Status |
|---|---|---|---|---|---|
| FR-01 | CQ5–CQ10 | `sosa:Observation`, `sosa:madeBySensor`, `sosa:hasFeatureOfInterest`, `sosa:resultTime`, `sosa:hasResult` | AllSky observation | SPARQL: target, sensor, site, timestamp, result | To implement |
| FR-02 | CQ11–CQ15 | `sosa:Sensor`, SKOS status terms, PROV role assertions, GeoSPARQL | TESS + AllSky | SPARQL: active sensors at date; SHACL: sourced dated status | To design |
| FR-03 | CQ31 | ORG/PROV + documented participation role; avoid equating membership with operation | FRIPON network | SPARQL: participating stations and roles | To design |
| FR-04 | CQ36 | time-bounded deployment relation; `time:Interval`, `geo:Feature` | TESS deployment | SPARQL: deployment valid at date; negative temporal case | To design |
| FR-05 | CQ38 | `dcat:Dataset`, `dcat:Distribution`, `dcat:accessURL` / `dcat:accessService` | AllSky/TESS resources | SPARQL: dataset and usable access location | To implement |
| FR-06 | CQ39 | `prov:wasDerivedFrom`, `prov:wasAttributedTo`, `dcterms:modified`; statement-level provenance pattern to select | All three | SHACL: source on chosen assertion unit; SPARQL: source and update date | To design |
| FR-07 | CQ2–CQ3, CQ13, CQ35 | GeoSPARQL, OWL-Time, deployment validity | Regional instrument search | SPARQL: spatial and temporal filters, no false historical claims | To design |
| FR-08 | CQ6, CQ15, CQ37 | SOSA/SSN; model and configuration only where documented | AllSky camera + lens | SPARQL: configuration at date (optional) | Deferred/partial |
| NFR-01 | MP1–MP4, MP9 | Term-level reuse rationale | Ontology core | Review every newly coined OAKE term | To review |
| NFR-02 | MP5–MP6 | SKOS and curated mapping assertions | Phenomenon/status vocabularies | Check URI, definition and mapping justification | To review |
| NFR-03 | CQ39 | PROV-O and distinct time fields | Data source records | Verify validity/update/ingestion separation | To design |
| NFR-04 | MP1, MP8 | External ontology references | Core and modules | Syntax + ontology alignment review | To review |
| NFR-05 | CQ tests | SHACL, SPARQL, OWL | Small KG fixture | Positive/negative tests and CI | To implement |
| NFR-06 | FAIR publication | OWL metadata, persistent URI, citation, licence | v0.1.0 release | Metadata and link checks | To implement |
| NFR-07 | MP6, MP10 | Distinct ontology/vocabularies/KG folders | Repository architecture | Structural review | Partially in place |
| NFR-08 | MP11; multilingual policy | Language-tagged `rdfs:label`/`rdfs:comment` for OAKE OWL terms; SKOS annotations for concepts; stable language-independent IRIs | Core and modules | Check required `en`/`fr`/`es` labels and definitions; report coverage for `ar`, `zh-Hans`, `ru`, `de`, `it`, `pt`, `ja`, `hi`; validate tags and IRI resolution | To implement |

## Next decisions

1. Confirm this proposed scope against the existing CQs and roadmap.
2. Review each proposed OAKE-specific term in the preliminary Turtle against MP1 and MP9.
3. Define actual instance identifiers and evidence sources before populating graphs.
4. Create SHACL shapes and SPARQL tests only after model patterns are agreed.
