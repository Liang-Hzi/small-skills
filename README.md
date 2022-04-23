# small-skills
###export excel
install.packages("writexl")
library("writexl")
write_xlsx(a,"/Users/lzh21/Downloads/AB.xlsx")

### CHANGE EXCEL IN R
setwd("Documents/CMV/")
phenotype <- read.xlsx("database.xlsx", sep='\t')
SampleID <- fread('sampleID_GEO (2).txt',sep = ",", header = T) 
reads <- read_tsv("mapped_cmvreads.tsv", col_names = FALSE)
SampleID$reads <- reads$X3

idx <- match(SampleID$externalSampleID, phenotype$ID_500fg)
SampleID$EBV <- phenotype$EBV[idx]
SampleID$CMV <- phenotype$CMV[idx]

Cell Ranger ATAC
cd /vol/data/gmak/runs/raw/novaseq$ ll
lzhou@bioinf002:/vol/data/gmak/runs/raw/novaseq$ cat 220412_A00704_0084_AHTKCMDRXY

lzhou@bioinf002:/vol/projects/lzhou$ mkdir IBD
lzhou@bioinf002:/vol/projects/lzhou$ cd IBD/
lzhou@bioinf002:/vol/projects/lzhou/IBD$ mkdir ATAC
lzhou@bioinf002:/vol/projects/lzhou/IBD$ cd ATAC/
lzhou@bioinf002:/vol/projects/lzhou/IBD/ATAC$ vi makefq.sh   rm makefq.sh
vi makefq.sh    vim makefq.sh
(copy)cp /vol/projects/CIIM/MHH_projects/Hepatology/LiverTX/citeseq/sample.csv samplesheet.csv

(base) lzhou@bioinf002:/vol/projects/lzhou/IBD/ATAC$ ll
total 16
drwxr-xr-x 2 lzhou clusers 4096 Apr 22 15:08 ./
drwxr-xr-x 3 lzhou clusers 4096 Apr 22 14:54 ../
-rw-r--r-- 1 lzhou clusers  576 Apr 22 15:05 makefq.sh
-rw-r--r-- 1 lzhou clusers  115 Apr 22 15:08 samplesheet.csv
(base) lzhou@bioinf002:/vol/projects/lzhou/IBD/ATAC$ l
makefq.sh  samplesheet.csv

(base) lzhou@bioinf002:/vol/projects/lzhou/IBD/ATAC$ vim samplesheet.csv       wq q i x 1
(base) lzhou@bioinf002:/vol/projects/lzhou/IBD/ATAC$ rm makefq.sh 
(base) lzhou@bioinf002:/vol/projects/lzhou/IBD/ATAC$ vi makefq.sh
(base) lzhou@bioinf002:/vol/projects/lzhou/IBD/ATAC$ cat makefq.sh 
(base) lzhou@bioinf002:/vol/projects/lzhou/IBD/ATAC$ vim samplesheet.csv 
(base) lzhou@bioinf002:/vol/projects/lzhou/IBD/ATAC$ cat samplesheet.csv 


(base) lzhou@bioinf002:/vol/projects/lzhou/IBD/ATAC$ qsub makefq.sh 
Your job 1171798 ("scATAC_mkfastq") has been submitted
(base) lzhou@bioinf002:/vol/projects/lzhou/IBD/ATAC$ qstat
(base) lzhou@bioinf002:/vol/projects/lzhou/IBD/ATAC$ l
log.mkfastq.err  log.mkfastq.out  makefq.sh  samplesheet.csv
(base) lzhou@bioinf002:/vol/projects/lzhou/IBD/ATAC$ cat log.mkfastq.err
(base) lzhou@bioinf002:/vol/projects/lzhou/IBD/ATAC$ rm l*

(base) lzhou@bioinf002:/vol/projects/lzhou/IBD/ATAC$ cd ../../../CIIM/IBD/
(base) lzhou@bioinf002:/vol/projects/CIIM/IBD$ ll

