# ONT-Smith-Waterman-INDEL-Validation

## Description

A Bash pipeline for validating nanopore sequencing read alignments
using Smith-Waterman local alignment.

The workflow extracts reads containing candidate variants from BAM
alignment files and performs independent local alignment against the
reference region.

## Workflow

BAM
 |
 | samtools view
 |
Candidate reads
 |
 | seqkit extraction
 |
FASTQ reads
 |
 | EMBOSS water
 |
Smith-Waterman alignment
 |
Variant summary


## Features

- Extracts reads overlapping a genomic region
- Performs local Smith-Waterman alignment
- Calculates:
    - Identity
    - Similarity
    - Gaps
    - Alignment score
    - SNP count
    - Insertions
    - Deletions
    - CIGAR statistics


## Requirements

- samtools
- seqkit
- EMBOSS water


## Usage

Modify:

GENOME
BAM
FASTQ
CHR
START
END


Run:

bash smith_waterman_pipeline.sh


## Output

reports/alignment_summary.tsv

Contains:

Read ID
Identity
Similarity
Gaps
Score
MAPQ
CIGAR
SNPs
Insertion events
Deletion events


## Application

Designed for validation of nanopore sequencing alignment errors
and detection of small INDEL events.
