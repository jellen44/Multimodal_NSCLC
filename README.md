# Autoencoder-Based Multimodal Prediction of Non-Small Cell Lung Cancer Survival

This study presents a novel, autoencoder-based pipeline for both adenocarcinoma (LUAD) and squamous cell carcinoma (LUSC) patients that aims to predict survival more effectively and identify NSCLC survival subtypes. We implemented a combined linear feature selection and denoising autoencoder approach for the compression of multiple modalities of data, including microRNA (miRNA), mRNA, DNA methylation, long non-coding RNAs (lncRNAs) and clinical data. Survival performance, as measured by the concordance index (C-index), was compared across data dimensionality reduction techniques, modality combinations, time of data integration and training data types. A regularized Cox proportional hazards model, Elastic Net, was chosen to make survival predictions using a 5-fold cross validation scheme on 732 NSCLC (408 LUAD; 324 LUSC) patients from the Cancer Genome Atlas (TCGA) dataset. 

Using all data modalities, we achieved C-indexes of 0.67 (±.04) and 0.63 (±.02) for LUAD and LUSC, respectively. Notably, utilizing only lncRNA and clinical data led to effective survival discrimination, with C-indexes of 0.69 (±.03) for LUAD (the highest performance of any LUAD combination) and 0.62 (±.03) for LUSC. Overall, higher performance was achieved by using a single denoising autoencoder for all biological data (early integration) and by training on both LUSC and LUAD together. Two significant survival subtype clusters (log rank test p-value = 1e-9) were identified, allowing us to locate 991 differentially expressed transcripts in the poorer survival group across all four biological modalities.

# Pipeline Script Descriptions

### 1. DownloadingData.Rmd

- Hello

### 2. PreProcessing.R

### 3. AllModality_Comparison.R

### 4. LFS.R

### 5. PCA.R

### 6. OnlyAutoencoder.R

### 7. PostProcessing.Rmd

# Differential Expression Analysis Scripts

### 1. KMeans_Clustering.R

### 2. DEA_mRNA.Rmd

### 3. DEA_miRNA.Rmd

### 4. DEA_Methylation.Rmd

### 5. DEA_LNCRNAS.Rmd

# Important Files

### 1. LUAD_indices_sample_5fold.Rdata

### 2. LUSC_indices_sample_5fold.Rdata

### 3. barcode_disease_mapping.Rdata
