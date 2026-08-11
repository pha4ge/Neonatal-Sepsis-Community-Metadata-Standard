# Neonatal Sepsis Metadata Standard for Genomic Epidemiology

A structured, ontology-anchored metadata standard for the genomic epidemiology of neonatal sepsis — packaged with a ready-to-use, macro-enabled data collection template, a colour-coded data dictionary, and step-by-step standard operating procedures (SOPs).

![Template version](https://img.shields.io/badge/template-v2.0.1-blue)
![Standard](https://img.shields.io/badge/PHA4GE-Neonatal%20Sepsis-informational)
![Format](https://img.shields.io/badge/format-Excel%20%2B%20SOPs-green)

---

## Table of contents

- [Overview](#overview)
- [Background](#background)
- [Scope](#scope)
- [Community development](#community-development)
- [Community terminology and ontology-linked semantics](#community-terminology-and-ontology-linked-semantics)
- [Repository contents](#repository-contents)
- [Getting started](#getting-started)
- [Versioning](#versioning)
- [Intended audience](#intended-audience)
- [Contributing and feedback](#contributing-and-feedback)
- [Citation](#citation)
- [License](#license)
- [Acknowledgements and contact](#acknowledgements-and-contact)

---

## Overview

Neonatal sepsis remains a major cause of morbidity and mortality worldwide, particularly in low- and middle-income countries. Advances in whole-genome sequencing (WGS) and other high-throughput genomic technologies have transformed our ability to study the epidemiology, transmission dynamics, and antimicrobial resistance patterns of the pathogens that cause it. The full value of genomic data, however, is only realised when it is accompanied by high-quality, standardised metadata.

This repository is the authoritative home of the **Neonatal Sepsis Metadata Standard**: a structured and harmonised framework designed to support genomic epidemiology studies of neonatal sepsis. The standard enables consistent data collection, interoperability across studies and platforms, and meaningful comparison and reuse of genomic datasets.

---

## Background

### Neonatal sepsis

Neonatal sepsis is a systemic infection occurring in newborns, typically classified as early-onset or late-onset based on the timing of symptom onset. It is caused by a diverse range of bacterial and fungal pathogens and is influenced by host, environmental, and healthcare-associated factors. Despite improvements in diagnostics and clinical care, it continues to pose significant challenges due to nonspecific clinical presentation, evolving pathogen landscapes, and increasing antimicrobial resistance.

Genomic epidemiology has emerged as a powerful approach to identify and track causative pathogens, understand transmission routes within neonatal units, characterise virulence and antimicrobial resistance determinants, and inform infection prevention and control strategies. Robust metadata describing the host, clinical context, sample, and laboratory processes are essential to interpret genomic findings accurately and to place them in an epidemiological context.

### Metadata standards in genomic epidemiology

Metadata standards define a common structure, vocabulary, and set of expectations for describing data. In genomic epidemiology, standardised metadata improves data quality and completeness, enables interoperability across databases, tools, and studies, facilitates data sharing and reuse in line with the FAIR principles (Findable, Accessible, Interoperable, Reusable), and supports reproducibility and transparent interpretation of results. Without it, genomic datasets are difficult to integrate, compare, or interpret beyond their original study context.

---

## Scope

This metadata standard supports the genomic epidemiology of neonatal sepsis by defining a harmonised set of metadata elements relevant to pathogen genomics, clinical context, and epidemiological analysis. It is designed for use in research, public health surveillance, and data-sharing initiatives, and it:

- focuses on metadata accompanying pathogen genomic data related to neonatal sepsis;
- is applicable across diverse geographic, laboratory, and healthcare settings; and
- supports both retrospective and prospective genomic studies.

This standard is **not** intended to replace clinical diagnostic criteria or treatment guidelines, to serve as a comprehensive electronic health record schema, or to function as a regulatory or clinical decision-support tool.

---

## Community development

The Neonatal Sepsis Community Metadata Standard has been developed in collaboration with the **Public Health Alliance for Genomic Epidemiology (PHA4GE)**.

Development of the standard has followed an open, community-driven process involving experts from microbiology, laboratory medicine, genomic epidemiology, public health, bioinformatics, data management, and related disciplines. Metadata requirements, terminology, and controlled vocabularies were identified through stakeholder consultation and refined through iterative review, ensuring that the standard reflects the practical requirements of laboratories, surveillance programmes, and public health agencies working with neonatal sepsis.

This collaborative approach ensures that the standard remains scientifically robust, operationally practical, and responsive to the evolving needs of the global neonatal sepsis community.

---

## Community terminology and ontology-linked semantics

The metadata fields and controlled vocabulary terms included within the Neonatal Sepsis Community Metadata Standard were identified through community consultation, ensuring that the standard reflects terminology familiar to laboratories, surveillance programmes, researchers, and public health practitioners.

Following community agreement, metadata fields and controlled vocabulary terms were systematically searched against existing biomedical ontologies using the Ontology Lookup Service (OLS). Where an appropriate ontology concept exists, the metadata element or controlled vocabulary term is linked to the corresponding ontology identifier, providing stable semantic identifiers that support interoperability with external standards, databases, and analytical systems.

Where no suitable ontology concept currently exists, the community-approved terminology remains part of the standard and is retained in both terminology display modes. These concepts remain fully supported within the metadata collection template and supporting documentation, while simultaneously being identified as candidates for future New Term Requests (NTRs) — ensuring that important community requirements are represented today while supporting the continued evolution of the biomedical ontology ecosystem.

---

## Repository contents

The repository is organised into two data-capture **templates** and four supporting **documents (SOPs)**.

### Templates

| File | Format | Version | Description |
|---|---|---|---|
| `NN_Sepsis_template_v2.0.1` | Excel workbook (`.xlsm`, macro-enabled) | 2.0.1 | The **VBA-encoded data collection template**. Data collectors enter metadata directly into this workbook, which guides and validates entry through dependent picklists, conditional (context-sensitive) fields, automatic ISO&nbsp;8601 date handling and derived date calculations, controlled-vocabulary dropdowns, header guidance tooltips, and one-way cross-sheet synchronisation of shared identifiers. Macros must be enabled for this functionality to run — see `SOP_Enabling_Excel_Macros`. |
| `NN_Sepsis_data_Refdata_dictionary_v2.0.1` | Excel workbook | 2.0.1 | The **standards data dictionary combined with the reference data dictionary**. The data dictionary groups fields under parent categories and, for each field, provides the field name, ontology ID, definition, guidance, value type, example, and base picklist options — colour-coded to indicate whether a field is mandatory, recommended, or optional. The reference data dictionary holds the full controlled vocabulary behind every picklist (allowed value, ontology ID, and definition). |

### Supporting documents

| Document | Version / ID | Purpose |
|---|---|---|
| `SOP_Enabling_Excel_Macros` | v1.0.1 | How to enable macros in Excel so the collection template's automated functionality will run. |
| `SOP_Using_NN_Sepsis_Data_Dictionary` | v1.0.1 | How to read and use the data / reference dictionary — navigating parent groupings, field definitions, ontology IDs, value types, examples, and the requirement colour key. |
| `NN_Sepsis_Metadata_Template_SOP` | v1.01 | How to use the data collection template — the end-to-end data-entry workflow across the worksheets. |
| `SOP_NN_Sepsis_Template_VBA_Functionality` | SOP-VBANN-001 | A detailed, plain-English explanation of the VBA-coded functionality embedded in the collection template (picklists, dependent dropdowns, conditional fields, date handling, cross-sheet synchronisation, and guidance comments). |

### Field requirement colour coding

Each field in the data dictionary is colour-coded to show how it should be treated during data collection. The exact colours and their key are shown within the dictionary file; the three tiers are:

| Requirement | Meaning |
|---|---|
| **Mandatory** | Must be completed for every record. Core to the standard and required for reliable data sharing and interoperability. |
| **Recommended** | Should be completed wherever the information is available. Adds substantial epidemiological or analytical value. |
| **Optional** | May be completed to provide additional context. Not required. |

---

## Getting started

The templates and SOPs are designed to be used together. A typical workflow is:

1. **Enable macros.** Download the collection template (`NN_Sepsis_template_v2.0.1`) and enable macros so its automated features work. Follow `SOP_Enabling_Excel_Macros`.
2. **Understand the fields.** Open the data dictionary (`NN_Sepsis_data_Refdata_dictionary_v2.0.1`) to see what each field means, its ontology ID, value type, example, allowed picklist values, and whether it is mandatory, recommended, or optional. Follow `SOP_Using_NN_Sepsis_Data_Dictionary`.
3. **Enter your data.** Complete the template worksheets. The workbook guides you with dropdown picklists, context-sensitive fields, automatic date formatting, derived calculations, and header tooltips. Follow `NN_Sepsis_Metadata_Template_SOP`.
4. **Understand the automation (optional but recommended for maintainers and reviewers).** For a full explanation of how the template behaves and why, see `SOP_NN_Sepsis_Template_VBA_Functionality` (SOP-VBANN-001).

> **Tip:** If picklists, greyed-out fields, or automatic dates are not working, the most common cause is that macros are disabled. Close the file, re-open it, and enable content — the template rebuilds all of its automated behaviour each time it opens.

---

## Versioning

Templates and documents are versioned independently, with the version recorded in each file name (for example, `v2.0.1`). Substantive changes to a template or document are accompanied by a version increment and a summary of the change in its own version history. Changes to the automated behaviour of the collection template are reflected in `SOP_NN_Sepsis_Template_VBA_Functionality`, which is re-versioned whenever the underlying macros change.

---

## Intended audience

This repository is intended for genomic epidemiology researchers studying neonatal sepsis; clinical and public health teams generating or using pathogen genomic data; bioinformaticians and data managers implementing metadata standards; and standards developers and stakeholders interested in neonatal health data harmonisation.

---

## Contributing and feedback

Contributions are welcomed from researchers, laboratories, surveillance programmes, public health agencies, ontology developers, and the wider scientific community. Examples of contributions include:

- Proposing new metadata fields
- Suggesting improvements to metadata definitions
- Recommending additional controlled vocabulary terms
- Identifying ontology mappings
- Suggesting ontology-linked terminology
- Supporting New Term Requests (NTRs)
- Reporting issues or inconsistencies within the documentation
- Improving supporting documentation and resources

To contribute, open an issue or pull request in this repository. Community review and consensus remain central to the ongoing development of the standard.

---

## Citation

If you use, adapt, or reference this metadata standard in your work, please credit the **Public Health Alliance for Genomic Epidemiology (PHA4GE)**. A formal citation and a citation file (`CITATION.cff`) may be added in a future release.

---

## License

This work is released under the license included in this repository. Please refer to the `LICENSE` file for the terms of use and redistribution.

---

## Acknowledgements 

Developed in support of the **Public Health Alliance for Genomic Epidemiology (PHA4GE)**.

The authors gratefully acknowledge the contributions of the international community of experts from microbiology, laboratory science, genomic epidemiology, bioinformatics, ontology development, public health, and data management whose expertise and collaborative efforts have shaped the development of this standard.