lzhou@bioinf002:/vol/projects/CIIM/IBD/scATAC$ ll
total 28
drwxrwxr-x 3 mzoodsma clusers 4096 Apr 22 16:30 ./
drwxrwxr-x 5 bzhang   clusers 4096 Apr 22 15:58 ../
drwxrwxr-x 5 mzoodsma clusers 4096 Apr 22 16:30 fastq_pools4_5/
-rw-rw-r-- 1 mzoodsma clusers 1264 Apr 22 16:30 __fastq_pools4_5.mro
-rw-r--r-- 1 mzoodsma clusers    0 Apr 22 16:30 log.mkfastq.err
-rw-r--r-- 1 mzoodsma clusers 1760 Apr 22 16:43 log.mkfastq.out
-rwxr-xr-x 1 mzoodsma clusers  452 Apr 22 16:00 makefq.sh*
-rw-r--r-- 1 mzoodsma clusers   91 Apr 22 16:28 samplesheet.csv

(base) lzhou@bioinf002:/vol/projects/CIIM/IBD/scATAC$ tail log.mkfastq.out 
Checking samplesheet specs...
2022-04-22 16:30:43 [runtime] (ready)           ID.fastq_pools4_5.MAKE_FASTQS_CS.MAKE_FASTQS.PREPARE_SAMPLESHEET
2022-04-22 16:30:43 [runtime] (run:local)       ID.fastq_pools4_5.MAKE_FASTQS_CS.MAKE_FASTQS.PREPARE_SAMPLESHEET.fork0.chnk0.main
2022-04-22 16:30:46 [runtime] (chunks_complete) ID.fastq_pools4_5.MAKE_FASTQS_CS.MAKE_FASTQS.PREPARE_SAMPLESHEET
2022-04-22 16:30:47 [runtime] (ready)           ID.fastq_pools4_5.MAKE_FASTQS_CS.MAKE_FASTQS.BCL2FASTQ_WITH_SAMPLESHEET
2022-04-22 16:30:47 [runtime] (run:local)       ID.fastq_pools4_5.MAKE_FASTQS_CS.MAKE_FASTQS.BCL2FASTQ_WITH_SAMPLESHEET.fork0.split
2022-04-22 16:30:47 [runtime] (split_complete)  ID.fastq_pools4_5.MAKE_FASTQS_CS.MAKE_FASTQS.BCL2FASTQ_WITH_SAMPLESHEET
2022-04-22 16:30:47 [runtime] (run:local)       ID.fastq_pools4_5.MAKE_FASTQS_CS.MAKE_FASTQS.BCL2FASTQ_WITH_SAMPLESHEET.fork0.chnk0.main
2022-04-22 16:36:48 [runtime] (update)          ID.fastq_pools4_5.MAKE_FASTQS_CS.MAKE_FASTQS.BCL2FASTQ_WITH_SAMPLESHEET.fork0 chunks_running
2022-04-22 16:42:49 [runtime] (update)          ID.fastq_pools4_5.MAKE_FASTQS_CS.MAKE_FASTQS.BCL2FASTQ_WITH_SAMPLESHEET.fork0 chunks_running

(base) lzhou@bioinf002:/vol/projects/CIIM/IBD/scATAC$ cat makefq.sh
#! /bin/bash

#$ -N scATAC_mkfastq
#$ -l arch=linux-x64
#$ -pe multislot 8
#$ -b n
#$ -i /dev/null
#$ -o log.mkfastq.out
#$ -e log.mkfastq.err
#$ -q all.q
#$ -l vf=8G
#$ -cwd

export PATH=/vol/projects/CIIM/resources/tools/cellranger-arc-2.0.1:$PATH
export PATH=/vol/biotools/bin:$PATH
cellranger-arc --version
cellranger-arc mkfastq --id=fastq_pools4_5 \
  --run=/vol/data/gmak/runs/raw/novaseq/220412_A00704_0084_AHTKCMDRXY \
  --csv=samplesheet.csv
