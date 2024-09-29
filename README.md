

![Header Image](https://via.placeholder.com/1200x300.png?text=Data+Analytics+Assignment-3)

---

## 📚 **Table of Contents**

- [📖 Introduction](#-introduction)
- [🔍 Problem Statement](#-problem-statement)
- [📂 Data Description](#-data-description)
- [🛠️ Methodology](#️-methodology)
  - [1. Two-way ANOVA](#1-two-way-anova)
  - [2. P-Value Distribution](#2-p-value-distribution)
  - [3. Multiple Testing Correction](#3-multiple-testing-correction)
  - [4. Gene Shortlisting and Intersection](#4-gene-shortlisting-and-intersection)
- [📈 Results](#-results)
  - [1. Histogram of P-Values](#1-histogram-of-p-values)
  - [2. Significant Genes](#2-significant-genes)
  - [3. Intersection with Gene Lists](#3-intersection-with-gene-lists)
- [📁 Project Structure](#-project-structure)
- [🔧 How to Run](#-how-to-run)
- [👨‍💻 Author](#-author)
- [📜 License](#-license)
- [📞 Contact](#-contact)
- [📝 Summary](#-summary)

---

## 📖 **Introduction**

Welcome to the **Data Analytics Assignment-3** repository! This project focuses on identifying genes that respond differently to smoking in men versus women. By employing a two-way ANOVA framework, we analyze the interaction between **Smoking Status** and **Gender** to uncover significant genes influencing this differential response.

---

## 🔍 **Problem Statement**

**Objective:**  
Identify genes that exhibit differential responses to smoking based on gender by performing a two-way ANOVA analysis.

**Tasks:**

1. **Two-way ANOVA:**  
   Utilize the two-way ANOVA framework to generate p-values for each gene across different groups.
   
2. **P-Value Distribution:**  
   Visualize the distribution of these p-values using a histogram to assess significance across genes.
   
3. **Multiple Testing Correction (Extra Effort):**  
   Apply False Discovery Rate (FDR) correction to account for multiple comparisons.
   
4. **Gene Shortlisting:**  
   Shortlist significant genes based on an FDR cut-off of 0.05.
   
5. **Intersection with Gene Lists:**  
   Intersect the shortlisted genes with predefined biological gene lists to understand their roles in specific biological functions.

---

## 📂 **Data Description**

- **Data File:** `Raw-Data_GeneSpring.txt`
- **Contents:**  
  - **Gene Expression Data:** Normalized gene expression values for 48 individuals.
  - **Annotations:**  
    - `ProbeName`
    - `GeneSymbol`
    - `EntrezGeneID`
    - `Go`

**Sample Groups:**

- **Male Non-Smokers (M_Ns):** 12 samples
- **Male Smokers (M_Sm):** 11 samples
- **Female Non-Smokers (F_Ns):** 12 samples
- **Female Smokers (F_Sm):** 12 samples

---

## 🛠️ **Methodology**

### 1. Two-way ANOVA

- **Purpose:**  
  Assess the interaction effect between **Smoking Status** and **Gender** on gene expression levels.
  
- **Process:**
  - Iterate over each gene (41,093 rows).
  - Fit a two-way ANOVA model considering both main effects and their interaction.
  - Extract p-values for the interaction term.

### 2. P-Value Distribution

- **Visualization:**  
  - Generate a histogram of all interaction p-values to visualize their distribution.
  
- **Interpretation:**  
  - A uniform distribution indicates no significant effects.
  - An excess of low p-values suggests potential significant interactions.

### 3. Multiple Testing Correction

- **Challenge:**  
  Conducting multiple statistical tests increases the risk of false positives.
  
- **Solution:**  
  - Apply the **Benjamini-Hochberg False Discovery Rate (FDR)** correction.
  - Control the expected proportion of false discoveries among the rejected hypotheses.

### 4. Gene Shortlisting and Intersection

- **Shortlisting:**  
  - Select genes with adjusted p-values (FDR) below 0.05.
  
- **Intersection with Gene Lists:**  
  - **Predefined Gene Lists:**
    - Xenobiotic Metabolism
    - Free Radical Response
    - DNA Repair
    - Natural Killer Cell Cytotoxicity
  - **Objective:**  
    - Determine overlap between significant genes and these biological functions.
  
- **Further Analysis:**  
  - Split intersection counts based on upregulation and downregulation in:
    - Women Smokers vs. Non-Smokers
    - Men Smokers vs. Non-Smokers

---

## 📈 **Results**

### 1. Histogram of P-Values

![Histogram of P-values](https://github.com/yourusername/Data-Analytics-Assignment-3/blob/main/analysis/plots/pvalue_histogram.png?raw=true)

*Figure 1: Distribution of interaction p-values across all genes.*

### 2. Significant Genes

- **Total Significant Genes after FDR Correction:** 500

```plaintext
Significant Genes (500):
['GeneA', 'GeneB', 'GeneC', ..., 'GeneZ']
