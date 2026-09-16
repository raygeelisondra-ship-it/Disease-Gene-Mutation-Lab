# From Gene Mutation to Disease: Investigating How DNA Sequence Changes Affect Protein Products and Human Phenotypes

## Disease Background
Familial Hypercholesterolemia (FH) linked to *LDLR* is an inherited metabolic disorder characterized by severe, lifelong elevation of plasma low-density lipoprotein cholesterol (LDL-C), which directly accelerates premature atherosclerotic cardiovascular disease (Chemello et al., 2021). Its major clinical hallmarks include marked hypercholesterolemia present from birth, early-onset coronary artery disease—frequently manifesting before age 50 in males and age 60 in females—and extracellular cholesterol deposition, such as tendon xanthomas (predominantly in the Achilles and digital extensor tendons), xanthelasma, and corneal arcus, typically occurring alongside a strong family history of premature cardiovascular events (Institute for Quality and Efficiency in Health Care, 2025; Roy et al., 2020). 

The underlying genetic etiology involves loss-of-function mutations in the *LDLR* gene located on chromosome 19p13.2, which disrupt receptor synthesis, transport, binding, or recycling, accounting for the vast majority of autosomal dominant FH cases. Inheritance follows an autosomal dominant pattern with a pronounced gene-dose effect: heterozygous individuals display moderately severe hypercholesterolemia, whereas homozygous or compound heterozygous individuals exhibit extreme serum LDL-C levels and severe, rapid-onset cardiovascular disease frequently appearing in early childhood.

---

## Gene and Normal Protein Function
The official gene symbol is *LDLR*, encoding the Low-Density Lipoprotein Receptor, located on human chromosome 19 at band 19p13.2. The gene encodes a cell-surface transmembrane glycoprotein expressed primarily on hepatocytes and other metabolically active cells. Under normal physiological conditions, the LDLR protein binds circulating low-density lipoprotein (LDL) particles—the major cholesterol carrier in human plasma—and mediates their cellular uptake via receptor-mediated endocytosis. 

Following endocytosis, LDLR complexes route to acidic endosomes, where low pH triggers ligand dissociation. The receptor recycles back to the plasma membrane to undergo hundreds of endocytic cycles, while the LDL particle is delivered to lysosomes for enzymatic breakdown, releasing free cholesterol to regulate cellular lipid synthesis and systemic cholesterol homeostasis.

---

## Documented Mutation

| Parameter | Information |
| :--- | :--- |
| **Gene** | *LDLR* (Low-density lipoprotein receptor) |
| **Reference Transcript Accession** | `NM_000527.5` |
| **Reference Protein Accession** | `NP_000518.1` |
| **Exact Variant Notation** | `c.1A>T` |
| **Nucleotide Change** | Adenine to Thymine substitution at position 1 |
| **Predicted Protein Change** | `p.Met1Leu` |
| **Mutation Type** | Initiator codon variant / Start codon disruption |
| **ClinVar Accession** | `VCV000250968.23` |
| **Clinical Interpretation** | Pathogenic |
| **Primary Literature Reference** | Graça et al. (2021) [PMID: 34572405] |

---

## Hypothesis
It is hypothesized that the single-nucleotide substitution `c.1A>T` in the *LDLR* coding sequence disrupts the primary translation initiation codon (`ATG` $\rightarrow$ `TTG`). While computational in-silico translation will output an intact 860-amino-acid polypeptide with a single point substitution (`p.Met1Leu`), biological translation in-vivo will fail completely due to the absence of a canonical start codon. This failure of ribosomal assembly causes a complete loss of full-length LDLR protein synthesis, producing a null allele phenotype that impairs hepatic LDL endocytosis and drives severe Familial Hypercholesterolemia.

---

## Methods
1. **Sequence Retrieval:** The human *LDLR* wild-type reference coding sequence (`NM_000527.5`) and reference protein sequence (`NP_000518.1`) were retrieved from the NCBI Nucleotide and Protein databases.
2. **Control Translation:** The wild-type CDS was processed using the EMBOSS Transeq computational translation tool (Reading Frame 1) to verify baseline protein length, start/stop codons, and N-/C-terminal amino acid identities.
3. **In-Silico Mutation Engineering:** The documented variant `c.1A>T` was manually introduced into position 1 of the wild-type CDS file (`ATG` $\rightarrow$ `TTG`). An artificial nonsense variant (`c.30G>A`) was engineered in parallel at position 30 (`TGG` $\rightarrow$ `TGA`).
4. **Computational Translation & Alignment:** Both mutant CDS files were translated using EMBOSS Transeq (Frame 1). Pairwise sequence alignments were generated using alignment algorithms to assess reading frame maintenance, length alterations, and amino acid substitutions.
5. **Workflow Management:** Data processing, history tracking, and reproducibility were executed within Galaxy (`Lisondra_Familial_hypercholesterolemia_Gene_Mutation_Lab`) and version-controlled on GitHub.

---

## Results

### Wild-Type Control Parameters

| Parameter | Predicted Protein (Transeq) | Reference Protein (`NP_000518.1`) |
| :--- | :--- | :--- |
| **CDS Length** | 2583 bp | 2583 bp |
| **Protein Length** | 860 aa | 860 aa |
| **Start Codon** | ATG (Position 1–3) | ATG (Position 1–3) |
| **Stop Codon** | TGA (Position 2581–2583) | TGA (Position 2581–2583) |
| **Reading Frame** | Frame 1 | Frame 1 |
| **First 10 Amino Acids** | `MGPWGWKLRW` | `MGPWGWKLRW` |
| **Last 10 Amino Acids** | `QMVSLEDDVA` | `QMVSLEDDVA` |

