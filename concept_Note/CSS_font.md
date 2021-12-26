# 폰트(Font)

폰트와 관련된 프로퍼티는 크게 폰트 크기(`font-size`), 폰트 종류(`font-family`), 폰트 형태(`font-style`, `fontweight`)가 있습니다.

## font-family

font-family는 원하는 폰트의 종류를 지정할 수 있습니다.

```
font-family: '폰트이름1' '폰트이름2';
```

일반적으로 한 단어로 구성된 폰트명은 따옴표 없이 사용을 할 수 있지만 **띄어쓰기 또는 하이픈(-)이 들어간 폰트명의 경우 따옴표를 사용하여 하나의 폰트명임을 명시**해야 합니다.

`font-family`를 통해 폰트의 종류를 정의할 때는 여러 개의 폰트를 지정하는게 좋습니다.<br>
모든 이용자의 기기에 동일한 폰트가 없을 수도 있기 때문에 폰트를 여러개 지정하여 앞 순서에 위치한 폰트부터 차례대로 적용합니다.<br>
때문에 마지막 폰트를 모든 OS 및 브라우저에 기본으로 설치된 일반 글꼴로 두어 문제가 발생하지 않도록 해야 합니다.<br>
보편적으로 시용되는 글꼴은 **Sana-serif, Serif, Cursive, Fantasy, Monospace** 등입니다.

## 웹 폰트(Web Font)

웹 폰트는 링크를 통해 폰트를 불러오는 방식을 뜻합니다.<br>
가장 많이 쓰이는 폰트 사이트는 구글에서 제공하는 구글 폰트입니다. [구글 폰트](https://fonts.google.com/)<br>
원하는 폰트를 찾은 후에 원하는 굵기를 선택하여 Select this style을 클릭한 뒤 사이트 맨 오른쪽 위에있는 ![image](https://user-images.githubusercontent.com/57892556/147409692-76e69541-25a9-4295-ad16-0acc80b5635f.png) Hide your selected families 이미지를 클릭하여 `<link>` 또는 `@import` 방식으로 폰트를 가져올 수 있습니다.

`<link>`는 HTML에 CSS 파일을 연결할 때와 동일하게 `<link>` 태그를 이용하여 가져옵니다.<br>
반면 `@import`는 CSS파일에서는 `<style>`태그를 제거하고 `@import`를 바로 작성하거나 HTML 파일에 `<style>` 태그를 이용하여 추가할 수 있습니다.
