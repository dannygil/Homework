# Homework

setwd("/Users/bioinformaticsteam/Desktop/data/3219685")

seqdata <- read.delim("GSE60450_Lactation-GenewiseCounts.txt", stringsAsFactors = FALSE
                      
myCPM <- cpm(countdata)

plot(myCPM[,2],countdata[,2])
plot(myCPM[,2],countdata[,2],ylim=c(0,50),xlim=c(0,3))
abline(v=0.5,col="blue")
abline(h=10,col="blue")

sampleinfo <- read.delim("SampleInfo_Corrected.txt")
par(mfrow=c(1,1))
col.virgin <- c("orange")
col.pregnant <- c("purple")
col.lactate <- c("red")
pch.basal <- c("1")
pch.luminal <- c("4")
pch.celltype <- c("1","4")[sampleinfo$CellType]
col.status <- c("red","orange","purple")[sampleinfo$Status]
plotMDS(y,col=col.status,pch=c(1,1,1,1,1,1,4,4,4,4,4,4))
legend("topleft",fill=c("red","purple","orange"),legend=levels(sampleinfo$Status),cex=0.8)
legend("bottom",legend=levels(sampleinfo$CellType),pch=c(1,4))
