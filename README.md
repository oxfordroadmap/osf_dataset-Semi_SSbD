# prj-Semiconductor_SSbD

## Methodology

This bibliometric analysis was conducted using data from the **Web of Science Core Collection**.

* **Database Access Date:** March 11, 2026
* **Search Query:** 

1. "TS=( (semiconductor* OR ""Wafer Fab*"" ) AND ( ""supply chain"" ) AND (""Scope 3"" OR ""carbon neutrality"" OR ""carbon emissions"" OR resilience OR safety) )	Editions: WOS.SCI,WOS.SSCI,WOS.AHCI,WOS.BSCI,WOS.BHCI,WOS.ESCI"
2. "TS= ( (semiconductor* OR ""Wafer Fab*"" OR ""digital platform*"" ) AND (""ITU-T L.1470"" OR ""ITU-T L.1480"" OR ""IEEE 7000"" OR ""IEEE standard*"" OR ""ITU standard*"" OR ""ISO standard*"" OR ""green standard*"" OR ""Carbon Border Adjustment Mechanism"" OR ""Responsible Business Alliance"" )  OR (EcoVadis OR IntegrityNext OR SupplyShift and SupplierGateway OR Workiva OR AuditBoard OR Intengine OR ""SAP Ariba"") )	Editions: WOS.SCI,WOS.SSCI,WOS.AHCI,WOS.BSCI,WOS.BHCI,WOS.ESCI"
3. "TS=( (semiconductor* OR ""Wafer Fab*"" ) AND (""federated data"" OR ""data space*"" OR interoperability) )	Editions: WOS.SCI,WOS.SSCI,WOS.AHCI,WOS.BSCI,WOS.BHCI,WOS.ESCI"
4. "TS=( (semiconductor* OR ""Wafer Fab*"" ) AND ( metrology  OR ""In-situ sensor*"" ) AND (""artificial intelligence"" OR ""machine learning"" OR ""data analytics"" ))	Editions: WOS.SCI,WOS.SSCI,WOS.AHCI,WOS.BSCI,WOS.BHCI,WOS.ESCI"
5. "TS=( (semiconductor* OR ""Wafer Fab*"" ) AND ( (multimodal OR foundation*) NEAR model* ) AND (manufacturing OR metrology ) )	Editions: WOS.SCI,WOS.SSCI,WOS.AHCI,WOS.BSCI,WOS.BHCI,WOS.ESCI"
6. "TS=( (semiconductor* OR ""Wafer Fab*"" ) AND ( ""Digital Circular"" OR ""Circular Economy"" OR ""Circular Engineering"" OR ""zero-waste"" OR  ""life cycle"" OR LCA ) AND (""artificial intelligence"" OR ""machine learning"" OR ""data analytics"" ))	Editions: WOS.SCI,WOS.SSCI,WOS.AHCI,WOS.BSCI,WOS.BHCI,WOS.ESCI"

---

## 🛠️ Data Curation & Intellectual Contribution

To comply with the database licensing agreements of **Web of Science (Clarivate)**, raw `.bib` or `.txt` export files containing copyrighted abstracts and proprietary "Keywords Plus" are **not** hosted in this repository.

Instead, this project provides a **Curated Open Dataset** and the associated **Socio-technical Thesaurus** developed specifically for this research area.

### 1. The Thesaurus (Original Research Contribution)

The files in the `/thesaurus` folder represent the core manual curation effort of this project. These files resolve terminological ambiguity and technical silos:

* **`thesaurus/Biblio-keyword-stop.txt`**: A custom exclusion list of non-informative terms (e.g., "analysis", "framework") to enhance thematic clarity.
* **`thesaurus/Biblio-keyword-synonyms.csv`**: Mapping file for R-based `bibliometrix` normalization.
* **`thesaurus/VOSVwr-keyword-synonyms.txt`**: Standardizes terminology (e.g., merging acronyms and full technical names) for VOSviewer.

### 2. The Processed Dataset

The file `data/processed/01-Data-Redacted-WoS.txt` is a redacted version of the bibliometric raw data (`data/processed/00-Data-Collected-WoS.txt`), containing only:

* **Core Identifiers:** DOI and WoS Accession Number (UT).
* **Bibliographic Basics:** Title, Authors, Source, and Year.
* **Author Keywords:** The original descriptors provided by authors.

---

## 🚀 How to Reproduce

You can reproduce the analysis using the provided code and your own institutional access:

1. **Re-hydrate the Data:** Use the **Search Query** above in Web of Science to export your own raw metadata, with or without the set new time period. 
2. **Bibliometrix/Biblioshiny:** Use the **`thesaurus/Biblio-keyword-stop.txt`** and **`thesaurus/Biblio-keyword-synonyms.csv`** accordingly.
3. **VOSviewer Analysis:** " Use  the **`thesaurus/VOSVwr-keyword-synonyms.txt`**

---

## License

### 🔓 Open Data & Code (CC-BY 4.0)
The **Thesaurus files** (`/thesaurus`) and **Methodological Documentation** are licensed under the [Creative Commons Attribution 4.0 International License (CC-BY 4.0)](https://creativecommons.org/licenses/by/4.0/). 

**You are free to:**
*   **Share** — copy and redistribute the material in any medium or format.
*   **Adapt** — remix, transform, and build upon the material for any purpose, even commercially.
*   **Attribution** — You must give appropriate credit (cite this repository).

### ⚠️ Third-Party Metadata
The bibliographic metadata (Titles, Authors, Source) provided in `data/processed/` is derived from **Web of Science**. Usage and redistribution of this specific metadata are subject to the terms and conditions of Clarivate Analytics. This data is provided here solely for the purpose of academic reproducibility.


### 💡 Repository Structure

```text
├── data/
│   ├── raw/                # (Ignored by git) Raw WoS export
│   └── processed/          # Cleaned bibliometric/metadata CSV
├── thesaurus/              # Your custom curation files
│   ├── VOSVwr-keyword-synonyms.txt   # VOSviewer format (Label, Replace by)
│   ├── Biblio-keyword-synonyms.R     # Bibliometrix R-based synonym mapping
│   └── Biblio-keyword-stop.txt       # List of words to exclude
└── README.md
```