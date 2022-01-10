# 위치 정렬

## block과 inline

html의 태그들은 크게 block과 inline 요소로 나눌 수 있습니다.

- block 요소<br>
`<address>`, `<article>`, `<aside>`, `<blockgquote>`, `<canvas>`, `<dd>`, `<div>`, `<dl>`, `<hr>`, `<header>`, `<form>`,`<h1>`, `<h2>`, `<h3>`, `<h4>`, `<h5>`, `<h6>`, `<table>`, `<pre>`, `<ul>`, `<p>`, `<ol>`, `<video>` ...

- inline 요소<br>
`<a>`, `<i>`, `<span>`, `<abbr>`, `<img>`, `<strong>`, `<b>`, `<input>`, `<sub>`, `<br>`, `<code>`, `<em>`, `<small>`, `<tt>`, `<map>`, `<textarea>`, `<label>`, `<sup>`, `<q>`, `<button>`, `<cite>` ...

### display

`display`는 요소가 보여지는 방식을 지정하는 프로퍼티입니다.<br>
html 태그는 각각 다른 `display` 프로퍼티 값을 가지고있으며 block 혹은 inline 속성 값을 기본 스타일로 가지고 있습니다.<br>

#### display: block

**block**이란 단어는 '덩어리' 또는 '막다'라는 뜻을 가지고 있습니다. 주로 전체 문단과 같이 큰 맥락을 가질 때 사용합니다.<br>
`display: block`을 기본 값으로 가지고 있는 요소들은 옆에 다른 요소들이 올 수 없도록 혼자 한 줄을 차지합니다. 항상 새로운 줄에서 시작하며 따로 너비를 지정하지 않아도 `width: 100%`을 기본 값으로 갖습니다. 또한 크기를 직접 지정하면 자동으로 남은 길이를 `margin`으로 채워 옆으로 다른 요소가 오는 것을 막습니다.<br>
주로 `div`, `h1`~`h6`, `p`, `header`, `footer`, `section` 등이 이에 해당합니다.<br>

```
<!-- display: block; -->
<h1>h1 태그</h1>
<div>div 태그</div>
<p>p 태그</p>
<article>article 태그</article>
<li>li 태그</li>
```

#### display: inline

**inline**이란 단어는 '일렬로 늘어선' 이라는 뜻을 가지고 있습니다. 주로 단어, 링크, 이미지 등에 쓰입니다.<br>
`display: inline`의 경우 요소의 콘텐츠 크기에 한정된 크기를 가지며, 부모의 너비 안에서 한 줄에 들어갈 수 있는 만큼 일렬로 배치됩니다.<br>
`inline`은 `width`, `height`, `margin-top`, `margin-bottom` 프로퍼티를 지정할 수 없습니다.<br>
주로 `span`, `a`, `img`가 이에 해당합니다.

```
<!-- display: inline; -->
<strong>strong 태그</strong>
<span>span 태그</span>
<a href="/">a 태그</a>
```

#### display: inline-block

`display: inline`에서 `width`, `height`, `margin-top`, `margin-bottom` 프로퍼티가 적용되지 않아 불편함이 발생하여 이를 해결하기 위해 `display: inline-block`가 등장합니다.<br>
`inline-block`은 `block`과 `inline`의 특징을 모두 가집니다<br>
기본적인 쓰임은 `inline`과 동일하지만 사용할 수 없었던 `width`, `height`, `margin-top`, `margin-bottom`을 지정할 수 있습니다.

#### display: none

`display: none`으로 설정하면 브라우저에 해당 요소가 출력되지 않습니다.<br>
주로 자바스크립트를 이용하여 요소를 사라지거나 나타나게 할 때 쓰입니다.

## position

**position**은 이름 그대로 요소를 배치하는 방법을 정하는 프로퍼티입니다.<br>
`static`, `relative`, `absolute`, `fixed` 네 가지 값을 주로 사용합니다.

### position: static

`position`의 기본 값입니다.<br>
`static`에서는 `top`, `right`, `bottom`, `left`와 같은 좌표 프로퍼티를 사용할 수 없습니다.

### position: relative

**relative**는 상대 위치입니다.<br>
기본 위치를 기준으로 좌표 프로퍼티를 사용하여 위치를 이동합니다. 여기서 기본 위치란 static일 때의 위치입니다.<br>

