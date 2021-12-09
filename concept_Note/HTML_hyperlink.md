# 하이퍼링크(Hyperlink)

하이퍼 링크는 간단하게 말하면 **주소 링크** 입니다.<br>
하이퍼 텍스트 안에서 직접 모든 형식의 자료를 연결하고 가리킬 수 있는 참조 고리입니다.<br>
동영상, 음악, 그림, 프로그램, 파일, 글 등의 특정 위치를 지정할 수 있습니다.<br>
이는 하이퍼텍스트의 핵심 개념이며, HTML을 비롯한 마크업언어에서 구현하고 있습니다.

- "하이퍼링크"(hyperlink)라는 용어는 1965년 테드 넬슨이 제너두 프로젝트(project Xanadu)를 시작하면서 고안하였습니다.

## 링크 태그 `<a>`

`<a>`는 anchor(닻)의 약자로, HTML에서 하이퍼 링크의 역할을 수행합니다.<br>
`<a>`태그를 사용하면 링크를 통해 다른 웹페이지로 이동하거나 문서로 이동할 수 있는 통로가 만들어집니다.<br>
`<a>` 태그는 태그와 콘텐츠, 속성으로 구성되어 있으며, `<a 속성>콘텐츠</a>` 와 같이 작성합니다.<br>
**속성(attributes)은 태그의 특징, 즉 태그에 대한 추가 정보의 모음** 입니다.<br>
링크 태그에서 갖춰야 할 필수 속성은 **링크 주소** 입니다.<br>
링크 주소에 들어가는 종류는 **키(Key)**, 그에 따른 실제 링크 주소는 **값(Value)** 으로 `<a 키="값">hyperlink</a>`와 같이 작성합니다.<br>
링크 태그의 주소 이외에 속성을 추가한다면 이름 속성을 추가할 수 있습니다.<br>
`<a 주소="https://github.com/tinskyblue/HTML-CSS_Concept_Note" 설명="HTML-CSS_Concept_Note 메인">HTML-CSS_Concept_Note</a>`<br>

### `<a>`의 속성, href

`<a>` 태그는 태그, 콘텐츠 이외에 href 라는 속성을 함께 사용해야 올바르게 동작합니다.<br>
**href** 는 **Hypertext Reference** 의 약자로 `<a>`가 참조하는 웹 사이트 주소(경로)를 값으로 가집니다.<br>
예시로 `<a>`는 https://github.com/tinskyblue/HTML-CSS_Concept_Note 라는 사이트를 연결하고 있다는 정보를 담습니다.<br>
이 href는 속성칸에 들어가며 속성은 링크 태그의 이름 바로 뒤에 한 칸 공백을 가진 뒤 작성을 해야합니다.

실제로 링크 태그를 작성해보겠습니다.

과정
```
<a href="https://github.com/tinskyblue/HTML-CSS_Concept_Note" 설명="HTML-CSS_Concept_Note 메인">HTML-CSS_Concept_Note</a>
```
  
결과
<pre>
<a href="https://github.com/tinskyblue/HTML-CSS_Concept_Note" 설명="HTML-CSS_Concept_Note 메인">HTML-CSS_Concept_Note</a>
</pre>

## `<a>`의 속성, target

**target** 속성은 링크를 클릭했을 때 해당 페이지를 어디에서 열지 정하는 속성입니다.<br>
**target** 속성에서 사용할 수 있는 대표 값은 _self와 _blank 입니다.<br>

- targt="_self" 는 현재 탭에서 링크를 엽니다.
- target="_blank" 는 새 탭 혹은 새 창에서 링크를 엽니다.

과정
```
<a href="https://github.com/tinskyblue/HTML-CSS_Concept_Note" target="_self">HTML-CSS_Concept_Note_self</a>
<a href="https://github.com/tinskyblue/HTML-CSS_Concept_Note" target="_blank">HTML-CSS_Concept_Note_blank</a>
```

결과
<pre>
<a href="https://github.com/tinskyblue/HTML-CSS_Concept_Note" target="_self">HTML-CSS_Concept_Note_self</a>
<a href="https://github.com/tinskyblue/HTML-CSS_Concept_Note" target="_blank">HTML-CSS_Concept_Note_blank</a>
</pre>
