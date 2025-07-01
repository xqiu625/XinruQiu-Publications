# 2023-05-RELMα-Obesity-eLife.md

## 📊 Paper Metadata
- **Title:** Sexual dimorphism in obesity is governed by RELMα regulation of adipose macrophages and eosinophils
- **Authors:** Jiang Li, Rebecca E Ruggiero-Ruff, Yuxin He, Xinru Qiu, Nancy Lainez, Pedro Villa, Adam Godzik, Djurdjica Coss, Meera G Nair
- **Publication:** eLife (2023)
- **Institution:** University of California Riverside School of Medicine
- **Paper Link:** DOI: https://doi.org/10.7554/eLife.86001
- **Code/Data:** GEO: GSE219119, GitHub: rrugg002/Sexual-dimorphism-in-obesity

## 🎨 Key Figures

### Figure 1: [relma-obesity-protection.png]
**Why this figure is exceptional:**
- **Sex-specific Protection:** Demonstrates that RELMα deficiency specifically affects female obesity protection, not males
- **Multi-parameter Analysis:** Integrates body weight, adipose mass, cytokine levels, and immune cell frequencies
- **Temporal Resolution:** Shows progressive weight gain over 12-15 weeks with clear divergence in RELMα KO females
- **Flow Cytometry Integration:** Links phenotypic changes to specific immune cell population shifts in stromal vascular fraction

**Design principles to mimic:**
- Multi-panel design combining weight curves, tissue masses, and cellular analysis
- Sex-stratified analysis with clear male/female comparisons throughout
- Time-course data presentation with error bars and statistical annotations
- Integration of phenotypic and immunological readouts

### Figure 5: [scrna-seq-sex-relma-differences.png]
**Single-cell excellence:**
- **Comprehensive Analysis:** Single-cell RNA-seq of 57,133 cells across 4 experimental groups
- **Pathway Discovery:** Identifies novel pathways like amyloid-beta response and hemoglobin upregulation
- **Sex-specific Mechanisms:** Reveals unique gene expression patterns in protected WT females
- **Functional Validation:** Links transcriptional changes to metabolic and immune phenotypes

## 🔄 Key Scientific Insights

```python
### 1. Conceptual Innovation
- **Sex-specific Immune Protection:** First demonstration that RELMα provides female-specific protection from diet-induced obesity
- **RELMα-Eosinophil-Macrophage Axis:** Novel immune circuit where RELMα recruits eosinophils to maintain anti-inflammatory macrophages
- **Therapeutic Rescue:** Shows that eosinophil transfer or RELMα treatment can rescue obesity phenotype in knockout females

### 2. Methodological Framework
- **Study Design:** RELMα knockout vs wild-type mice on high-fat diet (HFD) for 6-12 weeks
- **Sex-stratified Analysis:** Comprehensive comparison of male vs female responses
- **Multi-modal Approach:**
  1. **Phenotypic Analysis:** Body weight, adipose mass, metabolic parameters
  2. **Flow Cytometry:** Stromal vascular fraction immune cell profiling
  3. **Single-cell RNA-seq:** 10x Genomics platform with cell multiplexing
  4. **Functional Rescue:** Eosinophil adoptive transfer and RELMα treatment

### 3. Validation Strategy
**Comprehensive Evaluation Across:**
- **5 RELMα KO and WT mice** per sex and diet condition
- **57,133 single cells** from adipose stromal vascular fraction
- **Multiple timepoints** (6-week and 12-week HFD exposure)
- **Rescue experiments** with eosinophil transfer and recombinant RELMα treatment
```

## 🔬 Critical Technical Details
```python
### 1. Diet-Induced Obesity Model

# Experimental design:
- HFD: D12492 (60% kcal from fat, 5.21 kcal/g)
- Control: D12450J (10% kcal from fat, 3.82 kcal/g)
- Duration: 6-12 weeks post-weaning
- Endpoints: Body weight, adipose mass, immune profiling

### 2. Single-cell RNA Sequencing
- **Platform:** 10x Genomics Chromium Next GEM Single Cell 3' v3.1
- **Cell Multiplexing:** CMO labeling for biological replicate pooling
- **Processing:** Cell Ranger v6.1.2 with mm10-2020-A genome
- **Analysis:** Seurat v4.3.0 and Monocle3 v3.1.2.9 for trajectory analysis

### 3. Key Performance Metrics
- **RELMα KO Female Weight Gain:** Significantly increased vs WT females on HFD
- **Eosinophil Loss:** 10% in NS LS vs 1% in healthy controls in SVF
- **Macrophage Polarization:** Increased CD11c+ M1-like macrophages in RELMα KO females
- **Rescue Efficacy:** Both eosinophil transfer and RELMα treatment normalized weight gain
```

