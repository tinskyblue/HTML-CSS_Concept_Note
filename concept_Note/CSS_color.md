# CSS의 색상

CSS에서 색과 관련된 값은 일반적으로 3가지 방법이 쓰입니다.

- 키워드
- hex code
- rgb

HTML 색상표 페이지에서 여러 색상 값을 확인할 수 있습니다. (https://html-color-codes.info/Korean/)

## 키워드

키워드는 색을 지정하는 가장 간단한 방법 중 하나입니다.<br>
내부적으로 지정되어 있는 키워드를 쓰면 색을 지정할 수 있습니다. 브라우저는 140가지 색상 이름을 지원합니다.

```
.box {
  width: 200px;
  height: 100px;
  background-color: blue;
}
```

## RGB

빛의 3원색인 빨간색(Red), 초록색(Green), 파란색(Blue)를 혼합하여 색을 표현하는 방식입니다.<br>
RGB 값은 0 ~ 255의 값으로 나타냅니다.

<img src="https://user-images.githubusercontent.com/57892556/146678640-67ef4db5-58e3-452f-9c1e-abce05f1e74d.png" width="300" height="300"/>

```
.box {
  width: 200px;
  height: 100px;
  background-color: rgb(121, 73, 211)
}
```

## HEX Code

HEX 값은 16진수 6자리 코드로 색상을 표현하는 방식입니다.<br>
6자리 코드는 각각 2자리씩 빨간색, 녹색, 파란색에 대한 값을 표현합니다.<br>
예를 들어 빨간색은 #FF0000, 보라색은 #800080으로 표현됩니다.

```
.box {
  width: 200px;
  height: 100px;
  background-color: #720000;
}
```

## Alpha

HEX code와 RGB에는 alpha라는 값이 존재합니다.이는 우리가 흔히 아는 투명도입니다.<br>

### RGB

**rgb**는 rgba를 통해 alpha 값을 표현할 수 있고, hex code는 6자리에 2자리를 추가하여 alpha 값을 표현할 수 있습니다.<br>
rgba에서 alpha 값은 0 ~ 1 사이의 숫자로 결정이 됩니다. 투명도 0% ~ 100%와 같습니다.<br>
rgba(R, G, B, alpha)

```
.box {
  width: 200px;
  height: 100px;
  background-color: rgba(121, 73, 211, 0.5);
}
```

### HEX Code

**HEX Code**에서 alpha 값은 00~FF사이의 16진수 숫자로 결정이 됩니다. 투명도 0 ~ 100%와 같습니다.<br>
#RRGGBBAlpha

```
.box {
  width: 200px;
  height: 100px;
  background-color: #72000055;
}
```
