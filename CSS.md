## CSS3(p.91~)

#### ex02_11.html 

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="EUC-KR">
<title>Insert title here</title>
<style>
	hr{background-color: gray;}
	ol#coun li{color:red;}
	ol#coun li:hover{color:orange; font-weight:bold;}
</style>
</head>
<body>
	<hr>
	<ol id="coun">
		<li>중국</li>
		<li>일본</li>
		<li>미국</li>
		<li>호주</li>
	</ol>
	
	<hr>
	<ol id="island">
		<li>제주도</li>
		<li>하와이</li>
		<li>오키나와</li>
		<li>발리</li>
	</ol>
</body>
</html>
```

- ol#coun li{}는 ol tag 중에서 id가 coun을 가진 ol에서 속하는 li들이 영향을 받는다.
- li:hover는 위에다가 마우스를 올리면 변하는 것을 hover라고 한다.
- color:orange는 글씨 색깔을 orange로 하며 font-weight:bold는 글씨 두께를 정한다.



#### ex02_12.html

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="EUC-KR">
<title>Insert title here</title>
<style>
	h1, div, p{
		color: green;
		font-size: 25px;
		font-weight: bold;
		font-family: "나눔고딕";
	}
</style>

</head>
<body>
	<h1>123</h1>
	<div>가나다</div>
	<p>ABC</p>
</body>
</html>
```

- h1, div, p{} 이렇게 묶으면 모든 태그에 동시에 적용할 수 있다.
- font-family:"나눔고딕"을 사용하면 글씨체를 지정할 수 있다.

#### ex02_13.html

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="EUC-KR">
<title>Insert title here</title>
<style>
	p{font-size: 25px; font-weight: bold; color: #8041D9;}
	t1.{font-size: 15px; font-family: 휴먼옛체, 맑은고딕; 
	color:rgb(255,0,221);}
	#t2{font-size: 35px; font-family: "Times New Roman", "Comic Sans MS";
	color: gray;}
</style>

</head>
<body>
	<h1>[CSS를 이용한 폰트]</h1>
	<p class="t1" id="t2">Good Morning</p>
	<p class="t1">안녕하세요</p>
	<p class="t1" id="t2" style="color:red"; font-size:50px;">Good Morning</p>
	<p>안녕하세요</p>
	<strong class="t1" id="t2">안녕하세요</strong>
</body>
</html>
```

- 우선 순위가 가장 높은 인라인 선택자입니다. 
- 우선 순위가 두번째 높은 선택자는 아이디 선택자입니다.
- 우선 순위가 세 번째 높은 선택자는 class 선택자입니다.
- 마지막 순위인 태그 선택자입니다.

#### ex02_14

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="EUC-KR">
<title>Insert title here</title>
<style>
	.fs{
		font-size: 25px;
		line-height: italic;
	}
	#f1{font-variant: small-caps;}
	#f2{font-style: italic;}
	#f3{font-family: "Comic Sans MS";}
	#f3{font-weight: bold;}
</style>
</head>
<body>
	<div class="fs">Rather be dead than cool.</div>
	<div class="fs" id="f1">Rather be dead than cool.</div>
	<div class="fs" id="f2">Rather be dead than cool.</div>
	<div class="fs" id="f3">Rather be dead than cool.</div>
	<div class="fs" id="f4">Rather be dead than cool.</div>
</body>
</html>
```

- small-caps는 대문자로 바꿔준다.

####  문단 스타일 속성

- text-decoration 

\- 문자에 밑줄 또는 취소선 등을 넣습니다.

\- none: 선을 만들지 않습니다.

\- line-through: 글자 중간에 선을 만듭니다.

\- overline: 글자 위에 선을 만듭니다.

\- underline: 글자 아래에 선을 만듭니다.

\- initial: 기본값으로 설정합니다.

\- inherit: 부모 요소의 속성값을 상속 받습니다.

- text-align

\- 문단을 왼쪽, 가운데, 오른쪽 정렬합니다.

\- justify는 양쪽 정렬입니다.

- text-indent

\- 문단의 들여쓰기 또는 내어 쓰기를 지정합니다.

- text-transform

\- 영문자 모두를 대문자로 또는 소문자로 변경합니다.

\- capitalize: 단어의 첫번째 글자를 대문자로 바꿉니다.

- letter-spacing

\- 글자 간의 간격을 조절합니다.

- word-spacing

\- 단어 간의 간격을 조절합니다.



#### 배경 스타일 속석

- background-color: 배경에 색상을 넣는 속성입니다.
- background-image: 배경에 이미지를 넣는 속성입니다.(background-image: url('경로'))
- background-repeat: 배경 이미지의 반복 여부를 설정하는 속성입니다. (background-repeat: repeat|repeat-x|repeat-y|no-repeat|inherit)



#### 테이블 스타일 속성

- border-collapse: 테이블 셀 간의 간격 여부를 설정합니다.

\- seperate: 표(table)의 테두리와 셀(td)의 테두리 사이에 간격을 둡니다.

\- collapse: 표(table)의 테두리와 셀(td)의 테두리 사이의 간격을 없앱니다. 겹치는 부분은 한 줄로 나타냅니다.

\- initial: 기본값으로 설정합니다.

\- inherit: 부모 요소의 속성값을 상속 받는다.



####  Navigation과 Dropdown



