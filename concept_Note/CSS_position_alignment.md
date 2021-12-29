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

#### display: none

## position

### position: static

### position: relative

### position: absolute

### position: fixed

### z-index

## float
