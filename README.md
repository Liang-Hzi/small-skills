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




############### cellranger-atac count

aalaswas@bioinf001:/vol/projects/CIIM/IBD/scATAC$ ll
total 28
drwxrwxr-x+ 3 mzoodsma clusers 4096 Apr 22 17:14 ./
drwxrwxr-x+ 5 bzhang   clusers 4096 Apr 22 15:58 ../
drwxrwxr-x+ 4 mzoodsma clusers 4096 Apr 22 17:14 fastq_pools4_5/
-rw-r--r--+ 1 mzoodsma clusers    0 Apr 22 16:30 log.mkfastq.err
-rw-r--r--+ 1 mzoodsma clusers 4461 Apr 22 17:14 log.mkfastq.out
-rwxr-xr-x+ 1 mzoodsma clusers  452 Apr 22 16:00 makefq.sh*
-rw-r--r--+ 1 mzoodsma clusers   91 Apr 22 16:28 samplesheet.csv
aalaswas@bioinf001:/vol/projects/CIIM/IBD/scATAC$ cat makefq.sh 
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
  
  aalaswas@bioinf001:/vol/projects/CIIM/IBD/scATAC$ tail log.mkfastq.out
Outputs:
- FASTQ output folder:   /vol/projects/BIIM/IBD/scATAC/fastq_pools4_5/outs/fastq_path
- Interop output folder: /vol/projects/BIIM/IBD/scATAC/fastq_pools4_5/outs/interop_path
- Input samplesheet:     /vol/projects/BIIM/IBD/scATAC/fastq_pools4_5/outs/input_samplesheet.csv

Waiting 6 seconds for UI to do final refresh.
Pipestance completed successfully!
2022-04-22 17:14:06 Shutting down.
Saving pipestance info to "fastq_pools4_5/fastq_pools4_5.mri.tgz"

aalaswas@bioinf001:/vol/projects/CIIM/IBD/scATAC$ ll
total 28
drwxrwxr-x+ 3 mzoodsma clusers 4096 Apr 22 17:14 ./
drwxrwxr-x+ 5 bzhang   clusers 4096 Apr 22 15:58 ../
drwxrwxr-x+ 4 mzoodsma clusers 4096 Apr 22 17:14 fastq_pools4_5/
-rw-r--r--+ 1 mzoodsma clusers    0 Apr 22 16:30 log.mkfastq.err
-rw-r--r--+ 1 mzoodsma clusers 4461 Apr 22 17:14 log.mkfastq.out
-rwxr-xr-x+ 1 mzoodsma clusers  452 Apr 22 16:00 makefq.sh*
-rw-r--r--+ 1 mzoodsma clusers   91 Apr 22 16:28 samplesheet.csv
aalaswas@bioinf001:/vol/projects/CIIM/IBD/scATAC$ cd fastq_pools4_5/
aalaswas@bioinf001:/vol/projects/CIIM/IBD/scATAC/fastq_pools4_5$ ll
total 372
drwxrwxr-x+ 4 mzoodsma clusers   4096 Apr 22 17:14 ./
drwxrwxr-x+ 3 mzoodsma clusers   4096 Apr 22 17:14 ../
-rw-rw-r--+ 1 mzoodsma clusers     78 Apr 22 17:14 _cmdline
-rw-rw-r--+ 1 mzoodsma clusers 136100 Apr 22 17:14 fastq_pools4_5.mri.tgz
-rw-rw-r--+ 1 mzoodsma clusers   5374 Apr 22 17:14 _filelist
-rw-r--r--+ 1 mzoodsma clusers  87426 Apr 22 17:14 _finalstate
-rw-r--r--+ 1 mzoodsma clusers   1264 Apr 22 16:30 _invocation
-rw-r--r--+ 1 mzoodsma clusers      5 Apr 22 16:30 _jobmode
-rw-r--r--+ 1 mzoodsma clusers  12185 Apr 22 17:14 _log
drwxrwxr-x+ 4 mzoodsma clusers   4096 Apr 22 16:30 MAKE_FASTQS_CS/
-rw-r--r--+ 1 mzoodsma clusers  11981 Apr 22 16:30 _mrosource
drwxrwxr-x+ 4 mzoodsma clusers   4096 Apr 22 17:14 outs/
-rw-r--r--+ 1 mzoodsma clusers  40696 Apr 22 17:14 _perf
-rw-rw-r--+ 1 mzoodsma clusers  26401 Apr 22 17:14 _sitecheck
-rw-r--r--+ 1 mzoodsma clusers      2 Apr 22 16:30 _tags
-rw-r--r--+ 1 mzoodsma clusers     51 Apr 22 17:14 _timestamp
-rw-r--r--+ 1 mzoodsma clusers     36 Apr 22 16:30 _uuid
-rw-r--r--+ 1 mzoodsma clusers   1162 Apr 22 17:14 _vdrkill
-rw-r--r--+ 1 mzoodsma clusers     68 Apr 22 16:30 _versions
aalaswas@bioinf001:/vol/projects/CIIM/IBD/scATAC/fastq_pools4_5$ cd outs/

