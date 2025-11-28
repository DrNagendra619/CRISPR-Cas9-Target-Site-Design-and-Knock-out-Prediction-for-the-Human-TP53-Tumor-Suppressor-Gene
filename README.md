# CRISPR-Cas9-Target-Site-Design-and-Knock-out-Prediction-for-the-Human-TP53-Tumor-Suppressor-Gene
CRISPR/Cas9 Target Site Design and Knock-out Prediction for the Human TP53 Tumor Suppressor Gene
# CRISPR/Cas9 Target Site Design and Knock-out Prediction for the Human TP53 Tumor Suppressor Gene

### 🧬 Project Overview

This repository contains the results of a CRISPR/Cas9 target site search conducted using the **CHOPCHOP** tool. The primary objective was to identify highly specific and efficient **single-guide RNA (sgRNA)** sequences for performing a **gene knock-out** experiment targeting the human tumor suppressor gene, **TP53** (*Homo sapiens*, genome assembly GRCh38).

***

### 🎯 Key Findings: Optimal sgRNA Target Site

The search identified several high-quality sgRNAs based on predicted specificity and efficiency.

| Rank | Target Sequence (5' to 3') | PAM | Genomic Location | Strand | Efficiency Score |
| :---: | :--- | :--- | :--- | :---: | :---: |
| **1** | **CGCTATCTGAGCAGCGCTCA** | **TGG** | chr17:7675056 | + | 43.15% |
| **6** | **GAGCGCTGCTCAGATAGCGA** | **TGG** | chr17:7675052 | - | **63.35%** |

*Note: Rank 6 exhibits the highest predicted on-target cleavage efficiency at 63.35%.*

#### **Specificity (Off-Target Analysis for Rank 1)**

The top-ranked sgRNA sequence exhibits outstanding specificity, with:

| Off-Target Mismatches (MM) | Count |
| :---: | :---: |
| **Perfect Matches (MM0)** | **0** |
| **1 Mismatch (MM1)** | **0** |
| **2 Mismatches (MM2)** | **0** |
| **3 Mismatches (MM3)** | **0** |

This indicates an extremely low risk of unintended edits at other genomic locations. The target region is located within a **coding exon**, ensuring disruption of the protein product.

#### **Predicted Knock-out Outcome (Repair Profile for Rank 1)**

The analysis of the repair profile (Shen et al. 2018 predictions) for the Rank 1 site suggests a high probability of successful gene inactivation through Non-Homologous End-Joining (NHEJ).

| Metric | Predicted Value | Interpretation |
| :--- | :--- | :--- |
| **Frameshift Frequency** | **42.76%** | The predicted probability that the repair process introduces an insertion/deletion (indel) that shifts the reading frame, leading to premature termination and protein knock-out. |
| **Highest Deletion Frequency**| **44.83%** | The single most frequent repair outcome. |
| **Microhomology Deletion** | **76.56%** | High percentage suggesting predictable deletion patterns. |
| **Product Size Range** | 259 bp – 284 bp | Optimal sizes for standard validation assays. |

***

### 🔬 Validation Strategy: PCR Primers

The tool successfully designed highly specific PCR primer pairs (0 predicted off-targets for all pairs) for validating the editing success at the Rank 1 target site.

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
