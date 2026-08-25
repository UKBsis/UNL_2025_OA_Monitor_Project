# SURF_2025_OA_Monitor_Project
# OA Monitor Qlik Scripts

This repository contains Qlik Sense ETL scripts used in the **2025 SURF OA Monitor Project**.  
It consolidates metadata from CrossRef, DOAJ, Unpaywall, Institute received reports, and SURF  Metadata Hub snapshots, applying business rules to classify publications (DOIs) into **OA categories A–D**.

---

🔄 Workflow Overview

- Mapping – loads ISSN.org ISSN–ISSN-L mappings for journal-level checks.
- Institutes Data (CRIS) – loads DOIs and metadata returned by participating institutes.
- CrossRef – loads DOI metadata and ISSNs harvested from CrossRef.
- DOAJ – loads DOAJ journal metadata for OA checks.
- UPW (Unpaywall) – loads OA status, repository locations.
- SURF – ingests DOIs from the SURF Publisher Report dataset.
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
- `06_SURF.qvs` → SURF snapshot data  
- `07_FinalModel.qvs` → Final OA classification  
- `Main_Call.qvs` → Orchestration

---

## 📊 Business Rules

- **A** → Gold (ISSN in DOAJ via CrossRef)  
- **B** → Gold/Hybrid verified by SURF Publisher Reports  
- **C** → Green (repository copy URL provided)  
- **D** → Bronze/Closed
- **No Cat** → DOI not found in DOAJ / UPW / CrossRef / SURF PR



---

## ⚙️ Data Sources

- **ISSN.org** (ISSN to ISSN-L mappings)  
- **CrossRef** (DOI & ISSN metadata)  
- **DOAJ** (Directory of Open Access Journals)  
- **Unpaywall** (OA status, URLs per DOI)  
- **Institute Reports** (CSV reports by institutions)  
- **SURF Metadata QVD Snapshots** (Publisher report DOIs, Journals data)

## 📂 Datasets and Resources 
All sets and subsets can be accessed in the link below: 
https://zenodo.org/uploads/22013457 


✍️ Maintained by SURF OA Monitor Project Team

