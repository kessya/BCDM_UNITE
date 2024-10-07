# BCDM_UNITE
This repository contains the implementation of the Barcode Core Data Model (BCDM) for [UNITE](https://unite.ut.ee) data. More information about the BCDM can be found at https://github.com/DNAdiversity/BCDM.

## Mapping of UNITE (PlutoF) data fields to BCDM

**mapping_UNITE_to_BCDM.tsv** ([link](mapping_UNITE_to_BCDM.tsv)): This document provides the mapping of UNITE (PlutoF) data fields to BCDM. BCDM fields without an equivalent in UNITE are kept in the mapping table with *predicate_id* set to *notApplicable*. The columns in the mapping table are based on the Simple Standard for Sharing Ontological Mappings ([SSSOM](https://mapping-commons.github.io/sssom/)) and include: 

| **Column name** | **Definition** |
|:--------------- |:-------------- |
| subject_id | BCDM field id |
| subject_label | BCDM field name |
| predicate_id | Mapping predicate, the semantic mapping relationship used |
| object_id | UNITE field id |
| object_label | UNITE field name |
| mapping_justification | Mapping justification |
| mapping_date | Mapping date |
| author_id | ORCID of the person(s) responsible for asserting the mapping |
| confidence | A score between 0 and 1 to denote the confidence or probability that the match is correct, wehere 1 denotes total confidence |
| comment | Comments regarding the mapping |
| example | Example values for objects |

Additional fields that could potentially be added to the mapping table include subject_source, subject_source_version, object_source, and object_source_version. These were omitted because the BCDM and UNITE field names do not yet use versioning.

A list of UNITE fields, along with their data types and formats, can be found in the field_definitions.tsv ([link](field_definitions.tsv)).

## Public downloads
Versioned releases of UNITE data in BCDM-compliant format are available for download on the [UNITE Resources page](https://unite.ut.ee/repository.php). The latest release can be found at [https://dx.doi.org/10.15156/BIO/3301224](https://dx.doi.org/10.15156/BIO/3301224).

## Generating BCDM-formatted output for UNITE (for internal use)
```console
python manage.py shell
exec(open("/Users/kessy/GitHubRepos/BCDM_UNITE/scripts/generate_bcdm.py"))
```