```
.relative {
  position: relative;
  background pink;
  left: 16px;
  top: 16px;
}
```

해당 요소가 `position:static` 이었을 때의 위치에서 left와 top으로 16px 만큼 멀어집니다.

### position: absolute

**absolute**는 절대 위치입니다.<br>
부모 요소나 조상 요소 중 `relative, `absolute` 혹은 `fixed`가 선언된 곳을 기준으로 좌표 프로퍼티가 작동합니다.<br>
만약 부모나 조상 프로퍼티에 `relative, `absolute` 혹은 `fixed`가 선언된 곳이 없다면 최상단 태그인 `<body>`를 기준으로 위치가 지정됩니다.

### position: fixed

`fixed`는 보이는 화면을 기준으로 좌표 프로퍼티를 이용하여 위치를 고정시킵니다.<br>
우리가 자주 보는 화면을 스크롤할 때 따라다니는 메뉴가 바로 `fixed`를 활용한 겁니다.

```
.fixed {
  position: fixed;
  right: 16px;
  top: 16px;
  background-color: pink;
}
```

### z-index

`position`과 함께 쓰이는 프로퍼티로 `top`, `right`, `bottom`, `left` 이외에 `z-index`도 있습니다.<br>
`z-index`를 통해 수직으로 어떻게 쌓이는지 정하는 프로퍼티로, 값은 숫자로 표현됩니다. 숫자가 클수록 전면에 출력됩니다.<br>
`static`을 제외할 요소에서만 적용됩니다.

```
<!-- HTML -->
<div class="parent">
	<div class="box top">top</div>
	<div class="box middle">middle</div>
	<div class="box bottom">bottom</div>
</div>

/* CSS */
.box {
	width: 100px;
	height: 50px;
	position: absolute;
}
.parent {
	position: relative;
	border: 2px solid red;
	width: 200px;
	height: 100px;
}
.top {
	background-color: pink;
	right: 16px;
	bottom: 16px;
	z-index: 3;
}
.middle {
	background-color: skyblue;
	right: 32px;
	bottom: 32px;
	z-index: 2;
}
.bottom {
	background-color: lemonchiffon;
	right: 48px;
	bottom: 48px;
	z-index: 1;
}
```
## float

**float**은 뜨다, 띄우다 라는 뜻을 가지고 있습니다.<br>
`float` 프로퍼티는 요소를 디자인의 흐름에서 벗어나게 한 뒤 사용자가 지정한 방향에 배치하도록 하는 프로퍼티입니다.<br>
문서 작성 프로그램에서 사진과 본문 사이의 배치를 조정하여 사진과 글이 함께 보여지도록 하는 것과 같이 웹에서도 이와 동일하게 배치가 가능합니다.<br>

```
.a-img {
	border: 2px solid red;
	width: 200px;
	float: left;
}
```

## flexbox

flexbox는 크기가 불분명한 요소들을 효율적으로 동작시키고 특별한 계산 없이 정렬할 수 있습니다.
부모 요소인 flex container와 자식 요소인 flex item으로 구성되어 있으며 부모 요소와 자식 요소에는 사용할 수 있는 프로퍼티에 차이가 있습니다.

flex container 부모 요소
- flex-direction
- flex-wrap
- flex-flow
- justify-content
- align-items
- align-content

flex item 자식 요소
- flex
- flex-grow
- flex-shrink
- flex-basis
- order

flexbox를 쓰려면 정렬하고자 하는 요소의 부모 요소인 flex container에 `display: flex;`를 추가하면 됩니다.
`display: flex;`를 사용하지 않으면 flex는 사용 할 수 없습니다.

```
<!-- HTML -->
<div class="parent">
	<div class="child">child</div>
</div>

/* css */
.parent { /* 배치, 정렬하고자 하는 요소를 감싸는 부모 요소 */
	display: flex;
}
.child { /* 배치, 정렬하고자 하는 요소 */
}
```

flex 아이템들은 가로 방향으로 배치되고, 자신이 가진 내용물의 width 만큼만 차지하게 됩니다.<br>
height는 컨테이너의 높이만큼 늘어나니까 컬럼 레이아웃같은걸 만들 때 좋습니다. height는 정렬 속성을 통해 조정할 수 있습니다.<br>
아이템들이 배치된 방향의 축을 메인축(Main Axis), 메인축과 수직인 축을 수직축 또는 교차축(Cross Axis)라고 부릅니다.

