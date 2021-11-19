# Accessing User Data and Resources

사용자의 개인 정보는 매우 중요합니다. 사람들이 앱을 신뢰할 수 있도록 하려면 필요한 개인 정보 관련 데이터 및 리소스, 사용 방법에 대해 투명하게 밝히는 것이 중요합니다. 예를 들어, 아래와 같은 접근 권한을 요청해야 합니다.

- 지역, 건강, 금융, 연락처, 개인 식별 정보를 포함한 개인 데이터
- 이메일, 메시지, 캘린더 데이터, 연락처, 게임 플레이 정보, App Music 활동, HomeKit 데이터, 오디오, 비디오 및 사진 콘텐츠와 같은 사용자 생성 콘텐츠
- Bluetooth 주변기기, 홈 자동화 기능, Wi-Fi 연결 및 로컬 네트워크와 같은 보호된 리소스
- 카메라 및 마이크와 같은 장치 기능

<br>

> IMPORTANT <br>
> iOS 14.5 그리고 iPadOS 14.5에서, 만약 유저 혹은 그들의 디바이스의 advertising identifier에 접근하려고 한다면, 무조건 [AppTrackingTransparency framework](https://developer.apple.com/documentation/apptrackingtransparency)를 사용하여 사용자의 권한을 요청해야 합니다. 자세한 내용은 [User Privacy and Data Use](https://developer.apple.com/app-store/user-privacy-and-data-use/)를 참조하세요

<br>

새로운 앱 혹은 업데이트된 앱 스토어에 제출하려고 한다면, 개인 정보 관련 데이터에 대한 세부 사항을 App 페이지에 표시할 수 있게 제공해야 합니다. [App Store Connect](https://help.apple.com/app-store-connect/#/dev1b4647c5b)에서 언제든지 이 정보를 관리할 수 있습니다. 유저들은 당신의 앱을 다운로드 하기 전에 당신의 제품 페이지에 있는 개인 정보 관련 정보를 이용해 결정을 내릴 것입니다. 자세한 내용은 [App privacy details on the App Store](https://developer.apple.com/app-store/app-privacy-details/)를 참고하세요

<br>

<img src="https://user-images.githubusercontent.com/64566207/142598792-96dca7c5-baa7-45fd-9a50-10e87b4dcedf.png">

<br>

# Requesting Access Permission

유저 데이터 또는 보호된 리소스를 사용하려면 먼저 사용자의 사용 권한을 얻어야만 합니다.

<br>


## 앱에서 데이터 또는 리소스에 접근해야 하는 경우에만 권한을 요청합니다.

유저들이 기기 기능에 대한 명백한 필요성이 없을 경우 개인정보 요청이나 접근을 의심하는 것은 당연하다. 사람들이 접근 권한이 필요한 앱 기능을 실제로 사용할 때까지 기다린 이후에 요청하는 것이 적절하다. 위치 요청의 경우 위치 Button을 통해서 사람들에게 위치를 공유할 수 있는 즉각적인 방법을 제공할 수 있다.

<br>

## 앱을 위해서 꼭 필요한 데이터나 리소스는 꼭 필요한 경우에만 실행 시 권한 요청을 합니다.

사람들은 당신의 앱에 정보가 필요한 이유가 명백할 때 Launch-time 요청에 신경을 덜 쓸 것입니다. 앱을 실행하는 즉시 앱 추적을 수행하려면 추적 데이터를 수집하기 전에 시스템에서 제공한 알림을 표시해야 합니다.

시스템은 개인 정보 또는 보호된 리소스에 접근하기 위한 요청을 볼 수 있는 표준 Alert을 제공합니다. 앱에서 여러 개인 정보나 리소스가 왜 필요한지를 제공하면, Alert 창은 그 이유를 사용자를 납득시키기 위해서 View를 통해서 보여줄 것입니다. 만약에 허용하지 않는다고 해도, Setting > Privacy를 통해서 변경할 수 있다.

<br>

## 요청한 데이터 또는 리소스를 앱에서 사용하는 방법을 명확하게 설명하는 문장을 작성하세요

표준 Alert은 앱 이름 뒤와 사람들이 권한을 부여하거나 거부하는데 사용하는 버튼 앞에 (사용 목적 또는 사용 설명)을 표시합니다. 간단하고 구체이고 이해하기 쉬운 짧고 완전한 문장을 목표로 하세요. 문장으로 작성하고, 사용하고, 수동적인 음성을 피하고, 끝에 마침표를 포함합니다. [Requesting Access to Protected Resources](https://developer.apple.com/documentation/uikit/protecting_the_user_s_privacy/requesting_access_to_protected_resources) 그리고 [App Tracking Transparency](https://developer.apple.com/documentation/apptrackingtransparency)를 참고하세요.

<br>

<img src="https://user-images.githubusercontent.com/64566207/142598789-60242c2e-4f08-4fa3-b0a4-6a987702578b.png">

<br>

<img src="https://user-images.githubusercontent.com/64566207/142598782-3283ef3d-31d1-4263-bbc4-b3a18193a4d6.png">

<br>

# Using the Location Button

iOS 15 이후에는, Core Location 가 사람들이 앱에 작업이 필요한 시점에 자신의 위치에 접근할 수 있는 임시 권한을 부여할 수 있도록 버튼을 제공합니다. Location 버튼의 모양은 앱의 UI에 따라 다를 수 있지만 항상 즉시 인식할 수 있는 방식으로 위치 공유 작업을 전달합니다.

<br>

<img src="https://user-images.githubusercontent.com/64566207/142598776-a912a847-d315-4092-a936-0628376a9c33.png">

<br>

Location 버튼은 앱에 장치 위치를 요청할 수 있는 임시 권한을 부여합니다. 앱에 인증 상태가 없는 경우 Location 버튼을 누르면 표준 Alert에서 `Allow Once`를 선택하는 것과 동일한 효과가 있습니다. 만약 유저들이 이전에 `While Useing the App`(사용 중일 때만)을 선택했다고 한다면, Location 버튼을 눌러도 앱 상태가 변하지 않을 것입니다. Developer's Document의 [LocationButton (SwiftUI)](https://developer.apple.com/documentation/corelocationui/locationbutton)와 [CLLocationButton (Swift)](https://developer.apple.com/documentation/corelocationui/cllocationbutton)를 참고하세요.

<br>

사람들이 처음으로 앱을 열고 Location 버튼을 누르면 시스템은 표준 Alert를 표시한다. Alert는 사용자가 이 버튼을 사용하여 앱의 위치에 대한 접근을 제한하는 방법을 이해하는데 도움이 되며 공유가 시작될 때 나타나는 위치 표시기를 상기시킬 것입니다.

<br>

<img src="https://user-images.githubusercontent.com/64566207/142599612-9333097e-bd45-4ada-adb3-3753c602f625.png">

<br>

사람들은 버튼의 동작에 대한 이해를 확인한 후 앱이 자신의 위치에 접근할 수 있는 일회성 권한을 부여하고자 할 때 Location 버튼을 누르기만 하면 됩니다. 비록 사람들이 당신의 앱 사용을 중단하면 일회성 인증이 만료되지만, 그들은 버튼의 동작에 대한 이해를 재확인할 필요가 없다.

<br>

## Location 버튼을 사용하여 사람들이 특정 앱 기능에 대해 위치를 공유할 수 있는 가벼운 방법을 제공하세요.

예를들어서, 당신의 앱은 사람들이 메시지나 게시물에 그들의 위치를 첨부하거나, 상점을 찾거나, 그들의 위치에서 마주친 건물, 식물 또는 동물을 식별하는 것을 도울 수 있다. 사람들이 앱에 `Allow Once` 권한을 부여하는 경우가 많다는 것을 알고 있다면 Alert와 상호 작용하지 않고도 위치를 공유할 수 있도록 Location 버튼을 사용하는 것을 고려해보세요

<br>

## UI와 조화가 잘 되는 Location 버튼을 커스터마이징 하는 것을 고려해보세요

- "Current Location" 또는 "Share My Current Location"와 같이 사용자 기능에 가장 적합한 제목을 선택하세요
- 채우거나 윤곽이 잡히는 glyph를 선택
- 제목의 글자 색, 배경 색 등을 선택해라
- 버튼의 둥근 모서리를 고려해라

사용자가 Location 버튼을 인식하고 신뢰할 수 있도록 다른 시각적 속성은 커스터마이징 할 수 없습니다. 또한 시스템은 저대비 색상 조합 또는 너무 많은 반투명도와 같은 문제에 대해 영향을 받지 않기를 원합니다. 다른 언어로 번역될 때, 혹은 Accessibility에서 텍스트 크기를 Dynamic하게 변경하더라도 Button에 알맞아야 한다.

<br>

> IMPORTANT <br>
 커스터마이징 Location Button에서 일관된 문제가 발견되면 사용자가 해당 Location 버튼을 누를 때 앱이 기기 위치에 접근할 수 없게 됩니다. 이러한 버튼은 다른 앱별 작업을 수행할 수 있지만 Location 버튼이 예상대로 작동하지 않으면 앱에 대한 신뢰를 잃을 수 있습니다.

<br>

# Using Microphone in a ShazamKit App

ShazamKit은 오디오 샘플을 ShazamKit 카탈로그 또는 사용자 정의 오디오 카탈로그와 비교하여 오디오 인식을 가능하게 한다. iOS 15 이상에서 앱들은 ShazamKit을 사용하여 다음과 같은 기능을 활성화할 수 있다.

- 현재 재생 중인 음악 장르와 일치하는 그래픽으로 앱 경험 향상
- 오디오와 동기화되는 자막 또는 수화를 제공하여 청각 장애인이 미디어 컨텐츠에 접근할 수 있도록 만들기

앱이 인식할 오디오 샘플을 얻기 위해 장치 마이크가 필요한 경우 장치 마이크에 대한 액세스를 요청해야 한다. 모든 유형의 권한 요청과 마찬가지로 접근을 요청하는 이유를 다른 사람이 이해할 수 있도록 돕는 것이 중요하다.

<br>

<img src="https://user-images.githubusercontent.com/64566207/142599901-11aca134-3ebf-4caf-9d61-702df8b995e3.png">

<br>

ShazamKit을 사용하도록 기기의 마이크에 대한 접근 권한을 얻은 이후, 다음과 같은 경우에는 아래 가이드라인을 따르라

<br>

## 가능한 빨리 녹화를 중지하세요.

 사람들이 인식을 위해 오디오를 늑음하는 것을 허용할 때, 그들은 마이크가 계속 켜저 있을 것이라고 예상하지 않습니다. 개인 정보 보호를 위해 필요한 샘플을 가져오는데 걸리는 시간 동안만 기록하세요


<br>

## 사람들이 앱에 인식된 노래를 자신의 iCloud 라이브러리에 저장하도록 하세요.

앱이 인식한 노래를 iCloud에 저장할 수 있는 경우 먼저 이 작업을 승인할 수 있는 방법을 제공하세요. 음악 인식 컨트롤러와 Shazam 앱이 모두 인식된 노래의 소스로 당신의 앱을 보여주지만, 사람들은 어떤 앱이 그들의 라이브러리에 콘턴체를 저장할 수 있는지에 대한 제어를 갖는 것에 감사할 것이다. 

<br>
<br>

# Displaying Custom Messaging Befor the Alert

상황에 따라 권한을 요청하는 이유를 이미 알고 있지만 추가 세부 정보를 제공해야 하는 경우 Alert이 나타나기 전에 Customized 메세지를 표시할 수 있습니다.

<br>

## 커스터마이징된 메시지 화면에서 사용자가 수행할 수 있는 유일한 작업은 시스템 Alert 열기입니다

사람들은 사전 Alert 메시지를 지연 행위라고 해석할 수 있으므로 메시지를 신속하게 무시하고 시스템 Alert를 볼 수 있도록 하는 것이 중요핮ㅂ니다. 개인 정보 관련 사용 권한 요청 앞에 커스터마이징된 화면을 표시할 경우 시스템 Alert를 표시해야하는 작업을 하나만 제공해야 합니다. "계속"과 같은 단어를 사용하여 작업 제목을 지정하고, "허용"이나 사용자 지정 화면에서 다른 작업을 수행하거나 권한을 부여한 것으로 생각할 수 있는 용어는 사용하지 마세요

<br>

<img src="https://user-images.githubusercontent.com/64566207/142600253-b8aaa631-5d09-45f2-8870-1c67b1ae8317.png">

<br>

# 추적 요청 명확화

앱 추적은 민감한 문제입니다. 추적의 이점을 명확하게 설명하는 Custom 메시지를 표시하는 것이 적합한 경우도 있습니다.

시스템에서 제공하는 Alert를 혼동하거나 사람들에게 오도할 수 있는 커스텀 메시징을 선행하지 마세요. 사람들은 때때로 Alert를 읽지 않고 무시하기 위해 빠르게 탭합니다. 이러한 행동을 이용하여 선택에 영향을 미치는 커스터마이징된 메시지 화면은 앱스토어에서 reject 사유 중 하나입니다.

reject의 원인이 되는 몇 가지 금지된 사용자 지정 메시지 설계가 있습니다. 인센티브 제공, 요청처럼 보이는 화면 표시, 경고 이미지 표시, 경고 뒤에 있는 화면, 자세한 내용은 [App Store Review Guidelines: 5.1.1 (iv)](https://developer.apple.com/app-store/review/guidelines/#data-collection-and-storage)을 참조하세요 