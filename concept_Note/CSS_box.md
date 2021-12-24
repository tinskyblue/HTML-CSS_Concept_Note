# 박스(Box) 모델

HTML의 모든 요소(Element)는 상자(Box)의 형태를 갖습니다.<br>
태그 내부에 위치해 실제 표시되는 내용을 Content(내용)라고 합니다.<br>
보이지는 않지만 이러한 컨텐츠를 감싸고 있는 다른 요소들이 있습니다. 이러한 박스 형태 전체를 가리켜 박스 모델(Box Model)이라고 부릅니다.<br>
박스 모델은 **내용(Content), 패딩(Padding), 경계선(Border), 마진(Margin)** 으로 이루어져 있습니다.

![Box](https://user-images.githubusercontent.com/57892556/147089559-ac4ba5b0-d905-48c0-b969-81eb2ebb9a7e.JPG)

732x309.672 는 Content의 폭과 높이입니다.<br>
**내용(Content)** 은 이미지나 텍스트와 같이 우리가 코드 상에서 태그 사이에 담은 내용, 즉 실제로 담고 있는 부분입니다.<br>
다음으로 **경계선(Border)** 은 컨텐츠를 감싸고 있는 테두리입니다.<br>
마진과 패딩은 둘 다 여백을 뜻하지만 **경계선(Border)** 을 기준으로 역할이 다릅니다.<br>
**패딩(Padding)** 은 컨텐츠와 경계선 사이의 여백이지만 **마진(Margin)** 은 경계선 밖의 여백입니다.


```
<!-- html -->
<body>
  <div id="box">
    box model
  </div>
</body>

/* css */
#box {
  background-color: red;
  width: 200px;
  height: 100px;
}
```

개발자 도구에서 **inspect 도구** 를 통해 box를 찍어보면 컨텐츠의 크기가 200X100으로 설정되어있음을 확인할 수 있습니다.<br>
추가로 컨텐츠의 영역의 크기가 지정되어 있는 상태에서 컨텐츠의 크기를 늘리면 내용이 컨텐츠 박스를 벗어나게 됩니다.

## border

`border`는 컨텐츠를 감싸는 경계선으로 크게 세 프로퍼티를 이용합니다.<br>
`border-style`, `border-width`, `border-color`

### border-style

`border-style`은 선의 스타일로, 선의 종류를 지정하는 프로퍼티입니다.<br.
원하는 모양의 경계선을 추가할 수 있으며 여러 종류 중 가장 많이 사용하는 4가지는 `실선(solid)`, `파선(dashed)`, `점섬(dotted)`, `이중선(double)`입니다. <br>


```
/* css */
#box {
  background-color: green;
  border-color: red;
  border-style: solid dashed dotted double;
  border-width: 8px;
}
```

위와 같이 실행하면 박스의 사각형의 각 변은 실선, 파선, 점선, 이중선이 적용됩니다.<br>
CSS에서는 방향이 상(Top), 우(Right), 하(Bottom), 좌(Left) 순서로 스타일을 지정합니다.<br>
또한 값을 지정해주는 개수에 따라 스타일 적용 위치도 변경됩니다.<br>

- border-sytle: solid; / 상하좌우 모두 solid
- border-style: solid dashed; / 상하 solid, 좌우 dashed
- border-style: solid dashed dotted; / 상 solid, 좌우 dashed, 하 doutted
- border-style: solid dashed dotted double; / 상 solid, 우 dashed, 하 dotted, 좌 double

### border-width와 border-color

`border-width`와 `border-color`를 이용하여 **선의 두께와 색을 지정**할 수 있습니다.<br>
이 두 프로퍼티는 `border-style`을 지정해야 적용할 수 있습니다.<br>
`border-style`과 마찬가지로 사용하는 개수에 따라 적용되는 위치가 달라지고, 위치를 지정하여 따로 스타일을 지정할 수 있습니다.

```
/* css */
#box {
  background-color: green;
  border-color: red;
  border-style: solid dashed dotted double;
  border-width: 6px 8px 10px 12px;
}
```

### border의 shortcut

`border`프로퍼티는 Shortcut을 이용하여 한 번에 지정할 수 있습니다.

```
border: red solid 1px;
```

만약 한 면에만 선을 적용하고 싶으면 아래와 같이 작성합니다.

```
border-bottom: red solid 1px;
```

### border-radius

`border-radius`라는 프로퍼티는 border로 만든 **경계선을 둥글게 표현**할 때 사용합니다.<br>
`border-radius`의 값은 **모서리의 반지름의 값** 입니다.

```
/* css */
#box {
  background-color: green;
  border-color: red blue yellow black;
  border-style: solid dashed dotted double;
  border-width: 6px 8px 10px 12px;
  border-radius: 24px;
}
```

border-radius 또한 shortcut이 가능합니다.

- border-top-left-radius
- border-top-right-radius
- border-bottom-left-radius
- border-bottom-right-radius

```
/* css */
#box {
  background-color: green;
  border-color: red blue yellow black;
  border-style: solid dashed dotted double;
  border-width: 6px 8px 10px 12px;
  border-top-right-radius: 24px;
}
```

만약 `border-radius: 8px 16px 24px 36px`을 적용하면 `top-left: 8px`, `top-right: 16px`, `bottom-right: 24px`, `bottom-left: 36px`와 같이 시계 방향으로 적용이 됩니다.

또한 타원형에도 radius를 적용할 수 있습니다. 가로 반지름을 먼저 적고 세로 반지름이 그 다음에 따라옵니다.<br>
`border-top-left: 12px;`, `border-top-left: 24px 12px;`와 같이 적용이 가능합니다.<br>
네 모서리를 전부 사용하고 싶다면 `/`로 구분하여 차례대로 작성합니다.<br>
`border-radius: 가로 반지름 / 세로 반지름;`

```
/* css */
.radius {
	border-radius: 8px 16px 24px 36px / 36px 24px 16px 8px;
}
```

## Padding과 Margin

padding과 margin은 border의 내부와 외부에 존재하는 여백입니다.<br>
`border`를 기준으로 경계선 내부 여백을 패딩(Padding), 경계선 외부 여백을 마진(Margin)이라고 합니다.<br>
패딩과 마진 둘 모두 border처럼 네 방향 따로 혹은 한꺼번에 적용을 할 수 있습니다.

```
margin: 12px 24px 32px 63px; /* 상 우 하 좌 */
padding: 6px 12px 24px 32px; /* 상 우 하 좌 */
```

### 마진 상쇄

마진과 패딩은 비슷하지만 서로 다른 두 요소를 위 아래로 배치하면 마진은 서로 맞닿는 부분이 상쇄됩니다.
두개의 박스가 맞닿는 부분의 마진이 20px, 20px일 경우 40px가 아니라 20px입니다.

```
body { background: skyblue;}
.box {
	display: inline-box;
	width: 100px;
	height: 100px;
}
#top{
	background: pink;
	margin-bottom: 20px;
}
#bottom {
	background: lemonchiffon;
	margin-top: 40px;
}
```

## box-sizing

`box-sizing`은 박스의 크기를 화면에 표시하는 방식을 변경하는 속성입니다.<br>
width와 height는 요소(Element)의 콘텐츠의 크기를 지정합니다. 따라서, 테두리가 있는 경우에는 테두리의 두께로 인해서 원하는 크기를 찾기 어렵습니다.<br>
`box-sizing` 속성의 기본 값은 `box-sizing: content-box;`로 `content-box`를 기준으로 크기를 정합니다.<br> 
`box-sizing` 속성을 `border-box`로 지정하면 `border-box`의 크기는 `border` 바로 전 `padding`까지를 기준으로 정해집니다. 이렇게 하면 테두리를 포함한 크기를 지정할 수 있기 때문에 예측하기가 더 쉽습니다.<br>

- `box-sizing: content-box;`<br>width(height) = content size
- `box-sizing: border-box;`<br>width(height) = content size + padding + border size