### 부모 요소 프로퍼티 flex-direction 배치 방향 설정

아이템들이 배치되는 축의 방향을 결정하는 속성입니다.<br>
"메인축의 방향을 가로로 할거냐 세로로 할거냐"를 정해주는 프로퍼티입니다.<br>

```
.container {
	flex-direction: row; /* 행(가로) */
	flex-direction: row-reverse; /* 행(가로) 역순 */
	flex-direction: column; /* 열(세로) */
	flex-direction: column-reverse; /* 열(세로) 역순 */
}
```

### 부모 요소 프로퍼티 flex-wrap 줄넘김 처리 설정

컨테이너가 더 이상 아이템들을 한 줄에 담을 여유 공간이 없을 때 아이템 줄바꿈을 어떻게 할지 결정하는 속성입니다.<br>
컨테이너의 width가 너무 작아 item을 더 줄일수 없게 되면 item이 컨테이너를 벗어 납니다. 이를 해결하기 위한 속성입니다.<br>

flex-direction이 row일 경우
|flex-direction|row|
|:---:|:---:|
|1|2|
|3|4|
|5|6|

flex-direction이 cloumn일 경우
|flex-direction|cloumn||
|:---:|:---:|:---:|
|1|3|5|
|2|4|6|

```
.container {
	flex-wrap: nowrap; /* 기본 값 */
	flex-wrap: wrap; /* 줄바꿈을 합니다. */
	flex-wrap: wrap-reverse; /* 역순으로 줄바꿈합니다. */
```

### 부모 요소 프로퍼티 flex-flow

`flex-direction`과 `flex-wrap`을 한꺼번에 지정할 수 있는 단축 속성입니다.<br>
`flex-direction`, `flex-wrap`의 순으로 한 칸 때고 써주시면 됩니다.

```
.container {
	flex-flow: row wrap;
	/* flex-direction:row;, flex-wrap: wrap; */
}
```

### 부모 요소 프로퍼티 jstify-content 메인축 방향 정렬

justify는 메인축 방향으로 아이템들을 정렬하는 속성입니다.<br>

```
.container {
	justify-content: flex-start; /* 기본 값으로 아이템들을 시작점으로 정렬합니다. */
	justify-content: flex-end; /* 아이템들을 끝점으로 정렬합니다. */
	justify-content: center; /* 아이템들을 가운데로 정렬합니다. */
	justify-content: space-between; /* 아이템들의 "사이(between)"에 균일한 간격을 만듭니다. */
	justify-content: space-around; /* 아이템들의 "둘레(around)"에 균일한 간격을 만듭니다. */
	justify-content: space-evenly; /* 아이템들의 사이와 양 끝에 균일한 간격을 만듭니다. IE와 엣지(Edge)에서는 지원되지 않습니다. */
}
```

