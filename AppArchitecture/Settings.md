# Settings

- 모든 앱들이 다 그런 것은 아니지만 필요에 따라서 앱의 설정을 바꿀 수 있도록 해야 한다.
- 좋은 앱들의 경우, 설정을 변경할 수 있는 간편한 기능들을 제공한다.
- 대부분 유저가 예상하도록 앱을 구성할 경우, 설정의 필요성은 줄어들 것이다.

<br>

<img src="https://user-images.githubusercontent.com/64566207/142425673-f460a20a-2a0e-40f2-abd3-a28dca10403d.png" width="300">

<br>

## 시스템을 통해서 할 수 있는 것들을 추론해보자

사용자, 디바이스 또는 환경에 대한 정보가 필요한 경우 사용자에게 요청하는 대신 가능하면 시스템에 해당 정보를 쿼리합니다. 예를 들어, 로컬 옵션을 제공할 수 있도록 사용자에게 우편 번호를 입력하도록 요청하는 대신 현재 위치를 사용할 수 있는 권한을 요청하세요. 사용자가 정보에 대한 접근을 거부할 경우에는 수동으로 입력하게 합니다.

<br>

## 앱에서 설정 옵션들의 우선순위를 고려해라

앱의 메인 화면은 필수적이거나 자주 바뀌는 옵션을 위한 좋은 장소입니다. 보조 화면은 가끔만 변경되는 옵션에 더 좋습니다.

<br>

## 설정(앱)에서 자주 바뀌지 않는 옵션들을 노출해라

- 설정 앱의 경우 시스템 전체에서 Configuration을 변경할 수 있는 중앙 위치이지만, 유저가 앱에서 나가서 설정을 해야만 한다.
- 앱 내에서 직접 설정을 조정하는 것이 훨씬 편리합니다. 변경이 거의 필요하지 않은 설정을 제공해야 하는 경우 [Implementing an iOS Setting Bundle](https://developer.apple.com/library/archive/documentation/Cocoa/Conceptual/UserDefaults/Preferences/Preferences.html) in [About Preferences and Settings](https://developer.apple.com/library/archive/documentation/Cocoa/Conceptual/UserDefaults/Introduction/Introduction.html)를 참고하세요.

<br>

<img src="https://user-images.githubusercontent.com/64566207/142425690-5aa49a77-bee0-4e19-b2fd-e5d26e13eeb0.png" width="300">

<br>

## 적절한 시점에 설정(Settings)에 대한 단축을 제공하라

만약 설정 앱에서 유저가 직접 설정해야하는 경우가 있다면, "설정 > 나의 앱 > 사생활 정보 > 위치 서비스" 로 이동 할 수 있는 버튼을 제공해라. 개발자를 위한 문서 [openSettingsURLString](https://developer.apple.com/documentation/uikit/uiapplication/1623042-opensettingsurlstring)과 [UIApplication](https://developer.apple.com/documentation/uikit/uiapplication)를 참고하세요

<br>