# Pickers

Picker는 사용자가 선택할 수 있는 고유한 값들을 스크롤 가능한 목록을 통해서 표시하는 것입니다. Date Picker는 Calendar View에서 날짜를 선택하는 것 혹은 numeric keyboard를 통해서 숫자를 직접 입력하는 것과 같이 값을 선택하는 추가 방법을 지원합니다. 두 가지 유형의 Picker 모두 단일 또는 다중 값을 선택하여 정보를 쉽게 입력할 수 있도록 합니다.

<br>

## Picker를 사용하여 중간에 긴 항목 목록을 중간-긴 항목 목록을 제공하는 것을 고려해 보세요

만약에 선택의 리스트가 짧은 경우에는, Pull-Down button을 대신 하는 것이 좋습니다. Picker를 사용하면 많은 항목을 빠르게 스크롤할 수 있지만 짧은 목록에 시각적 가중치가 너무 많이 추가될 수 있습니다. 반면에 매우 큰 항목의 리스트를 제공해야 하는 경우에는 list나 table을 사용하는 것이 좋습니다. List혹은 Table은 높이를 조정할 수 있으며, 표는 index를 포함할 수 있으므로, 목록의 한 section을 대상으로 지정하는 것이 훨씬 빠릅니다

자세한 내용은 [Table](https://developer.apple.com/design/human-interface-guidelines/ios/views/tables/)을 참고하세요

<br>

## 예측가능하고 논리적으로 정렬된 값을 사용하세요

스크롤할 수 있는 목록이 고정 된 경우 Picker의 선택 경우의 수가 많은 값을 숨기고 있을 수 있습니다. 사람들이 알파벳 순서대로 정렬된 국가 목록과 같이 예측가능한 목록일 때 선택의 속도가 빨라집니다

<br>

## Picker를 사용하기 위해서 화면을 스위칭하지 마세요

Picker는 편집 중인 필드의 아래 또는 근처에 나타날 때 잘 작동됩니다. Picker는 보통 화면 아래 혹은 popover 형태로 구현을 합니다

<br>


[Apple Developer Document - UIPickerView](https://developer.apple.com/documentation/uikit/uipickerview)를 참고하세요