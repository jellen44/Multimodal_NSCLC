# Autoencoder-Based Multimodal Prediction of Non-Small Cell Lung Cancer Survival

This study presents a novel, autoencoder-based pipeline for both adenocarcinoma (LUAD) and squamous cell carcinoma (LUSC) patients that aims to predict survival more effectively and identify NSCLC survival subtypes. We implemented a combined linear feature selection and denoising autoencoder approach for the compression of multiple modalities of data, including microRNA (miRNA), mRNA, DNA methylation, long non-coding RNAs (lncRNAs) and clinical data. Survival performance, as measured by the concordance index (C-index), was compared across data dimensionality reduction techniques, modality combinations, time of data integration and training data types. A regularized Cox proportional hazards model, Elastic Net, was chosen to make survival predictions using a 5-fold cross validation scheme on 732 NSCLC (408 LUAD; 324 LUSC) patients from the Cancer Genome Atlas (TCGA) dataset. 

Using all data modalities, we achieved C-indexes of 0.67 (±.04) and 0.63 (±.02) for LUAD and LUSC, respectively. Notably, utilizing only lncRNA and clinical data led to effective survival discrimination, with C-indexes of 0.69 (±.03) for LUAD (the highest performance of any LUAD combination) and 0.62 (±.03) for LUSC. Overall, higher performance was achieved by using a single denoising autoencoder for all biological data (early integration) and by training on both LUSC and LUAD together. Two significant survival subtype clusters (log rank test p-value = 1e-9) were identified, allowing us to locate 991 differentially expressed transcripts in the poorer survival group across all four biological modalities.

# Instruction Steps

1. Download the 'Multimodal' folder above and add it to your desktop 
2. If you have not downloaded R, go to https://www.r-project.org/ and click the “Download R” link under the “Getting Started” header. Next, go to https://rstudio.com/products/rstudio/download/, choose the “RStudio Desktop” Option and click “Download.”
3. Open and run the 'DownloadingData.Rmd' script above in R or R Studio, which will download mRNA, miRNA and DNA Methylation data directly from TCGA and save it into the Multimodal folder.
4. Run the 'PreProcessing.R' script to process all of the data for all five modalities, including extracting lncRNA data from the mRNA file, removing biological transcripts with too many missing values/zeros (see paper) and taking only the 732 eligible patients. Again, the processed files will be saved in the Multimodal folder.
5. Run the files below (see descriptions) to get results and then run the 'PostProcessing.Rmd' script to analyze those results.

# Pipeline Script Descriptions

### 1. AllModality_Comparison.R

### 2. LFS.R

### 3. PCA.R

### 4. OnlyAutoencoder.R

### 5. PostProcessing.Rmd

# Survival Subtype Script Descriptions

### 1. KMeans_Clustering.R

- It is important to note that you must run the 'AllModality_Comparison.R' script above in order to get the multimodal feature space used for K Means Clustering. You also must run this script before running any of the DEA scripts below for each modality.

### 2. DEA_mRNA.Rmd

### 3. DEA_miRNA.Rmd

### 4. DEA_Methylation.Rmd

### 5. DEA_LNCRNAS.Rmd

# Important File Descriptions

### 1. LUAD_indices_sample_5fold.Rdata

### 2. LUSC_indices_sample_5fold.Rdata

### 3. barcode_disease_mapping.Rdata
