# TextFields

텍스트 필드는 한줄로 이루어져 있는 텍스트 입력기로, 사용자가 해당 누르면 키보드가 자동으로 올라온다. 텍스트 필드를 사용하여 이름 또는 전자 메일 주소와 같은 적은 양의 정보를 요청한다.

![스크린샷 2021-11-22 오전 1 10 21](https://user-images.githubusercontent.com/64566207/142769759-774ffa27-eb3e-4db0-89c4-a9aa44c29ab9.png)


## 텍스트 필드에 힌트를 표시하여 해당 필드의 목적을 표시해라

- 텍스트 필드 앞쪽에 해당 텍스트 필드에 대한 설명 Text가 없다면 "Email" 혹은 "Password" 와 같은 placeHolder를 두어라
- placeHolder로 텍스트 필드에 대한 설명이 충분한 경우에는 별도의 Label를 두지 마세요

<br>

## 입력 내용을 지우는데 도움이 되도록 텍스트 필드의 맨 뒤에 지우기 버튼을 두세요

- 이 버튼이 있다면 사람들이 Delete 키를 계속 누르고 있지 않아도 편하게 텍스트를 지울 수 있습니다

<br>

## Secure TextField를 사용하여 개인 데이터를 숨기세요

- 앱이 암호와 같은 중요한 데이터를 요청할 때는 항상 Secure TextField를 사용하세요

<br>

## 이미지 및 버튼을 사용하여 텍스트 필드에 선명도와 기능을 제공합니다

- 커스텀 이미지를 텍스트 필드 양 끝에 표시할 수 있으며, 혹은 Bookmarks 버튼과 같은 system-provided button을 사용할 수 있습니다. 일반적으로, 텍스트 필드의 앞쪽에는 목적을, 텍스트 필드의 뒤쪽에는 추가 기능을 위한 목적의 버튼을 둔다.

<br>

> TIP<br>
만약에 다중 라인, 다중 스타일 텍스트 입력기가 필요하다면 TextView를 사용하세요