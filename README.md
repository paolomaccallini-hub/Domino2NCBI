This R script adds NCBI Gene IDs to the gene list for which the DOMINO tool provides the probability of a dominant inheritance pattern. The script leverages the rentrez package to retrieve NCBI Gene IDs by querying the gene names. It streamlines the process of mapping genes from DOMINO predictions to their corresponding NCBI entries, making further genetic analysis more efficient.
Tools and References:

    DOMINO: A tool that predicts the dominance likelihood of human genetic variants. DOMINO website: https://domino.iob.ch/
    rentrez: An R package for interacting with NCBI databases. rentrez CRAN: https://cran.r-project.org/web/packages/rentrez/index.html
