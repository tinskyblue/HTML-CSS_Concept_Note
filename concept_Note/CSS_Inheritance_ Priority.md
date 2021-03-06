# 상속과 우선순위

## 상속

CSS를 사용하면서 가끔 내가 스타일을 적용한 적이 없는데 자동으로 적용된 경우를 본 적 있을 겁니다.<br>
이런 경우의 대부분은 CSS를 잘못썻기 때문에 발생한 것이 아니라 상속으로 인해 부모나 조상 요소에 적용된 CSS 프로퍼티를 자식 혹은 후손 요소가 물려 받아서 생기는 일입니다.

부모 요소에 `color: red;`를 적용 할 경우 부모 요소의 글씨만 빨갛게 변하는게 아닌 하위 요소 모두에게 적용되는 것을 볼 수 있습니다.<br>
이렇게 상속된 요소는 덮어 씌울 수도 있습니다.<br>
하위 요소의 속성에 `color: blue;`를 적용하면 하위 요소는 파란색이 됩니다.<br>
이러한 상속이라는 기능이 없었다면 우리는 모든 글자에 빨간색을 적용하고 싶을 때 요소마다 직접 일일이 폰트 색을 적용해야 했을 겁니다.

하지만 모든 CSS 프로퍼티에 상속이 적용되는게 아닌 `width`, `height`, `margin`, `padding`, `display` 등 상속이 되지않는 프로퍼티 또한 많습니다.<br>
상속이 되지않는 프로퍼티는 W3C에서 제공하는 Full property table에서 찾아볼 수 있습니다.<br>
이러한 상속이 되지 않는 프로퍼티를 상위에서 상속 받기를 원한다면 값으로 `inherit`을 주어 해결할 수 있습니다.

## 우선순위

CSS의 약자는 Cascading Style Sheet입니다.<br>
여기서 Cascading은 CSS 적용 우선순위를 뜻합니다. 이 적용 우선순위에는 세 가지의 규칙이 있습니다.

- 1.중요도
- 2.명시도
- 3.선언순서

### 중요도

중요도는 CSS가 어디에 선언되었는지에 따라 우선순위가 달라집니다.

- 1.`<head>` 태그 내의 `<style>` 태그
- 2.`<head>` 태그 내의 `<style>` 태그 내의 `@import`문
- 3.`<link>` 태그로 연결된 CSS
- 4.`<link>` 태그로 연결된 CSS 내의 `@import` 문
- 5.브라우저 디폴트 스타일시트

### 명시도

CSS는 명시도에 따라 우선순위가 달라집니다.

- 1.`!important`
- 2.인라인 스타일 inline style
- 3.아이디 선택자 id selector
- 4.클래스, 속성, 가상클래스 선택자 class, attribute, pseudo class selector
- 5.태그 선택자 type selector
- 6.전체 선택자 universal selector
- 7.상속 `inherit`

### 선언순서

선언 순서에 따라서 또한 우선 순위가 달라집니다. 나중에 선언된 스타일이 우선 적용됩니다.
