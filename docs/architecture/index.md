# Architecture Overview

## Graphical Representation

*Graphical representation to be added - showing the architecture of core model, pluggable sections, cross-cutting models, and extension models*

## Layered Architecture Structure

The CE-RISE DPP architecture is organized into 8 functional layers, where each layer serves specific purposes while maintaining interoperability across the system.

### 1. Core Product Layer
Static, foundational, always present.

**`product-profile` (required)**  
Defines the immutable identity and origin of a product.

### 2. Dynamic Lifecycle Layer
Models describing events, operations, and time-dependent changes.

**`traceability-and-life-cycle-events`**  
Dynamic traceability and supply-chain events.  
Includes only **events**, not static identifiers.

* `ProductHistory`  
* `OwnershipEvent`  
* `ValueAddingActivityLocation`  
* `ActorTracking` / `ValueChainActors`  
* Logistics events (`BorderCrossing`, routing, etc.)  
* Reverse logistics (`CustomerReturnChannels`)  
* Excludes information already in `product-profile` (e.g., static import identifiers).

**`diagnostic-results`**  
Structured outputs produced during *diagnostic, repair, service, or automated condition-assessment operations*.  
These are **event-bound results**, not static product information.

Includes:

* technician service reports  
* device self-diagnostic outputs (battery health, laptop system tests, etc.)  
* predictive maintenance assessments  
* condition monitoring snapshots  
* calibration/test results  
* error codes and evaluation metrics  

### 3. Operation & Use Layer
Models describing how a product is used, maintained, and operated.

**`usage-and-maintenance`**  

* `MaintenanceRepairRelatedData`  
* `UsageRelatedData`  
* `UseInstructions`  
* `MaintenanceInstructions`

### 4. Impact Assessment Layer
Models supporting environmental, economic, and social impact calculations.

**`integrated-lca`**  
Umbrella for environmental & social LCA.

* `EnvironmentalImpact`  
* impact categories, methods, inventory links  
* `SocialImpact`  
* Potential: **LCC** (life-cycle costing)

**`see-impacts-specification`**  
Specification supporting CE-RISE SEE module:

* indicator definitions  
* calculation metadata  
* harmonised SEE structures

### 5. Circularity & End-of-Life Layer
Models defining circularity criteria and EoL pathways.

**`circularity-and-eol`**

* `DesignForCircularity`  
* `ProductPerformanceFactors`  
* `ProductPerformanceScores`  
* `EndOfLifeInformation` (recycling, CRM recovery, treatment options)

**`re-indicators-specification`**  
Specific EoL indicators and options.

### 6. Legal, Compliance & Standards Layer
Models describing regulatory, certification, and normative requirements.

**`compliance-and-standards`**

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
Specification layer for compliance and normative information needs.

### 7. Cross-Cutting Utility Layer
Reusable components linked by reference to multiple models.

**`uncertainty-and-quality`**  
Cross-cutting metadata for:

* data quality  
* uncertainty structures  
* provenance / lineage

Used by: circularity, SEE, LCA, traceability, compliance.

### 8. Technical Infrastructure Layer
DPP-specific technical metadata relevant to data records and interoperability.

**`technical-infrastructure`**  
Contains infrastructure-level metadata:

* `DataAccessAndSecurity`  
* `DataCarrier`  
* `AccessLevel`  
* `DataAccessLongevity`  
* `InteroperabilityMetadata`
* `OntologyMetadata` - References to supported data modeling standards and schemas
  * Supported schema URLs and versions
  * Primary and extended ontology references  
  * Data representation format capabilities
  * Validation and conformance endpoints

For detailed specifications and internal structure of each model, see the individual component repositories.
