This repository contains the code and datasets used in the following study: Identifying Key Biomarkers Across Cancers Through Bootstrapped Logistic Regression

creatingGeneData.ipynb is the script used to extract gene expression data from the TCGA project. To use it follow these steps:

1.  In the retrieveFiles function, you'll see:
  
    filters={
        "op":"and",#The main filter; every child filter in content must be satisfied for the file to be returned.
        "content":[
            {"op":"in",#Child filter 1: Only files from the TCGA-BRCA project
                "content":{
                    "field":"cases.project.project_id",
                    "value":["TCGA-BRCA"]} <--- CHANGE THIS PROJECT TO MATCH THE CANCER OF INTEREST. HERE, "TCGA-BRCA" WILL BE USED TO COLLECT BREAST CANCER SAMPLES.
            }
       ......

2. Once the desired project has been selected, run the first code block to obtain a tsv file. Run this file through the second block to rehape it into wide format. The dataset is now ready to be used.

main.ipynb contains the code to run n bootstrap replicates. Use the dataset created with creatingGeneData.ipynb here. 
