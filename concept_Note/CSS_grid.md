# grid layout

Grid는 격자 또는 눈금을 뜻합니다.<br>
CSS에서 grid는 행렬을 통해 요소들을 좀 더 정교하게 그리고 복잡하게 정렬 및 배치를 할 수 있는 레이아웃입니다.<br>

## Grid 요소들의 명칭

grid 내부 요소들은 **Lines, Track, Area, Gap** 이라는 명칭을 가진 영역으로 이루어져 있습니다.

### Grid Lines

Grid Lines는 격자를 이루는 선의 집합을 뜻합니다.<br>
Grid를 이루는 행과 열의 선들을 모두 Grid Lines라고 부릅니다.<br>
엑셀의 행과 열을 생각하시면 됩니다. Grid Lines에서 행은 Grid row, 열은 Grid column이라고 말합니다.

### Grid Track

평행한 Grid Line 두 줄 사이의 공간을 Grid Track이라 부릅니다.

### Grid Area

Grid Line 네 줄로 둘러싸인 공간을 Grid Area라고 부릅니다.<br>

## Grid Cell

Grid Area 안에 더 이상 쪼개지지 않는 한 칸을 Grid Cell이라고도 부릅니다. 이러한 Grid Cell이 한 개일 때 혹은 그 이상일 때 해당 공간을 Grid Area라고 합니다.

### Grid Gap

행 여러 개(Rows) 혹은 열 여러 개(Columns) 사이의 간격을 Grid Gap이라고 부릅니다. 이해하기 쉽게 Grid Lines의 두께라고 생각하시면 됩니다.

## Grid의 구성

Grid는 부모 요소인 **Grid Container**와 자식 요소인 **Grid items**로 구성되어 있으며, 각각 사용하는 프로퍼티가 다릅니다.<br>

### grid container: template

#### display: grid / inline-grid

Grid item들은 Grid Container안에 배치하기 때문에 display: grid;를 설정하는 것으로 시작합니다.
`display: inline-grid;`는 block과 inline-block의 관계를 생각하시면 됩니다.

```
.container {
  display: grid;
  /* display: inline-grid; */
}
```

#### grid-template-rows / grid-template-column

컨테이너에 Grid Track의 크기들을 지정해주는 속성입니다.
행에 해당하는 Grid Track은 `grid-template-rows` 열에 해당하는 Grid Track은 `grid-template-column`으로 지정할 수 있습니다.

```
.container {
  grid-template-rows: 100px 300px 200px;
  grid-template-column: 1fr 3fr 2fr;
  /* 1fr 2fr 1fr은 1:2:1 비율입니다. */
  /* repeat(3, 1fr)은 1fr을 3번 반복합니다 */
  /* minmax(100px, auto)는 최소크기를 100px로 최대는 내용에 따라 자동으로 늘어납니다 */
  /* auto-fill, auto-fit은 column의 개수를 미리 정하지 않고 설정된 너비가 허용하는 한 최대한 셀을 채웁니다.
     repeat(auto-fill, minmax(20%, auto));는 20%크기로 설정했으므로, 1개의 row에 5개의 셀이 들어갑니다. auto-fill은 셀의 개수가 모자라면 빈 공간이 생기지만 auto-fit은 빈 공간을 채웁니다. */
 }
 ```
 
 #### row-gap / column-gap / gap
 
 그리드 셀 사이의 간격을 설정합니다.
 
 ```
 .container {
  row-gap: 10px;
  column-gap: 10px;
  /* gap: 10px 10px나 gap: 10px와 같이 한꺼번에 지정할 수도 있습니다. */
}
```

초기에는 grid-gap이라고 grid-를 붙여서 사용했습니다
IE에서는 gap의 대체 속성이 없기 때문에, IE와 구조를 통일해야하면 처음부터 gap을 사용하지 않고 구조를 설계하는게 좋습니다.

