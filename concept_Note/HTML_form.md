# 입력 양식(form)

## form 태그

HTML 입력 양식을 사용하려면 `<form>` 태그를 사용해야 합니다.<br>
form 태그 안에는 질문, 선택사항, 답변 작성 공간 등이 배치됩니다.
  
```
<form>
  <!-- 다양한 input form이 들어감 -->
</form>
```
 
### form 태그의 다양한 속성

`form`태그와 사용할 수 있는 속성은 매우 다양하지만, 그 중 3가지를 골라보자면 action과 method 속성은 필수 name 속성은 선택입니다.<br>
action 속성은 데이터를 보낼 URL을 지정합니다, 즉 해당 데이터를 처리할 웹 서버 URL을 값으로 가집니다.<br>
method 속성은 보내는 방식을 지정합니다, get또는 post를 값으로 가지며 두 방식의 기능은 동일하게 브라우저에서 사용자가 양식에 입력한 데이터를 서버로 보내는 역할을 수행합니다.<br>
name 속성은 form 요소의 이름을 지정해주는 속성으로 한 문서 안에 여러개의 `<form>`태그가 있을 경우 form들을 구분해주는 역할을 합니다.

```
<form name="joinForm" action="https://www.naver.com/" method="get">
	<label for="name">이름</label>
	<input id="name" name="name" type="text" />
	<button type="submit">네이버로 이동!</button>
	<button type="reset">리셋</button>
</form>
```

#### method 속성

method 속성은 자세히 알 필요가 있는데 사전적 의미로는 '방법, 체계성'을 의미합니다.<br>
method 속성은 `<form></form>`태그 안에 속한 input, button 요소 등을 서버로 전송하는 방법을 말합니다.<br>
간단하게 서버로 전송하는 방법을 지정해주는 속성으로 이 속성은 **이름과 값** 으로 구성되어있습니다.<br>
method 속성이 가지고 있는 속성 값으로는 GET과 POST가 있는데, 동일한 기능을 수행하지만 보내는 방식에 차이가 있습니다.<br>

##### GET 방식

GET은 서버로부터 정보를 조회하기 위해 설계된 메소드로 GET은 요청을 전송할 때 필요한 데이터를 Body에 담지 않고 쿼리스트링을 통해 전송합니다.
GET 방식은 파라미터가 주소창에 나오는 방식으로 해당 페이지의 파라미터만 알고 있다면 브라우저의 주소창에 그 주소를 입력하여 이동할 수 있습니다.<br>
당연히 하이퍼링크를 통해서도 이동이 가능하며, **우리가 흔히 지인과 정보를 공유할 때 URL을 복사하여 붙여넣기 할 수 있는 모든 페이지가 GET 방식으로 이루어진 페이지입니다.**<br>
이렇게 주소창의 복붙으로 이동하기 편하다는 편리성이 있으나 보안성이 없고 256byte ~ 4096byte까지의 데이터로 제한되는 용량 제한이 있습니다.

###### 파라미터와 쿼리스트링이란?

파라미터는 name(이름)과 value(값)으로 구성되어 있고 클라이언트(유저)에서 요청 시 넘어가는 데이터입니다.<br>
쉽게말해 유저가 입력한 정보 혹은 클릭한 정보가 서버의 특정 주소로 넘겨주는 데이터를 의미합니다.<br>
https://movie.naver.com/movie/bi/mi/basic.naver?code=208077 이 주소는 네이버 영화 페이지의 주소입니다.<br>
'?'가 시작을 의미하고 파라미터 이름=파라미터 값을 작성해주면 파라미터가 완성됩니다. 주소 뒤에 있는 '?파라미터 이름=파라미터 값'을 **쿼리스트링** 이라고 부릅니다.<br>
위 네이버 영화 페이지에서 스파이더맨: 노 웨이 홈의 정보가 들어있는 페이지는 'code'라는 피라미터와 '208077'라는 파라미터 값을 가지고 있는 것입니다.
만약, 요청 파라미터가 여러 개이면 &로 연결합니다. `?name1=value1&name2=value2`<br>
쿼리스트링을 사용하게 되면 URL에 조회 조건을 표시하기 때문에 특정 페이지를 링크하거나 북마크할 수 있습니다.

그리고 GET은 불필요한 요청을 제한하기 위해 요청이 캐시될 수 있습니다.<br>
js, css, 이미지 같은 정적 컨텐츠는 데이터양이 크고 변경될 일이 적어서 반복해서 동일한 요청을 보낼 필요가 없습니다.<br>
정적 컨텐츠를 요청하면 브라우저에서는 요청을 캐시해두고, 동일한 요청이 발생할 때 서버로 요청을 보내지 않고 캐시된 데이터를 사용합니다.<br>
프론트엔드 개발을 하다보면 정적 컨텐츠가 캐시돼 컨텐츠를 변경해도 내용이 바뀌지 않는 경우가 종종 발생합니다.<br>
이 때는 브라우저의 캐시를 지워주면 다시 컨텐츠를 조회하기 위해 서버로 요청을 보내게 됩니다.

