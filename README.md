# EPS-ML
# Author: Cai John
### This repo contains the code from "Extreme Phenotype Sampling Improves LASSO and Random Forest Marker Selection in Complex Traits"

### Pipelines
Both pipelines as detailed in the above manuscript are available in `lasso_pipeline.R` and `rf_pipeline.R`. Both pipelines use the same input files.

The LASSO pipeline contains more post-processing and visualizations. If you want to create identical PCA plots for the RF pipeline simply run a PCA on all your markers beforehand (see code in `lasso_pipeline.R` if unfamiliar with how to do this). Then take the set of selected features output from the RF pipeline and run a PCA using *only* the selected features. Note that the `{}_transcriptImportance.txt` file output from the RF pipeline contains variable importance values for all features, you need to filter this based on your desired significance cut-off for your data.

The `example` directory contains data to run a small example analysis. This will demonstrate all output statistics and visualizations. This is a random subset of the Poplar data presented in the paper so do not expect to obtain the same results.

### Malaria Data
The meta-data used for both the Zhu et al. and Mok et al. datasets are included in the `malaria data` directory. We have included this to make it easier for future investigators as some data was generated via text-scraping.

The paper describing the Mok et al. data can be found here: https://pubmed.ncbi.nlm.nih.gov/25502316/. Their transcriptome data can be downloaded from here: https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE59097.

The paper describing the Zhu et al. data can be found here: https://www.nature.com/articles/s41467-018-07588-x. Their transcriptome data can be downloaded from here: https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE121505.

### Using On Your Data
To use the code with your own data, open the pipeline file in your favorite editor and simply change the strings in the first lines:

`samples` - The path to the samples file

`expr` - The path to the expression file

`outname` - Name of output directory containing stats and visualizations

`subtit` - The string to use as a subtitle on each plot. Not used in the RF pipeline as no plotting is done.

Once changed, the pipeline can easily be run using the `Rscript` command.

### Required files
The pipeline requires two main files:

1. **The samples file**: this is a tab-separated text files with two columns. Headers must be "Genotype_ID" and "Pheno". The Genotype_ID column should contain genotype codes to match samples to the expression data. The Pheno column should contain phenotypic class values for each sample.


2. **The expression data file**: this is a tab-separated text file. The first column must be named "Genotype_ID" and these values should match those in the samples file. All subsequent columns should contain the markers to look for associations with.
