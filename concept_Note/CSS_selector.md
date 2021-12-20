# 선택자(Selector)

선택자(Selector)는 크게 세 가지로 분류할 수 있습니다

- 단순 선택자
- 복합 선택자
- 가상 클래스 선택자

## 단순 선택자

단순 선택자로 사용할 수 있는 것은 다음과 같습니다.

- 타입 선택자(Type Selector)
- 아이디 선택자(Id Selector)
- 클래스 선택자(Class Selector)
- 전체 선택자(Universal Selector)
- 속성 선택자(Attribute Selector)

### 타임 선택자(Type Selector)

타입 선택자는 해당 태그를 가지는 모든 요소에 스타일을 적용합니다.<br>
선택자 자리에 태그를 넣으면 태그에 해당하는 모든 요소에 스타일이 적용됩니다.

```
p {
  color: red;
}
```

### 아이디 선택자(ID Selector)

아이디 선택자는 아이디 이름으로 스타일을 적용합니다.<br>
아이디(id)는 Identification의 약자이며 '신분증'이란 뜻을 가지고 있습니다.<br>
HTML 문서 내에서 중복된 아이디는 존재할 수 없으며, 이는 서로 다른 요소들을 구별하기 위한 장치로 사용합니다.

```
<!-- html -->
<p id="tinskyblue">이 p 태그의 id는 tinskyblue 입니다.</p>
```

```
/* css */
p {
  color: red;
}

#tinskyblue {
  background-color: blue;
}
```

### 클래스 선택자(Class Selector)

클래스 선택자는 Id와 마찬가지인 HTML 속성입니다.<br>
클래스는 비슷한 특징을 갖는 요소들을 지정하여 묶어 그룹으로 만들 수 있습니다.<br>
클래스 선택자는 HTML의 클래스 속성을 선택자로 사용하여 스타일을 적용합니다.<br>
클래스 선택자는 css에서 다음과 같은 형태를 가집니다. `.`과 지정할 class를 함께 사용하여 해당 class를 선택합니다.

```
<!-- html -->
<p class="developer">개발자</p>
<p class="consumer">소비자</p>
<p class="developer">개발자</p>
```

```
/* css */
.developer {
  color: red;
  background-color: blue;
}

.consumer {
  color: white;
  background-color: black;
}
```

### 전체 선택자(Universal Selector)

전체 선택자는 모든 요소에 스타일을 적용합니다.<br>
모든 요소에 적용시키기 때문에 속도가 저하될 수 있어서 쓰지 않기를 권장합니다.<br>
전체 선택자를 사용하고 싶다면 선택자 자리에 `*`를 입력하면 됩니다.

```
* {
  color: red;
}
```

### 속성 선택자(Attribute Selector)

속성 선택자는 특정 HTML 속성을 가지고 있는 모든 요소에 스타일을 적용합니다.<br>
속성 선택자를 사용하고 싶다면 선택자 오른쪽에 `[]`(대괄호)로 속성과 속성 값을 넣어 작성하면 됩니다.

```
선택자[속성명="속성값"] {
  color: red;
}
```

## 복합 선택자

복합 선택자는 HTML 요소 사이에 존재하는 부모-자식-후손이라는 개념에 대한 이해가 필요합니다<br>
코드로 나타내면 아래와 같습니다.

```
<body>
  부모 요소
  <div>
    나
    <p>자식 요소</p>
  </div>
</body>
```

부모-자식 관계는 상대적입니다.<br>
`<p>`를 기준으로 하면 `<div>`가 부모 요소가 됩니다.<br>
또한 `<div>`의 하위에 있는 `<div>`, `<p>`는 모두 자식 요소입니다.<br>
그리고 그 자식 요소와 그 아래에 포함된 모든 태그들을 아울러 후손 요소(Descendant Element)라고 부릅니다.
  
### 자식 선택자(Child Selector)

자식 선택자는 선택자 A와 모든 자식 중 선택자 B와 일치하는 요소를 선택합니다.<br>
자식 선택자는 복합 선택자이기 때문에 선택자를 두 개 사용하며 중간에 `>`(꺽쇠)를 씁니다.

```
선택자A > 선택자B {
  color: red;
}
```

선택자 A를 부모로 가지고 있는 선택자 B의 색만 변합니다.

```
<body>
  부모 요소
  <div id="me">
    나
    <div>자식 요소 1
      <p>후손 요소 1</p>
    </div>
    <p>자식요소 2</p>
  </div>
</body>
```

```
#me > p {
	background-color: red;
}
```

후손 요소에 해당하는 `<p>`태그는 색이 변하지 않고 `#me`의 바로 하위인 `<p>자식 요소 2</p>`만 색이 변합니다.<br>
이처럼 바로 하위에 해당하는 자식 요소에만 스타일을 적용하고 싶을 때 자식 선택자를 사용합니다.<br>