##### POST 방식

POST는 리소스를 생성/변경하기 위해 설계되었습니다. GET과 달리 전송해야될 데이터를 HTTP 메세지의 Body에 담아서 전송합니다.<br>
POST 방식은 주소창에 파라미터가 넘어가는 방식이 아니라 HTTP 프로토콜의 body에 파라미터가 넘어가는 방식입니다.<br>
우리 눈에 보이지 않아 보안성이 유지되므로 주로 로그인 페이지, 회원가입 페이지, 글 작성 페이지, 파일 업로드 페이지 등에 사용됩니다.<br>
그리고 용량 제한이 있는 GET 방식과는 다르게 사용자의 입력을 표준 입력으로 넘겨주기 때문에 입력 내용의 길이 제한을 받지 않습니다.<br>
POST는 데이터가 Body로 전송되고 내용이 눈에 보이지 않아 GET보다 보안적인 면에서 안전하다고 생각할 수 있지만 POST 요청도 크롬 개발자 도구, Fiddler와 같은 툴로 요청내용을 확인할 수 있기 때문에 민감한 데이터는 반드시 암호화해 전송해야 합니다.

그리고 POST로 요청을 보낼 때는 요청 헤더의 Content-Type에 요청 데이터의 타입을 표시해야 합니다.
데이터 타입을 표시하지 않으면 서버는 내용이나 URL에 포함된 리소스의 확장자명 등으로 데이터 타입을 유추합니다. 만약, 알 수 없는 경우에는 application/octet-stream로 요청을 처리합니다.

###### HTTP란?

HyperText Transfer Protocol의 약자로 HTTP 혹은 HTTP 프로토콜이라고 표현합니다.<br>
이 HTTP는 '인터넷에서, 웹 서버와 사용자의 인터넷 브라우저 사이에 문서를 전송하기 위해 사용되는 통신 규약'입니다.
쉽게 웹 서버와 웹 브라우저 사이의 통신에 사용하는 프로토콜이며 **'요청(request)과 응답(response)으로 이루어진 프로토콜'** 이라고 이해하면 됩니다.

##### GET과 POST의 차이

GET은 Idempotent, POST는 Non-idempotent하게 설계되어 있습니다.<br>
idempotent(멱등)은 수학적 개념으로 다음과 같습니다
수학이나 전산학에서 연산의 한 성질을 나타내는 것으로, 연산을 여러 번 적용하더라도 결과가 달라지지 않는 성질
즉 동일한 연산을 여러 번 수행하더라도 동일한 결과가 나타나야 합니다.

GET이 idempotent하도록 설계되어 있다는 것은 GET으로 서버에게 동일한 요청을 여러번 전송하더라도 동일한 응답이 돌아와야 한다는 것을 의미합니다.
이에 따라 GET은 설계 원칙에 따라 서버의 데이터나 상태를 변경시키지 않아야되기 때문에 주로 조회를 할 때에 사용합니다.
예를 들어 브라우저에서 웹페이지를 열어보거나 게시글을 읽는 등 조회를 하는 행위는 GET으로 요청하게 됩니다.

반대로 POST는 Non-idempotent하기 때문에 서버에게 동일한 요청을 여러 번 전송해도 응답은 항상 다를 수 있습니다.
POST는 서버의 상태나 데이터를 변경시킬 때 사용됩니다. 게시글을 쓰면 서버에 게시글이 저장이 되고, 게시글을 삭제하면 해당 데이터가 없어지는 등 POST로 요청하게 되면 서버의 무언가는 변경되도록 사용됩니다.
이처럼 POST는 생성, 수정, 삭제에 사용할 수 있지만 POST 수정은 PUT 또는 PATCH, 삭제는 Delete가 더 용도에 맞는 메소드라고 할 수 있습니다.

## input 태그

`<input>` 태그는 입력 양식 중에서도 가장 많이 쓰이는 태그입니다.<br>
주로 사용자에게 입력을 받기 위해 사용되며, 빈 태그이기 때문에 종료태그를 사용하지 않습니다.<br>
`<input>`태그에는 텍스트뿐만 아니라 제출 버튼, 파일 업로드, 날짜 등 다양한 값이 입력 될 수 있습니다.<br>
`<input>`태그에 type이라는 속성을 설정하여 어떤 값을 입력할 것인지 결정합니다.<br>
`<input>`태그에는 `type`뿐만 아니라 `name`이라는 속성도 중요합니다.<br>
사용자가 서버로 데이터를 전송할 때, 입력 받은 데이터를 구분하기 위해 `name` 속성을 키(key)로, 입력 받은 데이타를 값(value)로 전송합니다.<br>
그렇기 때문에 `name`속성은 전송하는 데이터를 구분하는데 매우 중요한 역할을 합니다.

다양한 값을 입력받을 수 있는 input 태그

