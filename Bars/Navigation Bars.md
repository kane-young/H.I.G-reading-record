# Navigation Bars

- 네비게이션 바는 앱 스크린 상단, 상태 바 아래에 위치하게 되며, 일련의 계층적 화면을 탐색할 수 있습니다. 
- 새 화면이 보여지게 되면, 이전 화면 제목으로 Back Button이 만들어져 네비게이션 바 좌측에 위치하게 됩니다.
- 그리고 가끔, 네이게이션 바 우측에서는 Done, Edit 과 같은 버튼들이 위치하기도 합니다.
- SplitView에서 네비게이션 바는 SplitView의 단일 창에 나타날 수도 있습니다.
- 네비게이션 바는 반투명하고 배경색을 가질 수 있으며, 키보드가 화면에 있는 경우 혹은 제스처가 발생할 경우 또는 View의 크기가 조정될 때 숨기도록 해야합니다.

<br>

<img width="400" src="https://user-images.githubusercontent.com/64566207/142430204-72af2eae-3cbf-446f-9229-fb6d36b67911.png">

<br>

## 더 몰입감 있는 경험을 위해서 임시적으로 네비게이션 바를 숨기는 것을 고려해보자

예를들어, Photos앱은 사용자가 풀스크린으로 사진을 보려고 할 경우, 네비게이션 바와 다른 인터페이스를 모두 숨긴다. 만약에 이렇게 구현을 시도한다면, 간단한 제스쳐인 탭과 같은 제스쳐로 복구될 수 있도록 해야 한다.

<br>

개발자 가이드라인인, [UINavigationBar](https://developer.apple.com/documentation/uikit/uinavigationbar)를 참고하세요

<br>
<br>

# Navigation Bar Titles

## 네비게이션 바에 현재 뷰의 제목을 보여주세요

- 대부분의 경우에는, 네비게이션 바에 제목이 있는 것이 유저들에게 하여금 자신이 무엇을 보고 있는지 이해하는데 도움을 준다.
- 하지만, 만약에 이것이 중복된다면 과감하게 비워두는 것도 좋다
- 예를들어, Note 앱 같은 경우에 첫 번째 줄에 해당 노트의 제목이 있을 것이다. 이럴 경우에는 네비게이션 바에 제목을 적으면 중복되기에 비워두는 것이 좋다

<br>

## 현재 뷰의 정보를 더 강조하고 싶다면 큰 크기의 제목을 사용하세요

- 어떤 앱에서는 큰 Bold체의 텍스트로 작성된 제목이 유저들이 탐색을 하거나 검색을 할 때를 돕습니다.
- 예를 들어, tabbed layout에서는 큰 제목이 명료하게 탭이 활성화 되었음을 알리고 사람들에게 가장 위로 스크롤 되었음을 알려줄 수 있습니다.
- Music 앱의 경우에는 앨범, 아티스트, 플레이리스트, 라디오와 같은 컨텐츠 영역과 구분 짓는 용도로 큰 제목을 사용합니다.
- iOS 13 이상부터는, 큰 제목의 네비게이션 바는 배경요소나 그림자 효과를 기본 값으로 가지지 않습니다. 또한, 사용자가 컨텐츠를 스크롤하기 시작하면 큰 제목에서의 일반 제목으로의 전환효과가 일어납니다.

자세한 내용은 [PrefersLargeTitles](https://developer.apple.com/documentation/uikit/uinavigationbar/2908999-preferslargetitles)를 참고하세요

<br >

<img width="747" alt="스크린샷 2021-11-18 오후 11 24 23" src="https://user-images.githubusercontent.com/64566207/142439553-f297380a-749b-4fae-9f2d-4fa3f09223cc.png">

<br>

## 큰 제목의 네비게이션 바를 사용할 때는 테두리를 숨기시오

- iOS 13 이상에서는 네비게이션 바의 하단 부분의 경계선을 그림자를 없앰으로써 숨길 수 있습니다. (이 부분은 유저가 아래로 스크롤함으로써 다시 나타난다.)
- 경계선이 없는 네비게이션 바 스타일은 Content와 Title이 이어져 있는 느낌을 향상시켜줍니다.
- 하지만, Standard 네비게이션 바에서는 경계선이 없는 스타일을 사용하지 않습니다. 왜냐하면, 네비게이션 바의 제목과 버튼을 좀 더 뚜렷하게 해주기 위해서죠
- iPad의 SplitView에서는 예외가 있는데, primary view와 secondary view에 일관성을 유지해주기 위해서 경계선이 없는 스타일을 사용하기도 합니다.

<br>
<br>

# Navigation Bar Controls

## 너무 많은 Control들을 배치시키는 것을 피해라

- 일반적으로 네비게이션 바는 뒤로 가기, 현재 제목, Content를 관리하는 하나의 Control 이외에는 포함하지 않는다.
- 네비게이션 바에 segmented control을 사용할 것이라면, 그 네비게이션 바에는 segmented control을 제외하고는 제목이나 다른 Control 요소가 배치되면 안된다

<br>

- 만약에 네비게이션 바 Control를 위한 사용자 정의 glyph를 만드려고 한다면, 아래 사이즈를 따르고 균형을 맞춰라

<img width="748" alt="스크린샷 2021-11-18 오후 11 40 47" src="https://user-images.githubusercontent.com/64566207/142439552-dd0dce9a-5ede-4eb7-9f15-ac6e01fe55bd.png">

<br>

## 표준 Back Button을 사용하세요

- 커스텀 Back Button을 만드려고 한다면, 사람들이 Back Button이라고 인식할 수 있게 구성해야 한다.
- 또한 앱 전체에서 Back Button을 일관성 있게 구현해라

<br>

## 다중 영역 이동 경로를 포함하지 마십시오

- Back Button은 항상 이전 화면으로 돌아가는 단일 작업을 수행해야 된다. 현재 화면으로 가려고 한다면 전체 경로가 없으면 사람들이 길을 잃을 수 있기에, 앱의 계층을 평평하게 만드는 것을 고려해보세요

<br>

## 텍스트 버튼에는 충분한 공간을 확보해주세요

- 만약 내비게이션 바에 여러 개의 텍스트 버튼을 추가한다면, 텍스트 버튼이 알아보기 힘들 수도 있습니다.
- 버튼 사이에 고정된 공간을 부여해서 구분되도록 만들어주어야 합니다.
- 개발자 가이드: [UIBarButtonSystemItemFixedSpace](https://developer.apple.com/documentation/uikit/uibarbuttonsystemitem/uibarbuttonsystemitemfixedspace) / [UIBarButtonItem](https://developer.apple.com/documentation/uikit/uibarbuttonitem)

<br>

## 앱의 정보 계층을 단순화하기 위해 Segmented Control의 사용을 고려해보세요

- 만약 네비게이션 바에 Segmented Control을 사용할 것이라면, 앱의 계층 중에서 최상위에서만 사용해라

<br>

<img width="499" alt="스크린샷 2021-11-18 오후 11 57 25" src="https://user-images.githubusercontent.com/64566207/142439540-b7f4a723-1fe7-4fea-9bfd-af853ea7b691.png">
