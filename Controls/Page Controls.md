# Page Controls

Page Control는 각각 플랫한 목록의 페이지를 나타내는 이미지 indicator의 행을 나타냅니다. indicator의 행 스크롤은 사람들이 그들이 찾는 페이지를 찾는데 있어서 도움을 줍니다. Page Control는 계층 구조 혹은 비선형 구조의 페이지를 시각화하거나 탐색하는데에는 도움이 되지 않습니다. Page Control는 원하는 수의 페이지를 처리할 수 있으므로, 사용자 정의 목록을 작성할 수 있는 상황에서 특히 유리합니다.

<br>



<br>

Page Control는 Indicator의 외관(appearance)을 조정하여 리스트에 대한 더 자세한 정보를 제공할 수 있습니다. 예를들어서, Page Control는 목록에서 해당 페이지의 위치가 어딘지 쉽게 파악할 수 있도록 강조 표시를 합니다. Page Control가 들어갈 수 있는 공간보다 리스트의 목록이 길다면, Page Control의 양쪽 끝을 축소시킨 듯한 모양으로 더 많은 페이지가 있음을 사용자에게 암시할 수 있습니다

<br>

> DEVELOPER NOTE <br>
API에서는 tapping은 (한번의, 별개의) interaction이다. 문지르는 것이 연속적인 interaction이다. 가이드 라인, [UIPageControl.interactionState](https://developer.apple.com/documentation/uikit/uipagecontrol/interactionstate)를 참고하세요

<br>

## 매우 긴 리스트를 보여주는 리스트 뷰의 경우에 Page Control을 보는 것을 고려해봐라

Page의 list를 보기 위해서, 사람들은 일반적으로 다음 혹은 이전 페이지로 넘길 것(Swipe)이다. 그러나 이 동작은 수 많은 페이지를 넘기다(Swipe)보면 굉장히 피곤해집니다. Page Control을 Scrubbing(문지르다)하는 것은 각 페이지를 넘기는(Swipe) 것보다 빠르고 쉬울 수 있습니다.

PageControl은 tapping과 scrubbing이라는 다른 visual feedback을 제공할 수 있습니다. 사람들이 다음 혹은 이전 페이지를 위해서 tap할 경우, Page Control는 Page를 Swipe를 할 때 볼 수 있는 page-scrolling 애니메이션을 제공할 것입니다.srcub을 할 경우에는 전환 애니메이션 없이 바로 화면이 전환됩니다

<br>

> **요약** <br>
Page Control을 사용하여 화면을 전환하는 방법은 세 가지 이다. Tap, Scrub, Swipe <br>
<br>
Tap : Page Control을 직접적으로 Tap하면 한 페이지씩 앞 혹은 뒤쪽으로 전환된다. 이때는 넘겨지는 애니메이션으로 화면 전환된다.<br>
Scrub : Page Control를 직접 문지르면 화면 전환 애니메이션 없이 해당 페이지로 전환된다.

<br>

## Scrubbing을 하는 동안에는 Page 전환 애니메이션을 사용하지 마라

유저들은 scrub을 통해서 빠르게 화면전환을 할 수 있다. 애니메이션을 매번 넣으며 scroll하게 되면 앱에 대한 유저들의 집중력을 흐트리며 방해할 수 있다. 탭하는 경우에만 애니메이션을 사용해라.

Page Control는 반투명, 둥근 사각형의 모양을 제공할 수 있다. 또한 여러 가지 Background Style이 있는데, 한 번 살펴보자.

- Automatic : 사용자가 Page Control과 Interaction할 때만 Background를 표시합니다. Page Control이 UI의 기본 탐색 요소가 아닌 경우에 이 유형을 선택하세요.

- Prominent : 배경을 항상 표시합니다. 이 스타일은 Page Control이 화면에서 기본 Navigation Control인 경우에만 사용하세요.

- Minimal : 배경을 표시하지 않습니다. 목록에서 현재 페이지의 위치만 표시하고 Scrubbing 도중에 시각적 피드백이 필요 없는 경우 이 유형을 선택하세요.

[backgroundStyle](https://developer.apple.com/documentation/uikit/uipagecontrol/3577676-backgroundstyle)을 참고

<br>

## minimal background Style을 사용할 경우 scrubbing을 지원하지 마라

minimal style은 scrubbing 도중에 시각적 피드백을 제공하지 않는다. 만약에 앱에서 페이지 리스트를 scrub하는 것을 원한다면, automatic 혹은 prominent 스타일을 사용하세요.

<br>

## 스크린의 아래 가운데에 위치 시켜라

유저들이 항상 Page Control 위치를 알 수 있도록 Page Control을 가로로 가운데 놓고 화면 아래쪽에 위치시키세요.

<br>
