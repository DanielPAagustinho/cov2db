# cov2db : a low frequency variant DB for SARS-CoV-2

## Problem statement
VCF files storing low frequency info for SARS-CoV-2 are not widely available due to their size and limited downstream usage to date. However, there are over 1.2 million sequenced datasets in ENA/SRA from COVID-19 samples, representing a unique opportunity to create a community resource for query and tracking intrahost viral evolution. The goal of this hackathon project is to create an easy to use database for the community that is able to store SARS-CoV-2 low frequency/intrahost variants.

## Team members
* Daniel Agustinho, Washington University (data acquisition, writer) <br>
* Li Chuin Chong, Twincore GmbH/HZI-DKFZ under auspices MHH (Sysadmin, mongodb) <br>
* Maria Jose, Pondicherry Central University (data acquisition, mongodb)
* BaiWei Lo, University of Konstanz (data acquisition, QC) <br>
* Ramanandan Prabhakaran, Roche Canada (Sysadmin, mongodb) <br>
* Nick Sapoval, Rice University (Team co-lead, data acquisition, writer) <br>
* Todd Treangen (Team Lead) <br>

## Related work
[VAPr](https://github.com/ucsd-ccbb/VAPr/) is an excellent mongodb based database for storing variant info. USCS SARS-CoV-2 genome broswers also provides visualization of intrahost variants [here](https://genome.ucsc.edu/cgi-bin/hgTracks?db=wuhCor1&lastVirtModeType=default&lastVirtModeExtraState=&virtModeType=default&virtMode=0&nonVirtPosition=&position=NC_045512v2%3A1%2D29903&hgsid=1183075721_4GlEuE8o51gGamZyAQfT5UgwpPhq). 

## Workflow figure
![covid db workflow figure](https://github.com/collaborativebioinformatics/covid_freq/blob/main/coviddb_workflow.png)

------
## cov2db will contain the following information:
* ENA/SRA id (and bioproject)
- [ ] assigned lineage/VOC of SRA sample
- [ ] geographic location 
- [ ] sample collection date
- [ ] sequencing type (amplicon, shotgun, etc)
- [ ] sequencing platform (ONT, Illumina, pacbio)
- [ ] total number of reads

* Reference genome (wuhan)
- [ ] accession
- [ ] location of fasta
- [ ] length/md5

* VCF variant alleles for SRA
- [ ] variant type (SNV, etc)
- [ ] variant position 
- [ ] variant frequency
- [ ] variant coverage
- [ ] pvalue (if available)
- [ ] synonymous/nonsynonymous mutation 
- [ ] gene containing variant
- [ ] variant caller (program, iVar, lofreq, etc) 
- [ ] version 
- [ ] parameters

#### Queries to support
* Has intrahost variant V1 been previously observed? If so, when and where? 
* Show me a histogram of frequency of intrahost variants across the reference (for all data in the database)
* filter intrahost variants by pvalue, min coverage, variant caller, etc

------

