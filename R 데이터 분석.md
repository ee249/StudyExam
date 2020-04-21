## R 데이터 분석

#### 데이터 분석 설계

1. 먼저 분석하려는 주제를 명확하고 구체적으로 설정 후 주제 선정
2. 브레인 스토밍을 이용해서 다양한 관점의 가설 설정. 가설 설정 단계에서는 가설을 세운 후 데이터 수급 여부를 판단하는 것이 좋습니다. 

※ 단) 데이터 수급을 먼저 고민하면 시각이 지나치게 좁혀질 수 있으므로 주의



#### 데이터 준비 -> 데이터 가공 및 통합 -> 데이터 분석 -> 결론 도출

- 결론 도출: 다양한 통계량을 통해 가설을 검증하고 의미 있는 결과를 정리하여 최종 결과를 도출



#### 데이터의 생김새와 변수와 함수

\- 행(Row) : 데이터 세트의 가로 영역으로 데이터의 관측치라고도 부릅니다.

\- 열(Column) : 데이터 세트의 세로 영역으로 변수(Variable)라고도 부릅니다.



#### 변수명 생성 규칙

\- 첫 글자는 반드시 영문자(알파벳) 또는 마침표(.)여야 합니다. 

※ 단) 마침표(.)를 첫글자로 하는 경우는 드뭅니다.

\- 두 번째 글자부터는 영문자, 숫자, 밑줄(_)를 사용할 수 있습니다.

\- 대문자와 소문자를 구분합니다.

\- 변수명 중간에 빈칸을 넣을 수 없습니다.



#### 함수와 패키지

- 함수(Function) : 미리 정해 둔 공식에 따라 처리하여 특정한 결과로 도출해주는 기능

- 패키지(Package) : 함수를 상자 하나에 둔 것입니다.

  \- 설치 : install.packages("설치할 패키지명")

  \- 로드 : library(로드할 패키지명)



#### 데이터 구조 간 관계 파악하기

- 단일형 : 숫자형 또는 문자형과 같이 한 가지 데이터 형태로만 구성된 데이터입니다.
- 다중형 : 숫자 데이터 또는 문자 데이터 등 여러 가지 데이터 형태로 구성된 데이터입니다. 리스트와 데이터 프레임이 다중형 데이터에 속합니다.

- 차원에 따른 분류: 

  \- 1차원 데이터는 직선 위에 데이터 값이 나열되어 있으므로 찾고자 하는 값이 기준점을 중심으로 얼마만틈 떨어져 있는지(면 번째인지)만 알면 됩니다.

  \- 반면 2차원은 두 가지 정보를 , n차원은 n가지 정보를 알아야 원하는 값을 찾을 수 있습니다.



#### 데이터 구조의 가장 기본인 벡터

- 숫자형 벡터

  \- str() 함수 : 변수의 속성이 num, 즉 숫자형 벡터라는 것과 포함된 데이터 값 확인 가능

  \- length() 함수 : num[1:3]  -1 0 1 일때, 데이터 길이(length)가 3이라는 것도 알 수 있다.

- 문자형 벡터

  \- 문자형 벡터는 문자로 이루어진 데이터입니다.

  \- 할당할 문자 데이터를 따옴표 (" " 또는 ' ')로 감싼 형식으로 구성합니다.

- 논리형 벡터

  \- 논리형 벡터는 TRUE와 FALSE라는 논리값으로 이루어진 데이터입니다.

  \- str()을 하면 논리형 데이터(logi)인 것을 확인할 수 있습니다.



※ rm(데이터명), remove(데이터명) -> 데이터 삭제



#### 행렬 생성하기

- 행렬 데이터는 matrix() 함수를 이용

  \- matrix(변수명, nrow=행 개수, ncol=열 개수)



#### 배열 생성하기

- 배열 데이터는 array() 함수를 이용

  \- array(변수명, dim = c(행 수, 열 수, 차원 수))



#### 리스트 생성하기

- 숫자형과 문자형 등 여러 가지 데이터 형을 동시에 포함할 수 있는 데이터 세트입니다.

  \- list(c(1,2,3), "Hello")  # 숫자형 벡터, 문자형 벡터로 구성된 list1 생성



 	#### 데이터 프레임 생성하기

