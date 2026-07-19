---
permalink: /toolkit/
title: "Bioinformatics Toolkit"
author_profile: true
---


## Sequence Analysis Tools

### BLAST (Basic Local Alignment Search Tool)

**Use example:** I used BLASTN to compare the E. coli acrB nucleotide FASTA sequence against the NCBI nr/nt database. I evaluated the top matches using E-value, percent identity, and query coverage, and found several E. coli sequences with 100% identity and 100% coverage.

**Strengths / limitations:** A strength of BLASTN is that it quickly identifies similar DNA sequences and provides useful measures such as E-value, percent identity, and query coverage. A limitation is that high sequence similarity does not prove identical function, and the large nr/nt database may return whole chromosome records instead of individual gene records.

---

### NCBI RefSeq

**Use example:** I used NCBI RefSeq to retrieve only the 3,150-bp acrB gene sequence from the E. coli reference chromosome, making sure I did not accidentally download the entire chromosome. I then saved the sequence in FASTA format for the BLASTN search.

**Strengths / limitations:** A strength of NCBI RefSeq is that it provides reliable reference sequences with clear accession numbers and genomic locations. A limitation is that the accession may refer to an entire chromosome, so I had to carefully extract only the acrB gene sequence rather than downloading the full chromosome.

---

## Databases & Data Retrieval

### UniProt

**Use example:** I used UniProt to look up the reviewed AcrB protein entry P31224 from E. coli K-12. I used the record to confirm the protein’s function in the AcrAB–TolC multidrug efflux system and review its evidence level and GO terms.

**Strengths / limitations:** A strength of UniProt is that reviewed Swiss-Prot entries provide reliable protein-function information, evidence codes, GO terms, and references. A limitation is that UniProt is less useful for retrieving exact gene locations or nucleotide sequences, and the supporting evidence still needs to be checked carefully.

---

## Data Visualization

### NCBI BLAST Graphic Summary

**Use example:** I used the NCBI BLAST Graphic Summary to visualize how strongly the acrB query sequence aligned with the database hits across its full length. The coloured alignment bars helped me compare query coverage and quickly identify the strongest, full-length matches.

**Strengths / limitations:** A strength of the NCBI BLAST Graphic Summary is that it provides a quick visual comparison of alignment strength and query coverage across many hits. A limitation is that it does not show all exact numerical details, so I still needed to check the results table and individual alignments for E-values, percent identity, and precise coverage.

---
## Gene Lookup

### NCBI Gene

**Use example:** I used NCBI Gene to locate the acrB record for E. coli K-12, confirm Gene ID 945108, and identify its chromosomal location.

**Strengths / limitations:** It is a strong starting point for gene names, IDs, locations, and linked records. However, it provides less detailed protein-function information than UniProt.

---
## Sequence Format

### FASTA

**Use example:** I downloaded the acrB nucleotide sequence in FASTA format and used it as the input for the BLASTN search.

**Strengths / limitations:** FASTA is simple, readable, and accepted by most bioinformatics tools. However, it contains limited annotation information beyond the sequence header.

---
## Statistical Evaluation

### E-value

**Use example:** I used the E-value to determine whether the top acrB BLAST matches were likely to have occurred by chance; the strongest hits had an E-value of 0.0.

**Strengths / limitations:** It is useful for judging statistical significance, with lower values indicating stronger evidence. However, it should not be interpreted alone without percent identity and query coverage.

---
