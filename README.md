[toc]

# 비즈니스 스타일 꾸미기

## 1. 레이아웃 기본 구조 생성

### 1) 박스 준비

```html
<body>
    <div class="boxA">
        <div class="box1">BOX1</div>
        <div class="box2">BOX2</div>
    </div>
    <div class="box3">BOX3</div>
    <div class="box4">BOX4</div>
    <div class="box5">BOX5</div>
</body>
```

### 2) 박스 가로 정렬

- 포괄 박스

```css
display:block;
clear:both;
content:'';
```

- 작은 박스

```css
float:left;
width:50%;
```

### 3) 반응형 웹 디자인과 관련된 설정

```css
@media (min-width:768px){
    ...
}
```

### 4) 완성 코드

```css
@charset "UTF-8";

body{
    font-family: '맑은 고딕','Apple SD Gothic Neo',sans-serif;
}

/* ####### 768px 이상 ####### */
@media (min-width:768px){
    /* BOX1과 BOX2를 가로 정렬하는 설정 */
    .boxA::after{
        content: '';
        display: block;
        clear: both;
    }
    .box1{
        float: left;
        width: 50%;
    }
    .box2{
        float: left;
        width: 50%;
    }
}

```

## 2. 박스 내부에 요소를 추가

### 1) 사이트 이름

- h1 태그 내부에 a 태그를 활용하였다.

```html
<div class="box1">
    <div class="site">
        <h1><a href="#">Business Style CSS</a></h1>
    </div>
</div>
```

```css
/* 사이트 이름 */
.site h1{
    margin: 0;
    font-size: 30px;
}
.site h1 a{
    color: #000000;
    text-decoration: none;
}
```

### 2) 네비게이션

- ul, li a, li a:hover, 가로정렬을 사용하였다.
  - ul은 list-style을 none으로 지정해줘서 앞에 점을 없앰. 
  - li a 는 text-decoration 을 none으로 주고, diaplay: block으로 한줄처리함
  - 가로정렬 공식 사용함

```html
<div class="box2">
    <nav class="menu">
        <ul>
            <li><a href="#">메인</a></li>
            <li><a href="#">연혁</a></li>
            <li><a href="#">사업 소개</a></li>
            <li><a href="#">채용 정보</a></li>
            <li><a href="#">문의</a></li>
        </ul>
    </nav>
</div>
```

```css
/* 네비게이션 */
.menu ul{
    margin: 0;
    padding:0;
    list-style: none;
}
.menu li a{
    display: block;
    padding: 5px;
    color: #000000;
    text-decoration: none;
    font-size: 14px;
}
.menu li a:hover{
    background-color: #eeeeee;
}
.menu ul:after{
    content:'';
    display: block;
    clear: both;
}
.menu li{
    float: left;
    width: auto;
}
```

### 3) 이미지 처리

