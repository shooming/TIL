# CSS TIL 정리

## CSS(Cascading style Sheets)란?
css는 간단하게 html을 꾸며주기 위한 언어이다.
물론 태그에 속성을 입혀 html을 꾸며 줄 수 있지만 html의 내용이 지저분해지며, 정보만을 전달하고자하는 html의 목적과 맞지않기 때문에 css를 사용하여 주는 것이 좋다.

### css의 적용
css는 3가지 방법으로 적용가능하다.

1. #### inline style
    ```html
    <h1 style="color: red;"> 내요요용</h1>
    ```
    태그에 바로 적용 가능한 방식이지만 가독성 떨어지며 유지보수가 어렵다.

2. #### style 태그
    ```html
    <head>
        <style>
            h1{
                color:blue;
            }
        </style>
    </head>
    ```
    html의 head태그 밑데작성하는 방식으로 편하고 빠르나 기능적으로 분리되지 않아 유지보수 어려움

3. #### css파일 별도 작성
    ```html
    <link href="index.css" rel="stylesheet" type="text/css"/>
    ```
    head 태그에 위와 같이 작성
    
    html과 css 파일을 분리하여 작성하는 방식으로 유지관리가 쉬움

    href - css파일 위치
    rel - html과 css 파일 연결관계 설명
    type - link연결 파일이 어떤 파일인가

### css 작성법
    ```css
    h1 {
        font-size: 16px;
    }
    ```
css는 h1태그(selector)를 선택하여 css를 color(property)와 16px(property value)를 사용하여 꾸며준다.

1. #### tag selector
    ```css
    h1 {
        font-size: 16px;
    }
    ```
    `태그이름`을 선택하여 꾸며준다.

2. #### class selector
    ```css
    .classname{
        font-size: 16px;
    }
    ```
    `.클래스이름`을 선택하여 꾸며준다.

3. #### id selector
    ```css
    #idname{
        font-size: 16px;
    }
    ```
    `#id이름`을 선택하여 꾸며준다.

------

## font style

```css
body{
    font-family: font이름1, "font 이름 2", font이름3, serif;
    font-size: 10px;
    font-weight: bold;
    font-style: italic;
    color: red;
    color: #eb4639;
    color: rgb(255, 255 ,255);
    color: hsl(4, 66%, 33%);
}
```

### font-family
글자 폰트를 정하며 폰트이름을 작성하여 html에 폰트 지정한다. ""(따옴표)는 폰트에 띄어쓰기가 있을겨우 사용하며, serif는 거의 모든 브라우저에서 지원되는 폰트로 앞에 폰트가 지원안될시 사용된다.

### font-size
폰트의 크기를 지정한다.
px, em, pt등의 단위가 사용된다.

### font-weight
폰트의 글자 두께를 나타낸다.
normal, bold, 숫자값이 지정됨
400 = normal과 같다.
700 = bold와 같다.

### font-style
글씨 스타일을 바꿀 수 있고 italic을 작성하면 이탤릭체로 변하게됨

### color
글씨의 색상을 지정함.
- 색상이름 - red, blue와 같이 간단한 색상은 단어로도 지원함
- hex - #eb4639와 같이 6자리로 표현
- rgb - rgb(255, 255 ,255) red, green, blue의 값으로 표현
- hsl - hsl(4, 66%, 33%) 색상, 채도, 명도로 표현
- rgba

------

## 문구 스타일

### 텍스트 정렬
```css
a{
    text-align: left;
    text-align: center;
    text-align: right;
}
```
text-algin을 통하여 텍스트를 정렬한다.
오른쪽은 right, 왼쪽은 left, 가운데는 center이다

### 들여쓰기
1. #### text-indent
    ```css
    b{
        text-indent: 50px;
    }
    ```
    text-indent를 사용하여 들여쓰기가 가능하다

2. #### blockquote
    ```html
    <blockquote></blockquote>
    ```
    blockquote태그를 사용한다.(인용문 작성시 사용)


