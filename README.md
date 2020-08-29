# EPS-ML
# Author: Cai John
### This repo contains the code from "Extreme Phenotype Sampling Improves LASSO and Random Forest Marker Selection in Complex Traits"

All code necessary to run the analyses are contained within the `lasso_pipeline.R` file. This file will handle data pre-processing, analysis and visualizations.

The `example` directory contains data to run a small example analysis. This will demonstrate all output statistics and visualizations.

To use the code open the pipeline file in your favorite editor and simply change the strings in the first lines:

`samples` - The path to the samples file

`expr` - The path to the expression file

`outname` - Name of output directory containing stats and visualizations

`subtit` - The string to use as a subtitle on each plot, for differentiating between runs


### Required files
The pipeline requires two main files:

1. **The samples file**: this is a tab-separated text files with two columns. Headers must be "Genotype_ID" and "Pheno". The Genotype_ID column should contain genotype codes to match samples to the expression data. The Pheno column should contain phenotypic class values for each sample.


2. **The expression data file**: this is a tab-separated text file. The first column must be named "Genotype_ID" and these values should match those in the samples file. All subsequent columns should contain the markers to look for associations with.
