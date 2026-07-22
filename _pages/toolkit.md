---
permalink: /toolkit/
title: "Bioinformatics Toolkit"
author_profile: true
---

_This toolkit summarizes the main bioinformatics tools, databases, file formats, and methods I have used during the course._

## Sequence Analysis Tools

### BLASTN

**Use example:** I used BLASTN to compare the 3,150-bp *acrB* nucleotide sequence from *Escherichia coli* K-12 against the NCBI nucleotide collection database. I reviewed the top five results and found several full-length matches with 100% identity, 100% query coverage, and an E-value of 0.0.

**Strengths / limitations:** BLASTN can find similar nucleotide sequences very quickly and gives useful statistics for evaluating each match. However, a strong sequence match does not prove the same biological function, and the database may return complete chromosome records instead of individual gene records.

---

### FASTA Format

**Use example:** I downloaded the *acrB* nucleotide sequence in FASTA format and used it as the query for my BLASTN search. I checked the header and confirmed that the sequence length was 3,150 bp before running the search.

**Strengths / limitations:** FASTA is simple, readable, and accepted by most sequence-analysis tools. However, it contains limited information beyond the sequence and its header.

---

### BLAST Result Measures

**Use example:** I used E-value, percent identity, query coverage, and bit score to compare the top *acrB* BLAST results. Looking at these values together helped me confirm that the strongest results covered the full query and were not short matches to only one conserved region.

**Strengths / limitations:** These measures provide different information about the quality and significance of an alignment. None of them should be interpreted alone because a high percent identity can still be misleading when the query coverage is low.

---

## Databases and Data Retrieval

### NCBI Gene

**Use example:** I used NCBI Gene to locate the *acrB* record for *E. coli* K-12, confirm Gene ID 945108, and find its location on the reference chromosome.

**Strengths / limitations:** NCBI Gene is a useful starting point for finding gene names, IDs, locations, and links to sequence records. It provides less detailed protein-function information than UniProt.

---

### NCBI RefSeq

**Use example:** I used the RefSeq chromosome record NC_000913.3 to retrieve only the *acrB* gene region. I made sure that I downloaded the 3,150-bp gene sequence instead of using the full *E. coli* chromosome.

**Strengths / limitations:** RefSeq provides standardized reference sequences and clear accession numbers. However, one accession may represent a complete chromosome, so the correct coordinates and strand need to be checked carefully.

---

### UniProt / Swiss-Prot

**Use example:** I used the reviewed UniProt entry P31224 to examine the AcrB protein from *E. coli* K-12. I checked its function in the AcrAB–TolC multidrug efflux system, protein length, evidence level, and GO terms.

**Strengths / limitations:** Reviewed Swiss-Prot records provide detailed protein information with supporting evidence and references. However, UniProt is less useful for retrieving exact nucleotide sequences and chromosome coordinates.

---

### NCBI GEO

**Use example:** I used NCBI GEO to examine a gene-expression study and check its experimental conditions, sample information, biological replicates, and available processed data.

**Strengths / limitations:** GEO keeps study information and functional-genomics data together in one place. However, the completeness and quality of the metadata can be different between studies, so each dataset needs to be evaluated before it is used.

---

## Genome and Transcriptome Analysis

### Count Matrix

**Use example:** I used a count matrix to understand how the number of RNA-seq reads for each gene could be compared between treated and control plant samples.

**Strengths / limitations:** A count matrix organizes expression data into genes and samples and is an important input for differential-expression analysis. Raw counts should not be compared directly without normalization and statistical analysis.

---

### Differential Expression Analysis

**Use example:** I interpreted differential-expression results to identify which plant genes increased or decreased after exposure to a bacterial signal. I used log2 fold change to evaluate the direction and size of the change and adjusted p-values to evaluate statistical confidence.

**Strengths / limitations:** Differential-expression analysis can reduce thousands of genes to a smaller list of genes that changed between conditions. The final list depends on the statistical method and the fold-change and significance cutoffs selected.

---

### Functional Enrichment Analysis

**Use example:** I used enrichment results to examine whether differentially expressed genes were connected to biological functions such as defence response and stress signalling.

**Strengths / limitations:** Enrichment analysis can make a long gene list easier to understand by grouping genes into biological processes. It shows which functions are associated with the gene list, but it does not prove that those functions caused the observed response.

---

## Protein Structure and Function

### InterPro

**Use example:** I used InterPro to examine the domain structure of the NPR3 protein and check which domain databases supported the different protein regions.

**Strengths / limitations:** InterPro combines information from several protein-family and domain databases. Different prediction methods may give slightly different domain names or boundaries, so the evidence should be compared.

---

### AlphaFold

**Use example:** I viewed the predicted three-dimensional structure of NPR3 and used the confidence colours to compare well-predicted regions with regions that may be flexible or disordered.

**Strengths / limitations:** AlphaFold provides structural models for many proteins that do not have an experimental structure. However, the structure is a prediction, and low-confidence regions should not be interpreted as exact shapes.

---

### Protein Domains and Motifs

**Use example:** I examined the BTB domain, ankyrin-repeat region, salicylic-acid-binding region, and conserved motifs of NPR3. This helped me understand how different parts of one protein may have different structural and functional roles.

**Strengths / limitations:** Domains and motifs provide useful clues about protein function and interaction sites. Their presence alone does not fully explain how the whole protein behaves inside a cell.

---

## Computational and Scripting Tools

### RStudio

**Use example:** I used RStudio to open the course project, run the instructor's R scripts one line at a time, and review objects and data in the Console and Environment panels.

**Strengths / limitations:** RStudio keeps scripts, data, plots, and results in one working environment. At first, the different panels, project folders, and working directory can be confusing.

---

### R Scripts

**Use example:** I saved the course scripts in the Scripts folder of my RStudio project and ran the commands in order. I also used comments to understand what each section of the code was doing.

**Strengths / limitations:** Scripts provide a reproducible record of the analysis and can be run again on new data. Later commands may depend on objects created earlier, so the order of the script is important.

---

### CSV Files and Data Cleaning

**Use example:** I worked with plant-growth and synthetic differential-expression CSV files in R. In the plant dataset, I checked missing values and corrected a leaf-count column that had been read as text because it contained the word “dead.”

**Strengths / limitations:** CSV files are simple and can be opened in both spreadsheets and R. They do not automatically preserve data types, so missing values and incorrect text entries need to be checked before analysis.

---

## Data Visualization

### BLAST Graphic Summary

**Use example:** I used the BLAST Graphic Summary to see where the database results aligned along the full length of the *acrB* query. The alignment bars helped me quickly recognize the strongest full-length matches.

**Strengths / limitations:** It provides a quick visual comparison of query coverage and alignment strength. Exact E-values, percent identity, and accession information still need to be checked in the results table.

---

### Volcano Plot

**Use example:** I used a synthetic differential-expression table in R to create a volcano plot. I used the plot to identify genes with large positive or negative fold changes and strong statistical significance.

**Strengths / limitations:** A volcano plot provides a useful overview of many differential-expression results at once. It depends on the selected thresholds and does not show how individual samples behaved.

---

### Heatmap

**Use example:** I used a heatmap to compare expression patterns between treated and control samples and to check whether biological replicates showed similar patterns.

**Strengths / limitations:** Heatmaps are useful for seeing clusters of genes and comparing several samples together. Their appearance can change depending on the selected genes, scaling, and clustering method.

---

### Boxplot

**Use example:** I created a boxplot in R to compare plant height between control and treated groups.

**Strengths / limitations:** A boxplot clearly shows the median and spread of values in different groups. It may hide individual observations, especially when the number of samples is small.