3. #### 스페이스 문자 입력
    ```html
    <p>&nbsp;&nbsp;&nbsp;&nbsp;</p>
    ```
    위와 같은 스페이스 문자를 입력하여 공백을 만든다.

------

## margin과 padding
### margin
```css
h1{
    margin: 10px;
    margin: 10px 20px 30px 40px;
    margin-top: 10px;
    margin-right: 20px;
    margin-bottom: 30px;
    margin-left: 40px;
    margin: 10px 20px;
}
```
border를 기준으로 테두리 바깥에 생기는 빈공간이다.
첫줄은 4방향 전부 10px의 margin을 주겠다는 뜻이다.
두번째는 margin을 시계방향으로 순서대로 쓰면 margin값이 들어간다
밑의 top ~ bottom을 한줄 처리한것이라고 보면된다.
margin에 2개의 값만 들어간것은 위/아래, 좌/우라고 생각하면된다.

### padding
```css
h1{
    padding: 10px;
    padding: 10px 20px 30px 40px;
    padding-top: 10px;
    padding-right: 20px;
    padding-bottom: 30px;
    padding-left: 40px;
    padding: 10px 20px;
}
```
border를 기준으로 테두리 안쪽에 생기는 빈공간이다.
첫줄은 4방향 전부 10px의 padding을 주겠다는 뜻이다.
두번째는 padding을 시계방향으로 순서대로 쓰면 padding값이 들어간다
밑의 top ~ bottom을 순서대로 한줄 처리한것이라고 보면된다.
padding에 2개의 값만 들어간것은 위/아래, 좌/우라고 생각하면된다.

------
## box-sizing
padding과 margin을 적용하다보면 적용하는 기준에 따라 box의 크기가 달라진다는 사실을 알수있다.
그래서 눈에 보이는 그대로 값대로 적용시키기위해 box-sizing을 사용한다. 
```css
.newbox {
  box-sizing: border-box;
}
```
------

## css Specificity
css selector의 적용 우선순위는 보면 된다
사실 상황에 따라 다른 경우도 존재하긴 하지만 보통의 경우 이 순서이다.
```bash
tag(우선순위 낮음) <<<<< class <<<< id <<<<<< inline css (우선순위 높음)
```
------

## inline, inline-block, block

### inline
text 크기만큼만 공간을 점유하고 줄바꿈을 하지 않아 다른 엘리먼트들과 나란히 배치된다.
inline은 몇가지 제약이 있다.
1. width / heigh 값 적용 불가
2. margin-top / margin-bottom 적용 불가
3. padding은 좌우는 공간과 시각적인 부분이 모두 적용됨, 위아래는 시각적으로는 추가되지만 공간을 차지 하지는 않음.

### block
block 속성은 무조건 한줄을 점유하고 있고, 다음 태그는 무조건 줄바꿈이 적용된다
1. block은 height / width 값을 지정 가능
2. block은 margin / padding을 지정 가능

### inline-block
inline-block 속성은 inline 속성의 특징과 block 속성의 특징 둘 다 가지고 있는 속성이다.
1. 줄바꿈을 시행하지 않아 동일한 라인에 작성
2. height / width / margin /padding 적용 가능
3. 별도의 width값 지정하지 않으면 content의 크기만큼만 width 할당됨
4. line-height 적용 가능

### 속성 바꾸기
```css
h1{
    display: inline;
}
```
css에 display 속성을 이용하여 inline, block, block-line, none을 사용하여 바꿀 수 있다.

none 값은 아무것도 안나오게 하는 값이지만 필요할때 감추고 필요할때 나오게 할 수 있다 예로는 검색어 자동완성과 같은 기능이 있다.

------

