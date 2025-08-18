# PSI_FC_RawData
PSI_FC_RawData sorting

# NPEC Data Sorter
Python pipeline to organize raw NPEC chamber data into a clean, analysis-ready structure.  
Handles **FluoroCam (FC)**, **RGB**, **SWIR (hyperspectral)**, **IR (thermal)**, and **metadata**.

---

## Features
- Sorts and groups:
  - FC TARs (by protocol identity)
  - RGB images (from TARs or loose)
  - SWIR files (`.hdr` + `.bil`)
  - IR data (`.raw` + `.txt`)
  - Metadata (`.xlsx` / `.csv`)
- Works with both structured (`RawData/`, `Metadata/`) and flat layouts
- Generates `.csv` reports for all data types
- Optional **fast mode** (process only one day)

---

## Input Examples
**Structured**
```
DownloadsRoot/
RawData/2025-02-1/
RawData/2025-02-2/
Metadata/metadata.xlsx
```

**or Flat, if you already did things with the data and everything is in one folder**
```
DownloadsRoot/
Experiment\_1.tar
Thermal\_001.raw
metadata.xlsx
```

---

## Output Layout
```
Sorted/
Rest/
Code/
Anaconda Environment/
Reports/   # indexes + metadata
FC/          # protocol-grouped TARs
RGB/         # all PNGs
SWIR/        # .hdr + .bil
IR/          # .raw + .txt

````

---
## Usage
1. Edit paths in script:
   ```python
   DOWNLOADS_ROOT = Path("D:/.../Downloads")
   OUT_ROOT       = Path("D:/.../Sorted")
````
2. (Optional) adjust fast mode:
   ```python
   ONLY_ONE_DAY = True
   ONE_DAY_NAME = None   # or "2025-02-1"
   ```
3. Run:
   ```bash
   python 18-8_Automatic_sorting_Chris.py
   ```

---

## Reports 
* `fc_index.csv` / `protocol_grouping.csv` → FluoroCam TARs + protocols
* `swir_index.csv` → SWIR HDR/BIL
* `ir_index.csv` → IR RAW + metadata
* `rgb_loose_index.csv` → loose PNGs
* `metadata_index.csv` → Excel/CSV metadata

---

## Environment

Auto-generated in:
```
Sorted/Rest/Anaconda Environment/environment.yml
```
Create with:
```bash
conda env create -f environment.yml
conda activate npec-pipeline
```