aalaswas@bioinf001:/vol/projects/CIIM/IBD/scATAC/fastq_pools4_5/outs/fastq_path$ ll
total 6829556
drwxrwxr-x+ 5 mzoodsma clusers       4096 Apr 22 17:12 ./
drwxrwxr-x+ 4 mzoodsma clusers       4096 Apr 22 17:14 ../
drwxrwxr-x+ 4 mzoodsma clusers       4096 Apr 22 17:13 HTKCMDRXY/
drwxrwxr-x+ 3 mzoodsma clusers       4096 Apr 22 17:12 Reports/
drwxrwxr-x+ 2 mzoodsma clusers       4096 Apr 22 17:12 Stats/
-rw-rw-r--+ 1 mzoodsma clusers  320474677 Apr 22 16:51 Undetermined_S0_L001_I1_001.fastq.gz
-rw-rw-r--+ 1 mzoodsma clusers 1206954690 Apr 22 16:51 Undetermined_S0_L001_R1_001.fastq.gz
-rw-rw-r--+ 1 mzoodsma clusers  642414162 Apr 22 16:51 Undetermined_S0_L001_R2_001.fastq.gz
-rw-rw-r--+ 1 mzoodsma clusers 1290339368 Apr 22 16:51 Undetermined_S0_L001_R3_001.fastq.gz
-rw-rw-r--+ 1 mzoodsma clusers  328066721 Apr 22 17:11 Undetermined_S0_L002_I1_001.fastq.gz
-rw-rw-r--+ 1 mzoodsma clusers 1229345082 Apr 22 17:11 Undetermined_S0_L002_R1_001.fastq.gz
-rw-rw-r--+ 1 mzoodsma clusers  659606599 Apr 22 17:11 Undetermined_S0_L002_R2_001.fastq.gz
-rw-rw-r--+ 1 mzoodsma clusers 1316228742 Apr 22 17:11 Undetermined_S0_L002_R3_001.fastq.gz
aalaswas@bioinf001:/vol/projects/CIIM/IBD/scATAC/fastq_pools4_5/outs/fastq_path$ ll -ha
total 6.6G
drwxrwxr-x+ 5 mzoodsma clusers 4.0K Apr 22 17:12 ./
drwxrwxr-x+ 4 mzoodsma clusers 4.0K Apr 22 17:14 ../
drwxrwxr-x+ 4 mzoodsma clusers 4.0K Apr 22 17:13 HTKCMDRXY/
drwxrwxr-x+ 3 mzoodsma clusers 4.0K Apr 22 17:12 Reports/
drwxrwxr-x+ 2 mzoodsma clusers 4.0K Apr 22 17:12 Stats/
-rw-rw-r--+ 1 mzoodsma clusers 306M Apr 22 16:51 Undetermined_S0_L001_I1_001.fastq.gz
-rw-rw-r--+ 1 mzoodsma clusers 1.2G Apr 22 16:51 Undetermined_S0_L001_R1_001.fastq.gz
-rw-rw-r--+ 1 mzoodsma clusers 613M Apr 22 16:51 Undetermined_S0_L001_R2_001.fastq.gz
-rw-rw-r--+ 1 mzoodsma clusers 1.3G Apr 22 16:51 Undetermined_S0_L001_R3_001.fastq.gz
-rw-rw-r--+ 1 mzoodsma clusers 313M Apr 22 17:11 Undetermined_S0_L002_I1_001.fastq.gz
-rw-rw-r--+ 1 mzoodsma clusers 1.2G Apr 22 17:11 Undetermined_S0_L002_R1_001.fastq.gz
-rw-rw-r--+ 1 mzoodsma clusers 630M Apr 22 17:11 Undetermined_S0_L002_R2_001.fastq.gz
-rw-rw-r--+ 1 mzoodsma clusers 1.3G Apr 22 17:11 Undetermined_S0_L002_R3_001.fastq.gz

