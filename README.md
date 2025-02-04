## BSH analysis pipeline

This pipeline is for BSH gene identification for Lucas et al. paper.


## Steps

The input data for this pipeline should be a list of bacteria genomes of interest. See example in `data/`.

### [1] Build HMM

The shotgun sequencing usually contain host contamination reads, the proportion of host reads vary from sample to sample (e.g., human vs. mouse, diets also impact)

- First, reference sequences were aligned using [muscle](https://www.drive5.com/muscle/) to `.afa` file. Then `.afa` file was convert to stockholm format  `.sto` file.

- Then, HMM was built using [hmmer3](http://hmmer.org/) (`hmmbuild`). 

### [2] HMM search

All CDS from input genomes were screened against HMM using [hmmer3](http://hmmer.org/) (`hmmsearch`). HMM output was converted into single table file.