## Baseline Models, Evaluation Metrics, and Datasets
```python
### Experimental Groups (n=4-6 per group)
- **Wild-type:** Male and female C57BL/6 mice
- **RELMα KO:** Male and female knockout mice
- **Diet conditions:** Control diet vs high-fat diet

### Evaluation Metrics
- **Primary:** Body weight gain, adipose tissue mass
- **Immune profiling:** Flow cytometry of stromal vascular fraction
- **Molecular:** Cytokine levels, single-cell transcriptomics
- **Functional rescue:** Eosinophil transfer, RELMα treatment efficacy

### Single-cell Dataset
- **Total cells:** 57,133 cells across all conditions
- **Cell types:** 12 clusters including fibroblasts, macrophages, eosinophils, lymphocytes
- **Experimental design:** 3 biological replicates per group with cell multiplexing
- **Sequencing depth:** 20,000 read pairs per cell on NovaSeq 6000
```

## 💭 Critical Research Implications
```python
### 1. Methodological Impact
- **Sex-stratified Analysis:** Demonstrates importance of including both sexes in obesity research
- **Immune-Metabolic Integration:** Shows how specific immune circuits regulate metabolic outcomes
- **Single-cell Resolution:** Reveals cell-type-specific mechanisms underlying sex differences

### 2. Obesity Research Relevance
- **Female Protection Mechanisms:** Identifies RELMα as key mediator of female obesity resistance
- **Therapeutic Targets:** RELMα and eosinophils represent novel intervention points
- **Precision Medicine:** Suggests sex-specific therapies may be more effective

### 3. Immunology Insights
- **RELMα Function:** Expands understanding of RELMα beyond helminth responses to metabolic regulation
- **Eosinophil Biology:** Shows adipose eosinophils are critical for metabolic homeostasis in females
- **Macrophage Plasticity:** Demonstrates RELMα-dependent macrophage polarization in adipose tissue
```

## 💻 Computational Requirements
```python
### Single-cell RNA-seq Infrastructure
- **Sequencing:** NovaSeq 6000 with 250M reads per sample
- **Storage:** GEO repository GSE219119 for data sharing
- **Analysis:** R/Bioconductor environment with Seurat and Monocle3
- **Visualization:** 10x Genomics Loupe Browser for interactive analysis

### Software Environment
- **Primary:** Cell Ranger v6.1.2, Seurat v4.3.0, R v4.2.3
- **Analysis:** Monocle3 v3.1.2.9 for trajectory analysis
- **Statistics:** GraphPad Prism 9 for statistical analysis and visualization
- **Pathway Analysis:** ShinyGO 0.76.3 for GO enrichment analysis

### Processing Pipeline
- **Cell QC:** UMI >500, <20,000; mitochondrial genes <10%
- **Integration:** Cell Ranger aggr pipeline with batch correction
- **Clustering:** Graph-based clustering with resolution 1.0
- **Differential Expression:** MAST method with Benjamini-Hochberg correction
```

## 📋 Implementation Checklist
```python
### For Reproducing Results
- [ ] RELMα knockout mouse strain (available from authors)
- [ ] High-fat diet feeding protocol for 6-12 weeks
- [ ] Flow cytometry setup for adipose stromal vascular fraction analysis
- [ ] 10x Genomics single-cell RNA-seq platform access

### For Adapting to New Contexts
- [ ] Validate in other mouse strains or human tissue samples
- [ ] Extend to other metabolic challenges (aging, different diets)
- [ ] Test RELMα therapeutic potential in preclinical models
- [ ] Investigate other tissue-specific roles of RELMα-eosinophil axis
```

## 🔗 Related Work & Context
- **Previous RELMα Work:** Li et al. (2021) - RELMα in regulatory T cell interactions
- **Eosinophil Metabolism:** Wu et al. (2011) - eosinophils in adipose homeostasis
- **Sex Differences in Obesity:** Chen et al. (2021) - macrophage sex differences in obesity
- **Single-cell Adipose:** Jaitin et al. (2019) - adipose tissue macrophage heterogeneity

---
*Note based on analysis of: Li, Ruggiero-Ruff et al. Sexual dimorphism in obesity is governed by RELMα regulation of adipose macrophages and eosinophils. eLife 2023;12:e86001.*
