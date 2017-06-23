library(stringr)
data <-readLines(file.choose())


#With DPRK
a1 <- 0
a2 <- sum(str_count(data, "China/DPRK"))
a3 <- sum(str_count(data, "China/Japan"))+sum(str_count(data, "China/DPRK/Japan"))
a4 <- sum(str_count(data, "China/Mongolia"))+ sum(str_count(data, "China/DPRK/Mongolia"))+sum(str_count(data, "China/Japan/Mongolia"))+sum(str_count(data, "China/DPRK/Japan/Mongolia"))
a5 <- sum(str_count(data, "China/ROK"))+sum(str_count(data, "China/DPRK/ROK"))+sum(str_count(data, "China/Japan/ROK"))+sum(str_count(data, "China/Mongolia/ROK"))+sum(str_count(data, "China/DPRK/Japan/ROK"))+sum(str_count(data, "China/DPRK/Mongolia/ROK"))+sum(str_count(data, "China/Japan/Mongolia/ROK"))+sum(str_count(data, "China/DPRK/Japan/Mongolia/ROK"))
a6 <- sum(str_count(data, "China/Russia"))+sum(str_count(data, "China/DPRK/Russia"))+sum(str_count(data, "China/Japan/Russia"))+sum(str_count(data, "China/Mongolia/Russia"))+ sum(str_count(data, "China/ROK/Russia"))+sum(str_count(data, "China/DPRK/Japan/Russia"))+sum(str_count(data, "China/DPRK/Mongolia/Russia"))+ sum(str_count(data, "China/DPRK/ROK/Russia"))+ sum(str_count(data, "China/Japan/Mongolia/Russia"))+sum(str_count(data, "China/Japan/ROK/Russia"))+ sum(str_count(data, "China/Mongolia/ROK/Russia"))+ sum(str_count(data, "China/DPRK/Japan/Mongolia/Russia"))+ sum(str_count(data, "China/DPRK/Japan/ROK/Russia"))+ sum(str_count(data, "China/Japan/Mongolia/ROK/Russia"))+sum(str_count(data, "China/DPRK/Japan/Mongolia/ROK/Russia"))

b1 <- a2
b2 <- 0
b3 <- sum(str_count(data, "DPRK/Japan"))
b4 <- sum(str_count(data, "DPRK/Mongolia"))+sum(str_count(data, "DPRK/Japan/Mongolia"))
b5 <- sum(str_count(data, "DPRK/ROK")) + sum(str_count(data, "DPRK/Japan/ROK"))+ sum(str_count(data, "DPRK/Mongolia/ROK"))+ sum(str_count(data, "DPRK/Japan/Mongolia/ROK"))
b6 <- sum(str_count(data, "DPRK/Russia"))+ sum(str_count(data, "DPRK/Japan/Russia"))+ sum(str_count(data, "DPRK/Mongolia/Russia"))+ sum(str_count(data, "DPRK/ROK/Russia"))+ sum(str_count(data, "DPRK/Japan/Mongolia/Russia"))+ sum(str_count(data, "DPRK/Japan/ROK/Russia"))+ sum(str_count(data, "DPRK/Mongolia/ROK/Russia"))+  sum(str_count(data, "DPRK/Japan/Mongolia/ROK/Russia"))

c1 <- a3
c2 <- b3
c3 <- 0
c4 <- sum(str_count(data, "Japan/Mongolia"))
c5 <- sum(str_count(data, "Japan/ROK")) + sum(str_count(data, "Japan/Mongolia/ROK"))
c6 <- sum(str_count(data, "Japan/Russia")) + sum(str_count(data, "Japan/Mongolia/Russia")) + sum(str_count(data, "Japan/ROK/Russia"))+ sum(str_count(data, "Japan/Mongolia/ROK/Russia"))

d1 <- a4
d2 <- b4
d3 <- c4
d4 <- 0
d5 <- sum(str_count(data, "Mongolia/ROK"))
d6 <- sum(str_count(data, "Mongolia/Russia"))+ sum(str_count(data, "Mongolia/ROK/Russia"))

e1 <- a5
e2 <- b5
e3 <- c5
e4 <- d5
e5 <- 0
e6 <- sum(str_count(data, "ROK/Russia"))

f1 <- a6
f2 <- b6
f3 <- c6
f4 <- d6
f5 <- e6
f6 <- 0


network1 <- matrix(
  c(a1, a2, a3, a4, a5, a6, b1, b2, b3, b4, b5, b6, c1, c2, c3, c4, c5, c6, d1, d2, d3, d4, d5, d6, e1, e2, e3, e4, e5, e6, f1, f2, f3, f4, f5, f6),
  nrow=6,
  ncol=6
)
print(network1)

index_a <- sum(a1, a2, a3, a4, a5, a6)
index_b<- sum(b1, b2, b3, b4, b5, b6)
index_c <- sum(c1, c2, c3, c4, c5, c6)
index_d<- sum(d1, d2, d3, d4, d5, d6)
index_e<- sum(e1, e2, e3, e4, e5, e6)
index_f<- sum(f1, f2, f3, f4, f5, f6)
print(index_a)
print(index_b)
print(index_c)
print(index_d)
print(index_e)
print(index_f)


