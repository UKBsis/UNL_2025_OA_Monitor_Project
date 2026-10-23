# UNL_2025_OA_Monitor_Project
# OA Monitor Qlik Scripts

This repository contains Qlik Sense ETL scripts used in the **2025 UNL OA Monitor Project**.  
It consolidates metadata from CrossRef, DOAJ, Unpaywall, Institute received reports, and SURF (UKB) Metadata Hub snapshots, applying business rules to classify publications (DOIs) into **OA categories A–D**.

---

🔄 Workflow Overview

- Mapping – loads ISSN.org ISSN–ISSN-L mappings for journal-level checks.
- Institutes Data (CRIS) – loads DOIs and metadata returned by participating institutes.
- CrossRef – loads DOI metadata and ISSNs harvested from CrossRef.
- DOAJ – loads DOAJ journal metadata for OA checks.
- UPW (Unpaywall) – loads OA status, repository locations.
- SURF (UKB)– ingests DOIs from the SURF (UKB) Publisher Report dataset.
- FinalModel – merges all sources and applies the business rules to assign OA categories (A–D).
- Main_Call – orchestrates execution of all subscripts in the correct order.
---

## 📂 Scripts

Each script is modular:

- `01_Mapping.qvs` → ISSN mappings  
- `02_InstitutesData.qvs` → Institutional identifiers  
- `03_CrossRef.qvs` → CrossRef metadata  
- `04_DOAJ.qvs` → DOAJ metadata  
- `05_UPW.qvs` → Unpaywall metadata   
- `06_SURF.qvs` → SURF (UKB) snapshot data  
- `07_FinalModel.qvs` → Final OA classification  
- `Main_Call.qvs` → Orchestration

---

## 📊 Business Rules

- **A** → Gold (article is published in a full open access journal, ISSN found in DOAJ via CrossRef lookup)  
- **B** → Gold/Hybrid (article is published open access in a hybrid or full open access journal that is not registered in the DOAJ) verified by UPW or SURF (UKB) Metadata Hub Publisher Reports  
- **C** → Green (article is published closed access but shared open access in a repository) URL link to repository record provided by UPW or the Institution 
- **D** → Bronze/Closed (article is published closed access or shared in bronze open access on the site of the publisher)
- **No Cat** → DOI not found in DOAJ / UPW / CrossRef / SURF (UKB) PR



---

## ⚙️ Data Sources

- **ISSN.org** (ISSN to ISSN-L mappings)  
- **CrossRef** (DOI & ISSN metadata)  
- **DOAJ** (Directory of Open Access Journals)  
- **Unpaywall** (OA status, URLs per DOI)  
- **Institute Reports** (CSV reports by institutions)  
- **SURF (UKB) Metadata QVD Snapshots** (Publisher report DOIs, Journals data)

## 📂 Datasets and Resources 
All sets and subsets can be accessed in the link below: 
https://zenodo.org/uploads/22013457 



✍️ Maintained by UNL OA Monitor Project Team

