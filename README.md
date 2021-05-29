# Name
genome_ref_cal.sh: Script for inferring the genome reference from a vcf file. Works with genome ref grch37, grch38 and hg17.

# Synopsis

This script allows to calculate the genome reference from a vcf file.

We created a dictionary consisting of unique chr/pos/ref in hg17, grch37, grch38 reference genomes.

The script searches for matches in the 3 dicts and outputs (infer_ref) the reference genome having more matches.

A maximum of 10K variants per chromosome are analyzed. Also a maximum of 100 matches per chromosome are analyzed.

The script includes the dictionaries for inferring the genome reference.

# How to run

Before running it for the first time you need to set the variable 'path_dic' inside 'genome_ref_cal.sh'.
In the installation directory the dictionaries are inside a folder named './ref_dics'

The script is written in _Bash_ and uses standard bash commands. The script was tested on Debian-based i(e.g., Ubuntu, Mint) distributions.

Please note that input vcf file has to be gzipped (or bgzipped).


```
bash /path/genome_ref_cal.sh input.vcf.gz
```

Once run you should check if the number of matches in the inferred genome reference is confident for you (displayed in \*.final). We have established a number of 100 matches in just one genome reference to be confident although you may consider another cutoff.

Intermediate files with information regarding the variants matching the reference genome are deleted (file \*.variants) but you may be interested in checking them just in case you find some inconsistencies (e.g matches in more than one genome ref).

# Demo

Demo folder contains a subset of vcf from chromosome 22 from 1000 Genomes data for testing purposes.

1. \*.final: contains total number of matches for each genome reference.
2. \*.demo_subset.chr: file generated with the number of variants per chromosome present in the demo vcf.
4. infer_ref: contains the inferred genome reference.
5. log: A log file of the STDOUT.

# Author

Written by Dietmar Fernandez, PhD. Info about EGA can be found at https://ega-archive.org/.


# Copyright

This Bash script is copyrighted. See the LICENSE file included in this distribution.
