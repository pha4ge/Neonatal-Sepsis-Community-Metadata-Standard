# CHANGELOG

## Neonatal Sepsis Community Metadata Standard

**Version 1.0.0.1 → Version 2.0.1**

---

## Document Information

|                    |                                                         |
| ------------------ | ------------------------------------------------------- |
| **Document Title** | Changelog — Neonatal Sepsis Community Metadata Standard |
| **From Version**   | v1.0.0.1                                                |
| **To Version**     | v2.0.1                                                  |
| **Status**         | ☒ Draft    ☐ Under Review    ☐ Approved                 |

---

## How to Use This Document

This changelog records every modification made between versions of the Neonatal Sepsis Metadata Specification. It follows the **Keep a Changelog** convention and **Semantic Versioning (SemVer)** principles adapted for data/metadata standards.

Entries are grouped by change category and annotated with scientific rationale to support peer review and grant reporting.

### Change Categories

| Category       | Meaning                                                                                         |
| -------------- | ----------------------------------------------------------------------------------------------- |
| **Added**      | New fields, concepts, or metadata elements introduced for the first time.                       |
| **Changed**    | Modifications to existing fields (e.g., data type, cardinality, allowed values, naming).        |
| **Deprecated** | Fields that are still present but scheduled for removal in a future version; usage discouraged. |
| **Removed**    | Fields or sections permanently eliminated from the specification.                               |
| **Fixed**      | Corrections to errors in definitions, constraints, or validation rules without semantic change. |
| **Security**   | Changes related to patient privacy, data de-identification, or access-control requirements.     |

---

# [v2.0.1] — 2026-08-04

Major release introducing structural redesign of domain modules. Patch release addressing field-level corrections and deprecating legacy identifiers flagged during clinical data collection pilot.

> **Important:** This version is **NOT backwards compatible** with v1.0.0.6.

## Summary of Changes

| Added | Changed | Deprecated | Removed | Fixed |
| ----: | ------: | ---------: | ------: | ----: |
|     6 |      23 |          0 |       4 |     5 |

---

## Detailed Changes — v2.0.1

### Fixed

| Field / Element                         | Previous Value                                   | New Value                                                                                                                                                                                                       | Rationale                                                                                                                                          |
| --------------------------------------- | ------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Null value handling**                 | Not explicitly documented                        | Five standard null terms added to applicable dropdowns: Not collected, Not known, Missing data, Data unavailable, Other relevant null values                                                                    | Allows mandatory fields to be completed when information is unavailable; improves data quality by distinguishing true negatives from missing data. |
| **Healthcare facility size definition** | Ambiguous (could be confused with neonatal beds) | Clarified as total hospital beds (not neonatal beds specifically)                                                                                                                                               | Separate field exists for neonatal beds; avoids double-counting.                                                                                   |
| **Template functionality guidance**     | Not specified                                    | Explicit instruction to use Excel, not Google Sheets                                                                                                                                                            | Dropdown lists break when opened in Google Sheets, removing Excel-based validation rules.                                                          |
| **AST testing date**                    | Template heading ambiguous                       | Template heading specifies `YYYY-DD-MM` format                                                                                                                                                                  | Corrected error and standardized date entry across the specification.                                                                              |
| **Purpose of sampling definition**      | Original definition vague                        | Refined definition: "The description of the study/surveillance that this isolate was collected for (e.g., targeted surveillance of an outbreak, or untargeted collection of isolates from routine diagnostics)" | Clarifies intended use and reduces ambiguity.                                                                                                      |

### Removed

| Field / Element                                           | Previous Value | New Value | Rationale                                                                                                                                                                                        |
| --------------------------------------------------------- | -------------- | --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Finding by Cause (Colonization vs Infection)**          | Present        | Removed   | Miscategorization introduces significant bias into datasets; information can be inferred from specimen source material and biospecimen type. Risk of data contamination outweighed benefit.      |
| **Water Availability Field**                              | Present        | Removed   | Highly variable and difficult to determine accurately; "sometimes available" is poorly defined and subjective; potential to introduce ambiguous or inaccurate information; low analytical value. |
| **Hospital Acquired Infection (HAI) Surveillance Fields** | Present        | Removed   | Definitions vary widely between institutions; responses would be inconsistent and potentially misleading; removing unreliable data improves overall dataset quality.                             |
| **Surveillance**                                          | Present        | Removed   | Too ambiguous and subjective. Muddies the metadata.                                                                                                                                              |

