# 오디오와 비디오 태그

## 오디오 태그

`<audio>` 태그는 HTML5에서 새로 추가되었습니다.<br>
오디오 파일이 저장된 경로를 src(source)값으로 설정하면, 웹 페이지에 해당 오디오 파일을 재생하는 플레이어가 추가됩니다.<br>
오디오 태그는 다음과 같이 사용하며 확장자의 음원 형식을 뜻하는 `type` 속성은 생략할 수 있습니다.

```
<audio controls>
  <source src="오디오 URL" type="audio/mpeg">
</audio>
```

## 비디오 태그

`video` 태그는 비디오 파일이 저장된 경로를 src(source)값으로 설정하면, 해당 비디오 파일을 재생할 수 있는 플레이어가 웹 페이지에 추가됩니다.<br>
비디오 태그는 다음과 같이 사용하며 확장자의 음원 형식을 뜻하는 `type` 속성은 생략할 수 있습니다.<br>
또한, `<video>`태그는 `<audio>`태그와 다르게 `height`와 `width` 속성을 지정 할 수 있습니다.

```
<video controls>
  <source src="비디오 URL" type="video/mp4">
</video>
```
