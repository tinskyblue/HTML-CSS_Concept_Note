# HTML 이란?

HTML(Hyper Text Markup Language)은 컨텐츠의 구조를 정의하는 마크업언어로, 컨텐츠(내용)에 태그(마크)를 씌워 구조를 구분하여 정의합니다.

HTML에서는 <시작 태그>컨텐츠</종료 태그>와 같은 한 덩어리를 요소(Element)라고 합니다.

컨텐츠는 말 그대로 사용자가 접하는 텍스트, 이미지 등을 지칭합니다. 태그는 이러한 컨텐츠가 어떤 역할을 수행해야 하는지 지정하고, 그 사용 영역을 구분하여 구조를 정의합니다.

<ul>
    <li>HyperText는 단순 텍스트 이상의, 링크 등의 개념이 포함 된 텍스트입니다.</li>
    <li>Markup은 꺽쇠(<,>)로 이루어진 태그를 사용하는 규격입니다.</li>
</ul>

<h1>HTML 문서 예제</h1>

```
<!DOCTYPE html>
<html>
    <head>
        <title>Page Title</title>
    </head>
    <body>
        <h1>Hello HTML</h1>
        <p>Hello World!</p>
    </body>
</html>
```

<h3>예제 설명</h3>
<ul>
    <li><code>!DOCTYPE html</code>: 문서 형식(Document type)을 정의할 때 사용하는 문장으로 HTML 문서의 가장 처음에 배치되어 이 문서가 HTML 문서라고 브라우저에 알려주는 역할을 수행합니다.</li>
    <li><code>html</code>: 이 원소는 HTML페이지의 루트 원소입니다.</li>
    <li><code>head</code>: 이 원소는 문서에 관한 메타 정보를 포함합니다.</li>
    <li><code>title</code>: 이 원소는 문서의 제목에 특화되어 있습니다.</li>
    <li><code>body</code>: 이 원소는 페이지에 보여지는 내용을 포함합니다.</li>
    <li><code>h1</code>: 이 원소는 큰 헤딩을 말합니다.</li>
    <li><code>p</code>: 이 원소는 단락을 정의합니다.</li>
</ul>

<h3>HTML 주석</h3>

`<!--`로 시작하여 `-->`로 끝납니다.

<!-- 주석란 -->