- 실제 업무에서 가장 많이 사용하는 데이터 세트입니다.
- 데이터 프레임의 각 열에는 변수명이 있어야 합니다.



#### readxl 패키지 설치

- 엑셀 파일을 불러올 때는 read_excel() 함수를 사용합니다. 
- 불러온 엑셀 데이터를 exdata1 데이터 세트로 저장합니다.



#### read.table() 함수로 TXT 파일 가져오기

- header : 원시 데이터에서 1행이 변수명인지 안지 판단(1행이 변수명이면 header = TRUE)
- skip : 특정 행까지 제외하고 데이터 가져오기(3행부터 가져오려면 skip=2)
- nrows : 특정 행까지 데이터 가져오기(7행까지 가져오려면 nrows = 7)
-  sep : 데이터 구분자 지정(쉼표로 구분된 데이터가 있다면 sep=",")

```R
vername <- c("ID","SEX","AGE","AREA")
ex2_data <- read.table("C:/Rstudy/data_ex2.txt", sep=",", col.names=varname)
# colname에 값을 집어넣는다.
```





#### 데이터 추출 및 정렬하기

- filter() 함수로 추출하기

  \- filter() 함수는 조건식에 맞는 데이터를 필터링할 때 사용합니다. ex)filter(mtcars, cyl == 4)

- arrange() 함수로 정렬하기

  \- 데이터를 오름차순으로 정렬할 때 사용합니다.

- select() 함수로 변수 선택하기

  \- filter() 함수는 행을 추출할 때 사용하지만 select() 함수는 열, 즉 지정한 변수만 추출할 때 사용합니다.



#### 데이터 추가 및 중복 데이터 제거하기

- mutate() 함수로 열 추가하기

  \- mutate() 함수는 데이터 세트에 열을 추가할 때 사용합니다.  mutate(데이터 세트, 추가할 열 이름 = 조건 1, ...)

- distinct() 함수로 중복 값 제거하기

  \- distinct() 함수는 중복된 값을 제거할 때 사용합니다.



#### 데이터 요약 및 샘플 추출하기

- summarise() 함수로 데이터 요약하기

  \- summarise() 함수는 통계 함수와 함께 사용하며 데이터를 요약할 때 사용합니다.  

  (summarise(데이터 세트, 요약 결과 저장 열=통계 함수)

- 그룹별로 요약하기

  \- summarise() 함수는 전체를 요약할 때 사용하는데 반해 group_by() 함수는 그룹별 데이터를 요약할 때 사용합니다. 

  \- group_by() 함수는 단독으로 쓰기보다는 다른 함수와 연계해서 사용하는 경우가 많습니다. %>% 연산자를 이용하면 더 편하게 사용하실 수 있습니다.



#### 데이터에서 샘플 추출하기

\- sample_n() 함수와 sample_frac() 함수는 데이터에서 샘플 데이터를 추출할 때 사용합니다.

\- sample_n(mtcars, 10) # mtcars에서 10개의 샘플 데이터 추출

\- sample_frac(mtcars,0.2) #mtcars에서 20%를 샘플 데이터로 추출



#### 함수와 함수를 연결하는 %>% 연산자

\- %>% 연산자는 파이프, 즉 연결하여 연산하는 기능을 가지고 있습니다. 

\- 함수의 결과 값을 별도의 변수에 저장하지 않아도 %>% 연산자를 이용하면 바로 사용할 수 있습니다.

\- ex) group_by(mtcars, cyl) %>% summarise(n())



#### ggplot2 패키지 설치 및 기본 사용법 알고 가기 

- 그래프 기본 틀 만들기

  \- ggplot2 패키지에 담긴 모든 그래프의 기본은 ggplot() 함수이다. 

  \- ggplot() 함수는 그래프를 표현하는 좌표를 그리기 위해 판을 짜는 함수이다.

  \- ggplot(데이터 세트, aes(데이터 속성))

  \- aes() 함수를 이용해  x축과 y축을 맵핑할 수 있습니다.