## 가상 선택자
```css
1button:hover {
    cursor: pointer;
}

2button:hover {
  opacity: 0.8;
}

3li:first-child{
  background: red;
}

4li:last-child{
  background: red;
}

5li:nth-child(n){
  background: red;
}

6li:nth-child(odd) {
  background: red;
}

7li:nth-child(even) {
  background: blue;
}

```
hover은 마우스를 hover가 지정된 대상에 올려놓으면 hover에 들어간 동작이 작동한다.
아래는 첫번째부터 예시에 대한 설명이다.

1. 예시는 hover시 마우스 버튼에 손가락 모양이 나오는 것
2. 해당 요소를 불투명하게 하는 것이다.
3. li요소중 첫번째인것을 선택한다.
4. li요소중 마지막것을 선택한다.
5. li요소중 n번째인것을 선택한다.
6. li요소중 홀수인것만 선택한다.
7. li요소중 짝수인것만 선택한다.



## 속성 선택자
```css
input::placeholder {
  color: #bbb;
}

input[type="text"] {
}

input[type="text"]::placeholder {
  color: red;
}
```
속성 선택시에는 : (콜론)을 두번치고 대상 속성을 작성한다.

1. place홀더만 선택된한것이고
2. input태그에 type="text"인 속성만 선택한것이고
3. input태그에 type="text"인 속성을 선택하여 placeholder를 빨간색으로 강조하라는 내용이다.

------

## position의 속성 
CSS에는 position을 사용하여 페이지에 레이아웃을 배치할 수 있다.

position에는 대표적으로 4가지가 있다.

### position: static;
따로 작성하지 않는다면 기본적으로 지정되는 속성으로 자기가 원래 위치해야하는 곳에 정적으로 위치함

왼쪽 -> 오른쪽
위 -> 아래
    
의 순서대로 쌓인다.

### position: relative;

태그의 위치를 변경하고 싶을때 사용된다. top, bottom, left, right 값을 사용하여 현재 대상이 위치하고 있는 위치를 기준으로 위치조절 가능하다.
    
### position: absolute;
static 속성을 가지고 있지 않은 부모를 기준으로 움직이며  relative, absolute, fixed인 태그가 없다면 가장 위의 태그(body)가 기준이 된다.

### position: fixed;
브라우저에 해당 레이아웃을 고정하고 싶을때 사용한다. top, bottom, left, right 값으로 위치를 고정하면 스크롤을 움직여도 그 위치에 고정되어 있다.


------

## Float
페이지 전체 레이아웃 잡을 때 사용한다.
이미지 주위를 텍스트로 감싸기 위해 만들어진 것이다.

```css
img{
    float: left;
}
```

Float는 left, right, none 중 하나를 값으로 줄 수 있다.

Float 속성을 지니게되면 부모의 높이를 인지할 수 없어 내용이 밖으로 튀어나는 현상이 발생한다.

Float를 사용하기위해서는 몇가지 방법을 사용하여야한다.

```html
예시1
<div class="wecode-box">
    <img class="float-left" src="https://s3.ap-northeast-2.amazonaws.com/cdn.wecode.co.kr/logo/wecode_logo_bk.png">
    <p>아래에 clear요소를 두거나</p>
    <br class="clear">
</div>

예시2
<div class="wecode-box last-box">
    <img class="float-right" src="https://s3.ap-northeast-2.amazonaws.com/cdn.wecode.co.kr/logo/wecode_logo_bk.png">
    <p>이게 젤 낫네</p>
</div>

예시3
<div class="wecode-box float-right">
    <img class="float-right" src="https://s3.ap-northeast-2.amazonaws.com/cdn.wecode.co.kr/logo/wecode_logo_bk.png">
    <p>.wecode-box도 float이거나</p>
</div>
```

```css
.wecode-box {
  border: 1px solid #ddd;
}

.float-left {
  float: left;
}

.float-right {
  float: right;
}

.clear {
  clear: both;
}

.width-100 {
  width: 100%;
}

.last-box {
  overflow: hidden;
}
``` 

