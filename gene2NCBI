# file name: gene2NCBI
#
# Rome 14 September 2024
#
# This script adds the NCBI gene ID to the file with DOMINO score
#
library(rentrez) # for NCBI database
#
#-------------------------------------------------------------------------------
# Convert gene symbol to NCBI ID 
#-------------------------------------------------------------------------------
#
Symbol2NCBI<-function(gene.symbol) {
  NCBI<-lapply(gene.symbol,function(gene) {
    search<-entrez_search(db="gene",term=paste(gene,"[Gene Name] AND human[Organism]"))
  })
  NCBI<-NCBI[[1]]$ids[1]
  NCBI<-paste0("NCBIGene:",NCBI)
  return(NCBI)
}
#
#-------------------------------------------------------------------------------
# Add NCBI id
#-------------------------------------------------------------------------------
#
genes<-read.csv(file="C:/Users/macpa/OneDrive/Appunti/Genetics/Domino/DOMINO_feb_2019.txt",sep="\t")
colnames(genes)<-c("SYMBOL","Domino")
#
for (i in 1:nrow(genes)) {
  genes$NCBI[i]<-Symbol2NCBI(genes$SYMBOL[i])
  if (as.integer(i/10)==i/10) print(paste(i,Sys.time()))
}
#
write.table(genes,file="DOMINO_NCBI_feb_2019.txt",sep="\t",col.names=T,row.names=F,quote=F)
