---
title: April 30th Notes
layout: post
date: 2015-04-30
category : notes
tags : []
---
{% include JB/setup %}

## Notes

9:30 am to 11:00 am - Continued working on sequencing error script from day before.

11:00 am to 12:00 - Xuemei Chen presentation

12:00 to 5:00 pm - figuring out baseline error rates and how that would translate to OTU


#### Notes on sequencing errors and proliferation of OTUs for today

See following papers:

  1. [Insight into biases and sequencing errors for amplicon sequencing with the Illumina MiSeq platform](http://nar.oxfordjournals.org/content/early/2015/01/13/nar.gku1341.full)

  2. [Characterizing and measuring bias in sequence data](http://link.springer.com/article/10.1186/gb-2013-14-5-r51)

  3. [A tale of three next generation sequencing platforms: comparison of Ion Torrent, Pacific Biosciences and Illumina MiSeq sequencers](http://www.biomedcentral.com/1471-2164/13/341)

[Other post on MiSeq errors on 600 cycle run](http://seqanswers.com/forums/showthread.php?t=40879)

#### Error rates of polymerase from experimental data

[Error Rate Comparison during Polymerase Chain Reaction by DNA Polymerase](http://www.hindawi.com/journals/mbi/2014/287430/)

[New England Biolabs DNA Polymerase Selection Chart](https://www.neb.com/tools-and-resources/selection-charts/dna-polymerase-selection-chart)

**Table: Error rates of different brands of polymerase from above paper**

| Enzyme | Average doubling per reaction (192 rxns)  | Error rate (percent) | Code |
|--------------|---------------------------|------------------------------|----------------|
| Crimson & Taq Standard DNA Polymerase | NA | 0.000285 | Crimson |
| VentR® (exo–) DNA Polymerase | NA | 0.00019 | VentRexo |
| Large (Klenow) Fragment | NA | 0.00018 | LargeKlenow |
| LongAmp® & OneTaq® Polymerase | NA | 0.00014 | LongAmp |
| Klenow Fragment (3′→5′ exo-) | NA | 0.0001 | Klenow |
| VentR® DNA Polymerase | NA | 0.000057 | VentR |
| Taq | 18.6 +/- 0.95 | 0.000043 | Taq |
| T7 DNA Polymerase (unmodified) | NA | 0.000015 | T7 |
| AccuPrime-Taq  | 16.95 +/- 0.90 | 0.00001  | AccuPrime |
| E. coli DNA Polymerase I | NA | 0.000009 | Ecoli |
| KOD | 19.2 +/- 1.15 | 0.0000076  | KOD |
| Pfu (cloned) | 14.25 +/- 1.00 | 0.0000028  | Pfu |
| Phusion | 18.8 +/- 1.50 | 0.0000026  | Phusion |
| Pwo | 20.05 +/- 0.90 | 0.0000024  | Pwo |
| Template Lesions T4 DNA Polymerase | NA | 0.000001 | TemplateT4 |
| Flex & Phusion® DNA Polymerase | NA | 0.00000044 | Flex |

[Earth Microbiome protocol](http://www.earthmicrobiome.org/emp-standard-protocols/16s/) reports pcr for 35 cycles.

#### script desciption notes

Wrote script for each error polymerase type - see: ```mock_OTU_qsub_write.sh``` for qsub script generator.

[wgsim](https://github.com/lh3/wgsim) won't work for amplicon data, so I built off of the Grinder script from this paper: [Grinder: a versatile amplicon and shotgun sequence simulator](http://nar.oxfordjournals.org/content/40/12/e94)

For Grinder to work, the script needs to be compiled with perl on linux based computers (BSD Mac); ```cpan``` needs to be invoked (for my perl installation on Mac, YMMV on other linux kernels):
```sudo cpan -i Getopt::Euclid && sudo cpan -i Math::Random::MT```