#Without DPRK
a1 <- 0
a3 <- sum(str_count(data, "China/Japan")) - sum(str_count(data, "China/DPRK/Japan"))
a4 <- sum(str_count(data, "China/Mongolia"))+sum(str_count(data, "China/Japan/Mongolia")) - sum(str_count(data, "China/DPRK/Mongolia"))- sum(str_count(data, "China/DPRK/Japan/Mongolia"))
 a5 <- sum(str_count(data, "China/ROK")) +sum(str_count(data, "China/Japan/ROK"))+sum(str_count(data, "China/Mongolia/ROK"))+ sum(str_count(data, "China/Japan/Mongolia/ROK")) - sum(str_count(data, "China/DPRK/ROK")) - sum(str_count(data, "China/DPRK/Japan/ROK")) - sum(str_count(data, "China/DPRK/Mongolia/ROK")) - sum(str_count(data, "China/DPRK/Japan/Mongolia/ROK"))
a6 <- sum(str_count(data, "China/Russia"))+sum(str_count(data, "China/Japan/Russia"))+sum(str_count(data, "China/Mongolia/Russia"))+ sum(str_count(data, "China/ROK/Russia"))+ sum(str_count(data, "China/Japan/Mongolia/Russia"))+sum(str_count(data, "China/Japan/ROK/Russia"))+ sum(str_count(data, "China/Mongolia/ROK/Russia"))+ sum(str_count(data, "China/Japan/Mongolia/ROK/Russia")) - sum(str_count(data, "China/DPRK/Russia")) - sum(str_count(data, "China/DPRK/Japan/Russia")) - sum(str_count(data, "China/DPRK/Mongolia/Russia")) - sum(str_count(data, "China/DPRK/ROK/Russia")) - sum(str_count(data, "China/DPRK/Japan/Mongolia/Russia")) - sum(str_count(data, "China/DPRK/Japan/ROK/Russia")) - sum(str_count(data, "China/DPRK/Mongolia/ROK/Russia")) - sum(str_count(data, "China/DPRK/Japan/Mongolia/ROK/Russia"))

c1 <- a3
c3 <- 0
c4 <- sum(str_count(data, "Japan/Mongolia")) - sum(str_count(data, "DPRK/Japan/Mongolia"))
c5 <- sum(str_count(data, "Japan/ROK")) + sum(str_count(data, "Japan/Mongolia/ROK")) - sum(str_count(data, "DPRK/Japan/ROK"))- sum(str_count(data, "DPRK/Japan/Mongolia/ROK"))
c6 <- sum(str_count(data, "Japan/Russia")) + sum(str_count(data, "Japan/Mongolia/Russia")) + sum(str_count(data, "Japan/ROK/Russia"))+ sum(str_count(data, "Japan/Mongolia/ROK/Russia")) - sum(str_count(data, "DPRK/Japan/Russia")) - sum(str_count(data, "DPRK/Japan/Mongolia/Russia")) - sum(str_count(data, "DPRK/Japan/ROK/Russia")) - sum(str_count(data, "DPRK/Japan/Mongolia/ROK/Russia"))

d1 <- a4
d3 <- c4
d4 <- 0
d5 <- sum(str_count(data, "Mongolia/ROK")) - sum(str_count(data, "DPRK/Mongolia/ROK")) - sum(str_count(data, "DPRK/Japan/Mongolia/ROK"))
d6 <- sum(str_count(data, "Mongolia/Russia"))+ sum(str_count(data, "Mongolia/ROK/Russia")) - sum(str_count(data, "DPRK/Mongolia/Russia")) - sum(str_count(data, "DPRK/Mongolia/ROK/Russia"))- sum(str_count(data, "DPRK/Japan/Mongolia/Russia")) - sum(str_count(data, "DPRK/Japan/Mongolia/ROK/Russia"))

e1 <- a5
e3 <- c5
e4 <- d5
e5 <- 0
e6 <- sum(str_count(data, "ROK/Russia")) - sum(str_count(data, "DPRK/ROK/Russia"))- sum(str_count(data, "DPRK/Japan/ROK/Russia")) - sum(str_count(data, "DPRK/Mongolia/ROK/Russia")) - sum(str_count(data, "DPRK/Japan/Mongolia/ROK/Russia"))

f1 <- a6
f3 <- c6
f4 <- d6
f5 <- e6
f6 <- 0


network2 <- matrix(
  c(a1, a3, a4, a5, a6, c1, c3, c4, c5, c6, d1, d3, d4, d5, d6, e1, e3, e4, e5, e6, f1, f3, f4, f5, f6),
  nrow=5,
  ncol=5
)
print(network2)

index_aa <- sum(a1, a3, a4, a5, a6)
index_cc<- sum(c1, c3, c4, c5, c6)
index_dd<- sum(d1, d3, d4, d5, d6)
index_ee<- sum(e1, e3, e4, e5, e6)
index_ff<- sum(f1, f3, f4, f5, f6)
print(index_aa)
print(index_cc)
print(index_dd)
print(index_ee)
print(index_ff)

