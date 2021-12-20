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

