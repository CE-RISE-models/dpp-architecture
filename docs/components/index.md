# Components

The CE-RISE DPP architecture is organized into a layered modular structure, where each layer serves specific functional purposes while maintaining interoperability across the system.

## Layered Architecture Overview

### 1. Core Product Layer
Static, foundational, always present.
- **[Product Profile](product-profile.md)** (required) - Defines the immutable identity and origin of a product

### 2. Dynamic Lifecycle Layer
Models describing events, operations, and time-dependent changes.
- **Traceability and Lifecycle Events** - Dynamic traceability and supply-chain events
- **Diagnostic Results** - Structured outputs from diagnostic, repair, service, or automated condition-assessment operations

### 3. Operation & Use Layer
Models describing how a product is used, maintained, and operated.
- **Usage and Maintenance** - Maintenance, repair, and usage-related data and instructions

### 4. Impact Assessment Layer
Models supporting environmental, economic, and social impact calculations.
- **Integrated LCA** - Environmental and social life cycle assessment data
- **SEE Impacts Specification** - Supporting CE-RISE SEE module calculations

### 5. Circularity & End-of-Life Layer
Models defining circularity criteria and EoL pathways.
- **Circularity and EoL** - Design for circularity, performance factors, and end-of-life information
- **[RE Indicators Specification](re-indicators-specification.md)** - Specific EoL indicators and options

### 6. Legal, Compliance & Standards Layer
Models describing regulatory, certification, and normative requirements.
- **Compliance and Standards** - Regulatory compliance, certifications, and evidence documentation

### 7. Cross-Cutting Utility Layer
Reusable components linked by reference to multiple models.
- **Uncertainty and Quality** - Data quality, uncertainty structures, and provenance metadata

### 8. Technical Infrastructure Layer
DPP-specific technical metadata relevant to data records and interoperability.
- **Technical Infrastructure** - Data access, security, carriers, and interoperability metadata
