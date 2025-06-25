
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

## 📁 Repository Structure

Lyra_DO_Green_Mesurim/
├── TLC_analysis_protocol/ # 🌿 Documentation of chlorophyll pigment extraction and TLC experiment
│ ├── Acetone_Eppendorf_leaf.JPG # Acetone injected into Eppendorf tube for pigment extraction
│ ├── Chlorophyll_homeMade_spectroscope.JPG # Raw chlorophyll spectrum observed with homemade spectroscope and magnifier lens
│ ├── Chlorophyll_shines_red_UV.JPG # Chlorophyll fluorescence under UV light
│ ├── HomeMade_spectroscope.JPG # General view of the homemade spectroscope
│ ├── Lab_footage_1.JPG / Lab_footage_2.JPG # Photos of the home lab setup (from 2008)
│ ├── Potter_extraction_wooden_support.JPG # Wooden support used for pigment extraction with a Potter grinder (centrifuge visible)
│ ├── Sample_weighing.JPG # Sample weighing using a cage-type precision balance
│ ├── TLC_pigments_UV.JPG # Pigments after TLC migration, under UV light
│ ├── TLC_pigments_UV_2.JPG # Two TLC plates with UV fluorescence; concentrations marked (2–4–6–8)
│ └── TLC_pigments_UV_3.JPG # Juxtaposed TLC strips (5) showing upward pigment migration from deposit line
│
├── pictures/ # 🍃 Leaf chlorosis study and digital extraction process
│ ├── Planche_initiale_réduite.jpg # 15 ivy (Hedera helix) leaves with various degrees of chlorosis.
│ # Each leaf is annotated with its SPAD value (proxy for chlorophyll content).
│ # A 20 mm reference line is placed near each leaf for calibration.
│ # The setup uses a string grid to facilitate later digital slicing.
│ ├── miniwebtool.png # Screenshot of the slicing interface; lines follow the physical grid
│ └── regressions.png # Scatter plot regression results (Mean = optical green density from scanner)
│
├── Results/ # 📊 Final computed data from image and SPAD analysis
│ └── Results_completed.xls # Measurement table:
│ # - Mean: Optical green density (scanner)
│ # - S_chlorose: chlorosed surface (pixels)
│ # - S_totale: total surface per leaf (pixels)
│ # - SPAD: measured SPAD average per leaf
│
└── README.md # 📄 This file – method description and structure

🔗 Related project:

🔗 Part of the Lyra Ecosystem
- [Lyra_Leaf_SPAD_Calibration](https://github.com/Jerome-openclassroom/Lyra_Leaf_SPAD_Calibration) – SPAD sensor calibration for estimating chlorophyll density in leaves.
- [Lyra_LowCost_Soil_Leaf](https://github.com/Jerome-openclassroom/Lyra_LowCost_Soil_Leaf) – Integrated low-cost soil and leaf model for terrestrial primary productivity.
- [Leaf_Chlorose_CNN_Training](https://github.com/Jerome-openclassroom/Leaf_Chlorose_CNN_Training) – CNN-based classification of chlorotic vs. healthy leaves from scanned images.
- [TurbiditySensor_OpenScience](https://github.com/Jerome-openclassroom/TurbiditySensor_OpenScience) - A low-cost optical turbidity sensor calibrated in JTU, illustrating an open science approach for accessible, field-based water quality monitoring.
- [AI_Assisted_Lake_Ecology](https://github.com/Jerome-openclassroom/AI_Assisted_Lake_Ecology) – A full-scale NPP model combining field measurements, physical modeling, and GPT-4o-assisted ecological interpretation. Includes empirical correction for realistic annual productivity in clear lakes.
- [LimonTree_NPP_Model](https://github.com/Jerome-openclassroom/LimonTree_NPP_Model) — Low-cost water and NPP model for a potted lemon tree.
- [Mountain_Bocage_Soil_Analysis](https://github.com/Jerome-openclassroom/Mountain_Bocage_Soil_Analysis) — Complete soil dataset for a mid-mountain bocage site (Haute-Loire, France): texture, CEC, pH, nitrates, structural stability, and Berlèse funnel microfauna extraction. Ready for AI-assisted ecological modeling.
- [Lyra_Sentinel_MODIS_Site_HauteLoire](https://github.com/Jerome-openclassroom/Lyra_Sentinel_MODIS_Site_HauteLoire) — Combined Sentinel-2 NDVI and MODIS LST for a semi-natural site in Haute-Loire (France): ROI clipping, clean map, and reproducible notebook. Ready for AI-assisted ecological modeling.
- [Eco_Profile_Saint_Julien_1060](https://github.com/Jerome-openclassroom/eco-profile-saint-julien-1060) — 1-ha eco-climatological site (1060 m, Massif Central) with 2017–2018 records and multi-disciplinary field data.
- For field-based plant identification and LLM-assisted inference of ecological co-occurrence:  
[**Lyra_Botanical_Protocol**](https://github.com/Jerome-openclassroom/lyra-botanical-protocol) —  
*Protocol for probabilistic GPT-based species identification from photos and context (southern France, spring flora).*



## 🔖 License
MIT License – open science, open ecology.

