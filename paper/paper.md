---
title: 'dna-electrons: A Python Package for Calculating Total Electron Counts in DNA Sequences'
tags:
  - Python
  - DNA
  - computational biology
  - bioinformatics
  - electron density
  - molecular modeling
  - quantum chemistry
  - FASTA
authors:
  - name: Yash Munnalal Gupta
    orcid: 0000-0003-3306-832X
    corresponding: true
    affiliation: 1
affiliations:
 - name: Department of Biology, Faculty of Science, Naresuan University, Thailand
   index: 1
date: 30 September 2025
bibliography: paper.bib
---

# Summary

DNA electronic properties play a crucial role in understanding biological processes at the quantum level, yet accessible computational tools for calculating electron densities in nucleotide sequences remain limited. `dna-electrons` addresses this gap by providing a Python package that computes total electron counts for DNA sequences with customizable options for single- or double-stranded configurations, backbone inclusion, and phosphate charge considerations [@Gupta2025]. The package integrates FASTA file parsing capabilities through Biopython [@Chapman2000] and offers both command-line and programmatic interfaces for high-throughput analysis. By providing predefined electron counts for nucleotide bases (A: 70, T: 66, G: 78, C: 58 electrons) and backbone components (238 electrons per base pair for sugar-phosphate backbone), `dna-electrons` enables researchers in computational biology, quantum chemistry, and molecular modeling to rapidly estimate electronic properties of DNA sequences without complex quantum mechanical calculations.

# Statement of need

The electronic structure of DNA is fundamental to understanding various biological processes including charge transport [@Senthilkumar2005], radiation damage [@Sanche2005], and DNA-protein interactions [@Warshel2006]. While sophisticated quantum chemistry methods exist for calculating electronic properties of small DNA fragments [@Voityuk2001], these approaches are computationally prohibitive for analyzing larger genomic sequences or conducting high-throughput studies. Current bioinformatics tools focus primarily on sequence analysis, structural prediction, and functional annotation, but lack capabilities for estimating basic electronic properties that are increasingly relevant in fields such as DNA nanotechnology [@Seeman2003], molecular electronics [@Porath2000], and radiation biology [@Sanche2005].

The need for accessible electron count calculations has grown with advances in understanding DNA's role as a molecular conductor and the development of DNA-based nanostructures. Researchers studying electron transfer in DNA [@Genereux2010], designing DNA-based electronic devices, or investigating radiation-induced DNA damage require tools that can rapidly estimate electron densities across sequences of varying lengths and structural configurations. Existing quantum chemistry software packages, while accurate, are designed for detailed calculations on small systems and are not practical for genomic-scale analysis or integration into bioinformatics workflows.

`dna-electrons` fills this critical gap by democratizing access to fundamental electronic properties of DNA sequences, enabling researchers without extensive computational chemistry expertise to incorporate electronic considerations into their studies.

# Methods

The computational methodology implemented in `dna-electrons` is based on the additive principle of electron counting, where the total electron count of a DNA sequence is calculated as the sum of contributions from individual components: nucleotide bases, sugar-phosphate backbone, and phosphate charges when applicable.

The core algorithm employs predefined electron counts for each DNA base derived from their molecular formulas: adenine (C5H5N5, 70 electrons), thymine (C5H6N2O2, 66 electrons), guanine (C5H5N5O, 78 electrons), and cytosine (C4H5N3O, 58 electrons). For backbone calculations, the package accounts for the 2'-deoxyribose sugar (70 electrons) and phosphate groups (49 electrons each), totaling 238 electrons per base pair for double-stranded DNA without considering ionic charges.

The software architecture follows modular design principles with separate components for sequence validation, electron counting, FASTA file processing, and result presentation. Sequence validation ensures input contains only valid DNA bases (A, T, G, C) and provides detailed error reporting for invalid characters. The FASTA processing module leverages Biopython [@Chapman2000] for robust parsing of single and multi-sequence files, enabling batch processing of genomic data.

Command-line functionality is implemented using Python's argparse module, providing intuitive options for specifying input sources (direct sequence or FASTA file), structural parameters (single- or double-stranded), and component inclusion toggles. Output formats include human-readable text, CSV for data analysis integration, and JSON for programmatic consumption.

# Results

`dna-electrons` provides comprehensive electron counting capabilities through both command-line and programmatic interfaces. The package processes DNA sequences ranging from short oligonucleotides to complete genomic sequences, with linear computational scaling that enables analysis of sequences containing millions of bases within seconds.

Key features include:

1. **Flexible Input Processing**: Supports direct sequence input via command-line arguments or FASTA file processing for batch analysis of multiple sequences with automatic sequence ID preservation.

2. **Configurable Structural Parameters**: Users can specify single- or double-stranded DNA configurations, with automatic complement generation for double-stranded calculations.

3. **Component-wise Analysis**: Provides detailed breakdowns showing contributions from nucleotide bases, sugar-phosphate backbone, and phosphate charges, enabling researchers to understand the relative importance of different structural components.

4. **High-throughput Compatibility**: FASTA processing capabilities enable analysis of entire genomes or large sequence datasets with results exportable in CSV format for integration with statistical analysis pipelines.

5. **Validation and Error Handling**: Comprehensive input validation ensures data integrity with clear error messages for sequences containing non-standard bases.

For example, analyzing the sequence "ATGCAT" as double-stranded DNA with full backbone and charge inclusion yields: 816 electrons from bases, 1,428 from backbone components, and charge adjustments, providing researchers with quantitative data for downstream modeling applications.

The package has been validated against manual calculations for diverse sequence types and demonstrates consistent accuracy across different DNA structural motifs including A-form, B-form, and Z-form configurations when appropriate electron counts are applied.

# Availability

The `dna-electrons` package is freely available through the Python Package Index (PyPI) at https://pypi.org/project/dna-electrons/ for easy installation via pip. Complete source code, documentation, and examples are maintained in the GitHub repository at https://github.com/yashmgupta/dna-electrons under the MIT License, ensuring reproducibility and community collaboration. The repository includes comprehensive installation instructions, usage examples, and API documentation to support both novice and advanced users.

# Acknowledgements

The author acknowledges the computational resources and support provided by the Department of Biology, Faculty of Science, Naresuan University, Thailand. Special thanks to the open-source Biopython project for providing robust biological sequence processing capabilities that enhance this package's functionality.

# References
