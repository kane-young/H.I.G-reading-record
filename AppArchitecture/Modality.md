# Modality

Modality : n. 양식, 양상

>  [Modal Window](https://ko.wikipedia.org/wiki/모달_윈도)
>  UI 디자인 개념에서 자식 윈도우에서 부모 윈도우로 돌아가기 전에 사용자의 상호동작을 요구하는 창을 말한다. 그래서 프로세스의 주 창의 작업 흐름을 방해한다. 일반적으로 모달 대화상자라고 부르는데, 그 이유는 대화상자를 부를 때 흔히 사용되기 때문이다

<br>

`Modality` 는 해당 창에서 나가는 방법이 명시적이며, 내용을 임시적으로 보여주는 모드이다. Content를 `Modal` 식으로 표시하는 경우 다음 작업을 수행할 수 있다

- 유저가 스스로 집중해서 작업해야 하는 것을 돕거나, 밀접하게 관련되어있는 옵션들을 세팅할 때 `Modal` 도움을 준다
- 유저들이 중요한 정보를 수신하고 필요한 경우 조취를 취하도록 보장해 준다

<br>

![스크린샷 2021-10-02 오전 12 17 39](https://user-images.githubusercontent.com/64566207/135645235-2d16dc6c-c114-4033-8203-d282cfd869c4.png)

iOS 시스템에서 제공하는 Modal 환경에는  [alerts](https://developer.apple.com/design/human-interface-guidelines/ios/views/alerts/), [activity views](https://developer.apple.com/design/human-interface-guidelines/ios/views/activity-views/), [share sheets](https://developer.apple.com/design/human-interface-guidelines/ios/extensions/sharing-and-actions), 그리고 [action sheets](https://developer.apple.com/design/human-interface-guidelines/ios/views/action-sheets/). 가 있다. 앱에서 custom modal content를 보여주기 위해서는, 이와 같은 presentation style들 중 하나를 사용하시오

<br>

- **Automatic.** : 기본 default 스타일로, 일반적으로 pageSheet 타입이다 [참고](https://developer.apple.com/documentation/uikit/uimodalpresentationstyle/automatic)
- **Fullscreen** : 이전 view를 완전히 덮는 스타일이다. dismiss 버튼을 반드시 구성해야 한다 
- **Popover** : 가로 규격이 regular인 환경에서는 popover로 표현되고, 가로 규격이 compact인 환경에서는 sheet가 표현된다.
- **Page sheet and form sheet** : 이전 View를 부분적으로 가리는 presentation Style이다  [참고](https://developer.apple.com/design/human-interface-guidelines/ios/views/sheets/).
- **Current context** : 다른 ViewController의 뷰를 통해 표시되는 스타일 [참고](https://magi82.github.io/ios-modal-presentation-style-01/)
- **Custom** : 사용자 지정 container 를 통해서 content를 담고, 사용자 지정 animation 을 통해서 present된다. [UIViewControllerTransitioningDelegate](https://developer.apple.com/documentation/uikit/uiviewcontrollertransitioningdelegate) 를 채택하고, viewController의 [transitioningDelegate](https://developer.apple.com/documentation/uikit/uiviewcontroller/1621421-transitioningdelegate) 를 통해서 custom 진행 [참고](https://developer.apple.com/documentation/uikit/uimodalpresentationstyle/custom)

> **Note**
>
> 만약에 `Current context` presentation style을 사용하여, split View, popover에서 modal 창을 띄우거나, full screen 이 아닌 다른 View에 modal 창을 띄우려고 하는 경우, compact 환경에서 modal 창을 띄우려면, sheet 를 사용하는 것으로 전환해라

<br>

**쉽게 이해가 되는 상황에서 Modality를 사용해라**

현재 업무와 다른 선택을 하거나 업무를 수행하는데 사람들의 주의를 집중하는 것이 중요할 때만 modalIty를 사용해라. modal을 통한 경험은 사람들을 그들의 현재 상황에서 벗어나게 하고 무시할 행동을 요구하기 때문에, 그것이 분명한 이익을 제공할 때에만 그것을 사용하는 것이 필수적이다

<br>

**필수적인 정보를 제공할 때, 상호작용이 필요한 정보를 제공할 때에만 alert를 사용하는 것이 이상적이다**

일반적으로 문제가 발생했을 때 alert창을 사용한다. alert는 현재 진행중인 action을 중단시키고, 창을 띄우는 것이므로 사용자에게 있어서 action 중단에 대한 정당성을 얻어야만 한다. 그렇지 않으면 유저는 납득하지 않고 앱에 대한 신뢰를 잃을 것이다

<br>

**일반적으로 모달 작업은 단순하고 짧으며 집중되어야 한다**

만약에 modal 에서의 내용이 너무 복잡하다면, 유저는 자신이 modal에 들어갔을 때 자신이 일시 중단한 작업을 보지 못할 수 있습니다. 앱 내에 작은 앱을 보는 느낌도 주면 안된다. 특히, modal 에서는 view의 계층을 만드는 것을 피해야 한다. 왜냐하면 계층이 생기면 유저들이 돌아가는 방법을 까먹을 수도 있기 때문이다. modal 에 subview가 포함되어야 하는 경우에는 단일 경로와 완료에 대한 명확한 경로를 제공해야 한다. 그리고 작업 완료 이외의 다른 목적으로 done 버튼을 사용하지 말아라

<br>

**몰입형 컨텐츠 또는 복잡한 작업에 대해서는 fullScreen modal Style을 사용하는 것을 고려해 보세요**

fullScreen modal은 산만함을 최소화 하므로 video, photos, camera 를 표시하거나 문서에 마크업 또는 사진 편집과 같은 다단계 작업을 수행하는데 적합하다

<br>

**항상 modal view를 닫는 버튼을 포함하세요**

예를 들어서, done 그리고 cancel 버튼이 있어야만 합니다. 버튼을 포함하면 modal 에서 보조 기술에 접근할 수 있으며, 해제 제스처에 대한 대안을 제공합니다

<br>

**필요한 경우 modal 를 닫기 전에 확인 받아 사람들이 데이터 손실을 방지하도록 돕습니다**

사람들이 View를 닫기 위해 dismiss 제스처를 사용하든, 버튼을 사용하든 관계 없이 유저가 생성해놓은 content가 손실될 수 있는 경우에는 상황에 대해서 설명하고 해결 방법을 제공하는 action sheet를 제공해야 한다

<br>

**modal에서도 앱에서 사용하는 View의 형태를 일관성있게 사용해라**

navigation Bar 혹은 여러 view를 custom해서 사용할 경우 modal에서도 똑같은 templete를 사용해서 앱의 일관성을 지켜라

<br>

**적합한 transition style을 선택해서 modal로 전환해라**

각 modal style에 맞는 transition style을 골라서 전환을 수행시켜라. 그리고 앱 전체에서 일관된 transition style을 적용해야만 유저의 App experience를 높일 수 있다