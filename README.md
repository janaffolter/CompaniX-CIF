# ***[CompaniX]™ : Inspired by life, for life.***

***Note:***  
*This Markdown version provides a structured and readable presentation of the CIF 3.0 documentation.
All official, complete, and authoritative details — including annexes, methodological notes, and formal definitions — are available in the PDF reference documents that accompany this dossier.*

- [CompaniX - Agronomic Validation Dossier](<./CompaniX - Agronomic Validation Dossier.pdf>)
- [CompaniX - Dossier de Validation Agronomique FR](<./CompaniX - Dossier de Validation Agronomique FR.pdf>)


---

# **Agronomic Validation Dossier**  
### **Validation of the JSON Structure Representing a Full Crop Cycle**

**Supported by Innosuisse**  
**Version: 3.2 — 2026‑04‑01**  
**Background IP: Jan Affolter ITS (CHE‑104.801.264), owner of the CompaniX project.**

---

# **Release Notes**

## Version: 3.2 — 2026‑04‑01
This release introduces a single but major structural enhancement:

- **Addition of the `pre_establishment` stage**, covering **all agronomic conditions and management actions occurring between harvest and sowing**.  
  This includes:
  - soil structural evolution  
  - soil preparation  
  - early weed control  
  - soil moisture and temperature dynamics  
  - spatial variability indicators  
  - any intervention affecting the next crop’s establishment  

No other structural changes were made to the CIF JSON schema.


---

# **Foreword**

Modern agriculture requires tools capable of describing agronomic reality with precision, without unnecessary complexity or interpretation. In a context where farming operations seek to understand performance gaps between seemingly similar plots, the ability to document **what the crop actually experienced** becomes essential.

The **CIF – Cycle Invariant File** meets this requirement. It is a **standardized JSON format** designed to capture the **agronomic invariants** of a crop cycle, organized by **physiological stages**. The CIF does not model, predict, or simulate: it observes, structures, and documents the cycle exactly as it unfolded.

Version 3.0 introduces several key agronomic blocks:

- detailed integration of soil nature via the `soil_analysis` block  
- synthetic varietal characteristics via `variety_traits`  
- growth indicators structured by stage via `growthmetrics`  
- summary blocks for yield and limiting factors via `yield_breakdown` and `yield_summary`

These additions strengthen the explanatory capacity of the CIF while remaining readable and directly exploitable by agronomists and institutions.

Detailed soil analyses (texture, pH, CEC, organic matter, macro- and micronutrients) are carried out by specialized laboratories and integrated into the CIF via the `soil_analysis` block, which provides a structured and agronomically exploitable representation. The raw datasets can remain in the laboratory systems, while CIF 3.0 retains the information necessary for multi-plot comparison and agronomic interpretation.

The CIF thus contains structured data designed to empower farmers, agronomists, and agricultural authorities in their choices and decisions, in order to optimize the yield of an agricultural area.

The purpose of the CIF is therefore primarily oriented towards reporting and decision‑making, rather than direct in‑field operations. However, the same sensors and field tools deployed to produce the CIF invariants can also be used for precision operations — precision irrigation and/or treatments, whether automated, drone‑based, or manual — for example by dividing a field into **20×20 m zones**.

Furthermore, as this data is available in real‑time, it allows the farmer or agronomist to go directly to the affected area to evaluate the actions to be taken. This significantly increases the efficiency of problem detection and treatment, while reducing the risk of missing it entirely if the inspection were to be done randomly or through simple sampling.

This document presents the complete structure of CIF 3.0 and requests a formal agronomic validation. It is addressed to cooperatives, technical institutes, agronomists, and advisors, and aims to establish a common methodological foundation for the objective analysis of crop performance.

---

# **Table of Contents**

1. Purpose of the Document  
2. Role and Scope of the CIF  
   - 2.1 What CIF 3.0 Captures  
   - 2.2 What the CIF Does Not Capture  
   - 2.3 Role of the CIF within the CompaniX System  
3. General Structure of the JSON  
   - 3.1 Physiological Stages  
   - 3.2 Soil Invariants  
   - 3.3 Climatic Invariants  
   - 3.4 Variability Invariants  
   - 3.5 Biotic Stress Invariants  
   - 3.6 Management Invariants  
   - 3.7 Completeness  
   - 3.8 Previous Crop  
   - 3.9 Irrigation  
4. Why the CIF Represents a Major Advancement  
5. Benefits of the CIF for Farmers  
6. Benefits of the CIF for Agronomists  
7. Benefits of the CIF for Agricultural Authorities  
8. The Foundation of the Vision  
9. The Vision  
10. Toward a Global Cognitive Protocol for Agricultural Standardization  
11. CompaniX Architecture  
12. JSON CIF File  
13. List of Acronyms Used  
14. Project Ownership  

---

# **1. Purpose of the Document**  

This document requests a **formal agronomic validation** of the JSON structure used in the **CIF – Cycle Invariant File**.

The objective is to confirm that the format is:

- scientifically sound  
- physiologically coherent  
- operationally relevant  
- and sufficient to explain yield differences between plots sharing:  
  - the same soil type  
  - the same climate  
  - the same cultivated variety  

