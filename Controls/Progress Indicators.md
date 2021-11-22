# Progress Indicators

앱이 콘텐츠를 로드하거나 장시간 데이터 처리 작업을 수행하기를 기다리며 사람들이 가만히 앉아 정적 화면을 바라보게 하지 마세요. activity indicator와 progress Indicator를 사용하여 앱이 정지되지 않았다는 것을 알리고 얼마나 오래 기다려야 하는지 알려줍니다

참고) [Loading...](https://github.com/kane-young/H.I.G-reading-record/blob/main/AppArchitecture/Loading.md)

<br>

# Activity Indicators

- Activity Indicators는 복잡한 데이터 로드 또는 동기화와 같은 수량화할 수 없는 작업이 수행되는 동안 회전합니다.
- 작업이 완료되면 사라집니다. 활동 표시기는 상호작용을 할 수 없습니다.

<br>

<img width="400" alt="스크린샷 2021-11-22 오전 10 55 52" src="https://user-images.githubusercontent.com/64566207/142789799-f32069ac-2985-4a0f-9a36-59ecc649e5fe.png">

<br>

## Activity Indicator보다는 progress indicator를 선호합니다

Activity를 수량화할 수 있는 경우, Activity Indicator 대신해서 Progress Indicator를 사용하여 유저들이 무슨 일이 일어나고 시간이 얼마나 걸릴지 더 잘 예측할 수 있도록 해줍니다.

<br>

## Activity Indicator가 계속 움직이도록 합니다

사람들은 움직이지 않는 activity indicator를 보면 process가 정지되었다고 생각한다. 유저들이 계속해서 무엇인가 발생하고 있다고 느낄 수 있도록 회전시켜라

<br>

## 도움이 되는 경우 작업이 완료될 때까지 기다리면서 유용한 정보를 제공합니다

추가적인 context를 제공하기 위해서 activity indicator위에 Label을 제공합니다. loading 혹은 authenticating과 같은 모호한 용어는 일반적으로 어떠한 가치도 추가하지 못하므로 사용을 피하세요

[Apple Developer Document - UIActivityIndicatorView](https://developer.apple.com/documentation/uikit/uiactivityindicatorview)

<br>

# Progress Bars

Progress Bar에는 알려진 기간이 있는 태스크의 진행률을 표시하기 위해서 왼쪽에서 오른쪽으로 채워지는 트랙이 포함되어 있습니다. Progress bars는 해당 작업을 취소하기 위한 Button이 함께 제공되기는 하지만 사용자와 상호작용을 할 수는 없습니다.

<br>

<img width="400" alt="스크린샷 2021-11-22 오전 10 55 30" src="https://user-images.githubusercontent.com/64566207/142789812-7978dd5d-ae4a-48e9-9205-5a6de6af5135.png">


<br>

## 항상 진행사항을 정확하게 보고하세요

단지 앱이 작동하고 있다는 것을 보여주기 위해서 부정확한 진행률을 보여주지 마세요. 수량화할 수 있는 작업에만 Progress Bar를 사용하세요. 그렇지 않으면 Activity Indicator를 사용하세요

<br>

## 기간이 잘 정의된 작업의 경우 Progress Bar를 사용하세요

Progress Bar는 작업의 상태를 표시하기 때문에, 작업을 완료하는데 얼마나 더 많은 시간이 필요한지를 유저가 알 수 있어 굉장히 유용합니다.

<br>

## 네비게이션 바 혹은 툴 바에서 채워지지 않는 부분들을 숨기세요

기본적으로 Progress Bar는 채워지는 부분과 채워지지 않는 부분을 모두 포함합니다. 네비게이션 바와 툴 바에서 페이지 로딩을 나타날 때, 트랙의 채워지지 않는 부분을 숨기도록 진행 표시줄을 구성해야 합니다.

<br>

## Progress Bar는 앱에 앱에 맞게 커스터마이징하는 것을 고려하세요

Progress Bar의 모양(외관)을 앱의 디자인에 맞게 적용하세요. 예를 들어서, 사용자 지정 tint, image를 track과 채워지는 영역에 적용하세요

<br>

[UIProgressView](https://developer.apple.com/documentation/uikit/uiprogressview)를 참고해보세요

<br>


<br>

# Network Activity Indicators

Network Activity Indicators는 iOS13 및 엣지 투 엣지 디스플레이가 있는 디스플레이 기기에서 더 이상 사용되지 않습니다. iOS12 및 이전 버전에서 엣지 투 엣지 디스플레이가 없는 기기에서는 네트워킹이 발생할 때 화면 상단의 상태 표시줄에서 Network Activity Indicator가 회전했었습니다. 네트워킹이 끝나면 사라졌으며, Activity Indicator와 똑같이 생겼었습니다

<br>

<img width="400" alt="스크린샷 2021-11-22 오전 10 55 05" src="https://user-images.githubusercontent.com/64566207/142789951-51deffae-07f0-4f88-85fa-d961637e162e.png">


<br>

## Network Activity Indicator의 경우 몇 초 이상 걸리는 네트워크 작업에만 사용하세요

빠른 네트워크 작업의 경우에는 해당 indicator를 사용하지마세요. 네트워킹 작업이 짧으면 다른 사람들이 알아차리기 전에 Indicator가 사라질 것입니다