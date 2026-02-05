# Metadata Standard Documentation – Part 1: The Data Dictionary

## 1. Purpose

The Data Dictionary defines the structure, meaning, and usage of each metadata field within the metadata standard template. It is the main dictionary which is used to populate the excel template and provides ontology mappings (using an ontology ID where possible), standardized definitions, guidance and indicates expected data entry formats.

## 2. Overview

Each row in the data dictionary corresponds to a metadata field in the main metadata template.

The dictionary includes the following columns:

| Column Name | Description |
|------------|-------------|
| Parent Term | The higher-level category or grouping under which the field belongs. This helps organize related fields into a modular structure (e.g., Identifiers, Sample collection and processing, Facility information). Purpose: Groups related fields logically; enables hierarchical representation. |
| Field | The specific metadata field name as it appears in the metadata template. Purpose: Defines the exact element of metadata to be collected |
| Ontology Identifier | A persistent and unique reference to an external controlled vocabulary or ontology term. In cases where an ontology term matching the field is not found in the domain-relevant sources, this is marked with an x or is blank. Purpose: Anchors each field to an existing ontology or vocabulary term for semantic interoperability. |
| Definition | A concise, unambiguous description of the meaning of the field. It is derived from the ontology and where there is no matching information, it is marked with an x or is blank. Purpose: Provides an authoritative description of what the field represents. |
| Guidance | Practical instructions for completing the field. This section helps users correctly interpret the field and enter valid values. Purpose: Offers practical help to end users during data entry. |
| Permitted values | Specifies the expected format or restriction for data entry. Examples include free text, integer, date, dropdown list, Boolean (yes/no), or picklist. Purpose: Defines permissible data entry type or constraint to ensure consistency |

## 3. Relationship to Other Files

| Related File | Relationship |
|-------------|--------------|
| Metadata Template | The data dictionary defines all fields that appear in the template, ensuring consistent naming and interpretation. |
| Reference Term Dictionary | The data dictionary specifies which fields use controlled vocabularies and points to the relevant lists. |

---

# Metadata Standard Documentation – Part 2: Reference Term Data Dictionary

## 1. Purpose

The Reference Term Data Dictionary defines the controlled vocabularies and permissible terms associated with specific fields in the metadata standard. For each field with a pick list as a permissible value, the list is defined in this document. By using predefined reference terms, users can minimize ambiguity and errors associated with free text data entry and improve data validation.

## 2. Overview

Each pick lists reference terms are grouped according to the category to which they apply – these main fields are highlighted in the BLUE in the document. Each row belonging to the group describes one or more permissible values for a specific metadata field that requires standardized or controlled input.

| Column | Description |
|--------|-------------|
| Field | The metadata field from the main data dictionary that requires controlled input (e.g., geo_loc_name (Country), Biospecimen Type, Sequencing instrument). |
| Ontology Identifier | A persistent reference to the ontology term that defines the preferred term (e.g., from OBO, EFO, NCIT, or NCBI Taxonomy). Where there is no matching information, it is marked with an x or is blank. |
| Definition | A brief description of the concept represented by the preferred term. Usually derived from the source ontology. |

## 3. Relationship to Other Files

| Related File | Relationship |
|-------------|--------------|
| Data Dictionary | Identifies which fields use controlled vocabularies and specifies the “Allowed Input Type: Controlled term.” |
| Metadata Template | Provides the dropdown or validation lists populated using the preferred terms from this reference file. These validation lists are in the template document in a tab called `Reference_data`, `Country_coded_data` and `Pathogen_list` – please do not edit these sheets in the template. |

## 4. Important Notes

- These lists may not be complete.
- If a term is not included but commonly used in your setting, please contact the maintainers.

---

# Metadata Standard Documentation – Part 3: Metadata Template

## 1. Purpose

The Metadata Template provides the standardized structure for capturing descriptive information about datasets, samples, experiments, and other relevant research entities. The template is informed by the Data Dictionary (which defines each field) and supported by the Reference Term Data Dictionary (which provides controlled vocabularies for specific fields).

> **Note:** The template is provided as a macro-enabled Excel workbook. Please enable macros when opening and testing the template.

## 2. Overview

The Metadata Template is a structured spreadsheet designed for data entry by contributors.

- Each row represents a distinct metadata record for a sample
- Each isolate requires a new row
- Each column represents a metadata field defined in the Data Dictionary

## 2.1 File Structure

- **Format:** Macro-enabled Excel file
- **Organization:** Five distinct tabs/sheets grouped by logical sections
- **Column Headers:** Correspond to field names defined in the Data Dictionary
- **Validation:** Dropdown lists applied where controlled vocabularies are required

## 3. Column-Level Description

Each column corresponds to a field defined in the Data Dictionary.

- Row 1 contains guidance (hover text)
- Data entry begins on Row 2
- Do **not** edit Row 1

## 4. Sheet-Level Description

### 4.1 Facility Information (Sheet 1)

Facility-related information is captured once per facility.

| healthcare facility name | type of facility | health facility size | number of total neonatal beds |
|--------------------------|------------------|----------------------|-------------------------------|
| Tygerberg Hospital | Hospital (with neonatal ICU) | Very Large: > 500 beds | 60 |
| Parklands East Clinic | Rural Health Clinic | Very small: < 50 beds | 0 |

### 4.2 Template_clinical (Sheet 2)

Clinical data capture.

| subject identifier | specimen collector sample ID | healthcare facility name | purpose of sampling |
|--------------------|------------------------------|--------------------------|---------------------|
| S001 | K23U42 | Tygerberg Hospital | Targeted: Cluster/Outbreak investigation |
| S002 | BLU2583 | Parklands East Clinic | Not applicable |

### 4.3 Template_laboratory (Sheet 3)

Laboratory data collection.

| subject identifier | specimen collector sample ID | isolate ID | sample collected by |
|--------------------|------------------------------|------------|---------------------|
| S001 | K23U42 | K23U42-1 | National Health Laboratory Services |
| S002 | BLU2583 | 1-BLU-2583-3 | National Health Laboratory Services |

### 4.4 Template_genomics (Sheet 4)

Genome sequencing information.

| specimen collector sample ID | isolate ID | sequenced by | sequence submitted by |
|------------------------------|------------|--------------|-----------------------|
| K23U42 | K23U42-1 | National Health Laboratory Services | Stellenbosch University |
| BLU2583 | 1-BLU-2583-3 | National Health Laboratory Services | — |

### 4.5 Template_AST (Sheet 5)

Antimicrobial susceptibility testing data.

| isolate ID | AST testing date | antimicrobial agent name | AST phenotype |
|------------|-----------------|---------------------------|---------------|
| K23U42-1 | 2025-07-14 | ampicillin | Resistant antimicrobial phenotype |
| K23U42-1 | 2025-07-14 | tetracyclin | Susceptible dose dependent antimicrobial phenotype |

## 5. Data Entry Guidance

### 5.1 General Principles

- Do not rename, reorder, or delete columns
- Use consistent formatting:
  - Dates: `YYYY-MM-DD`
  - Numeric values: plain numbers (no units unless specified)
- For controlled vocabularies, select from dropdown menus
- Null values include: `missing`, `not applicable`, `restricted information`

### 5.2 Example Workflow

1. Open the Template
2. Familiarize yourself with each section and column header
3. Consult the Data Dictionary
4. Populate metadata systematically
5. Save your completed template
