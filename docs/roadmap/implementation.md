# Implementation Plan

## Development Status

The following table shows the current development status of all planned models in the CE-RISE DPP & DMP architecture, organized by the three main architectural groups:

## A. Core Layers

| Layer | Model | Status | Repository | Notes |
|-------|-------|--------|------------|-------|
| **Product Identification** |
| | `product-profile` | Completed | [Product Profile](../components/product-profile.md) | Required foundation model for product passports |
| **Material Identification** |
| | `material-profile` | Planned | [Material Profile](../components/material-profile.md) | Required foundation model for material passports |
| **DPP & DMP Metadata** |
| | `dp-record-metadata` | Completed | [DP Record Metadata](../components/dp-record-metadata.md) | Semantic and structural metadata |
| | `dp-access-and-governance` | Completed | [DP Access and Governance](../components/dp-access-and-governance.md) | Access and operational metadata |
| | `dp-record-custody` | Completed | [DP Record Custody](../components/dp-record-custody.md) | Chain of custody and governance history |

## B. Value-Added Information Layers

| Layer | Model | Status | Repository | Notes |
|-------|-------|--------|------------|-------|
| **Dynamic Lifecycle** |
| | `traceability-and-lifecycle-events` | Completed | [Traceability and Life Cycle Events](../components/traceability-and-life-cycle-events.md) | Dynamic traceability and supply-chain events |
| | `diagnostic-results` | Completed | [Diagnostic Results](../components/diagnostic-results.md) | Event-bound diagnostic outputs |
| **Operation & Use** |
| | `usage-and-maintenance` | Completed | [Usage and Maintenance](../components/usage-and-maintenance.md) | Usage and maintenance data and instructions |
| **Impact Assessment** |
| | `integrated-lca` | Completed | [Integrated LCA](../components/integrated-lca.md) | Environmental, social, and economic LCA data |
| | `product-system` | Planned | - | Product-system modeling for LCA |
| **Circularity & End-of-Life** |
| | `circularity-and-eol` | Completed | [Circularity and End-of-Life](../components/circularity-and-eol.md) | Circularity metrics and end-of-life information |
| | `re-indicators-specification` | Under Development | [RE Indicators Specification](../components/re-indicators-specification.md) | EoL indicators and recovery options |
| **Legal, Compliance & Standards** |
| | `compliance-and-standards` | Completed | [Compliance and Standards](../components/compliance-and-standards.md) | Regulatory compliance and certifications |
| | `conformity-requirements-specification` | Planned | - | Compliance specification layer |

## C. Cross-Cutting Utility Layers

| Layer | Model | Status | Repository | Notes |
|-------|-------|--------|------------|-------|
| **Uncertainty** |
| | `uncertainty-quantification` | Planned | - | Generic uncertainty representation structures |
| **Data Quality** |
| | `data-quality-framework` | Planned | - | Data quality and provenance metadata |

## Status Legend

* **Completed**: Model is fully developed, documented, and published with schemas available
* **Under Development**: Model is actively being developed and refined
* **Planned**: Model is planned for future development

## Contributing

Models under development welcome community input and feedback. Please visit the individual repository links for contribution guidelines and current development status.