- 산점도, geom_point() 함수

  \- 산점도는 두 변수의 관계를 파악하기 위해 평면에 관측점을 찍어서 표현하는 그래프입니다.

  \- 그래프를 그리기에 앞서  x축과 y축을 날짜와 온도의 관계를 파악하기 위해서입니다.

  \- ggplot(데이터 세트, aes(x=날짜,y=온도)) + geom_point()

  \- ggplot(데이터 세트, aes(x=날짜,y=온도)) + geom_point(size = 3, color = "red") // 점크기가 3이고, 칼라는 빨간이다.

- 꺾은선그래프, geom_line() 함수

  \- 꺾은선그래프는 geom_line() 함수를 사용하여 그립니다. 

  \- 꺾은선그래프는 그 점과 점을 순차대로 이어 선으로 표현한 시각화 자료로 산점도에 비해 변화를 관찰하기 쉽다.

  \- ggplot(데이터 세트,aes(x=날짜, y=온도)) + geom_line()

※ 코드가 길어지거나 복잡해지면 적절하게 줄을 바꾸면서 작성해야 읽기에도 편하고 추후 오류를 수정하기에도 좋습니다.

가능:

```R
 ggplot(airquality, aes(x=day, y=temp)) + 
geom_line()
```

불가능: 

```R
 ggplot(airquality, aes(x=day, y=temp)) 
 +geom_line()
```

- 그래프에 그래프 더하기

  \- 함수만 추가로 작성하면 산점도와 꺾은선그래프를 겹쳐서 표현할 수 있습니다.

  \- gglpot(데이터세트, aes(x=날짜, y=온도)) + geom_line() + geom_point()

- 막대그래프, geom_bar() 함수

  \- geom_bar() 함수에 막대그래프를 그릴 떄 사용합니다.

  \- 산점도, 꺾은선그래프는 두 변수의 관계를 파악하지만 막대그래프는 하나의 변수에서 각 값의 빈도를 파악할 수 있습니다.

  \- 산점도와 꺾은선그래프에서는 aes() 함수를 이용해 x축과 y축을 모두 지정했지만, 빈도를 파악하는 막대그래프에서는 x축만 지정하면 됩니다.

  \- ggplot(데이터세트, aes(x=cyl종류)) + geom_bar(width = 0.5)

  \- 빈범주를 제외하고 싶다면 문자형으로만 특정 값을 가질 수 있는 factor() 함수를 쓰면 됩니다.

  ex) gglot(데이터세트, aes(x=factor(cyl종류)))+geom_bar(width=0.5)

- 누적 막대그래프

  \- ggplot(데이터세트, aes(x=factor(cyl종류)))+geom_bar(aes(fill = factor(gear)))

  \- 누적 막대그래프를 그릴 때는 geom_bar() 함수 안에 aes() 함수를 이용하여 누적할 열을 지정하면 됩니다.

- 누적 막대그래프로 선버스트 차트 그리기

  \- ggplot(데이터 세트, aes(x=factor(cyl)))+geom_bar(aes(fill=factor(gear)))+coord_polar()

#### 상자 그림 & 히스토그램

- geom_boxplot() 함수

  \- 상자 그림은 분포를 비교할 때 사용하는 그래프로 ggplot2 패키지의 geom_boxplot() 함수를 사용하여 그릴 수 있습니다. 

  \- aes() 함수 안에 box로 그룹 지을 열을 설정해야 한다.

  \- ggplot(데이터세트, aes(x=Day, y=temp, group = Day)) + geom_boxplot()

- geom_histogram() 함수

  \- geom_histogram() 함수는 도수 분포를 기둥 모양 그래프로 표현한 히스토그램을 만드는 함수입니다. 

  \- ggplot(데이터세트, aes(Temp)) + geom_histogram()



#### 그래프의 이해를 높이는 객체 추가하기

- 직선 그리기

- 사선, geom_abline() 함수

  \- 사선, geom_abline() 함수는 x축 또는 y축과 만나는 값인 절편과 기울기를 설정하여 그래프에 사선을 그릴 때 사용합니다.

  \- ggplot(econmoics, aes(x=date, y=psavert)) + geom_line() + geom_abline(intercept=12.xxx, slope=-0.xxx)

  \- 이처럼 사선을 그릴 때는 y 절편(intercept)과 기울기(slope) 값을 옵션으로 입력해야 하는데, 절편 값과 기울기 값은 회귀분석을 통해 구할 수 있습니다.

