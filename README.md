# dacinicoiblast
BLAST database with COI reference sequences for Dacini fruit flies

This repository has a Basic Local Alignment Search Tool (BLAST) database that includes the COI reference sequences for Dacini fruit flies that were published in Doorenweerd et al. (2024), with several identification updates from Doorenweerd et al. (2025). The sequences are also available in the public NCBI Genbank and Barcoding of Life databases but identifications there may be hampered by innaccurately identified reference sequences from other sources. The sequences are therefore made available here as a convenient way to quickly get COI-based identifications through BLAST based on the reference dataset as published.

## Prerequisites
Have BLAST+ suite installed. Install BLAST+ through the installers available at https://blast.ncbi.nlm.nih.gov/doc/blast-help/downloadblastdata.html or through Anaconda https://anaconda.org/bioconda/blast

## Installation
Clone or download this github repository, which includes all the necessary BLAST database files.

## Suggested usage
Copy your query sequence in fasta format 'X.fasta' into the folder that has the BLAST database. Run the blastn command as following:

```
blastn -db 20250227_dacini_COI_1493.fas -query X.fasta -out results.out -max_target_seqs 10 -outfmt 10
```

Adjust the parameters and results format as needed, see ```blastn -h``` for options. The format above includes the number of mismatches with the ten closest hits, from which you can easily calculate the p-distance as 1-(mismatch / compared length).

## References
Doorenweerd C, San Jose M, Leblanc L, Barr N, Geib SM, Chung AYC, Dupuis JR, Ekayanti A, Fiegalan E, Hemachandra KS, Hossain MA, Huang C, Hsu Y, Morris KY, Maryani A. Mustapeng A, Niogret J, Pham TH, Thi Nguyen N, Sirisena UGAI, Todd T, Rubinoff D (2024) Towards a better future for DNA barcoding: Evaluating monophyly‐ and distance‐based species identification using COI gene fragments of Dacini fruit flies. Molecular Ecology Resources: e13987. https://doi.org/10.1111/1755-0998.13987 

- Doorenweerd et al. 2025: a checklist for the Dacini of Borneo

## Notes
> makeblastdb -in 20250227_dacini_COI_1493.fas -dbtype 'nucl' -out 20250227Dacini