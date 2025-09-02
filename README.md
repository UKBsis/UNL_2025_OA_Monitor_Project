# UKBsis-2024-OA-Monitor-Project
# OA Monitor Qlik Scripts

This repository contains Qlik Sense ETL scripts used in the **UKB OA Monitor Project**.  
It consolidates metadata from CrossRef, DOAJ, Unpaywall, Institute received reports, and UKBsis datahub snapshots, applying business rules to classify publications (DOIs) into **OA categories A–D**.

---

## 🚀 Workflow

1. **Mapping** – ISSN.org mappings for ISSN to ISSN-L.  
2. **Institutes Data** – Loads institutional identifiers and metadata.  
3. **CrossRef** – CrossRef publication metadata (DOIs, ISSNs, dates).  
4. **DOAJ** – Journal Open Access indicators.  
5. **UPW (Unpaywall)** – Open access status at article level.  
6. **Returned** – Adjustments from institutes.  
7. **ReturnedSheet** – Pure isolated returned data for testing.  
8. **UKBsis** – Datahub publisher reports as comparison.  
9. **Final Model** – Consolidates all sources, applies rules, assigns final OA categories.  
10. **Main_Call.qvs** – Executes all steps in correct order.

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
- Institute-returned corrections can override (Step 2b).  


---

## ⚙️ Data Sources

- **ISSN.org** (ISSN to ISSN-L mappings)  
- **CrossRef** (DOI metadata)  
- **DOAJ** (Directory of Open Access Journals)  
- **Unpaywall** (OA status per DOI)  
- **Institute Reports** (Excel corrections returned by institutions)  
- **UKBsis QVD Snapshots** (Publisher report DOIs, journal facts)

## 📂 Datasets and Resources 
https://zenodo.org/api/records/16962476/draft/files/Send%20Back%20Template%20OA%20monitor%20UKBsis.xlsx/content
https://zenodo.org/api/records/16962476/draft/files/FLOW%20OA%20Monitor.png/content
https://zenodo.org/api/records/16962476/draft/files/Initial%20Output%202024%20for%20OA%20analysis%20Template.csv/content