Within this homogeneous context, the CIF must allow for the identification of the factors truly responsible for performance gaps: management decisions, abiotic and biotic stress, water dynamics, spatial variability, and physical or topographical constraints.

The CIF summarizes the crop cycle through **agronomic invariants** that reflect the **conditions actually experienced** by the crop, enriched by **growth indicators** (`growthmetrics`) and summary blocks for yield and stress.

This document is addressed to cooperatives, agronomists, applied research institutes, and agricultural advisors.

---

# **2. Role and Scope of the CIF**

The CIF (Cycle Invariant File) is the **documentary standard** used by CompaniX to describe, in a structured and comparable manner, the **agronomic conditions actually experienced** by a crop during a production cycle.

It is a **factual, neutral, and operational** file, designed to enable **comparative performance analysis** between plots, between years, and between environments.

The CIF does not model the crop: it documents the invariants, growth indicators, and yield summaries that directly influence the observed yield.

---

## **2.1 What the CIF Captures**

The CIF captures invariant and derived agronomic information that is:

- measurable  
- comparable  
- reproducible  
- directly linked to crop performance  

This information is organized:

- at the **cycle level** (plot identity, crop, variety, `variety_traits`, `soil_analysis`, yield summaries)  
- by **physiological stages**, including:  
  - `pre_establishment`  
  - `establishment`  
  - `vegetative`  
  - `flowering`  
  - `grain_filling`  
  - `maturation`  

The addition of the `pre_establishment` stage ensures that the CIF covers **all agronomic conditions and interventions occurring between harvest and sowing**, completing the causal chain of the crop cycle.


### **a. Cycle Metadata and Global Climate**

Includes:

- `cif_version`, `id_cycle`, `plot_id`, `crop`, `variety`, `year`  
- planting and harvest dates  
- `season_climate_summary` (rainfall, GDD, ET0)

### **b. `variety_traits` Block**

Synthetic varietal traits:

- earliness  
- drought tolerance  
- disease resistance  
- lodging resistance  

### **c. `soil_analysis` Block**

Structured laboratory soil analysis:

- texture  
- chemistry  
- macro- and micronutrients  

### **d. Physiological Stages — `stages[]`**

Each stage includes:

- period (`start_date`, `end_date`)  
- soil, climate, variability, microclimate invariants  
- `growthmetrics`  
- `management` interventions  
- pathology indices  

### **e. Yield Summary Blocks**

`yield_breakdown`, `yield_summary`, `yield`:

- potential yield  
- losses by limiting factors  
- actual yield and yield gap  
- primary limiting factor  
- harvest quality (moisture, protein, test weight, harvest index)

---

## **2.2 What the CIF Does Not Capture**

The CIF does **not** contain raw time series.  
It contains only **agronomically relevant invariants and aggregates**.

Laboratory analyses remain in lab systems; CIF stores only structured summaries.

This ensures:

- lightness and readability  
- consistency of comparisons  
- integrity of laboratory data  

---

## **2.3 Role of the CIF within the CompaniX System**

The CIF enables:

- rigorous comparison between crop cycles  
- identification of explanatory factors  
- linking interventions, conditions, and outcomes  
- building a coherent multi‑year history  

It is an **open standard**, easy to populate, robust to analyze, universally applicable.

---

# **3. General Structure of the JSON**

The JSON describes a crop cycle through:

- 5 physiological stages  
- soil, climate, variability, biotic stress, management invariants  
- normalized indices (0–1), min/max, amplitudes, CV  
- compact size (7–8 kB)

---

## **3.1 Physiological Stages**

- Establishment  
- Vegetative  
- Flowering  
- Grain filling  
- Maturation  

→ Physiologically coherent and suited for signal aggregation.

---

## **3.2 Soil Invariants**

Includes:

- minimum moisture/amplitude  
- minimum temperature/amplitude  
- EC variability  
- compaction  
- microtopography  

→ Determinants of rooting, water availability, nutrition, resilience, heterogeneity.

---

## **3.3 Climatic Invariants**

Includes:

- min/max temperatures  
- humidity  
- VPD  
- heat days  
- frost days  

→ Essential climatic variables, without redundancy.

---

## **3.4 Variability Invariants**

Includes:

- moisture CV  
- temperature CV  
- EC CV  
- uniformity indices  

→ Accurate representation of spatial variability.

---

## **3.5 Biotic Stress Invariants**

Includes:

- disease pressure  
- disease damage  
- lodging  
- weed pressure  

---

## **3.6 Management Invariants**

Each intervention includes:

- product  
- date  
- dose  
- active substance  
- mode of action  
- formulation  
- concentration  
- timing index  
- intensity index  
- treatment goal  

→ Precise, explanatory, faithful to agronomic reality.

---

## **3.7 Completeness**

Covers all five families of yield determinants:

- Soil  
- Climate  
- Variability  
- Biotic stresses  
- Management  

---

## **3.8 Previous Crop**

Represented by the **CIF N‑1**, capturing:

- water dynamics  
- compaction  
- residual fertility  
- diseases  
- weeds  
- variability  
- stress  
- establishment quality  

---

