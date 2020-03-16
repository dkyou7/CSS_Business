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

