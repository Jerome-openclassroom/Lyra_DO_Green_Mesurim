
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

*************************

🧪 Historical expertise: pigment extraction and chromatography
Between 2008 and 2015, I developed and conducted a full protocol for identifying 7–9 photosynthetic and accessory pigments (chlorophyll a, b, carotenoids, xanthophylls, anthocyanins) using TLC (Thin Layer Chromatography) and solvent-based extraction (e.g. cyclohexane, petroleum ether).

The protocol required careful handling:

Extraction with Ultra-Turrax or Potter-Elvehjem in Eppendorf tubes (1 mL solvent),

Ventilated environment or fume hood,

Mandatory protective mask (solvents are volatile and flammable),

Spectacular visual readouts, especially under UV light (chlorophyll fluorescence appears deep red).

Although fully operational, this protocol is chemically sensitive, and not adapted to field-based or educational contexts.
Today, I promote a low-tech, AI-assisted alternative: combining SPAD sensors, RGB scans, and image-based greenness indices as robust proxies for pigment quantification — safer, reproducible, and aligned with citizen science goals.

*************************

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
- [Lyra_Leaf_SPAD_Calibration](https://github.com/Jerome-openclassroom/Lyra_Leaf_SPAD_Calibration) – SPAD sensor calibration for estimating chlorophyll density in leaves.
- [Lyra_LowCost_Soil_Leaf](https://github.com/Jerome-openclassroom/Lyra_LowCost_Soil_Leaf) – Integrated low-cost soil and leaf model for terrestrial primary productivity.
- [Leaf_Chlorose_CNN_Training](https://github.com/Jerome-openclassroom/Leaf_Chlorose_CNN_Training) – CNN-based classification of chlorotic vs. healthy leaves from scanned images.
- [TurbiditySensor_OpenScience](https://github.com/Jerome-openclassroom/TurbiditySensor_OpenScience/blob/main/README.md) - A low-cost optical turbidity sensor calibrated in JTU, illustrating an open science approach for accessible, field-based water quality monitoring.

## 🔖 License
MIT License – open science, open ecology.