## **3.9 Irrigation**

Irrigation is not a yes/no field.  
Actual water conditions are measured via:

- functional soil data  
- climatic balance (ET0, rainfall)  

If applied, irrigation appears as a **management intervention** with dose in mm.

---

# **4. Why the CIF Represents a Major Advancement**

The CIF transforms agricultural traceability into:

- enriched data  
- structured agronomic analysis  
- reproducible multi‑plot comparison  
- official reporting  
- strategic management  

With `soil_analysis`, `variety_traits`, `growthmetrics`, and `yield_*`, CIF 3.0 provides a structured reading of yield‑limiting factors.

---

# **5. Benefits of the CIF for Farmers**

- Single point of entry for traceability  
- Automatic generation of official reports  
- Clear understanding of yield influences  
- Objective comparison between plots  
- Valuable traceability for audits and certifications  
- Zero additional work  

---

# **6. Benefits of the CIF for Agronomists**

- Structured agronomic reading by physiological stages  
- Faster, more objective diagnostics  
- Rigorous comparison between plots and seasons  
- Better recommendations  
- Time savings  
- Support for precision agriculture  
- Direct view of limiting factors via yield blocks  

---

# **7. Benefits of the CIF for Agricultural Authorities**

- Standardized, neutral, verifiable format  
- Single point of entry for traceability  
- Automatic regulatory reports  
- Harmonized and comparable format  
- Enriched and verifiable traceability  
- Physiological vision of the cycle  
- Compatibility with public policies  

---

# **8. The Foundation of the Vision**

The CIF is the field‑level building block of a broader cognitive infrastructure.  
It enables a **Global Agricultural Standardization Protocol** built on sovereignty and collective learning.

---

# **9. The Vision**

A system where:

- every decision enriches collective intelligence  
- farms progress together  
- data becomes living knowledge  
- agriculture aligns with nutritional and health needs  

CompaniX is a project that reinforces existing systems and supports societal stability.

---

# **10. Toward a Global Cognitive Protocol for Agricultural Standardization**

CompaniX orchestrates:

- distributed technologies  
- evolving ontologies  
- sovereign knowledge graphs  
- antifragile cognitive learning  
- frugal cycle capture  
- IoT, robots, drones  

This creates a **shared language** between farms, regions, institutions.

The protocol becomes **self‑reinforcing** as the network grows.

CompaniX is a **cognitive infrastructure**, not a platform.

---

# **11. CompaniX Architecture**

```
================================================================================================
                         COMPANIX ARCHITECTURE: STRICT ROLE SEPARATION
================================================================================================

      [ ON-FARM / LOCAL ENVIRONMENT ]                         [ REMOTE / NATIONAL OR GLOBAL ]
 
   +------------------------------------+                 +------------------------------------+
   |             EDGE NODE              |                 |          COGNITIVE CORE            |
   |------------------------------------|                 |------------------------------------|
   |                                    |                 |                                    |
   |  [Sensors & IoT Devices]           |                 |  [Data Ingestion Pipeline]         |
   |        | (Raw Data)                |                 |        |                           |
   |        v                           |                 |        v                           |
   |  (Data Aggregation)                |    Transmits    |  (Ontologies & Vectorization)      |
   |        |                           |     CIF 3.0     |        |                           |
   |        +--> Real-Time Management   | ===============>|        +--> Cross-Learning         |
   |        +--> Precision Operations   |  (Standardized  |        +--> Yield Optimization     |
   |        +--> Instant Alerts         |   JSON File)    |        +--> Best Practices ID      |
   |        |                           |                 |        +--> Official Reporting     |
   |        v                           |                 |                                    |
   |  [CIF Generation Engine]           |                 |                                    |
   |                                    |                 |                                    |
   +------------------------------------+                 +------------------------------------+
         ^                            ^                                 |                  |
         |                            |      Collective Knowledge,      |                  |
         |                            |    Insights & Formal Reports    |                  |
         |                            +---------------+-----------------+                  |
         |                                            |                                    |
         v                                            v                                    v
+-----------------------+               +---------------------------+              +-----------------------+
|      THE FARMER       |               | AGRICULTURAL AUTHORITIES  |              |    THE AGRONOMISTS    |
|  (Local Execution &   |               |  (Regulatory Compliance   |              | (Strategic Insights & |
|   Automated Reports)  |               |   & Regional Monitoring)  |              |  Yield Optimization)  |
+-----------------------+               +---------------------------+              +-----------------------+
```
---

## License

This project is licensed under the **Apache License 2.0** – an open, permissive license that allows anyone (including commercial entities) to copy, modify, and redistribute the Cycle Invariant File (CIF) and related tools, as long as they keep the original attribution and do not misuse our brand.

This reflects our strategy to make **CIF a fully open standard** for precision agriculture, interoperable across farms, drones, OADs, and agronomic software.

---

## Project Ownership

Supported by: Innosuisse  
Owner & Founder: Jan Affolter — [jan.affolter@gmail.com](mailto:jan.affolter@gmail.com)  
Intellectual Property Holder: Jan Affolter ITS (CHE‑104.801.264)  
Location: Lausanne, Switzerland  