하지만 주의해야 할 점이 있습니다

```
#div > p {
	background-color: red;
}
```

다음과 같은 구조에서 자식 선택자를 `div > p`라고 사용하면 `div`바로 아래에 위치한 모든 p에 동일한 스타일이 적용됩니다.

### 후손 선택자

후손 선택자는 선택자 A의 모든 후손 중 선택자 B와 일치하는 요소를 선택합니다.<br>
후손 선택자 역시 복합 선택자이기 때문에 선택자를 두 개 사용하며 중간에 띄어쓰기를 사용합니다.

```
선택자A 선택자B {
  background-color: blue;
}
```

## 가상 클래스 선택자(Pseudo-class Selector)

가상 클래스 선택자는 요소의 특별한 상태를 정의하는데 사용합니다.<br>

일반적으로 쓰이는 클래스는 `<div class="tinskyblue">`, `tinskyblue{ ... }`와 같이 사용하지만 가상 클래스는 일반 클래스와 조금 다릅니다.<br>
스타일을 지정할 때 쓰인다는 점에선 클래스와 비슷하지만, 클래스와 달리 가상클래스는 직접 정의할 수 없고 실제 HTML에서는 보이지 않습니다.<br>

```
선택자:pseudo-class{
  color: red;
}
```

### 링크 선택자(The link pseudo-classes)와 동적 선택자(The user action pseudo-classes)

- E:link 방문하지 않은 링크 E를 선택합니다.
- E:visited 방문한 링크 E를 선택합니다.
- E:active E요소에 마우스 클릭 또는 키보드 엔터가 눌린 동안 E를 선택합니다.
- E:hover E요소에 마우스가 올라가 있는 동안 E를 선택합니다.
- E:focus E요소에 포커스가 머물러 있는 동안 E를 선택합니다.

:link와 :visited는 문서 안의 링크와 관련된 선택자입니다.<br>
나머지 세가지 선택자는 링크 요소뿐만 아니라 다른 요소에도 적용이 가능합니다.

```
<!-- html -->
<a href="https://github.com/tinskyblue/HTML-CSS_Concept_Note" target="_blank">tinskyblue</a>

/* css */
/* 방문하지 않은 링크일 때 */
a:link {
	color: turquoise;
}
/* 방문한 링크일 때 */
a:visited {
	color: green;
}
/* 링크에 마우스를 올렸을 때 */
a:hover {
	background-color: yellow;
}
/* 선택된 링크일 때 */
a:active {
	background-color: blue;
}
```

### 구조적 가상 클래스 선택자(Structural pseudo-classes)

구조적 가상 클래스 선택자는 위치를 기준으로 삼습니다.<br>
그래서 요소가 몇번째에 있느냐에 따라 스타일을 다르게 지정할 수 있게 해줍니다.<br>
순차적으로 같은 태그의 여러 항목이 있을 경우, 메뉴 간의 스타일을 변경하거나 할 때 이 선택자들이 유용하게 쓰입니다.

- E:root: 문서의 최상위 요소(html)를 선택합니다.
- E:nth-child(n): 앞으로부터 지정된 순서와 일치하는 요소가 E 라면 선택합니다. (E가 아닌 요소의 순서가 계산에 포함됨)
- E:nth-last-child(n): 뒤로부터 지정된 순서와 일치하는 요소가 E 라면 선택합니다. (E가 아닌 요소의 순서가 계산에 포함됨)
- E:nth-of-type(n): E 요소 중 앞으로부터 순서가 일치하는 E 요소를 선택합니다. (E 요소의 순서만 계산에 포함됨)
- E:nth-last-of-type(n): E 요소 중 끝으로부터 순서가 일치하는 E 요소를 선택합니다. (E 요소의 순서만 계산에 포함됨)
- E:first-child: 첫 번째 등장하는 요소가 E 라면 선택합니다. (E가 아닌 요소의 순서가 계산에 포함됨)
- E:last-child: 마지막에 등장하는 요소가 E 라면 선택합니다 (E가 아닌 요소의 순서가 계산에 포함)
- E:first-of-type: E 요소 중 첫 번째 E를 선택합니다. (E 요소의 순서만 계산에 포함됨)
- E:last-of-type: E 요소 중 마지막 E를 선택합니다. (E 요소의 순서만 계산에 포함됨)
- E:only-child: E 요소가 유일한 자식이면 선택합니다. (E가 아닌 요소가 하나라도 포함이 되면 선택되지 않습니다.)
- E:only-of-type: E 요소가 유일한 타입이면 선택합니다. (E가 아닌 요소가 포함되어도 E 타입이 유일하면 선택합니다.)
- E:empty: 텍스트 및 공백을 포함하여 자식 요소가 없는 E를 선택합니다.

