# OAKE Roadmap

This roadmap tracks the progressive development of the Ontology for the Astronomical Knowledge Ecosystem (OAKE).

The project follows an incremental, reuse-first approach. Each milestone is intended to produce reusable semantic artefacts that benefit both the astronomy community and the broader Semantic Web ecosystem.

OAKE is intended to provide a shared semantic foundation for multiple knowledge graphs, rather than a single centralised dataset. Its development distinguishes three complementary layers:

- **Shared ontology:** reusable concepts, relationships and alignments describing the astronomical knowledge ecosystem.
- **Optional extensions:** domain- or network-specific requirements that cannot be adequately addressed through the shared model and existing vocabularies.
- **Knowledge graphs:** independently maintained data using OAKE, with their own sources, provenance, governance and update processes.

The ontology schema and knowledge graph instances will be maintained separately. Feedback from practical applications will inform the evolution of the shared model.

## Legend

- [x] Completed
- [ ] Remaining work
- [ ] 🚧 In progress
- 💡 Long-term vision

Completion marks reflect the confirmed project milestones. Unchecked items include planned or ongoing work and any milestones whose completion still needs to be confirmed.

---

## Repository

- [x] Create the GitHub repository
- [x] Design the OAKE visual identity
- [x] Publish the README
- [x] Add the project licence (CC BY 4.0)
- [x] Add citation metadata (CITATION.cff)
- [ ] Create the first GitHub release
- [ ] Connect Zenodo

---

## Documentation

- [x] Initial project description
- [x] Project roadmap
- [ ] Vision Paper
- [x] Vision document
- [x] Governance model
- [ ] Contributing guidelines
- [ ] Code of conduct
- [ ] Frequently Asked Questions (FAQ)
- [ ] Document the separation between the shared ontology, optional extensions and knowledge graphs
- [ ] Document the intended use cases and the rationale behind modelling decisions

---

## Value and use cases

OAKE should be driven not only by what can be modelled, but by what semantic interoperability makes possible for astronomy communities.

Its development should demonstrate concrete benefits for amateur astronomy, professional astronomy, citizen science and the organisations and infrastructures connecting them.

Particular attention will be given to use cases that cross traditional community or domain boundaries and cannot be addressed effectively by isolated datasets or models.

- [ ] Identify concrete information needs from amateur astronomy
- [ ] Identify concrete information needs from professional astronomy
- [ ] Identify shared needs involving citizen science, education, outreach and dark-sky initiatives
- [ ] Identify cross-community scenarios connecting amateur and professional astronomy
- [ ] Translate representative information needs into competency questions
- [ ] Identify which questions can already be answered using existing semantic resources
- [ ] Identify which questions require semantic connections currently missing between resources
- [ ] Demonstrate the added value of OAKE through representative knowledge graphs and queries
- [ ] Use demonstrated benefits and unresolved questions to prioritise further modelling work

---

## Conceptual model

- [ ] Define the scope
- [ ] Identify stakeholders, astronomy communities and knowledge domains
- [ ] Examine how major professional astronomy domains are structured and represented in existing semantic resources
- [ ] Define the core concepts and their relationships
- [ ] Consolidate competency questions derived from demonstrated community needs
- [ ] Identify competency questions that cross amateur, professional and citizen-science contexts
- [ ] Distinguish organisations, projects, networks, observing facilities, geographical sites, platforms, instruments and deployments
- [ ] Distinguish individual instruments from instrument types and models
- [ ] Address both observation networks and territorial astronomy ecosystems
- [ ] Produce the conceptual diagram
- [ ] Refine the model through representative examples, knowledge graphs and community feedback

---

## Semantic interoperability

