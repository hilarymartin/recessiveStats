### recessiveStats: analysis of recessive variation

This package analyses genes suspecetd of having a recessive mode of inheritance.
We test for enrichment of compound heterozygous variants in genes and similarity
of suspected syndromes between probands. A combined test is calculated by
incorporating results from testing for similarity of Human Phenotype Ontology
(HPO) terms among probands (see https://github.com/jeremymcrae/hpo_similarity).

##### Enrichment of recessive variants in genes

- [ExAC](http://exac.broadinstitute.org/) version 0.3 datasets
- DDD unaffected parents

##### Suspected syndrome matches
- Inspect ‘suspected syndrome’ field and prepare it for manually curation to
  generate comma separated lists of correctly spelled clinical syndromes.
- Manually curate dataset, any uncertainties are flagged clinical review.
- Generate pairwise matrix of similarity based on exact matches between
  clinical syndromes and frequency with which each syndrome is suspected.

##### Installation
The package can be installed or updated using R 3.1.0 or greater with:
```R
library(devtools) # if necessary install with install.packages("devtools")
devtools::install_github("jeremymcrae/recessiveStats")

# Alternatively, clone the repository, run R 3.1 from within the top level of
# the repository and use the devtools::build() to build the package for other R
# versions.
```

##### Usage
```R
# load the package
library(recessiveStats)

hgnc ="DNAH14"
chrom = "1"
lof_lof = 5
lof_func = 6
probands = c("DDDP00000X", "DDDP00000Y", "DDDP00000Z")
analyse_inherited_enrichment(hgnc, chrom, lof_lof, lof_func, probands)
```
