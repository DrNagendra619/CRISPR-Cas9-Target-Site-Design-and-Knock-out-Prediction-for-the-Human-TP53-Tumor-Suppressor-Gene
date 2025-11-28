# CRISPR-Cas9-Target-Site-Design-and-Knock-out-Prediction-for-the-Human-TP53-Tumor-Suppressor-Gene
CRISPR/Cas9 Target Site Design and Knock-out Prediction for the Human TP53 Tumor Suppressor Gene
# CRISPR/Cas9 Target Site Design and Knock-out Prediction for the Human TP53 Tumor Suppressor Gene
# CRISPR/Cas9 Target Site Design and Knock-out Prediction for the Human TP53 Tumor Suppressor Gene

### 🧬 Project Overview

This repository documents the target site selection process for a CRISPR/Cas9-mediated **gene knock-out** of the human tumor suppressor gene, **TP53** (*Homo sapiens*, genome assembly GRCh38). Results were generated using the CHOPCHOP design tool.

***

### 🔬 Genomic Context (UCSC Genome Browser Analysis)

The analysis was focused on the gene locus on chromosome 17.

* **Genomic Coordinates:** The analysis window covers **chr17:7,668,401-7,687,550** (approximately 19.15 kb).
* **Transcript Structure:** The *TP53* gene is complex, transcribed on the **minus strand**, and possesses **multiple known splice variants** (isoforms, e.g., NM\_000546 and NM\_001126112), validating the decision to target a common **coding exon** to ensure comprehensive knock-out.

***

### 🎯 Key Findings: Optimal sgRNA Target Site

The search identified the following high-quality single-guide RNA (sgRNA) candidates.

| Rank | Target Sequence (5' to 3') | PAM | Genomic Location | Strand | Efficiency Score |
| :---: | :--- | :--- | :--- | :---: | :---: |
| **1** | **CGCTATCTGAGCAGCGCTCA** | **TGG** | chr17:7675056 | + | 43.15% |
| **6** | **GAGCGCTGCTCAGATAGCGA** | **TGG** | chr17:7675052 | - | **63.35%** |

*Note: Rank 6 exhibits the highest predicted on-target cleavage efficiency, while Rank 1 offers unmatched specificity.*

#### **Specificity (Off-Target Analysis for Rank 1)**

The Rank 1 sgRNA sequence is highly specific, showing **zero** predicted off-target matches with up to three mismatches (MM) found in the reference genome.

| Off-Target Mismatches (MM) | Count |
| :---: | :---: |
| **Perfect Matches (MM0)** | **0** |
| **1 Mismatch (MM1)** | **0** |
| **2 Mismatches (MM2)** | **0** |
| **3 Mismatches (MM3)** | **0** |

#### **Predicted Knock-out Outcome (Repair Profile for Rank 1)**

The predicted repair profile (Shen et al. 2018 predictions) for the Rank 1 site is favorable for generating a functional knock-out via NHEJ.

| Metric | Predicted Value | Interpretation |
| :--- | :--- | :--- |
| **Frameshift Frequency** | **42.76%** | The predicted probability of achieving a successful gene-inactivating frame-shift mutation. |
| **Highest Deletion Frequency**| **44.83%** | The single most frequent predicted repair outcome, which simplifies clone screening. |
| **Microhomology Deletion** | **76.56%** | High frequency indicating predictable deletion patterns. |

***

### 🔬 Validation Strategy: PCR Primers

The tool designed highly specific PCR primer pairs (0 predicted off-targets for all pairs) for validating the editing success at the Rank 1 target site.

| Pair | Left Primer (5' to 3') | Right Primer (5' to 3') | Product Size |
| :---: | :--- | :--- | :---: |
| **4** (Recommended) | `CTCAACAAGATGTTTTGCCAAC` | `GCCAGACCTAAGAGCAATCAGT` | 260 bp |
| 1 | `TCAACAAGATGTTTTGCCAACT` | `GCCAGACCTAAGAGCAATCAGT` | 259 bp |
| 3 | `TCAACAAGATGTTTTGCCAACT` | `ACTCGGATAAGATGCTGAGGAG` | 283 bp |

***

### 📂 File Structure

| File Name | Content |
| :--- | :--- |
| `TP53_gRNA_Screen_Summary.html` | The comprehensive, ranked list of all identified sgRNA candidates, including core specificity metrics and efficiency scores. |
| `TP53_Rank1_gRNA_Detail_Analysis.html` | The in-depth breakdown for the top-ranked sgRNA, containing gene visualization, predicted NHEJ repair statistics, and validation primer details. |