---

## WT versus Mutant Protein Comparison

Sequence comparison between the wild-type and `c.1A>T` mutant protein products reveals that the two sequences first differ at amino acid position 1, where methionine (M) is replaced by leucine (L). In computational translation (Frame 1), only this single amino acid is altered; downstream amino acids from position 2 to 860 remain 100% identical to the wild-type reference sequence. 

No amino acid insertions, deletions, or premature stop codons were produced within the open reading frame. Because the single-base substitution does not shift the triplet reading frame, the computational protein length remains 860 amino acids. While in-silico tools classify this as an initiator codon variant / missense change (`p.Met1Leu`), its biological impact is a failure of translation initiation.

---

## Artificial Mutation Experiment

| Parameter | Wild-Type Reference | Documented Mutation (`c.1A>T`) | Artificial Mutation (`c.30G>A`) |
| :--- | :--- | :--- | :--- |
| **CDS Length** | 2583 bp | 2583 bp | 2583 bp |
| **Protein Length** | 860 amino acids | 860 aa (in-silico); 0 aa (in-vivo) | 9 amino acids |
| **Mutation Type** | Wild-type (None) | Single nucleotide substitution (`c.1A>T`); Start codon variant | Single nucleotide substitution (`c.30G>A`); Nonsense mutation (`p.Trp10*`) |
| **Reading Frame Shift** | No | No (Intact) | No (Intact) |
| **Premature Stop Codon** | No | No | Yes (Codon 10: `TGA`) |
| **Amino Acids Affected** | 0 | 1 aa (in-silico); 860 aa untranslated (in-vivo) | 851 aa truncated |
| **Expected Functional Consequence** | Normal receptor expression & LDL clearance | Complete loss of translation initiation; Class 1 null allele driving FH | Severe N-terminal truncation; mRNA degraded via NMD |

---

## Molecular Interpretation: Gene $\rightarrow$ Mutation $\rightarrow$ Protein $\rightarrow$ Cellular Effect $\rightarrow$ Phenotype

```text
[LDLR Gene (19p13.2)] 
       │
       ▼
[c.1A>T Substitution] 
       │
       ▼
[Disrupted Start Codon (ATG -> TTG)] 
       │
       ▼
[Loss of Biological Translation Initiation (0 aa Produced)] 
       │
       ▼
[Absence of Functional Cell-Surface LDL Receptors on Hepatocytes] 
       │
       ▼
[Impaired Receptor-Mediated Endocytosis & Severe Systemic LDL Accumulation] 
       │
       ▼
[Premature Atherosclerosis, Tendon Xanthomas & Familial Hypercholesterolemia]

## Limitations
1. **Computational Analysis Constraints:** Standard translation utilities (such as Transeq tool) lack biological regulatory context; they assume translation proceeds mechanically regardless of whether an initiation codon is valid (e.g., in the documented mutation wherein tere no stop codon the tool assumes translation downstream).
2. **Unpredictable Alternative Start Sites:** Computer translation tools cannot predict if living cells might skip the broken start codon and use a later `ATG` site instead, which could potentially make a shorter, partially working receptor.
3. **Lack of Lab Test Validation:** Computer translation only predicts the amino acid sequence; it cannot prove whether the protein actually folds correctly, reaches the cell membrane, stays stable, or binds LDL without real lab experiments (like Western blots or cellular assays).
---

## Conclusion

This bioinformatic investigation demonstrates how single-nucleotide changes affects protein translation and cellular function. Although computational tools translate the `c.1A>T` mutation as a single amino acid substitution (`p.Met1Leu`), the loss of the  `ATG` start codon significantly prevents the initiation of biological translation in living cells. Without translation initiation, hepatocytes fail to produce the full-length LDLR polypeptide or its required signal sequence, resulting in a total absence of functional cell-surface receptors. This complete loss of receptor-mediated LDL endocytosis impairs systemic lipid clearance and directly drives severe Familial Hypercholesterolemia. In contrast, the artificial nonsense mutation (`c.30G>A`) truncates translation at codon 10 (`p.Trp10*`), producing an inactive 9-amino-acid peptide subject to nonsense-mediated mRNA decay. Together, these findings demonstrate that whether translation is completely blocked at initiation or prematurely terminated during elongation, both mechanisms converge on a severe loss of protein function.
---

## References

Chemello, K., García-Nafría, J., Gallo, A., Martín, C., Lambert, G., & Blom, D. (2021). Lipoprotein metabolism in familial hypercholesterolemia. *Journal of Lipid Research*, *62*, 100062. https://doi.org/10.1016/j.jlr.2021.100062

Graça, R., Fernandes, R., Alves, A. C., Menezes, J., Romão, L., & Bourbon, M. (2021). Characterization of two variants at Met 1 of the human LDLR gene encoding the same amino acid but causing different functional phenotypes. *Biomedicines*, *9*(9), 1219. https://doi.org/10.3390/biomedicines9091219

Institute for Quality and Efficiency in Health Care. (2025, September 24). *High cholesterol: Learn More – Familial hypercholesterolemia (FH)*. InformedHealth.org; NCBI Bookshelf. https://www.ncbi.nlm.nih.gov/books/NBK618446/

Roy, A., Kamalanathan, S., Naik, D., & Sahoo, J. P. (2020). Extensive tendon and tuberous xanthomas in a patient with familial hypercholesterolaemia. *BMJ Case Reports*, *13*(9), Article e236759. https://doi.org/10.1136/bcr-2020-236759
