# 비즈니스 스타일 꾸미기

## 1. 레이아웃 설정

### 1) 큰 상자 설정

```css
display:block;
clear:both;
content:'';
```

### 2) 작은 상자 설정

```css
float:left;
width:50%;
```

### 3) Media Query 설정

```css
@media (min-width:768px){
    ...
}
```

### 4) 조각 코드

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

