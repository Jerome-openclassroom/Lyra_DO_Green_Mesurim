
# Lyra_SPAD_RGB – Low-tech correlation between leaf greenness and SPAD values

## 🌿 Objective
This project demonstrates the feasibility of predicting SPAD values (chlorophyll density proxy) using low-cost image-based measurements:
- Green density from scanned leaves (ImageJ),
- Surface area and chlorosis zones (MesurimPro),
- Reference SPAD meter data (Konica Minolta SPAD-502).

## 🔬 Protocol Summary

A scanned image of 15 leaves was analyzed (300 DPI).

Green density (DO_green) was computed via ImageJ.

Surface areas (total and chlorotic) were measured with MesurimPro.

SPAD values were measured 3× per leaf and averaged.

All data were compiled into a structured Excel file.

One chlorotic outlier was excluded due to yellow bias in greenness detection.

Key variable correlations were explored through GPT-4o prompting, to assess consistency between DO_green, SPAD, and % chlorosis.

This analysis identified the best pairing of low-tech indicators for chlorophyll status evaluation.


***************

Individual leaf images were prepared using the online tool MiniWebTool – Image Splitter, which enabled precise segmentation of each leaf from the full scan for separate analysis in MesurimPro.

***************

## 📈 Correlation Graphs

The following figure shows the Pearson correlations between the key variables: DO_green (ImageJ), % chlorosis (MesurimPro), and SPAD values.

![Correlation scatter plots](pictures/regressions.png)



## 📈 Results
| Variable pair              | Pearson r  | Interpretation                    |
|---------------------------|------------|----------------------------------|
| DO_green ↔ SPAD           | +0.97      | ✅ Very strong positive correlation |
| % Chlorosis ↔ SPAD        | –0.18      | ❌ No significant correlation      |
| DO_green ↔ % Chlorosis    | –0.29      | ❌ Weak negative correlation       |

## ✅ Key Findings
- DO_green (ImageJ) is a reliable substitute for SPAD values.
- MesurimPro is accurate for leaf surface measurements.
- SPAD can be approximated using RGB-based image analysis in low-tech settings.

## 🧪 Scientific Justification
Although direct measurement of total chlorophyll (a + b) via chemical extraction and Thin Layer Chromatography (TLC) is possible, it requires:
- Hazardous solvents (e.g. petroleum ether, cyclohexane),
- Lab-grade equipment and safety protocols,
- Tedious sample preparation.

Instead, this project relies on:
- Published empirical relationships between SPAD and chlorophyll (e.g., 50 SPAD ≈ 600–800 µg Chl/g DW),
- High correlation (r = 0.97) between image-derived greenness and SPAD values.

This approach ensures safety, simplicity, and reproducibility in a citizen science or field context, aligned with the philosophy of Lyra_LowCost_Soil_Leaf.

## 🧠 Suggested Use
- Education and training in plant physiology and agroecology,
- Validation tool for leaf stress detection,
- Basis for modeling NPP (Net Primary Production) in low-input systems.

📂 Files included

- Results_completed.xlsx : structured dataset with DO_green, SPAD, and chlorosis data,

- pictures/planche_initiale_reduite.jpg : scanned reference image of the leaves,

- pictures/regressions/ : correlation graphs generated during analysis,

- pictures/miniwebtool/ : image cutouts prepared using the online tool MiniWebTool – Image Splitter for leaf-by-leaf analysis in MesurimPro,

- README.md : this documentation file.

🔗 Related project:

🔗 Part of the Lyra Ecosystem

   -  Lyra_Leaf_SPAD_Calibration – SPAD sensor calibration for estimating chlorophyll density in leaves.
   -  TurbiditySensor_OpenScience – Optical-based estimation of aquatic turbidity and primary productivity using open-source sensors.
   -  Leaf_Chlorose_CNN_Training – CNN-based classification of chlorotic vs. healthy leaves from scanned images.
   -  Lyra_LowCost_Soil_Leaf – Integrated low-cost soil and leaf model for terrestrial primary productivity.

## 🔖 License
MIT License – open science, open ecology.

