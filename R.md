## R

\- R은 index가 1부터 시작한다.

\- TRUE, FALSE를 무조건 대문자로 작성해야 한다.

#### 스칼라: 하나의 값

```R
문제1번
v1 <- 1:10
v2 <- v1*2
max_v <- max(v2)
min_v <- min(v2)
avg_v <- mean(v2)
sum_v <- sum(v2)
v3 <- v2[-5]
v1
v2
v3
max_v
min_v
avg_v
sum_v

문제2번
v4=v1[c(T,F)]
v5=rep(1, 5)
v6=rep(1:3, 3)
v7=rep(1:4,each=2)

문제3번
nums <- sample(1:100, 10)
sort(nums)
sort(nums, decreasing = TRUE)
nums[nums>50]
nums[nums<=50]
v1[which.max(nums)]
v1[which.min(nums)]

문제4번 
v8=v1[c(T,F,F)]
V8 <- LETTERS[1:4]
V8

문제5번
score <- sample(1:20, 5)
myFriend <- c("둘리","또치","도우너","희동","듀크")
paste(score, myFriend, sep="-")
myFriend[which.max(score)]
myFriend[which.min(score)]
myFriend[which(score > 10)]

```

