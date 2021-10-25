# 16S Vertebrate Reference Set For The RDP Classifier 

[![DOI](https://zenodo.org/badge/420446891.svg)](https://zenodo.org/badge/latestdoi/420446891)  

This repository contains trained reference sets that can be used with the Ribosomal Database Project classifier (Wang et al., 2007) to taxonomically assign vertebrate 16S mitochondrial gene sequences.  The latest releases can be downloaded from https://github.com/terrimporter/16SvertebrateClassifier/releases

This classifier is suitable for classifying vertebrate 16S mitochondrial gene sequences to species rank.  Reference sequences were obtained from the NCBI nucleotide [accessed August 2021].  Taxonomy is based on the NCBI taxonomy database.

## How to cite

You can cite this repository directly:  
Teresita M. Porter. (2021). terrimporter/12SvertebrateClassifier: 16S Vertebrate Classifier v1.0.0. Zenodo. https://zenodo.org/badge/latestdoi/420446891  

If you use this reference set with the RDP classifier please also cite the naive Bayesian classification tool:  
Wang et al. (2007) Naïve Bayesian classifier for rapid assignment of rRNA sequences into the new bacterial taxonomy. Applied and Environmental Microbiology, 73: 5261.

## How to use

Decompress the tar.gz file:

$ tar -xvzf FileName.tar.gz

Use with the RDP classifier:

java -Xmx8g -jar /path/to/rdp_classifier_2.13/dist/classifier.jar classify -t /path/to/mydata_trained/rRNAClassifier.properties -o ClassifiedQueryFilename QueryFilename

# Releases

### v1.0.0

These files are ready to be used with the RDP Classifier.  Created from the NCBI nucleotide database [accessed August 11, 2020].  This version contains 65,934 reference sequences (Chordata) plus 6,261 outgroup sequences (Archaea, Bacteria, Fungi, Viridiplantae, non-chordata Metazoans)  and 21,277 taxa at all ranks, including 15,155 species.

### v1.0.0-ref

These files were used to train the RDP Classifier.  Provided here for reference only.  Includes a FASTA file and a taxonomy file.

**Taxonomic assignment results should be filtered according to their bootstrap support values to reduce false positive assignments.**  Cutoffs are based on leave-one-sequence-out testing of non-singleton species. Here we recommend MINIMUM bootstrap cutoffs according to query length and assignment rank.  Assuming your query sequences are represented in the reference set, using the cutoffs presented in the first table below should ensure 99% accuracy.  If you wish to cast a wider net, you can use the following tables below for 95% or 90% accuracy.

*** Testing in progress, these cutoffs are not yet fully validated [October 23/21] ***

#### Bootstrap support cutoffs, 99% accuracy:

Rank | Full | 400 bp | 300 bp | 200 bp | 100 bp
--- |:---:|:---:|:---:|:---:|:---:
Superkingdom | 0 | 0 | 0 | 0 | 0
Kingdom | 0 | 0 | 0 | 0 | 0
Phylum | 0 | 0 | 0 | 0 | 0
Class | 0 | 0 | 0 | 0 | 0 
Order | 0 | 0 | 0 | 0 | 0 
Family | 0 | 0.2 | 0.2 | 0.3 | 0 
Genus | 0.95 | 0.95 | 0.9 | 0.95 | 0 
Species * | NA | NA | NA | NA | NA 

NA = No cutoff available will result in 99% correct assignments

#### Bootstrap support cutoffs, 95% accuracy:

Rank | Full | 400 bp | 300 bp | 200 bp | 100 bp
--- |:---:|:---:|:---:|:---:|:---:
Superkingdom | 0 | 0 | 0 | 0 | 0
Kingdom | 0 | 0 | 0 | 0 | 0
Phylum | 0 | 0 | 0 | 0 | 0
Class | 0 | 0 | 0 | 0 | 0
Order | 0 | 0 | 0 | 0 | 0 
Family | 0 | 0 | 0 | 0 | 0 
Genus | 0 | 0 | 0 | 0.1 | 0 
Species * | NA | NA | NA | NA | NA 

NA = No cutoff available will result in 95% correct assignments

#### Bootstrap support cutoffs, 90% accuracy:

Rank | Full | 400 bp | 300 bp | 200 bp | 100 bp
--- |:---:|:---:|:---:|:---:|:---:
Superkingdom | 0 | 0 | 0 | 0 | 0
Kingdom | 0 | 0 | 0 | 0 | 0
Phylum | 0 | 0 | 0 | 0 | 0
Class | 0 | 0 | 0 | 0 | 0
Order | 0 | 0 | 0 | 0 | 0 
Family | 0 | 0 | 0 | 0 | 0 
Genus | 0 | 0 | 0 | 0 | 0 
Species | 0.4 | 0.6 | 0.5 | 0.7 | 0  

# References

Wang, Q., Garrity, G. M., Tiedje, J. M., & Cole, J. R. (2007). Naive Bayesian Classifier for Rapid Assignment of rRNA Sequences into the New Bacterial Taxonomy. Applied and Environmental Microbiology, 73(16), 5261–5267. Available from https://sourceforge.net/projects/rdp-classifier/

# Acknowledgements

We acknowledge support from the Canadian federal Genomics Research & Development Initiative (GRDI), Metagenomics-Based Ecosystem Biomonitoring (Ecobiomics) project.

Last updated: October 24, 2021
