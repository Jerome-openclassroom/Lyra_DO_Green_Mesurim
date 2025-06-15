
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

🟥 Red line: Linear regression fit  
**Equation**: SPAD = 0.178 × Mean − 36.454


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

💡 I am fully aware of the limitations of low-cost protocols. The methods presented here (e.g., SPAD calibration via DO_green and image-based measurements) do not claim to replace laboratory-grade spectroscopy, HPLC, or chromatographic quantification used in research institutes such as INRAE. However, they are scientifically grounded, field-validated, and sufficient for many ecological or agronomic diagnostics.

Their main strength lies in accessibility, replicability, and ethical compatibility with citizen science and AGI-era decentralization. I propose these tools not out of ignorance, but out of conscious design — knowing exactly what they offer, and what they do not.


*************************

## 🧪 Historical expertise: 

Pigment extraction and chromatography

Between 2007 and 2008, I developed a full protocol for identifying and dosing 7–9 photosynthetic and accessory pigments (chlorophyll a, b, carotenoids, xanthophylls, anthocyanins) using TLC (Thin Layer Chromatography) and solvent-based extraction (acetone).

The protocol required careful handling:

Extraction with Ultra-Turrax or Potter-Elvehjem in Eppendorf tubes (1 mL solvent),

Ventilated environment or fume hood,

Mandatory protective mask (solvents are volatile and flammable),

Spectacular visual readouts, especially under UV light (chlorophyll fluorescence appears deep red).

Although fully operational, this protocol is chemically sensitive, and not adapted to field-based or educational contexts.
Today, I promote a low-tech, AI-assisted alternative: combining SPAD sensors, RGB scans, and image-based greenness indices as robust proxies for pigment quantification — safer, reproducible, and aligned with citizen science goals.

*************************
> 🧭 *Although this protocol is no longer used in my current workflow, it remains an important part of my training. I now promote image-based, safer, and low-cost alternatives — but grounded in real pigment chemistry and TLC experience.*


## 🔬 TLC Analysis Protocol – Historical Laboratory Skills (2007 - 2008)


This section illustrates a full pigment extraction and separation protocol performed in a non-institutional but scientifically rigorous setting.  
Each step is documented by original photographs and reflects experimental autonomy, practical chemistry skills, and precision lab engineering.

---

### ⚖️ Sample preparation and pigment extraction

🔗 [Sample_weighing.jpg](TLC_analysis_protocol/Sample_weighing.JPG)  
*Sample weighing on an analytical balance (±0.0001 g). Precision dry matter measurement for downstream chlorophyll quantification.*

🔗 [Acetone_Eppendorf_leaf.jpg](TLC_analysis_protocol/Acetone_Eppendorf_leaf.JPG)  
*Injection of cold acetone into an Eppendorf tube containing a leaf sample. First step of pigment extraction prior to homogenization.*

🔗 [Potter_extraction_wooden_support.jpg](TLC_analysis_protocol/Potter_extraction_wooden_support.JPG)  
*Custom-built wooden support to hold the tube during micro-homogenization with Potter-Elvehjem. Ensures verticality and safety during extraction.*

---

### 🌈 Pigment migration and UV fluorescence (TLC)

🔗 [TLC_pigments_UV.jpg](TLC_analysis_protocol/TLC_pigments_UV.JPG)  
*TLC plate photographed under UV light. Shows distinct chlorophyll and carotenoid spots post-migration.*

🔗 [TLC_pigments_UV_2.jpg](TLC_analysis_protocol/TLC_pigments_UV_2.JPG)  
*TLC plate under 254 nm inhibitory UV. Fluorescent pigment zones marked and analyzed for identification.*

🔗 [TLC_pigments_UV_3.jpg](TLC_analysis_protocol/TLC_pigments_UV_3.JPG)  
*Alternate view of pigment bands on the TLC plate under UV. Clear signal, confirming spot purity and separation quality.*

🔗 [Chlorophyll_shines_red_UV.jpg](TLC_analysis_protocol/Chlorophyll_shines_red_UV.JPG)  
*Characteristic deep red fluorescence of chlorophyll under UV illumination. This emission confirms the presence of intact chlorophyll molecules and their excitation efficiency.*

💡 The elution solvent used for pigment separation consisted of 6 parts petroleum ether, 4 parts acetone, and 1 part cyclohexane. This mixture provided optimal migration and resolution of major chlorophyll and carotenoid bands.

💡 The developed TLC plates were scanned using a flatbed scanner. ImageJ was then used to generate a chromatogram by plotting signal intensity along the migration axis. The relative concentration of each pigment was estimated from the area under the curve (AUC), which follows a linear relationship with pigment quantity.

---

### 🔎 Spectroscopy and optical verification

🔗 [Chlorophyll_homeMade_spectroscope.jpg](TLC_analysis_protocol/Chlorophyll_homeMade_spectroscope.JPG)  
*Absorbance of extracted chlorophyll observed through a homemade diffraction-based spectroscope.*

🔗 [HomeMade_spectroscope.jpg](TLC_analysis_protocol/HomeMade_spectroscope.JPG)  
*Full view of the custom-built spectroscope, using PVC tubing, adjustable slit, diffraction grating, and observation lens.*

---

### 🧪 Laboratory infrastructure

🔗 [Lab_footage_1.jpg](TLC_analysis_protocol/Lab_footage_1.JPG)  
*Chemical analysis zone: centrifuge, volumetric glassware, solvents, and glass bench setup.*

🔗 [Lab_footage_2.jpg](TLC_analysis_protocol/Lab_footage_2.JPG)  
*Informatics station: scanner, computer, and data processing zone integrated into the experimental workflow.*

---


*************************

## 🧠 Suggested Use for the DO_green flatbed scanner protocol

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
- [TurbiditySensor_OpenScience](https://github.com/Jerome-openclassroom/TurbiditySensor_OpenScience) - A low-cost optical turbidity sensor calibrated in JTU, illustrating an open science approach for accessible, field-based water quality monitoring.
- [AI_Assisted_Lake_Ecology](https://github.com/Jerome-openclassroom/AI_Assisted_Lake_Ecology) – A full-scale NPP model combining field measurements, physical modeling, and GPT-4o-assisted ecological interpretation. Includes empirical correction for realistic annual productivity in clear lakes.
- [LimonTree_NPP_Model](https://github.com/Jerome-openclassroom/LimonTree_NPP_Model) — Low-cost water and NPP model for a potted lemon tree.

## 🔖 License
MIT License – open science, open ecology.