```
<h3>button</h3>
<input type="button" value="Button">
<hr>

<h3>search</h3>
<input type="search" name="search">
<hr>

<h3>checkbox</h3>
<input type="checkbox" name="python" value="python" checked>Python<br>
<input type="checkbox" name="javascript" value="javascript">Javascript<br>
<input type="checkbox" name="cpp" value="cpp">C++<br>
<hr>

<h3>file</h3>
<input type="file" name="myfile">
<hr>

<h3>radio</h3>
<input type="radio" name="gender" value="male" checked> 남자<br>
<input type="radio" name="gender" value="female"> 여자<br>
<hr>

<h3>color</h3>
<input type="color" name="color">
<hr>

<h3>date</h3>
<input type="date" name="birthday">
<hr>

<h3>number</h3>
<input type="number" name="quantity" min="1" max="10" step="1" value="1">
<hr>

<h3>range</h3>
<input type="range" name="points" min="0" max="10" step="1" value="5">
<hr>

<h3>reset</h3>
<input type="reset">
<hr>

<h3>time</h3>
<input type="time" name="mytime">
<hr>
```

추가로 `placeholder`라는 속성도 때에 따라 유용하게 사용 할 수 있습니다.<br>
우리가 입력창에서 자주 보았던 '아이디를 입력하세요'와 같은 가이드 문구를 지정하는데 사용하는 속성입니다.<br>
`placeholder`속성을 사용하여 입력한 값은 입력 칸 안에 나타나며, 입력 칸을 클릭하여 값을 입력하면 해당 문구가 사라지는 것을 볼 수 있습니다.<br>
`placeholder`속성과 비슷하지만 조금 다른 속성이 하나 더 있습니다, `value`입니다.<br>
`value`는 말 그대로 값을 할당하는 속성이기 때문에 `<input>`에서 `value`에 값을 넣으면 그 값이 입력 칸 안에 나타나는 것은 `placeholder`와 동일하나, 입력 칸을 클릭하더라도 값이 남아 있는 것을 볼 수 있습니다.

```
<form action="URL" method="get">
  <div>
    <label for="userid">아이디: </label>
    <input type="text" id="userid" name="id" placeholder="아이디를 입력하세요.">
  </div>
  <div>
    <label for="password">비밀번호: </label>
    <input type="password" id="password" name="password" placeholder="비밀번호를 입력하세요.">
  </div>
</form>
```

위 코드를 실행해보면 `type="password"`는 `text`와 다르게 입력 칸에 값을 입력하면 별표로 표시되어 노출되지 않음을 볼 수 있습니다.<br>
`<label>`태그는 입력 양식의 역할이 무엇인지 알려주는 이름표 역할을 수행합니다.<br>
`<label>`태그의 `for`속성과 `<input>`태그의 `id`속성 한 세트로 봅니다.<br>
`<label>`태그에 해당하는 이름표를 클릭하면 입력 칸이 활성화되는 것을 볼 수 있습니다.<br>

## select 태그

`<select>`태그는 드롭다운 박스를 만드는 틀이고 `<option>`태그로 드롭다운 내부에 아이템들을 하나씩 넣을 수 있습니다.<br>
미리 준비된 여러 개의 선택지를 골라 선택할 수 있는 선택 박스(Select box)를 배치하기 위해서는 `<select>`태그를 사용하며, `<select>`태그는 `<option>`태그로 이루어져 있는 각 선택지를 하나로 감싸는 역할을 수행합니다.

```
<select name="job" id="job">
  <option value="student">학생</option>
  <option value="teacher">선생님</option>
  <option value="etc">기타</option>
</select>
```

`<select>`태그는 `name`이라는 속성을, `<option>`태그는 `value`라는 속성을 필히 가져야합니다.<br>
`<select>`태그에서는 `<select>`태그의 `name`과 `<option>`태그의 `value`가 서로 짝을 이룹니다.

## textarea 태그

`textarea`태그는 한 번에 많은 양의 글을 입력 받을 때 사용합니다. 

```
<form>
  <div>
    <label for="introduce">자기소개: </label>
    <textarea name="introduce" id="introduce" placeholder="자기소개를 입력하세요" cols="20" rows="6"></textarea>
  </div>
</form>
```

`<textarea>`태그는 rows랑 cols 속성을 사용할 수 있는데, 값으로 숫자를 넣으면 `<textarea>`의 크기를 조정할 수 있습니다.

## button 태그

`button`태그는 `<input type="button">`으로도 만들 수 있지만 `<button>`태그를 이용하면 HTML 요소를 `<button>`태그 내부에 담아 사용할 수 있다는 장점이 있습니다.<br>
또한 `type="reset"`을 사용하면 입력 양식을 모두 초기화 할 수 있습니다.

```
<form>
  <div>
    <label for="introduce">자기소개: </label>
    <textarea name="introduce" id="introduce" placeholder="자기소개를 입력하세요" cols="20" rows="6"></textarea>
    <button type="submit">제출</button>
    <input type="reset">
  </div>
</form>
```

