# Architecture Overview

## Graphical Representation

*Graphical representation to be added - showing the architecture of core layers, value-added information layers, and cross-cutting utility layers*

## Three-Group Architecture Structure

The CE-RISE DPP architecture is organized into three main groups containing 9 functional layers, where each group and layer serves specific purposes while maintaining interoperability across the system.

---

## A. Core Layers

The core layers form the foundation of every Digital Product Passport, providing essential identity and metadata management infrastructure.

### 1. Product Identification
**Model: `product-profile`** (required)  
Defines the immutable identity, origin, and basic specification of the product. This foundational model is static and always present in every DPP.

**Key Components:**
* Product identifiers and classification
* Manufacturing origin and date
* Basic specifications and attributes
* Material composition
* Bill of materials structure

### 2. DPP Metadata
**Models:**  

**`dpp-record-metadata`**  
Data model defining the semantic and structural metadata of the DPP record.  
Specifies the applied data models, profiles, ontology bindings, schema references, supported formats, validation schemas, and version information required for interpreting the content of the DPP. This is the primary metadata envelope read before processing any product data.

**Key Components:**
* Ontology bindings and schema references
* Supported data model versions
* Data representation formats
* Validation schemas and endpoints
* Profile specifications

**`dpp-access-and-governance`**  
Data model describing operational and access-related metadata for the DPP record.  
Defines access levels, security settings, data carrier characteristics, longevity policies, interoperability configurations, and other parameters governing how the DPP is stored, exposed, shared, and maintained across systems.

**Key Components:**
* Access levels and permissions
* Security settings and encryption
* Data carrier specifications
* Longevity and retention policies
* Interoperability configurations

**`dpp-record-custody`**  
Data model representing the chain of custody and governance history of the DPP record itself.  
Captures custody events (creation, update, transfer, archival), identifies custodians, records authorized transfers, and includes integrity evidence such as signatures or hashes. Ensures auditability, accountability, and secure lifecycle governance of the DPP as an information object.

**Key Components:**
* Custody event history
* Custodian identification
* Transfer authorizations
* Integrity evidence (signatures, hashes)
* Audit trail

---

## B. Value-Added Information Layers

These layers provide the rich, domain-specific information that creates value for different stakeholders throughout the product lifecycle.

### 1. Dynamic Lifecycle
Captures time-dependent changes and events throughout the product's journey.

**Models:**

**`traceability-and-lifecycle-events`**  
Dynamic traceability and supply-chain events. Includes only **events**, not static identifiers.
* `ProductHistory`
* `OwnershipEvent`
* `ValueAddingActivityLocation`
* `ActorTracking` / `ValueChainActors`
* Logistics events (`BorderCrossing`, routing, etc.)
* Reverse logistics (`CustomerReturnChannels`)

**`diagnostic-results`**  
Structured outputs produced during diagnostic, repair, service, or automated condition-assessment operations. These are **event-bound results**, not static product information.
* Technician service reports
* Device self-diagnostic outputs (battery health, laptop system tests, etc.)
* Predictive maintenance assessments
* Condition monitoring snapshots
* Calibration/test results
* Error codes and evaluation metrics

### 2. Operation & Use
Describes how a product is used, maintained, and operated throughout its active life.

**Model: `usage-and-maintenance`**

**Key Components:**
* `MaintenanceRepairRelatedData`
* `UsageRelatedData`
* `UseInstructions`
* `MaintenanceInstructions`
* Service history and schedules
* Operating parameters and recommendations

### 3. Impact Assessment
Supports comprehensive environmental, social, and economic impact calculations.

**Models:**

**`integrated-lca`**  
Represents environmental, social, and economic impact calculations:
* `EnvironmentalImpact`
* Impact categories, methods, inventory links
* `SocialImpact`
* Life-cycle costing (LCC) assessments

**`product-system`**  
The underlying product-system data model used to structure activities, flows, and elementary exchanges:
* System boundaries definition
* Process modeling
* Flow accounting
* Elementary exchange tracking
* Allocation methods

### 4. Circularity & End-of-Life
Defines circularity metrics, design principles, and end-of-life pathways.

**Models:**

**`circularity-and-eol`**  
Comprehensive circularity and end-of-life information:
* `DesignForCircularity`
* `ProductPerformanceFactors`
* `ProductPerformanceScores`
* `EndOfLifeInformation` (recycling, CRM recovery, treatment options)
* Disassembly instructions
* Material recovery potential

**`re-indicators-specification`**  
Specific end-of-life indicators and recovery options:
* Recycling indicators
* Reuse potential metrics
* Recovery pathways specification
* Treatment facility requirements

### 5. Legal, Compliance & Standards
Ensures regulatory compliance and standards conformity throughout the product lifecycle.

**Models:**

**`compliance-and-standards`**  
Regulatory compliance and certification information:
* `ProductCommitments`
* `ApplicableRegulationStandards`
* `ProductEvidence` (DoC, certificates, CE marking)
* `ProcessEvidence`
* `RegulatoryInformationSheet`
  * SafetyWarnings
  * SafeUseInstructions (legally required)
  * EMCComplianceStatement
  * ResponsiblePersonEU (name, address, contact, role)
  * AdditionalRegulatoryIdentifiers (market/regulation-specific secondary IDs)

**`conformity-requirements-specification`**  
Specification layer for compliance and normative information needs:
* Standard-specific data requirements
* Conformity assessment procedures
* Documentation templates
* Audit trail specifications

---

## C. Cross-Cutting Utility Layers

These layers provide reusable components that support data quality and reliability across all other layers.

### 1. Uncertainty
**Model: `uncertainty-quantification`**  
Generic structures for representing uncertainty in measurements, assessments, and indicators.

**Key Components:**
* Statistical uncertainty representations
* Confidence intervals and ranges
* Probability distributions
* Scenario-based uncertainty
* Epistemic vs. aleatory uncertainty handling

**Used by:** All layers where measurements, predictions, or assessments contain uncertainty

### 2. Data Quality
**Model: `data-quality-framework`**  
Defines metadata for data quality, provenance, representativeness, completeness, and assessment pedigree.

**Key Components:**
* Data source attribution
* Temporal representativeness
* Geographic representativeness
* Technological representativeness
* Completeness indicators
* Reliability scores
* Pedigree matrices
* Validation status

**Used by:** All layers to ensure transparency and trust in data

---

## Architecture Principles

### Modularity
Each model can be developed, updated, and deployed independently while maintaining interface compatibility.

### Interoperability
Models use standardized interfaces and semantic definitions to ensure seamless integration across different systems and platforms.

### Extensibility
The architecture allows for new models to be added within existing layers or new layers to be created as requirements evolve.

### Separation of Concerns
Each layer addresses distinct aspects of the product lifecycle, preventing unnecessary coupling and enabling focused expertise.

For detailed specifications and internal structure of each model, see the individual component repositories.
