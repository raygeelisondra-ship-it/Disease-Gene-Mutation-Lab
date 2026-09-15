# Bioinformatics Laboratory Report: LDLR Variant Analysis

## Metadata

* **Author Name:** Ray Gee Jurac Lisondra
* **Disease / Phenotype:** Familial Hypercholesterolemia (FH)
* **Gene:** *LDLR* (Low-density lipoprotein receptor)
* **Reference Transcript Accession:** `NM_000527.5`
* **Reference Protein Accession:** `NP_000518.1`
* **Documented Variant:** `c.1A>T` (`p.Met1Leu`)
* **ClinVar Accession:** `VCV000250968.23`
* **Galaxy History Name:** `Lisondra_Familial_hypercholesterolemia_Gene_Mutation_Lab`
* **Date of Analysis:** May 2026

---

## Project Overview

This repository contains bioinformatic workflows, sequence alignments, and comparative downstream functional analyses of mutations within the *LDLR* coding sequence (CDS). The project compares the wild-type reference sequence against the documented initiator codon variant (`c.1A>T`) and an artificial nonsense variant (`c.30G>A`) to evaluate their impact on translation initiation, open reading frame integrity, and receptor-mediated endocytosis in Familial Hypercholesterolemia.

## Disease and Normal Gene Function

### Normal LDLR Function
The Low-Density Lipoprotein Receptor (*LDLR*) gene encodes a cell-surface transmembrane glycoprotein expressed primarily on hepatocytes. Under normal physiological conditions, the LDLR protein binds circulating  low-density lipoprotein (LDL) particles and initiates receptor-mediated endocytosis. Internalized LDL complexes are routed to lysosomes for degradation—releasing free cholesterol into the cell—while the receptor recycles back to the plasma membrane. This pathway plays a critical role in maintaining systemic lipid homeostasis and preventing toxic elevations of circulating cholesterol.

### Molecular Basis of Familial Hypercholesterolemia (FH)
Familial Hypercholesterolemia (FH) linked to *LDLR* is an inherited metabolic disorder characterized by severe, lifelong elevation of plasma low-density lipoprotein cholesterol (LDL-C), which directly accelerates premature atherosclerotic cardiovascular disease (Chemello et al., 2021). Its major clinical hallmarks include marked hypercholesterolemia present from birth, early-onset coronary artery disease—frequently manifesting before age 50 in males and age 60 in females—and extracellular cholesterol deposition, such as tendon xanthomas (predominantly in the Achilles and digital extensor tendons), xanthelasma, and corneal arcus, typically occurring alongside a strong family history of premature cardiovascular events (Institute for Quality and Efficiency in Health Care, 2025; Roy et al., 2020). 

The genetic basis involves loss-of-function mutations in the *LDLR* gene located on chromosome 19p13.2, which disrupt receptor synthesis, transport, binding, or recycling, accounting for the vast majority of autosomal dominant FH cases. Inheritance follows an autosomal dominant pattern with a pronounced gene-dose effect: heterozygous individuals display moderately severe hypercholesterolemia, whereas homozygous or compound heterozygous individuals exhibit extreme serum LDL-C levels and severe, rapid-onset cardiovascular disease frequently appearing in early childhood.