- 평행선, geom_hline() 함수

  \- gglot(economics, aes(x=date, y=psavert)) + geom_line() + geom_hline(yintercept = mean(economics$psavert))

- 수직선, geom_vline() 함수

  \- geom_vline()  함수



#### 텍스트 입력 및 도형 그리기

- 텍스트, geom_text() 함수

  \- geom_text() 함수는 그래프에 텍스트를 입력할 때 사용합니다.

  \- 그래프의 범례나 제목과 달리 그래프 위에 직접 표현됩니다.

  \- geom_text(aes(label=라벨명, vjust=세로 위치, hjust=가로 위치))

  \- 데이터 레이블을 입력할 위치에서 세로 값과 가로 값을 모두 0으로 입력하면 레이블은 각 점의 오른쪽 위, +값은 아래/왼쪽, -값은 위/오른쪽에 표시됩니다.

- 도형 및 화살표, annotate() 함수

  \- annotate() 함수는 그래프 위에 사각형이나 화살표 등으로 특정 영역을 강조할 때 사용하며 다음과 같은 형식으로 사용합니다.

  \- annotate("모양", xmin = x축 시작, xmax = x축 끝, ymin=y축 시작, ymax=y축 끝)

  \- ggplot(데이터세트, aes(x=wt, y=mpg)) + geom_point()

  \# x축 3 ~ 4 ,y축 12 ~ 21 위치에  하늘색(skyblue) 투명한(alpha=0.5) 사각형(rect)  그리기

  annotate("rect",xmin=3, xmax=4, ymin=12,ymax=21,alpha=0.5,fill="skyblue")

- annotate("seqment", x=2.5, xend=3.7, y=10, yend=17, color="red", arrow=arrow())



####  그래프 제목 및 축 제목을 추가하고 디자인 테마 적용하기

- 그래프 및 축 제목, labs() 함수

  \- labs(x="x축 이름", y="y축이름",title="그래프 제목")

  \- labs(x="기어수", y="자동차수",title="변속기 기어별 자동차수") # 제목 추가하기

- 테마 적용, theme() 함수

  \- theme() 함수는 그래프의 여러 구성 요소 및 디자인을 지정되어 있는 형태로 일괄하여 변경할 떄 사용합니다.

  \- theme_gray(), theme_bw(), theme_linedraw(), theme_light(), theme_dark(), theme.minimal(), theme.classic(), theme.void()



#### Kormaps 패키지 소개

\- 한국행정지도도 Shape파일을 R에서 사용하기 쉽도록 변환한 패키지입니다. 이 패키지를 이용하면 각종 통계자료와 행정구역을 연계하여 단계구분도을 쉽게 만들 수 있게 하기 위하여 패키지를 제작하였습니다.

\- static image를 만들고자 할 때는 tmap패키지를 이용하면 쉽게 단계구분도를 그릴 수 있으며 웹상에서 축소/확대가 가능한 단계구분도를 그리고 싶을 때는 leaflet 패키지를 이용하면 좋습니다.



- 행정구역 지도 그림기

  ```
  require(kormaps)
  require(tmap)
  
  qtm(kormap1)
  ```



#### 지도에 그림 그리기

```
crime <- read.csv('data/2017crime.csv')
palette2<-colorNumeric(palette='Blues', domain=crime$폭력_발생)
popup1 <- paste0(seoulpopmap$name,'<br> 살 인')
map4<-leaflet(seoulpopmap) %>%  setView(lat=37.559957 ,lng=126.975302 , zoom=11)%>% addTiles() %>% addPolygons(stroke=FALSE,smoothFactor=0.2,fillOpacity=.5, popup=popup1, color=~palette1(crime$폭력_발생), group='폭력')
map4
```

- leaflet() : 지도로 보여주기
- setView(lat, lng, zoom) : 중심 위치를 입력한 후 줌을 표시
- addTiles() : 그래픽 요소 그리고 층을 맵 widget으로 추가한다.
- addPolygons()