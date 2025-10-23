# ml-amr-project
A Machine learning approach for analyzing antimicrobial resistance (AMR) genes in Escherichia coli using data retrieved from BV-BRC, Pathogen DB, and ABRicate (Linux).
# Machine Learning Analysis of AMR Genes in *E. coli*

This project explores the use of machine learning models to identify genes contributing to **meropenem resistance** in *Escherichia coli*.  
It combines **bioinformatics data retrieval** from public microbial databases with **predictive modeling** to understand gene-level patterns driving antibiotic resistance.

---

## Background

The **Bacterial and Viral Bioinformatics Resource Center (BV-BRC)** (Robert et al., 2023) provides open-source, web-based access to genotype, phenotype, protein, and metadata information on microbial organisms.  
Complementing this, the **Pathogen DB** maintained by **NCBI** offers an isolate browser to search and download isolate-level microbial data.

After retrieving the relevant genomic data, **ABRicate** (Seemann T.) was used to annotate the presence of antimicrobial resistance (AMR) genes within genomic contigs.  
The resulting dataset serves as the foundation for downstream **machine learning analysis**.

---

## Objective

1. Build ML models to analyze complex genomic AMR data.  
2. Identify genes and their activity patterns that contribute to **meropenem resistance** in *E. coli*.

---

## Workflow

1. **Data Retrieval** – Download good quality, WGS *E. coli* isolate data from BV-BRC and Pathogen DB.  
2. **Annotation** – Run ABRicate, a linux-based software to detect AMR genes in genomic contigs.  
3. **Feature Engineering** – Generate presence/absence matrices of AMR genes.  
4. **Modeling** – Apply classification algorithms such as:
   - Random Forest  
   - K-Nearest Neighbors (KNN)  
   - Logistic Regression  
   - Naïve Bayes  
5. **Evaluation** – Assess models using accuracy, precision, recall, and confusion matrices.  
6. **Feature Importance** – Identify the most predictive genes associated with meropenem resistance.

---

## 🧪 Output (Random Forest Classifier)

feature importance visualization:

```python
# Example output (simplified)
Top Features (Gene Importance):
1. blaNDM-5        0.224
2. blaCTX-M-15     0.187
3. oqxB            0.121
4. marR            0.084
5. acrA            0.072