#### ex02_25.html

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="EUC-KR">
<title>Insert title here</title>
<style>
	body{
		margin: 0;
	}
	.header{
		padding: 5px;
		text-align: center;
		background-color:red;
		border-bottom: 1px solid #bdbdbd;
	}
	ul{
		list-style-type: none;
		margin: 0;
		padding: 0;
		width: 100px;
		background-color: white;
		position: fixed;
		height: 100%;
		overflow: auto;
	}
	li a{
		display: block;
		color: #000;
		padding: 8px 16px;
		text-decoration: none;
	}
	li a:hover{
		background-color: #555;
		color:white;
	}	
</style>
</head>
<body>
	<div class="header">
		<h1>Web Site name</h1>
	</div>
	<ul>
		<li><a href="#main">메일</a></li>
		<li><a href="#cafe">카페</a></li>
		<li><a href="#blog">블로그</a></li>
		<li><a href="#shopping">쇼핑</a></li>
	</ul>
</body>
</html>
```



#### 02_25.html

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="EUC-KR">
<title>Insert title here</title>
<style>
	body{
		margin: 0;
	}
	.header{
		padding: 5px;
		text-align: center;
		background-color:red;
		border-bottom: 1px solid #bdbdbd;
	}
	ul{
		list-style-type: none;
		margin: 0;
		padding: 0;
		width: 100px;
		background-color: white;
		position: fixed;
		height: 100%;
		overflow: auto;
	}
	li a{
		display: block;
		color: #000;
		padding: 8px 16px;
		text-decoration: none;
	}
	li a:hover{
		background-color: #555;
		color:white;
	}	
</style>
</head>
<body>
	<div class="header">
		<h1>Web Site name</h1>
	</div>
	<ul>
		<li><a href="#main">메일</a></li>
		<li><a href="#cafe">카페</a></li>
		<li><a href="#blog">블로그</a></li>
		<li><a href="#shopping">쇼핑</a></li>
	</ul>
</body>
</html>
```

- list-style-type: none; // 어떤식의 모양의 마커를 사용할 지 정하는 것이다.
- overflorw

\- visible: 박스를 넘어가도 보여줍니다.

\- hidden: 박스를 넘어간 부분은 보이지 않습니다.

\- scroll: 박스를 넘어가든 넘어가지 않든 스크롤바가 나옵니다.

\- auto: 박스를 넘어가지 않으면 스크롤바가 나오지 않고, 박스를 넘어갈 때에는 스크롤바가 나옵니다.

\- initial: 기본값으로 설정합니다.

\- inherit: 부모 요소의 속성값을 상속받습니다.



#### ex02_28.html

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="EUC-KR">
<title>Insert title here</title>
<style>
	ul{
		list-style-type: none;
		margin: 0;
		padding: 0;
		overflow: hidden;
		background-color: #999;
	}
	li{
		float: left;
	}
	li a, .dropbtn{
		display: inline-block;
		color: white;
		text-align: center;
		padding: 14px 16px;
		text-decoration: none;
	}
	li a:hover, .dropdown:hover .dropbtn{
		background-color: red;
	}
	li.dropdown{
		display: inline-block;
	}
	li a.ative, a.active:hover{
		background-color:: #4CAF50;
	}
	.droptown-contenet{
		display:none;
		position: absolute;
		background-color: #f9f9f9;
		min-width: 160px;
		box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
		z-index: 1;
	}
	.dropdown-content a{
		color: black;
		padding: 12px 16px;
		text-decoration: none;
		display: block;
		text-align: left;
	}	
	.dropdown-content a:hover {background-color: #f1f1f1}
	.dropdown:hover .dropdown-content{
		display: block;
	}
</style>
</head>
<body>
	<ul>
		<li><a href="#home">Home</a></li>
		<li><a href="#mail">메일</a></li>
		<li><a href="#cafe">카페</a></li>
		<li><a href="#blog">블로그</a></li>
		<li class="dropdown">
			<a href="#shopping" class="dropbtn">쇼핑</a>
			<div class="dropdown-content">
				<a href="#">가전제품</a>
				<a href="#">의류/악세서리</a>
				<a href="#">가방/신발</a>
			</div>
		</li>
		<li class="dropdown">
			<a href="#new" class="dropbtn">뉴스</a>
			<div class="dropdown-content">
			<a href="#">정치</a>
			<a href="#">경제</a>
			<a href="#">생활/문화</a>
			</div>
		</li>
		<li style="float: right:"><a class="active" href="#login">로그인</a></li>
	</ul>
</body>
</html>
```

- a:hover, .dropdown:hover .dropbtn{ } // tag <a> 위에 마우스를 놓으면 hover 기능이 작동 그리고 dropdown이라는 클래스 이름을 가진 속성에 마우스를 놓으면 {}이 작동 그리고 클래스가 dropbtn을 가진 것에 갖다 놓아도 {} 작동



#### CSS 레이아웃 속성

#### position과 z-index

- z-index: 어느 요소가 앞에 나올지 배치 순서를 정하는 속성입니다.
- position: 레이아웃을 배치하거나 요소의 위치를 정할 때 사용하는 속성입니다.

#### float와 clear

- float: 요소를 오른쪽 또는 왼쪽에 배치합니다.

\- float: none / left / right / inherit

- clear: 요소의 옆을 취소합니다.

\- clear: none / left / right / both



