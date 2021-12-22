# 박스(Box) 모델

HTML의 모든 요소(Element는 상자(Box)의 형태를 갖습니다.<br>
태그 내부에 위치해 실제 표시되는 내용을 Content(내용)라고 합니다.<br>
보이지는 않지만 이러한 컨텐츠를 감싸고 있는 다른 요소들이 있습니다. 이러한 박스 형태 전체를 가리켜 박스 모델(Box Model)이라고 부릅니다.<br>
박스 모델은 내용(Content), 패딩(Padding), 경계선(Border), 마진(Margin)으로 이루어져 있습니다.

![Box](https://user-images.githubusercontent.com/57892556/147089559-ac4ba5b0-d905-48c0-b969-81eb2ebb9a7e.JPG)

732x309.672 는 Content의 폭과 높이입니다.<br>
내용(Content)는 이미지나 텍스트와 같이 우리가 코드 상에서 태그 사이에 담은 내용, 즉 실제로 담고 있는 부분입니다.<br>
다음으로 경계선(Border)은 컨텐츠를 감싸고 있는 테두리입니다.<br>
마진과 패딩은 둘 다 여백을 뜻하지만 경계선(Border)를 기준으로 역할이 다릅니다.<br>
패딩(Padding)은 컨텐츠와 경계선 사이의 여백이지만 마진(Margin)은 경계선 밖의 여백입니다.
