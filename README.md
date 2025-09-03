# UKBsis-2024-OA-Monitor-Project
# OA Monitor Qlik Scripts

This repository contains Qlik Sense ETL scripts used in the **2024 UKB OA Monitor Project**.  
It consolidates metadata from CrossRef, DOAJ, Unpaywall, Institute received reports, and UKBsis datahub snapshots, applying business rules to classify publications (DOIs) into **OA categories A–D**.

---

🔄 Workflow Overview

- Mapping – loads ISSN.org ISSN–ISSN-L mappings for journal-level checks.
- Institutes Data – loads DOIs and metadata returned by participating institutes.
- CrossRef – loads DOI metadata and ISSNs harvested from CrossRef.
- DOAJ – loads DOAJ journal metadata for OA checks.
- UPW (Unpaywall) – loads OA status, repository locations, and full-text availability.
- Returned – loads manual corrections and updates provided by institutes.
- ReturnedSheet – isolates returned results for independent testing by UKBsis.
- UKBsis – ingests DOIs from the UKBsis Publisher Report dataset.
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
- `06_Returned.qvs` → Institute feedback  
- `07_ReturnedSheet.qvs` → Isolated returned data  
- `08_UKBsis.qvs` → UKBsis snapshot data  
- `09_FinalModel.qvs` → Final OA classification  
- `Main_Call.qvs` → Orchestration

---

## 📊 Business Rules

- **A** → Gold (ISSN in DOAJ via CrossRef)  
- **B** → Gold/Hybrid verified by UKBsis Publisher Reports  
- **C** → Green (repository copy)  
- **D** → Bronze/Closed  
- Institute-returned corrections can override (Step 2b and later).


---

## ⚙️ Data Sources

- **ISSN.org** (ISSN to ISSN-L mappings)  
- **CrossRef** (DOI metadata)  
- **DOAJ** (Directory of Open Access Journals)  
- **Unpaywall** (OA status per DOI)  
- **Institute Reports** (Excel corrections returned by institutions)  
- **UKBsis QVD Snapshots** (Publisher report DOIs, Journals data)

## 📂 Datasets and Resources 
All sets and subsets can be accessed in the link below: 

https://zenodo.org/records/16962476?token=eyJhbGciOiJIUzUxMiJ9.eyJpZCI6ImI4MmNkNTk5LTVjOGEtNDZjOS1hYjEwLWJiYjhhODNiMTViZiIsImRhdGEiOnt9LCJyYW5kb20iOiI0NTIzODRkYmFiY2JkNmY5MmM3YzdhNWI4Nzg0ZmUzNSJ9.BkbSNDVXUv9P9x6dl5GX22eLi8tn6OQa_-zSJCBiNdAXn_sRwNInfS9I3zfG5K5HdKeYT4ro2ge_miK-ZUwMkw

✍️ Maintained by UKBsis OA Monitor Project Team