![image](https://user-images.githubusercontent.com/57892556/147877775-cb66e622-8f0f-4a11-b856-ef8c5d14818e.png)

![image](https://user-images.githubusercontent.com/57892556/147877782-f92ca51a-67fc-44a2-a370-aaf7fbb51ea3.png)

### 부모 요소 프로퍼티 align-items 수직축 방향 정렬

`align-items`는 기본값으로 stretch를 갖습니다.<br>
이는 별다른 크기가 지정되지 않았을 때 flex 아이템을 부모 요소의 크기만큼 늘려서 맞춰줍니다.<br>
`align-items: flex-start`를 추가하면 높이가 콘텐츠의 크기만큼 바뀝니다.<br>
이와 같이 `align-items: center`와 `align-items: flex-end`가 존재합니다.

```
.container {
	align-items: stretch; /* 기본값 */
	align-items: flex-start; /* 아이템들을 시작점으로 정렬합니다. row일 때는 위 column일 때는 왼쪽 */
	align-items: flex-end; /* 아이템들을 끝으로 정렬합니다 row일 떄는 아래 column일 때는 오른쪽 */
	align-items: center; /* 아이템들을 가운데로 정렬합니다 */
	align-items: baseline; /* 아이템들을 텍스트 베이스라인을 기준으로 정렬합니다. 글자 크기가 서로 다른 글자들을 적용해야 할 경우 사용합니다. */
}
```

### 부모 요소 프로퍼티 align-content 여러 행 정렬

flex-wrap: wrap;이 설정된 상태에서, 아이템들의 행이 2줄 이상 일 경우 수직축 방향 정렬을 결정하는 속성입니다.

```
.container {
	flex-wrap: wrap;
	align-content: stretch;
	align-content: flex-start;
	align-content: flex-end;
	align-content: center;
	align-content: space-between;
	align-content: space-around;
	align-content: space-evenly;
}
```

### 자식 요소 프로퍼티 flex-grow

`flex-grow`는 flex item의 확장과 관련되어 있습니다.<br>
단위 없는 숫자 값(비율)을 사용하며 기본값은 0입니다.<br>
값이 0일 경우 flex container가 커져도 flex item의 크기는 커지지 않고 원래 크기를 유지합니다.<br>
값이 1 이상일 경우 flex item의 원래 크기와 상관없이 flex container를 채우기 위해 flex item도 커집니다.<br>
`flex-gorw`의 값이 1 이상이고 flex item이 여러 개라면 flex-grow의 값에 따라 flex container의 크기가 나눠집니다.<br>
flex item이 3개고 값이 1, 2, 1 일 경우 1:2:1의 비율로 나눠집니다.<br>
`flex-gorw`의 크기는 비율이기에 flex container의 크기는 커지거나 줄어들면 동일한 비율로 크기가 커지거나 줄어듭니다.

### 자식 요소 프로퍼티 flex-shrink

`flex-shirink`는 `flex-gorw`와 쌍을 이루는 속성으로, 축소와 관련되어 있습니다.<br>
`flex-shirink`는 아이템이 `flex-basis`의 값보다 작아질 수 있는지를 결정합니다.<br>
`flex-shrink에는 숫자값이 들어가고 0과 정수(비율)를 사용하며, 속성값이 0일 경우 flex container 크기가 flex item의 크기보다 작아져도 flex item의 크기가 줄어들지 않고 원래 크기를 유지합니다.<br>
속성값이 1 이상이면 flex container의 크기가 작아질 때 flex item의 크기가 flex container의 크기에 맞춰 줄어듭니다.

### flex-basis

`flex-basis`는 flex item의 기본 크기를 결정하며, 기본값은 `auto`입니다.<br>
단위로는 모든 크기 단위를 사용할 수 있는데, `auto`로 값이 설정되면 원래 콘텐츠의 크기가 할당됩니다.<br>
(flex-direction이 row일 때는 너비, column일 때는 높이)

```
.item {
	flex-basis: auto; /* 기본값. */
	flex-basis: 0;
	flex-basis: 50%;
	flex-basis: 100px;
	flex-basis: 10rem;
	flex-basis: content; /* 콘텐츠의 크기로 width를 설정하지 않은 것과 같습니다. */
}
```

`flex-basis`의 값으로는 width, height와 같은 각종 단위의 수가 들어갈 수 있습니다.<br>
기본값 auto에는 해당 아이템의 width값을 사용합니다. 따로 설정을 안하면 콘텐츠의 크기가 됩니다.<br>
3개의 박스가 존재하며 각 박스의 크기는 50px, 150px, 100px일 경우 flex-basis를 100px로 설정하면<br>
50px의 박스는 100px로 늘어나고 150px와 100px로 설정한 박스는 변화가 없습니다.<br>
반면에 width를 설정하면 모든 박스가 100px로 맞춰집니다.

### flex

`flex` 는 `flex-grow`, `flex-shrink`, `flex-basis`를 한 번에 쓸 수 있는 축약형 속성입니다.

```
.item {
	flex: 1;
	/* flex-grow: 1; flex-shrink: 1; flex-basis: 0%; */
	flex: 1 1 auto;
	/* flex-grow: 1; flex-shrink: 1; flex-basis: auto; */
	flex: 1 100px;
	/* flex-grow: 1; flex-shrink: 1; flex-basis: 100px; */
}
```

### align-self 수직축으로 아이템 정렬

`align-items`의 아이템 버전입니다.<br>
`align-self`는 `align-items`보다 우선권이 있습니다. 전체 설정보다 각각의 개별 설정이 우선된다고 생각하시면 됩니다.

```
.item {
	align-self: auto;
	align-self: stretch;
	align-self: flex-start;
	align-self: flex-end;
	align-self: center;
	align-self: baseline;
}
```

### order 배치 순서

각 아이템들의 시각적 나열 순서를 결정합니다.<br>
숫자값이 들어가며, 작은 숫자일 수록 먼저 배치됩니다.<br>
시각적 순서일 뿐, HTML 자체의 구조는 변경되지 않기 때문에 접근성 측면에서 사용에 주의해야합니다.<br>
시각 장애인분들이 사용하는 스크린 리더로 화면을 읽을 때, order를 이용해 순서를 바꾼 것은 의미가 없습니다.

### z-index

여기서도 `z-index`를 사용하여 Z축 정렬을 사용할 수 있습니다.

## grid layout

Grid는 격자 또는 눈금을 뜻합니다.<br>
CSS에서 grid는 행렬을 통해 요소들을 좀 더 정교하게 그리고 복잡하게 정렬 및 배치를 할 수 있는 레이아웃입니다.<br>

### Grid 요소들의 명칭

grid 내부 요소들은 **Lines, Track, Area, Gap** 이라는 명칭을 가진 영역으로 이루어져 있습니다.

#### Grid Lines

Grid Lines는 격자를 이루는 선의 집합을 뜻합니다.<br>
Grid를 이루는 행과 열의 선들을 모두 Grid Lines라고 부릅니다.<br>
엑셀의 행과 열을 생각하시면 됩니다. Grid Lines에서 행은 Grid row, 열은 Grid column이라고 말합니다.

#### Grid Track

평행한 Grid Line 두 줄 사이의 공간을 Grid Track이라 부릅니다.

#### Grid Area

Grid Line 네 줄로 둘러싸인 공간을 Grid Area라고 부릅니다.<br>

#### Grid Cell

Grid Area 안에 더 이상 쪼개지지 않는 한 칸을 Grid Cell이라고도 부릅니다. 이러한 Grid Cell이 한 개일 때 혹은 그 이상일 때 해당 공간을 Grid Area라고 합니다.

#### Grid Gap

행 여러 개(Rows) 혹은 열 여러 개(Columns) 사이의 간격을 Grid Gap이라고 부릅니다. 이해하기 쉽게 Grid Lines의 두께라고 생각하시면 됩니다.

### Grid의 구성

Grid는 부모 요소인 **Grid Container**와 자식 요소인 **Grid items**로 구성되어 있으며, 각각 사용하는 프로퍼티가 다릅니다.<br>

#### grid container: template

##### display: grid / inline-grid

Grid item들은 Grid Container안에 배치하기 때문에 display: grid;를 설정하는 것으로 시작합니다.
`display: inline-grid;`는 block과 inline-block의 관계를 생각하시면 됩니다.

```
.container {
  display: grid;
  /* display: inline-grid; */
}
```

##### grid-template-rows / grid-template-column

컨테이너에 Grid Track의 크기들을 지정해주는 속성입니다.
행에 해당하는 Grid Track은 `grid-template-rows` 열에 해당하는 Grid Track은 `grid-template-column`으로 지정할 수 있습니다.

```
.container {
  grid-template-rows: 100px 300px 200px;
  grid-template-column: 1fr 3fr 2fr;
  /* 1fr 2fr 1fr은 1:2:1 비율입니다. */
  /* repeat(3, 1fr)은 1fr을 3번 반복합니다 */
  /* minmax(100px, auto)는 최소크기를 100px로 최대는 내용에 따라 자동으로 늘어납니다 */
  /* auto-fill, auto-fit은 column의 개수를 미리 정하지 않고 설정된 너비가 허용하는 한 최대한 셀을 채웁니다.
     repeat(auto-fill, minmax(20%, auto));는 20%크기로 설정했으므로, 1개의 row에 5개의 셀이 들어갑니다. auto-fill은 셀의 개수가 모자라면 빈 공간이 생기지만 auto-fit은 빈 공간을 채웁니다. */
 }
 ```
 
 ##### row-gap / column-gap / gap
 
 그리드 셀 사이의 간격을 설정합니다.
 
 ```
 .container {
  row-gap: 10px;
  column-gap: 10px;
  /* gap: 10px 10px나 gap: 10px와 같이 한꺼번에 지정할 수도 있습니다. */
}
```

초기에는 grid-gap이라고 grid-를 붙여서 사용했습니다
IE에서는 gap의 대체 속성이 없기 때문에, IE와 구조를 통일해야하면 처음부터 gap을 사용하지 않고 구조를 설계하는게 좋습니다.

