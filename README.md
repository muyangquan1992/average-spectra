# average-spectra
metabolites = read.csv("C:\\Users\\tian3969\\Desktop\\20.6uM 10h\\inner metabolites.csv", header = FALSE)
A1=matrix(,nrow=4,ncol=346)
A2=data.frame(A1)
for(i in 1:346){
  A2[1,i]=sum(metabolites[,i])
  A2[2,i]=mean(metabolites[,i])
  A2[3,i]=sd(metabolites[,i])
}
soa = sum(A2[2,])
for(i in 1:346){
  A2[4,i]=A2[2,i]*10E8/soa
}
write.csv(A2,file="inner average spectra.csv")

