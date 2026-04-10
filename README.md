# ***[CompaniX]™ : Inspired by life, for life.***


- [CompaniX - Presentation of the CIF - Cycle Invariant File](<./CompaniX - Presentation of the CIF - Cycle Invariant File.pdf>)
- [CompaniX - CIF JSON File](<./cif.json>)

# **CIF – Cycle Invariant File**  
### **Shared Agronomic Framework for Crop Cycle Analysis**

**Supported by Innosuisse**  
**Version: 4.0 — 2026‑04‑10**  

# **Release Notes**  
## Version: 4.0 — 2026‑04‑10

This release introduces a major structural extension of the CIF:  
the addition of **plant nutritional and systemic invariants**, enabling the CIF to serve as a unified reference for both **human food** and **livestock feed** applications.

**Addition of new top‑level block `plant_invariants`.**

### **Purpose of this addition**

The new block provides a **standardized nutritional signature** for each crop cycle, enabling:

- integration of CIF data into **human nutrition**, **food processing**, and **quality evaluation**  
- integration into **livestock formulation** and feed optimization  
- cross‑sector nutritional comparison of plant materials  
- quantification of systemic performance (sovereignty, circularity, resource pressure)  
- interoperability with downstream nutritional systems (food, feed, processing)  
- traceability and integrity anchoring on blockchain systems  

### **Scope of change**

- No existing blocks were modified.  
- No fields were deprecated.  
- The CIF remains lightweight and fully backward compatible.  
- Version increment reflects the introduction of a new functional domain:  
  **plant nutritional and systemic characterization for food and feed applications**.


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

The Cycle Invariant File (CIF) is an open, structured, and physiologically coherent framework for documenting the agronomic, nutritional, and systemic conditions experienced by a crop during its production cycle.

The CIF provides a unified language that enables farmers, cooperatives, advisors, researchers, food processors, feed formulators, and digital agriculture systems to describe crop cycles in a comparable, reproducible, and operationally meaningful way.  
It organizes information across six physiological and operational stages — from pre‑establishment to maturation — and consolidates the key invariants that explain differences in yield, quality, and nutritional value between plots exposed to the same soil, climate, and variety.

Beyond agronomic description, the CIF integrates **plant nutritional invariants** (measured and derived) and **systemic performance indicators**, enabling its use across both **human nutrition** and **livestock feeding**.  
This includes NIR‑based composition, digestibility, energy, amino acid patterns, and indicators of sovereignty, circularity, and resource pressure.

The CIF is designed to be:

- **neutral and interoperable** — usable by any agronomic, food, feed, or digital system  
- **lightweight and practical** — typically under 10 kB per crop cycle  
- **scientifically grounded** — aligned with crop physiology, soil science, and nutritional science  
- **operational** — directly usable for diagnostics, comparison, formulation, and reporting  
- **open and collaborative** — designed to evolve with contributions from agronomy, nutrition, and systems science  

This repository provides the CIF specification, examples, documentation of each invariant, and guidance for adoption and integration across agronomy, food systems, livestock nutrition, and circularity‑oriented infrastructures.

## License

This project is licensed under the **Apache License 2.0** – an open, permissive license that allows anyone (including commercial entities) to copy, modify, and redistribute the Cycle Invariant File (CIF) and related tools, as long as they keep the original attribution and do not misuse our brand.

This reflects our strategy to make **CIF a fully open standard** for precision agriculture, interoperable across farms, drones, OADs, and agronomic software.

## Project Ownership

Owner & Founder: **Jan Affolter — [jan.affolter@gmail.com](mailto:jan.affolter@gmail.com)** 

Background IP: **Jan Affolter ITS (CHE‑104.801.264), owner of the CompaniX project.**

Location: **Lausanne, Switzerland**  