- [ ] Review existing astronomy knowledge-graph and semantic-integration initiatives, starting with [Helio-KNOW](https://github.com/rmcgranaghan/Helio-KNOW/)
- [ ] Investigate comparable initiatives across heliophysics, planetary science and other astronomy domains
- [ ] Review existing ontologies and controlled vocabularies
- [ ] Prioritise reuse before introducing OAKE-specific terms
- [ ] Evaluate reuse and alignments involving SOSA/SSN, SAREF and SAREF4ENVI
- [ ] Evaluate reuse and alignments involving SKOS, PROV-O, ORG, GeoSPARQL, OWL-Time, DCAT and Schema.org
- [ ] Review astronomy-specific resources, including relevant IVOA vocabularies and the Unified Astronomy Thesaurus (UAT)
- [ ] Review citizen science resources, including PPSR Core and the Citizen Science Ontology (CSO)
- [ ] Document vocabulary versions, mapping rationale, limitations and unresolved gaps
- [ ] Validate proposed alignments against the competency questions and practical use cases

The resources listed here are candidates for evaluation, not commitments to import every vocabulary or declare equivalence between their terms.

---

## Core ontology

- [ ] Define and stabilise the ontology namespace and identifier policy
- [ ] Define ontology metadata
- [ ] Formalise the shared model using existing classes and properties wherever appropriate
- [ ] Define additional OAKE classes, object properties and datatype properties only where justified by identified gaps
- [ ] Maintain a clear separation between ontology schema and instance data
- [ ] Provide representative RDF examples
- [ ] Define SHACL validation shapes where useful
- [ ] Test the model with competency questions and example queries
- [ ] Publish OAKE v0.1 with documentation and versioned artefacts

---

## Knowledge graph development

OAKE will be tested through complementary real-world knowledge graph use cases. These applications are not intended as a fixed sequence or progression in complexity: each explores different parts and relationships of the astronomical knowledge ecosystem.

Initial use cases include TESS / STARS4ALL, Allsky, FRIPON and the territorial astronomy ecosystem in Brittany. Additional knowledge graphs should progressively be contributed by other communities and projects.

These are proposed applications, not established partnerships or commitments by the networks concerned. Their purpose is both to demonstrate useful applications of OAKE and to expose requirements that can improve the shared semantic model. Ingestion of observation streams or image archives is not assumed as an initial requirement.

### 1. TESS / STARS4ALL — international photometer network

⏳ Planned

- [ ] Initiate discussions with the STARS4ALL teams about a dedicated knowledge graph for the international TESS network
- [ ] Jointly clarify needs, scope, available metadata, reuse conditions and possible maintenance arrangements
- [ ] Map relevant instruments, sites, deployments, actors and services to OAKE
- [ ] Develop and review a pilot before considering broader international coverage
- [ ] Feed reusable modelling requirements back into OAKE

### 2. Allsky — Thomas Jacquin / Allsky community

⏳ Planned

- [ ] Explore a dedicated knowledge graph for the international Allsky camera network
- [ ] Discuss the approach with the relevant maintainers and contributors
- [ ] Assess metadata available through the camera map and other documented sources
- [ ] Describe camera installations, camera–lens configurations, sites, contributors and accessible services
- [ ] Reuse the shared model and identify requirements not covered by the TESS use case
- [ ] Define provenance, validation and update processes

### 3. FRIPON — meteor detection network

⏳ Planned

- [ ] Explore the relevance of an OAKE-based knowledge graph with the FRIPON teams
- [ ] Identify accessible metadata, reuse conditions and network-specific requirements
- [ ] Describe stations, instruments, sites, participating organisations and services
- [ ] Evaluate which patterns can be shared with TESS and Allsky and which require additional modelling

### 4. Astronomy in Brittany — territorial knowledge graph

⏳ Planned

- [ ] Use the collaborative uMap of astronomy in Brittany as an initial data source
- [ ] Review, structure and map its metadata to OAKE
- [ ] Describe the regional ecosystem: organisations, networks, observatories, instruments, services, knowledge resources, citizen science initiatives and astronomical events
- [ ] Include people and their roles where relevant, with appropriate consent and privacy safeguards
- [ ] Represent relationships between actors, places, equipment and activities
- [ ] Link regional entities to the international network graphs where relevant
- [ ] Establish a contribution and update process that preserves source provenance

### Shared requirements across knowledge graphs

- [ ] Define persistent identifiers and entity reconciliation practices
- [ ] Preserve source attribution, licensing and provenance
- [ ] Document coverage, uncertainty and missing information
- [ ] Define validation rules and reproducible metadata transformation workflows
- [ ] Maintain each graph's ownership and update responsibilities independently
- [ ] Support links between graphs without requiring their consolidation into one dataset
- [ ] Provide example queries demonstrating concrete benefits for different astronomy communities
- [ ] Demonstrate queries spanning multiple independently maintained knowledge graphs
- [ ] Demonstrate cross-community queries connecting amateur and professional astronomy
- [ ] Evaluate which questions become answerable only when previously separate ecosystem components are semantically connected

---

## Community and dissemination

- [ ] Engage potential contributors around the conceptual model and use cases
- [ ] Discuss proposed applications with the relevant network teams before treating them as collaborative deliverables
- [ ] Publish OAKE on an appropriate OntoPortal instance
- [ ] Publish versioned releases on Zenodo
- [ ] Create the project website
- [ ] Present OAKE at conferences
- [ ] Build an international community
- [ ] Establish a feedback process from knowledge graph maintainers to the shared ontology

---

## Potential future thematic extensions

💡 Candidate areas to be explored through demonstrated requirements and existing semantic resources:

- Citizen science and participatory astronomy
- Dark-sky protection and light pollution
- Astronomical education and outreach
- Space missions
- Planetariums
- Astronomical heritage
- Other specialised requirements identified through community knowledge graphs

These areas do not automatically require separate ontology modules. Amateur and professional astronomy are considered interconnected parts of the same astronomical knowledge ecosystem rather than separate modelling silos. Extensions will be introduced only when their scope and added value are demonstrated and cannot be adequately addressed through existing semantic resources.

---

## Long-term vision

💡 Develop OAKE as a modular semantic ecosystem that enables interoperability across worldwide astronomy by connecting people, organisations, infrastructures, instruments, observations, services and knowledge resources through shared semantic standards.

OAKE should enable questions and applications that are difficult to address when these resources remain semantically isolated, including use cases spanning amateur astronomy, professional astronomy, citizen science and other parts of the astronomical ecosystem.

This vision combines interoperable, independently maintained knowledge graphs at international, network and territorial scales, supported by a shared and progressively refined semantic model.
