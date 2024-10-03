# Comparative Metabolic Flux Analysis: ACC-COC3 vs. BPCre Tumor Model

## Overview

This project presents a comparative metabolic flux analysis between human adrenocortical carcinoma (ACC) samples (subgroup ACC-COC3) and the mouse BPCre tumor model. Using a methodology adapted from [REFERENCE ARTICLE], we aim to validate metabolic similarities between these two models and explore key metabolic pathways that may serve as potential therapeutic targets.

The analysis leverages normalized RNA-seq data and a detailed calculation of Metabolic Reaction Activity Scores (MRAS) to compute metabolic fluxes, offering insights into the metabolic behavior of tumor tissues in both species.

## Objectives

1. **Comparative Analysis**: Validate the metabolic flux similarity between human ACC-COC3 and mouse BPCre tumor model.
2. **Pathway-Level Insights**: Identify key metabolic pathways showing dysregulation or similarity between species.
3. **Therapeutic Potential**: Highlight metabolic vulnerabilities for potential therapeutic interventions.

## Data Sources

- **Human ACC-COC3 Data**: TCGA-based RNA-seq data (normalized).
- **Mouse BPCre Data**: RNA-seq data (normalized).

## Methodology

### 1. **Data Preprocessing**
   - Loaded and normalized RNA-seq data for both human ACC-COC3 and mouse BPCre models.
   - Removed negative values and applied cubic root normalization to the metabolic flux data.

### 2. **MRAS Calculation and Metabolic Flux Computation**
   - **MRAS Calculation**: Metabolic Reaction Activity Scores were calculated using gene expression data, providing a reaction-level metabolic activity profile.
   - **Metabolic Fluxes**: Computed based on reaction scores, with fluxes normalized to enhance comparability between human and mouse models.
   
### 3. **Pathway Activity Analysis**
   - Implemented a custom pathway activity scoring function to aggregate the metabolic fluxes across pathways.
   - Comparative analysis between human and mouse fluxes across shared metabolic pathways to assess correlation and pathway similarity.

### 4. **Correlation and Statistical Analyses**
   - **Spearman Correlation**: Conducted across common metabolic reactions and pathways between human and mouse models to quantify the degree of similarity.
   - **Subsystem Analysis**: Focused on specific metabolic subsystems such as "Steroid metabolism," "Pyrimidine metabolism," "Alanine, Aspartate and Glutamate metabolism," and "Arginine and Proline metabolism" to identify key metabolic reprogramming events.

## Key Results and Visualizations

### 1. **Figure 1: Mean Metabolic Fluxes Comparison**
   This figure compares the mean metabolic fluxes between ACC-COC3 (human) and BPCre (mouse) models. A strong correlation was observed, indicating a high degree of similarity between the metabolic behaviors of both models.

   ![Mean Fluxes](link_to_figure1)

### 2. **Figure 2: Pathway Activity Comparison**
   This visualization highlights the activity levels of key metabolic pathways between ACC-COC3 and BPCre. The analysis identified highly conserved pathways, particularly in amino acid and lipid metabolism.

   ![Pathway Activity](link_to_figure2)

### 3. **Heatmap: Correlation of Top 30 Reactions**
   The heatmap below shows the correlation of the top 30 metabolic reactions shared between human ACC-COC3 and mouse BPCre models, revealing potential therapeutic targets.

   ![Top 30 Correlations](link_to_heatmap)

### 4. **Figure: Specific Metabolic Pathways**
   We performed detailed analyses of several metabolic pathways:

   - **Pyrimidine Metabolism**:
     Significant similarity between fluxes in pyrimidine metabolism, suggesting similar nucleotide synthesis dynamics.
     ![Pyrimidine Metabolism](link_to_figure_pyrimidine)
   
   - **Arginine and Proline Metabolism**:
     Differences observed in fluxes may reveal species-specific metabolic vulnerabilities.
     ![Arginine Proline Metabolism](link_to_figure_arginine)

   - **Alanine, Aspartate and Glutamate Metabolism**:
     Highly correlated fluxes in this pathway suggest conserved amino acid metabolism mechanisms.
     ![Alanine Aspartate Glutamate Metabolism](link_to_figure_alanine)

## Insights and Implications

1. **Conserved Metabolism**: The high correlation between the ACC-COC3 and BPCre models supports the use of the BPCre model as a valid metabolic proxy for studying ACC-COC3.
2. **Therapeutic Target Identification**: Metabolic pathways such as steroid metabolism and amino acid metabolism show promise as therapeutic targets, given their dysregulation in both models.
3. **Species-Specific Differences**: Subtle differences in certain pathways like arginine and proline metabolism warrant further investigation, possibly offering insights into species-specific tumor biology.

## Future Directions

1. **Integration with Metabolomics**: Future work will integrate metabolomics data to further validate the metabolic flux findings.
2. **Expansion to Other Cancer Types**: This methodology could be extended to compare metabolic fluxes in other tumor types, identifying broader patterns of metabolic reprogramming across species.
3. **Drug Target Validation**: Ongoing work will explore the potential for targeting key dysregulated pathways in ACC treatment.

## Dependencies

- R (version 4.0 or higher)
- METAFlux package
- Bioconductor packages: DESeq2, clusterProfiler
- ggplot2, pheatmap, reshape2 for visualizations

## References

1. **Huang, Yuefan, et al. "Characterizing cancer metabolism from bulk and single-cell RNA-seq data using METAFlux." Nature communications 14.1 (2023): 4883.** - Original methodology adapted for this analysis.
2. **TCGA Data Portal** - Human ACC-COC3 data source.
3. **Mouse BPCre RNA-seq Data** - in-house generated mouse model expression data.
