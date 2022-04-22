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
