# 표(Table)

표는 데이터를 깔끔하고 효율적으로 보기 좋게 정리할 수 있는 정리 방식 중 하나 입니다.

## 테이블의 구조

표의 일반적인 구성은 아래와 같습니다.

- 전체를 담고 있는 테이블
- 데이터를 담은 데이터 셀
- 각 열의 제목을 담은 제목 셀
- 각 행

행(`<tr>`)을 기준으로 테이블 태그를 작성해야 편하게 작성할 수 있습니다.

![캡처](https://user-images.githubusercontent.com/57892556/146440165-03a0ceba-5793-401f-b8c0-3ac7a0dd0bd3.JPG)

```
<table> <!--전체를 담고 있는 표-->
	<tr> <!--각 행-->
		<th>제목 셀</th> <!--각 열의 제목을 담은 제목 셀-->
		<th>입니다</th>
		<th>th</th>
	</tr>
	<tr>
		<td>데이터 셀</td> <!--데이터를 담은 데이터 셀-->
		<td>입니다</td>
		<td>td</td>
	</tr>
	<tr>
		<td>표의 행</td>
		<td>입니다</td>
		<td>tr</td>
	</tr>
</table>
```

![Table1](https://user-images.githubusercontent.com/57892556/146440901-d9b628d8-03b5-42bd-89f8-4f05b62d2a3f.JPG)

```
<table>
	<tr>
		<th>제목</th>
		<td>데이터</td>
		<td>데이터</td>
	</tr>
	<tr>
		<th>제목</th>
		<td>데이터</td>
		<td>데이터</td>
	</tr>
	<tr>
		<th>제목</th>
		<td>데이터</td>
		<td>데이터</td>
	</tr>
</table>
```

- `<th>` = table heading
- `<td>` = table data
- `<tr>` = table row

행(`<tr>`)을 기준으로 테이블 태그를 작성해야 편하게 작성할 수 있습니다.

## 테이블 태그의 속성

테이블 태그에는 두 행 혹은 두 열을 차지하게 하는 속성이 있습니다.<br>

- `colspan="숫자"`는 **"숫자"** 만큼 셀이 행을 점유합니다.
- `rowspan="숫자"`는 **"숫자"** 만큼 셀이 열을 점유합니다.

![Table2](https://user-images.githubusercontent.com/57892556/146441921-5456f5a1-b004-42df-bda4-f5cef45fe8b3.JPG)

```
<table>
	<tr>
		<th>제목</th>
		<td>데이터</td>
		<td>데이터</td>
	</tr>
	<tr>
		<th>제목</th>
		<td colspan="2">데이터</td>
	</tr>
	<tr>
		<th>제목</th>
		<td>데이터</td>
		<td>데이터</td>
	</tr>
</table>
```
