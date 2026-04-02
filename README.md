# ***[CompaniX]™ : Inspired by life, for life.***


- [CompaniX - Presentation of the CIF - Cycle Invariant File](<./CompaniX - Presentation of the CIF - Cycle Invariant File.pdf>)
- [CompaniX - CIF JSON File](<./cif.json>)

# **CIF – Cycle Invariant File**  
### **Shared Agronomic Framework for Crop Cycle Analysis**

**Supported by Innosuisse**  
**Version: 3.2 — 2026‑04‑01**  

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


# Introduction

The **Cycle Invariant File (CIF)** is an open, structured, and physiologically coherent framework for documenting the agronomic conditions experienced by a crop during its production cycle.  
It provides a **shared agronomic language** that enables farmers, cooperatives, advisors, researchers, and digital agriculture systems to describe crop cycles in a **comparable, reproducible, and operationally meaningful** way.

Unlike traditional traceability formats, the CIF organizes information across **six physiological and operational stages** — from pre‑establishment to maturation — and captures the key invariants that explain yield differences between plots exposed to the same soil, climate, and variety.  
It integrates soil analysis, climate aggregates, spatial variability, management interventions, growth indicators, stress indices, and yield breakdowns into a compact, machine‑readable JSON structure.

The CIF is designed to be:

- **neutral and interoperable** — usable by any platform, robot, sensor, or agronomic system  
- **lightweight and practical** — typically 7–8 kB per cycle  
- **scientifically grounded** — aligned with crop physiology and agronomic reasoning  
- **operational** — directly usable for diagnostics, comparisons, and reporting  
- **open and collaborative** — welcoming agronomic feedback to strengthen its scientific consistency  

This repository provides:

- the **CIF specification**  
- an example of a CIF file  
- documentation of each block and invariant  
- guidance for adoption and integration  

The goal is to establish a **shared agronomic framework** that supports objective crop‑cycle analysis, multi‑plot comparison, and the development of next‑generation digital agriculture systems.

## License

This project is licensed under the **Apache License 2.0** – an open, permissive license that allows anyone (including commercial entities) to copy, modify, and redistribute the Cycle Invariant File (CIF) and related tools, as long as they keep the original attribution and do not misuse our brand.

This reflects our strategy to make **CIF a fully open standard** for precision agriculture, interoperable across farms, drones, OADs, and agronomic software.

## Project Ownership

Owner & Founder: **Jan Affolter — [jan.affolter@gmail.com](mailto:jan.affolter@gmail.com)** 

Background IP: **Jan Affolter ITS (CHE‑104.801.264), owner of the CompaniX project.**

Location: **Lausanne, Switzerland**  
