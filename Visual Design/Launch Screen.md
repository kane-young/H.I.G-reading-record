# Launch Screen

앱이 시작되면 `Launch screen`이 즉시 나타나고 앱의 첫 번째 화면으로 빠르게 교체되어 앱이 빠르고 반응이 좋다는 인상을 줍니다. 시작 화면은 미적 표현을 나타내기 위해서 존재하는 것이 아니다. 이는 앱을 빠르게 실행하고 즉시 사용할 수 있다는 인식을 향상시키기 위한 것이다. 모든 앱은 `Launch screen`은 제공 해야만 한다.

<br>

<img src= "https://raw.githubusercontent.com/kane-young/H.I.G-reading-record/main/Images/LaunchScreen1.png" width = "550">

<br>

**멀티태스킹과 같은 다양한 장치 및 환경의 화면 크기를 수용하려면 Xcode 스토리보드를 사용하여 Launch Screen을 제공하세요.** 스토리보드는 유연하여 단일 스토리보드를 사용하여 모든 `Launch Screen`을 관리할 수 있습니다. 개발자 가이드 문서, [Responding to the Launch of Your App](https://developer.apple.com/documentation/uikit/app_and_environment/responding_to_the_launch_of_your_app)를 참고하여라.

<br>

> IMPORTANT <br> `Launch Screen`에는 정적인 이미지를 사용하면 안된다. 만약에 다양한 화면에 대한 크기가 필요하다면, [Device Screen Sizes and Orientation]()을 참고하여라.<br><br>
iOS 14 이후부터는, `Launch Screen`의 크기가 25 MB로 제한된다.


<br>

**앱의 첫 화면과 거의 동일한 시작 화면을 디자인하세요.** 앱 실행이 완료되었을 때 다르게 보이는 요소를 포함하면 사람들이 앱의 `Launch Screen`과 첫 화면 사이에서 불쾌한 요소를 가질 수 있습니다. 또한 `Launch Screen`이 장치의 현재 디바이스의 `appearance mode` 와 동일한지 확인하세요.

해당 가이드 라인은 [Dark Mode](https://developer.apple.com/design/human-interface-guidelines/ios/visual-design/dark-mode/)를 참고하세요

<br>

**Launch Screen에 글자를 포함하는 것을 왠만하면 피해라.** `Launch Screen`는 변경되지 않기 때문에, Localization(현지화) 적용을 할 수 없다.

<br>

**Downplay launch(laucn를 대단치 않게 생각해라).** 사람들은 콘텐츠에 빠르게 접근하고 작업을 수행할 수 있는 앱을 중요하게 생각한다. 앱의 인터페이스와 유사한 `Launch Screen`을 디자인하면 앱이 즉시 시작되는 것처럼 보입니다. 빠른 실행 시간과 결합된 이 디자인 접근 방식은 앱이 즉각적으로 반응하는 느낌을 줍니다. 게임의 경우 `Launch Screen`이 게임이 표시하는 첫 번째 화면으로 정상적으로 전환되어야 합니다.

<br>

**광고 하지마라.** `Launch Screen`은 브랜딩을 위한 기회가 아니다. 시작 화면이나 "정보" 창 처럼 보이는 진입 환경을 디자인하지 마라. 앱의 첫 화면에서 고정된 부분이 아닌 한 로고나 기타 브랜딩 요소를 포함하지 마세요. 게임 또는 기타 몰입형 앱이 첫 번째 화면으로 전환하기 전에 단색을 표시하는 경우 해당 단색만 표시하는 시작 화면을 만들 수 있다.

<br>

# 요약

<img src="https://raw.githubusercontent.com/kane-young/H.I.G-reading-record/main/Images/AssetLaunchScreen.png" width = "600">

<br>

1. [akshitzaveri - how to design the launch screen on ios](https://akshitzaveri.medium.com/how-to-design-the-launch-screen-on-ios-bd54781a19b9) 에 따르면 이전에는 
이전에 `Launch Screen` 을 Storyboard가 아닌 asset에 `Launch Image`로 사용했다고 한다. 이렇게 Static Image를 사용하는 것은 Deprecated 되었고, 굳이 이미지를 사용하자면 LaunchScreen.storyboard 에서 UIImageView를 배치하여 사용해라

2. 앱의 첫 화면에 글자를 포함하지 마라. 지역화를 통해서 세계 지역마다 언어로 앱 이름을 표시해야될텐데, `Launch screen`는 변경하지 못하기에 왠만하면 텍스트를 포함하지 않는 것이 좋다

3. `Launch Screen`을 너무 대단하게 여기지 말아야 한다. `Launch Screen`은 단지 첫 화면에 들어가기 이전 일 뿐이다.

4. 광고를 포함하지 마라. `Launch Screen`는 광고를 하며, 정보를 제공하는 창이 아니다. 게임과 같은 몰입형 앱의 경우에는 첫 화면의 배경이 단색일 경우에 `Launch Screen`을 해당 단색으로 하는 것도 좋다
