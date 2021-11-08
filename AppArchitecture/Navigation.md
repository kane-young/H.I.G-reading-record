# Navigation

유저들은 네비게이션이 그들의 기대에 미치지 않는 한, 그것들에 대해서 잘 인식하지 못한다. 개발자는 앱의 구조와 목적을 지원하는 방식으로 네비게이션을 구현해야 한다. 네비게이션은 자연스럽고 친숙하게 느껴져야 하며 UI를 지배하거나 Content에서 초점을 벗어나게 해서는 안된다. iOS에서는 크게 세 가지 스타일의 네비게이션이 있다

<br>

## Hierarchical Navigation

목적지에 도달할 때까지 하나의 화면을 계속해서 선택해야 하는 `Navigation` 이다. 다른 목적지로 가려면, 왔던 길을 되짚어서 가거나 처음부터 다시 시작하고 다른 선택을 해야 한다. iOS의 `Settings` 나 `Mail` 을 보게 되면 이러한 계층적 네비게이션으로 구성되어 있는 것을 볼 수 있다

<br>

<img src="https://developer.apple.com/design/human-interface-guidelines/ios/images/NavigationHierarchical-Graphic.png" >

<br>

## Flat Navigation

다중 Content 카테고리를 스위칭할 수 있다. `Music`이나 `App Store` 를 통해서 해당 네비게이션 스타일을 확인할 수 있다

<br>

<img src="https://developer.apple.com/design/human-interface-guidelines/ios/images/NavigationFlat-Graphic.png">

<br>

## Content-Driven or Experience-Driven Navigation

Content 사이를 자유롭게 이동하거나, Content 자체가 네비게이션을 정의합니다. `Games`, `Books` 그리고 다른 몰입형 App들은 보통 해당 네비게이션 스타일을 사용합니다

<br>

<img src="https://developer.apple.com/design/human-interface-guidelines/ios/images/NavigationExperienceDriven-Graphic.png">

<br>

<br>

일부 앱은 여러 탐색 스타일을 결합하는데, 예를들어서 `flat navigation` 을 사용하는 앱은 각 카테고리내에서는 `hierarchical navigation`을 구현할 수 있습니다.

<br>

## Navigation 에서의 특징 / Tip

### Always Provide a clear path

유저는 항상 해당 앱에서 본인이 어떤 위치에 있는지 알아야 하며, 그들의 다음 목적지로 가는 방법을 알아야 한다. 네비게이션 스타일과 상관없이, 컨텐츠를 통과하는 경로가 논리적이고 예측 가능하며 따라가기 쉬운 것이 매우 중요하다. 일반적으로, 사람들에게 각 화면에 대한 하나의 경로를 제공한다. 여러 문맥에서 한 화면을 볼 필요가 있다면, `action sheet`, `alert`, `popover`, `modal view` 를 사용하는 것이 좋습니다.

<br>

### Design an information structure that makes it fast and easy to get to content

최소한의 탭, 스왑, 화면들이 필요한 방식으로 정보 구조를 구성합니다.

<br>

### Use touch gestures to create fluidity

최소한의 마찰(friction)을 하면서 인터페이스를 통해 쉽게 이동할 수 있도록 합니다. 예를 들어, 화면 측면을 swipe함으로써 이전 화면으로 돌아갈 수 있습니다.

<br>

### Use standard navigation components

가능하면 `page controls`, `tab bars`, `segmented controls`, `tableviews`, `collectionviews`, `splitviews` 와 같은 표준 탐색 컨트롤을 사용하십시오. 사용자는 이미 이러한 컨트롤들에 익숙해서, 직관적으로 App을 탐색하는 방법을 알 수 있습니다.

<br>

### Use a navigation bar to traverse a hierarchy of data

계층적인 구조에서 네비게이션 바의 제목은 현재 위치를 보여줄 수 있습니다. 그리고 뒤로가기 버튼은 이전 장소로 돌아가기 쉽게 해줍니다. 자세한 것은 [Navigation Bars](https://developer.apple.com/design/human-interface-guidelines/ios/bars/navigation-bars/)를 확인하세요

<br>

### Use a tab bar to present peer categories of content or functionality.

탭 바는 현재 위치를 유지하면서 사람들이 빠르고 쉽게 카테고리를 스위칭할 수 있게 해줍니다. 해당 가이드라인을 확인하세요. [Tab Bars](https://developer.apple.com/design/human-interface-guidelines/ios/bars/tab-bars/).

<br>

### **On iPad, use a split view instead of a tab bar.**

Split View들은 큰 대형 디스플레이를 더 잘 활용하면서 탭 바와 동일한 빠른 탐색을 제공합니다. 가이드라인을 확인하세요. [Split Views](https://developer.apple.com/design/human-interface-guidelines/ios/views/split-views/).

<br>

### Use a page control when you have multiple pages of the same type of content.

동일한 내용의 페이지가 여러 개인 경우 `page control`을 사용하시오. `page control` 은 사용 가능한 페이지의 수와 현재 사용 중인 페이지를 명확하게 전달합니다. `Weather` 앱의 경우 `page control` 을 사용하여 위치별 날씨 페이지를 표시합니다. 자세한 내용은  [Page Controls](https://developer.apple.com/design/human-interface-guidelines/ios/controls/page-controls/)를 확인하세요

<br>

> TIP
>
> Segmented controls와 toolbars는 탐색을 하지 않습니다. Segmented controls를 사용하여 정보를 다른 범주로 구성합니다. Toolbars을 사용하여 현재 문맥과 상호 작용하기 위한 컨트롤을 제공하세요. 이러한 요소에 대한 자세한 내용은 링크를 확인하세요  [Segmented Controls](https://developer.apple.com/design/human-interface-guidelines/ios/controls/segmented-controls/) and [Toolbars](https://developer.apple.com/design/human-interface-guidelines/ios/bars/toolbars/).

<br>

<br>

## 요약

1. 유저들은 네비게이션 바를 통해서 현재 위치를 파악하며, 목적지 이동에 대한 이동을 할 수 있다는 것을 경험적으로 알고 있다
2. 네비게이션은 Hierarchical, flat, Content-Driven or Experience-Driven 등 세 가지로 분류할 수 있으며, 섞어서 사용하는 앱들이 있다
3. 항상 하나의 화면에 대한 뚜렷한 경로가 정해져 있어야 한다. 여러 문맥이 존재한다면, alert, action sheet, pop over 등과 같은 형식으로 여러 문맥에 대해서 뚜렷하게 사용자에게 보여줘야 한다
4. 사용자들이 익숙한 Segmented Control, Tab bars, Table View 등을 활용해서 App을 탐색할 수 있는 방법을 제공해라
5. iPad에서는 Tab bar 대신에 Split View를 통해서 컨텐츠와 빠른 이동을 동시에 제공하자
6. 같은 컨텐츠를 여러 개 제공할 경우 page control를 통해서 나타내자