![image](https://user-images.githubusercontent.com/26649731/76718663-d1197900-677a-11ea-8b6a-d17161f3841f.png)

- 이미지를 넣으면 다음과 같이 빠져나간다.

```html
<div class="box3">
    <img src="img/06/header.jpg" alt="" class="topimg">
</div>
```

```css
/* 헤더 그림 */
.topimg{
    max-width: 100%;
    height: auto;
    vertical-align: bottom;
}
```

- 맞춰준다.

### 4) 공지사항

- ul, li a, li a:hover를 사용하였다.
- 네비게이션이랑 거의 유사하지만 가로정렬을 사용하지 않았음
  - ul은 list-style을 none으로 지정해줘서 앞에 점을 없앰. 
  - li a 는 text-decoration 을 none으로 주고, diaplay: block으로 한줄처리함

```html
<div class="box4">
        <div class="news">
            <h1>공지사항</h1>
            <ul>
                <li><a href="#"><time datetime="2020-03-16">3/6</time>데이터센터 유지 보수를 수행합니다.</a></li>
                <li><a href="#"><time datetime="2020-03-16">3/6</time>안드로이드 애플리케이션 버전 1.2를 출시했습니다.</a></li>
                <li><a href="#"><time datetime="2020-03-16">3/6</time>세미나/캠페인과 관련된 공지사항</a></li>
                <li><a href="#"><time datetime="2020-03-16">3/6</time>그래프 표시의 변경 방식을 쉽게 바꿨습니다.</a></li>
            </ul>
        </div>
    </div>
```

```css
/* 공지사항 */
.news h1{
    margin-top: 0;
    margin-bottom: 5px;
    font-size: 18px;
    color: #666666;
}
.news ul{
    margin: 0;
    padding: 0;
    list-style: none;
}

.news li a{
    text-decoration: none;
    display: block;
    padding: 5px;
    color: #000000;
    font-size: 14px;
    border-bottom: dotted 2px #dddddd;
}

.news li a:hover{
    background-color: #eeeeee;
}

.news time{
    margin-right: 10px;
    color: #999999;
    font-weight: bold;
}
```

### 5) 저작권

```html
<div class="box5">
    <div class="copyright">
        Copyright &copy; Business CSS
    </div>
</div>
```

```css
/* 저작권 */
.copyright p{
    margin: 0;
    color: #666666;
    font-size: 14px;
}
```

![image](https://user-images.githubusercontent.com/26649731/76724463-5fe3c100-678e-11ea-88d0-d842540e8ffa.png)

## 3. 레이아웃 조정

### 1) 네비게이션 매뉴 양쪽으로 분리하기

- 50:50으로 맞춰져있는 박스 두개를 분리하여 준다.

```css
/* ####### 768px 이상 ####### */
@media (min-width:768px){
    /* BOX1과 BOX2를 가로 정렬하는 설정 */
    .boxA::after{
        content: '';
        display: block;
        clear: both;
    }
    .box1{
        float: left;
        width: auto;
    }
    .box2{
        float: right;
        width: auto;
    }
}
```

### 2) 헤더 그림을 화면에 꽉 차게 출력

```css
/* 박스의 왼쪽, 오른쪽 */
.boxA, .box4, .box5{
    padding-left: 15px;
    padding-right: 15px;
}
```

### 3) 푸터를 바의 형태로 수정 및 요소 간격조정

```css
/* BOX5를 바 형태로 디자인 */
.box5{
    background-color: #dddddd;
    padding-top: 15px;
    padding-bottom: 15px;
}
/* 박스의 위아래 */
.boxA {
    padding-top: 20px;
    padding-bottom: 10px;
}
.box4{
    padding : 20px 0;
}

/* boxA와 box4의 배경 */
.boxA{
    background-color: #333333;
}
.box4{
    background-color: #e8e8c4;
}
```

## 4. 반응형 웹 디자인과 관련된 조정

- 안드로이드, 아이폰 등 작은 UI를 가지는 곳에서의 설정을 변경해보자
- 큰 화면에서의 설정을 변경해보자

### 1) 네비게이션 디자인 간소화

- 네비게이션이 깨지거나 두줄이 되지 않도록 폰트 크기나, padding값을 줄여준다.

```css
/* ####### 599px 이하 ####### */
@media (max-width:599px){
    .site h1{
        margin: 0;
        font-size: 20px;
    }
    .menu li a{
        padding: 10px 7px;
        font-size: 11px;
    }
}
```

### 2) 날짜 아래에 글자가 파고들지 않게 수정

- 한쪽 박스의 너비를 픽셀로 고정하는 방법을 사용할 것이다.

```css
.news a:after{
    content: '';
    display: block;
    clear: both;
}
.news time{
    float: left;
    width: 60px;
}
.news .text{
    float: none;
    width: auto;
    margin-left: 60px;
}
```

### 3) 레이아웃 전체 너비 고정

- 일정 크기 이상이 될 경우 레이아웃의 크기를 고정하여 정적 이미지 파일이 깨지지 않도록 한다.

```css
@media (min-width:1190px){

    /* 전체 너비를 고정 */
    .box3, .box4{
        width: 1140px;
        margin: 0 auto;
    }

    /* BOX A 아래에 테두리 삽입 */
    .boxA {
        margin-bottom: 20px;
        border-bottom: solid 1px #dddddd;
    }
}
```

### 4) 헤더와 푸터의 내용물을 다른 요소에 맞추기

- 제목을 깔끔하게 보일 수 있도록 한다.

- boxA-inner, box5-inner 태그를 생성한다.

```html
<div class="boxA">
        <div class="boxA-inner">
            <div class="box1">
                ...
```

```html
<div class="box5">
        <div class="box5-inner">
            <div class="copyright">
                ...
```

- 맞춰준다.

```css
@media (min-width:1190px){

    /* 전체 너비를 고정 */
    .box3, .box4, .boxA-inner, .box5-inner{
        width: 1140px;
        margin: 0 auto;
    }
    ...
}
```

![image](https://user-images.githubusercontent.com/26649731/76734123-98db6000-67a5-11ea-8d97-2faa0a49b513.png)

## 5. 요소의 추가와 수정

### 1) 사이트 이름을 그림으로 수정

- 그림의 화질이 좋지 않을 때가 있다. 더 큰 그림 그림*4 크기를 준비하고 1/4로 줄여 해상도를 높이자.

### 2) 말풍선 형태의 추가 설명

- css arrow please 사이트를 이용하여 만든다.

### 3) 헤더 그림에 캐치 카피 올리기

```html
<div class="box3">
    <div class="top">
        <img src="img/06/header.jpg" alt="" class="topimg">
        <p class="catch">비즈니스 스타일의 css를 지향합니다.</p>
    </div>
</div>
```

```css
/* 캐치 카피 */
.catch{
	...
    position: absolute;
    bottom: 7%;
    left: 3%;
    ...
}
.top{
    position: relative;
}
```

- 부모는 relative, 자식은 absolute 로 지정하여 표현하자.

