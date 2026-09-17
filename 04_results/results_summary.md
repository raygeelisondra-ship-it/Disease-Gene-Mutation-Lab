## WT versus Mutant Protein Comparison

Sequence comparison between the wild-type and `c.1A>T` mutant protein products reveals that the two sequences first differ at amino acid position 1, where methionine (M) is replaced by leucine (L) (`p.Met1Leu`). In computational translation (Frame 1), only this single amino acid is altered; downstream amino acids from position 2 to 860 remain 100% identical to the wild-type reference sequence.

No amino acid insertions, deletions, or premature stop codons were produced within the open reading frame. Because the single-base substitution does not shift the triplet reading frame, the computational protein length remains 860 amino acids. While in-silico tools classify this as an initiator codon variant / missense change, its biological impact is a complete failure of translation initiation in-vivo.

---

## Mutation Comparison Matrix

| Parameter | Wild-Type Reference | Documented Mutation (`c.1A>T`) | Artificial Mutation (`c.30G>A`) |
| :--- | :--- | :--- | :--- |
| **CDS Length** | 2583 bp | 2583 bp | 2583 bp |
| **Protein Length** | 860 amino acids | 860 aa (in-silico); 0 aa (in-vivo) | 9 amino acids |
| **Mutation Type** | Wild-type (None) | Single nucleotide substitution (`c.1A>T`); Start codon variant | Single nucleotide substitution (`c.30G>A`); Nonsense mutation (`p.Trp10*`) |
| **Reading Frame Shift** | No | No (Intact) | No (Intact) |
| **Premature Stop Codon** | No | No | Yes (Codon 10: `TGA`) |
| **Amino Acids Affected** | 0 | 1 aa (in-silico); 860 aa untranslated (in-vivo) | 851 aa truncated |
| **Expected Functional Consequence** | Normal receptor expression & LDL clearance | Complete loss of translation initiation | Severe N-terminal truncation |

---

## Alignment Results 
The Needle alignment tool demonstrates an exceptionally high degree of sequence conservation between the wild-type and computational `c.1A>T` mutant *LDLR* protein sequences. With an overall identity of 99.9% and zero gap penalties incurred, the quantitative metrics confirm that the single-base substitution is strictly confined to the N-terminal residue position. The alignment evaluation verifies that downstream codons from position 2 through the C-terminus maintain complete sequence integrity, proving that the computational alteration does not induce downstream frameshifts or amino acid stretches of missense variation. Consequently, any functional impairment must arise strictly from the initial nucleotide disruption rather than cumulative structural defects across the body of the polypeptide.