1. div마지막에 다른태그를 사용하여 clear 속성을 부여한다. 예시 1이 사용 예시이다. clear: both; css 속성을 사용하여 해결한다.
2. div에 overflow:hidden; 값을 주어서 해결한다.
예시 2이 사용 예시이며, 사용시 지정된 박스 밖으로 img나 내용이 빠져나가지 않는다. 그러나 넘어간 부분은 잘리게 된다.
3. 바깥 div를 float시켜 float 높이를 인지시켜 그높이 만큼을 차지하게됨 그러나 그렇게 되면 width값을 추가해 주어야 하며 예시 3이 사용 예시이다.

------
## Media tag
반응형 디자일을 만들기위한 태그라고 할 수 있다. Media 태그를 사용하면 특정 width값이 되었을때 그 넓이에 맞는 css를 출력하게 할 수 있다.
```css
@media only screen and (min-width: 320px) and (max-width: 480px) {
  body {
       background-color: yellow;
  }
}
```
위의 css는 최소 넓이 320px ~ 최대 480px 사이에서는 배경색을 노란색으로 출력하게하는 css이다.

only screen을 설정하여 스크린을 볼때로 결정하였고 어떤 디바이스에서 보여줄지결정해 줄 수 있다. 프린트를 하고싶을 때 보는것이라면 only print라고 설정하면된다.

이렇게 css를 사용하게되면 desktop 혹은 모바일 디바이스에서도 상황에 맞게 css를 출력하여 반응형 디자인을 구성할 수 있다.

------
## multi column
해당 기능은 다단 / 컬럼 으로 신문과 같이 단을 나눌때 사용할 수 있는 기능이다.
```css
      .column{
        text-align: justify;
        column-count: 4;
        column-width: 200px;
        column-gap:30px;
        column-rule-style: solid;
        column-rule-width: 5px;
        column-rule-color: red;
      }
```
- column-count: 단을 나눌 개수를 정한다.
- column-width: 단의 넓이를 정한다.
- column-gap: 단사이의 간격을 정한다.
- column-rule-style: 단 중간에 선, 점선등을 표현 할 수 있다.
- column-rule-width: 단 중간의 선의 굵기이다.
- column-rule-color: 단 중간의 선의 색을 정한다.

------

## felex
레이아웃을 잡을때 사용하는 css
felex는 아래와 같은 느낌으로 구성된다.
```html
<container>
  <item></item>
  <item></item>
</container>
```
flex는 container와 item에게 부여되는 속성이 나누어져 있다.
| container | item |
|:---:|:---:|
| display | order |
| flex-direction | flex-grow |
| flex-wrap | flex-shrink |
| flex-flow | flex-basis |
| justify-content | flex |
| align-items | align-self |
| align-content | |

컨테이너에 display 속성을 display:flex; 로 만드는것 부터 시작
   
적용하면 열방향으로 정렬되던것 (위에서 아래로)
행방향으로 정렬이 바뀜(좌에서 우)

### flex-direction
- flex-direction: row; : flex-direction의 기본값은 row로 지정되어 있음
- flex-direction:row-reverse;로 지정하면 반대로 정렬됨
- flex-direction:column;은 위에서 아래로 정렬됨
- flex-direction:column-revers; 위에서 아래 뒤집혀 정렬됨
- flex는 기본적으로 각각의 태그가 각각의 방향의 전체를 차지함

### flex-basis;
flex의 방향에 해당하는 크기를 지정함

### flex-grow;
여백을 균등하게 분할함

### flex-shrink;
공간을 고정해버림 크기를 줄여도 줄어들지 않음

### flex-wrap;
기본값은 nowrap이며 wrap을 지정하면 컨테이너보다 아이템들의 합의 크기가 크면 아이템을 줄바꿈함 wrap-reverse하면 역순으로 배치;

### align-items;
기본값은 stretch이며 flex가 적용되면 수직방향에 대한 정렬을 함
align-items사용시 사용하고자 하는 container의 height를 100%혹은 크기를 지정해야 해당 크기에 맞추어서 이동

### justify-content;
flex-start가 기본이며 수평방향에대한 정렬을 함