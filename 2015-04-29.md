---
title: April 29th Notes
layout: post
date: 2015-04-29
category : notes
tags : []
---
{% include JB/setup %}

### daily notes

1. data time from 9:30 to 11 am

2. 11 am into afternoon - worked on script to *in silico* test error rate on clustering of large data sets

Original script idea:
  * took 1000 16S sequences from greengenes in rough composition of normal alpha diversity curve for soil
  * used bwa synthesis module to make amplicon copies with various error (0.01, 0.02, 0.03, etc.) rates
  * Need better consideration for
    1. Taq polymerase data errors, and
    2. overall sequencing error of Illumina platform and read degeneration after (average) of 600 cycles for MiSeq run

Need better integration with actual Mock community sequencing to understand the role of amplicon PCR fidelity and sequencing error on number of OTUs generated from mock community.
