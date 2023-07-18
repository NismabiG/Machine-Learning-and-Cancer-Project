Using machine learning algorithms to predict a clinical condition related to cancer from omics data

Introduction: 
Prostate adenocarcinoma (PRAD) is a common type of prostate cancer that begins when normal prostate cells start to grow uncontrollably, eventually forming a tumor
Prostate adenocarcinoma (PRAD) is one of the most common neoplasms worldwide, ranking 4th among all cancer types in both sexes with an incidence of 7.1%

Hypothesis/Problem statement:
1:RACE influence survival in prostate cancer patientsAnd different races have had different prognosis 
2: GENE EXPRESSION influence survival make  significant difference for prognosis  between normal samples and primary prostate tumor samples 

Datasets:*GDCquery* function was used to access Prostate cancer cases from GDC from  TCGA-PRAD project.

Methods :
1: Download the data (clinical and expression) from TGCA
2: Transcriptome Profiling Query:  project = "TCGA-PRAD", RNA-seq - experimental strategy, STAR-counts: workflow
3:Both clinical and expression data are present in this object like table Eg: vital status , sample-type, Definition, 
4:Subsetted the query (150 samples, including 100 Primary Tumor and 50 Solid Tissue Normal )
5: Saved and downloaded the new sub-setted data. 
6:Survival analysis (Simple) for race 
7:RNA Seq Expression Analysis: Processing of the data (normalization) and saving it locally using simple table formats and saved the limma file.
8:Supervised analysis includes differential expression, PCA.
9:Build 7 machine learning model (classifier) to predict cancer survival, clustering for association, and GO analysis.
10: Perform a survival analysis of molecular markers detected in previous analyses.


Applying Machine Learning: 
1.Elastic net model - generalized linear model
2.Support Vector Machine training (SVM):  classify data based on hyperplane 
3. Linear Discriminant Analysis training (LDA)
4. K-nearest neighbors training (KNN): classify data based on distance
5. hypertuned KNN: Bootstrapping- resampling with replacement , no:50, k=9
6. KNN-Crossval, resampling without replacement , 10 fold
7. Random Forest training (RF): choose from the best means of decision tree 

Conclusion:
  -Using simple survival analysis : race doesn’t influence survival in prostate cancer patients
  -PCA definition plot shows that the two sample groups (tumor tissue, and healthy tissue) have a well-separated RNA expression profile.
  -2/7 machine learning algorithms have 100 % accuracy( LDA AND SVM)  which means it can used for  predicting the gene expression and survival analysis.
  -103 relevent genes and 8 genes of common found.
  -From heat map, selected genes group into two classes: genes highly expressed in tumors vs. genes in control. Interestingly, genes also detected by DE analysis are only 
     associated to high expression in the control group.
  -In gene expression and survival analysis it's found that APOBEC3C gene does not appear to make a difference for prognosis .
HENCE , I REJECTED MY HYPOTHESIS
GENE EXPRESSION influence survival MAKING NO significant difference for prognosis  between normal samples and primary prostate tumor samples 
RACE doesn’t influence survival in prostate cancer patient