HTKCMDRXY/aalaswas@bioinf001:/vol/projects/CIIM/IBD/scATAC/fastq_pools4_5/outs/fastq_path/HTKCMDRXY$ ll
aalaswas@bioinf001:/vol/projects/CIIM/IBD/scATAC/fastq_pools4_5/outs/fastq_path/HTKCMDRXY$ cd atac4
aalaswas@bioinf001:/vol/projects/CIIM/IBD/scATAC/fastq_pools4_5/outs/fastq_path/HTKCMDRXY/atac4$ ll
total 38258732
drwxrwxr-x+ 2 mzoodsma clusers       4096 Apr 22 17:13 ./
drwxrwxr-x+ 4 mzoodsma clusers       4096 Apr 22 17:13 ../
-rw-rw-r--+ 1 mzoodsma clusers 1318551267 Apr 22 17:12 atac4_S1_L001_I1_001.fastq.gz
-rw-rw-r--+ 1 mzoodsma clusers 7203200052 Apr 22 17:13 atac4_S1_L001_R1_001.fastq.gz
-rw-rw-r--+ 1 mzoodsma clusers 3729608629 Apr 22 17:13 atac4_S1_L001_R2_001.fastq.gz
-rw-rw-r--+ 1 mzoodsma clusers 7448078899 Apr 22 17:13 atac4_S1_L001_R3_001.fastq.gz
-rw-rw-r--+ 1 mzoodsma clusers 1309697335 Apr 22 17:12 atac4_S1_L002_I1_001.fastq.gz
-rw-rw-r--+ 1 mzoodsma clusers 7130142626 Apr 22 17:13 atac4_S1_L002_R1_001.fastq.gz
-rw-rw-r--+ 1 mzoodsma clusers 3682392990 Apr 22 17:13 atac4_S1_L002_R2_001.fastq.gz
-rw-rw-r--+ 1 mzoodsma clusers 7355250013 Apr 22 17:13 atac4_S1_L002_R3_001.fastq.gz

aalaswas@bioinf001:/vol/projects/CIIM/IBD/scATAC/fastq_pools4_5/outs/fastq_path/HTKCMDRXY/atac5$ cd ../../
aalaswas@bioinf001:/vol/projects/CIIM/IBD/scATAC/fastq_pools4_5/outs/fastq_path$ cd ../../
aalaswas@bioinf001:/vol/projects/CIIM/IBD/scATAC/fastq_pools4_5$ cd ../
aalaswas@bioinf001:/vol/projects/CIIM/IBD/scATAC$ ll
total 28
drwxrwxr-x+ 3 mzoodsma clusers 4096 Apr 22 17:14 ./
drwxrwxr-x+ 5 bzhang   clusers 4096 Apr 22 15:58 ../
drwxrwxr-x+ 4 mzoodsma clusers 4096 Apr 22 17:14 fastq_pools4_5/
-rw-r--r--+ 1 mzoodsma clusers    0 Apr 22 16:30 log.mkfastq.err
-rw-r--r--+ 1 mzoodsma clusers 4461 Apr 22 17:14 log.mkfastq.out
-rwxr-xr-x+ 1 mzoodsma clusers  452 Apr 22 16:00 makefq.sh*
-rw-r--r--+ 1 mzoodsma clusers   91 Apr 22 16:28 samplesheet.csv
aalaswas@bioinf001:/vol/projects/CIIM/IBD/scATAC$ rm l*

aalaswas@bioinf001:/vol/projects/CIIM/IBD/scATAC$ vi count4.sh
aalaswas@bioinf001:/vol/projects/CIIM/IBD/scATAC$ ll
aalaswas@bioinf001:/vol/projects/CIIM/IBD/scATAC$ qsub count4.sh  qstat 
aalaswas@bioinf001:/vol/projects/CIIM/IBD/scATAC$ cat log.count.err
aalaswas@bioinf001:/vol/projects/CIIM/IBD/scATAC$ vim count4.sh 
aalaswas@bioinf001:/vol/projects/CIIM/IBD/scATAC$ qsub count4.sh 
aalaswas@bioinf001:/vol/projects/CIIM/IBD/scATAC$ tail log.count.out 

aalaswas@bioinf001:/vol/projects/CIIM/IBD/scATAC$ vim count5.sh 
aalaswas@bioinf001:/vol/projects/CIIM/IBD/scATAC$ cat count5.sh 
aalaswas@bioinf001:/vol/projects/CIIM/IBD/scATAC$ tail log.count.out