### Changed

| Field / Element                                                  | Previous Value                             | New Value                                                                   | Rationale                                                                                                                                                                                                                                                                                              |
| ---------------------------------------------------------------- | ------------------------------------------ | --------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Authors**                                                      | Unspecified                                | Optional                                                                    | Authors list can be unwieldy, especially when multiple people contribute to sample collection, sequencing, and analysis at different stages. Have one person as point of contact.                                                                                                                      |
| **Geolocation Information (Country & State/Province/Territory)** | Unspecified                                | Mandatory                                                                   | These are required for INSDC database submissions and are essential for geographic tracking of pathogens.                                                                                                                                                                                              |
| **Geolocation Information (City, Latitude & Longitude)**         | Unspecified                                | Optional                                                                    | Reduces burden; location derivable from organization.                                                                                                                                                                                                                                                  |
| **Sample collected by**                                          | Unspecified                                | Mandatory                                                                   | The data custodian organization can facilitate this information if needed.                                                                                                                                                                                                                             |
| **Sample collector email**                                       | Unspecified                                | Optional                                                                    | Not essential for data integrity.                                                                                                                                                                                                                                                                      |
| **Sample collection date**                                       | Unspecified                                | Mandatory                                                                   | Critical for EOS vs LOS classification.                                                                                                                                                                                                                                                                |
| **Purpose of Sampling**                                          | Unspecified                                | Mandatory                                                                   | Essential to know whether samples were collected for surveillance, research, vaccine escape studies, etc.                                                                                                                                                                                              |
| **Purpose of sampling details**                                  | Unspecified                                | Optional                                                                    | Free text allowing elaboration.                                                                                                                                                                                                                                                                        |
| **Healthcare Facility Name**                                     | Unspecified                                | Mandatory                                                                   | The facility name carries substantial associated information that can be derived even if other facility fields are incomplete.                                                                                                                                                                         |
| **Health facility size**                                         | Unspecified                                | Optional                                                                    | Categorized ranges will improve usability and standardization. Without bed capacity or admission numbers, it's impossible to calculate infection rates. The group agreed to use dropdown ranges (e.g., 1–10 beds, 11–20 beds, 21–50 beds, 51–100 beds, 100+ beds) rather than requiring exact numbers. |
| **Neonatal beds**                                                | Unspecified                                | Optional                                                                    | Supports denominator data without burden.                                                                                                                                                                                                                                                              |
| **On-site Neonatal surgical Facility**                           | Unspecified                                | Optional                                                                    | Yes/no question.                                                                                                                                                                                                                                                                                       |
| **Host health state**                                            | Unspecified                                | Mandatory                                                                   | Health status of the neonate at the time of sample collection. Dropdown includes: Healthy, Symptomatic, Deceased (with null options).                                                                                                                                                                  |
| **Host health status details**                                   | Unspecified                                | Optional                                                                    | Free-text field for elaboration (e.g., "Maternal HIV-positive," "Baby premature, 35 weeks," "Post-surgery sample"). Include examples and guidance in the data dictionary.                                                                                                                              |
| **Host health outcome at discharge**                             | Unspecified                                | Mandatory                                                                   | Outcome at end of hospitalization. Dropdown includes: deceased, recovered, stable (still hospitalized), transferred, discharged with risk bond (newly added).                                                                                                                                          |
| **Host Health Outcome**                                          | Unspecified                                | Optional (Surveillance programs don't typically collect day 3 outcome data) | Outcome on discharge post-sample collection. Dropdown includes: deceased, deteriorating, recovered, stable, hospitalized, outpatient.                                                                                                                                                                  |
| **Days in Hospital Before Specimen Collection**                  | Unspecified                                | Mandatory                                                                   | Critical for distinguishing community-acquired vs. hospital-acquired infections.                                                                                                                                                                                                                       |
| **Age in Days at Specimen Collection**                           | Unspecified                                | Mandatory                                                                   | Essential for categorizing early-onset vs. late-onset sepsis and understanding disease patterns in different age groups.                                                                                                                                                                               |
| **Subject sex**                                                  | Unspecified                                | Mandatory                                                                   |                                                                                                                                                                                                                                                                                                        |
| **Gestational age at birth**                                     |                                            | Mandatory                                                                   |                                                                                                                                                                                                                                                                                                        |
| **Delivery location**                                            | Unspecified                                | Mandatory                                                                   | Where baby was delivered: home, community healthcare facility, hospital.                                                                                                                                                                                                                               |
| **Delivery Procedure**                                           | Unspecified                                | Mandatory                                                                   | Identifying patterns (e.g., all cases occurring in babies born by C-section) is epidemiologically valuable.                                                                                                                                                                                            |
| **AMR laboratory typing method**                                 | Field name: "AMR laboratory typing method" | Renamed to "Antimicrobial susceptibility testing method"                    | Aligns with standard terminology and improves clarity.                                                                                                                                                                                                                                                 |

### Added

| Field / Element                          | Previous Value | New Value                                                                                          | Rationale                                                                                                                                  |
| ---------------------------------------- | -------------- | -------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| **Environmental Material**               | Not Present    | New field capturing environmental sampling location (e.g., sink, surface, equipment)               | Required to better classify environmental sources in late-onset sepsis investigations.                                                     |
| **Number of Annual Neonatal Admissions** | Not present    | Optional integer field (ranges may be considered)                                                  | Provides denominator data for calculating infection rates, though acknowledged to be difficult to obtain from health information units.    |
| **Gestational Age Source**               | Not present    | Field capturing source (LMP, ultrasound, maternal recall)                                          | Addresses variability and uncertainty in gestational age estimation.                                                                       |
| **Date of Outcome**                      | Not present    | Separate field capturing date of outcome                                                           | Improves flexibility vs fixed timepoints (e.g., day 28 not always feasible).                                                               |
| **Neonatal care level**                  | Not present    | Field (ICU, high-dependency, general neonatal ward)                                                | Captures level of care rather than country-specific classifications; important for understanding severity of illness and resource context. |
| **Days in Hospital at Outcome**          | Not present    | Captures the number of days from admission to outcome; critical for understanding clinical course. | Very important for understanding the clinical course.                                                                                      |

---

## Prior Version History (v1.0.0.1 → v1.x)

The entries below summarise the evolution of the specification from its initial release. Full field-level details for each minor/patch version are maintained in the repository commit history.

| Version | Date       | Summary             |
| ------- | ---------- | ------------------- |
| 1.0.0   | 2026-08-11 | Draft first release |

---

## Versioning Policy

The Neonatal Sepsis Metadata Specification follows an adapted Semantic Versioning scheme:

`MAJOR.MINOR.PATCH[.BUILD]`

| Component | Increment Trigger                                               | Example                  |
| --------- | --------------------------------------------------------------- | ------------------------ |
| **MAJOR** | Breaking structural changes; removal of fields; paradigm shift. | `v1.x.x → v2.0.0`        |
| **MINOR** | Backwards-compatible new fields or modules; new enumerations.   | `v2.0.x → v2.1.0`        |
| **PATCH** | Bug fixes; clarifications; constraint corrections.              | `v2.1.0 → v2.1.1`        |
| **BUILD** | Internal drafts, pre-release annotations (not production).      | `v1.0.0.1` (pre-release) |

---

## Review & Approval Sign-off

| Role                | Name | Signature | Date |
| ------------------- | ---- | --------- | ---- |
| Data Curator        |      |           |      |
| Clinical Advisor    |      |           |      |
| Bioinformatics Lead |      |           |      |
| Project PI          |      |           |      |

---

# Curator Notes

Use this section to record contextual observations, outstanding issues, or implementation decisions not captured in the structured tables above.

## Note 1: Community-Acquired vs. Hospital-Acquired Infection, Refinement Needed

**Reference:** March 12, 2026 Section 8 (Patient Demographics & Birth Information)

**Issue:** Anne Amulele raised a critical issue: some neonates are born and discharged, then readmitted days later when they become sick. The current fields capture *days in hospital before specimen collection* but do not adequately capture the full admission/discharge/readmission pathway. This makes it difficult to distinguish between true community-acquired infections and hospital-acquired infections in readmitted neonates.

**Status:** Acknowledged as a gap. The current specification does not fully address this scenario.

**Action Required:** Future iteration of the specification should consider additional fields or guidance to handle readmission cases (e.g., number of prior admissions, time between discharge and readmission, admission source).

---

## Note 2: Worked Examples Initiative, In Progress

**Reference:** March 12, 2026 Section 10 (Worked Examples Initiative)

**Issue:** To improve usability and implementation clarity, the working group agreed to develop practical worked examples demonstrating how to complete the metadata template for real-world scenarios.

**Status:** In progress. Working group members are submitting brief case study synopses (e.g., "A baby was born in this region with these characteristics..."). Dom will convert these into filled-in template examples. Examples are particularly valuable for tricky cases where it's unclear which field should contain specific information, such as cases with multiple isolates from the same patient.

**Deliverable:** A worked examples document will be created in the shared Google Drive.

**Action Required:** Working group members to continue submitting case study synopses to the shared Google Drive.

---

## Note 3: Multi-use Case Design Considerations

**Reference:** January 29, 2026 Section B (Real-world usability of the standard)

**Issue:** The specification is intended to support both surveillance and research use cases, which have differing data requirements. Surveillance settings typically need a smaller set of core fields (e.g., 10–15 key variables), while research studies can collect a more extensive set (e.g., 70–80 fields). Balancing these needs introduces complexity in defining which fields are mandatory, recommended, or optional.

**Status:** Acknowledged. The working group discussed a tiered approach (e.g., minimum surveillance dataset, standard research dataset, extended research dataset) to improve usability across contexts. This approach was agreed in principle but has not yet been implemented in the current version.

**Action Required:** Future iterations of the specification should define use-case-specific tiers, all harmonized to the same underlying ontology. The working group may need to prioritize which fields belong in each tier.

---

## Note 4: Free-Text vs. Controlled Vocabulary — A Deliberate Balance

**Reference:** Throughout the specification

**Issue:** The specification contains a mix of free-text fields (e.g., identifiers, facility names, numeric values, elaboration notes) and controlled vocabulary fields (dropdowns with ontology terms). Free-text offers flexibility for local data entry but can hinder interoperability and aggregation.

**Status:** The working group has intentionally retained free-text for fields where local context is essential (e.g., specimen IDs, protocol descriptions) and where controlled lists would be impractical or overly restrictive. At the same time, the group has added controlled vocabularies for key clinical, microbiological, and demographic fields to support harmonization.

**Considerations for the future:**

* Numeric fields such as days in hospital, age at collection, and bed counts could be converted to dropdown ranges to improve consistency without losing analytical value.
* Facility names could be complemented with a facility identifier (e.g., a national health facility code) to enable linking without forcing a global list.
* Elaboration free-text fields should remain optional and accompanied by examples to guide useful entries.

**Action Required:** No immediate action, but the working group may revisit the balance in future iterations as implementation experience accumulates.

---

## Note 4: Denominator Fields Balancing Feasibility and Analytical Rigour

**Reference:** March 12, 2026 Section 6 (Healthcare Facility Information)

**Issue:** Several fields critical for calculating epidemiological metrics such as *healthcare facility size* (total beds), *total number of neonatal beds*, and *number of annual neonatal admissions* were classified as optional, despite their importance for calculating infection rates and contextualising findings.

**Rationale:** The working group recognised that requiring these fields as mandatory would create a significant burden for data collectors, particularly in resource-limited settings where such information is often unavailable or difficult to obtain. To balance the need for robust denominator data with practical usability, the group made these fields optional but included strong encouragement to provide them. Where possible, dropdown ranges (e.g., 1–10 beds, 11–20 beds) were used to reduce data entry burden while still enabling meaningful categorisation.

**Implications:** Users of the specification should be aware that optional denominator fields may be missing from some datasets, which will limit the ability to calculate precise infection rates. For studies where denominator data are essential, implementers should prioritise collecting these fields and, if necessary, supplement with local data sources.

**Future Considerations:** As implementation experience accumulates, the working group may revisit whether certain denominator fields should be elevated to mandatory for specific use cases (e.g., surveillance versus research) through a tiered approach.

---

## Note 4: Field Removal Criteria and Data Quality Prioritization

Fields such as **"colonization vs infection"** and **"water availability"** were removed due to concerns around reliability, ambiguity, and risk of introducing bias. This reflects a broader design principle prioritizing data quality and interpretability over completeness. Formalizing these criteria may improve consistency in future decision-making.

---


