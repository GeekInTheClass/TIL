# HIG Summarization

## Overview

### Design Principles

iOS 앱을 디자인하는데 있어서 지켜야할 중요한사항들이 있다.

- Clarity(명확성)
- Deference(경의와 복종?) - translucency, blurring, minimal use of bazels, fradients, and drop shadows -> 앱을 전체적으로 가볍게한다. 또한 컨텐츠 자체는 최고로 만든다.
- Depth(깊이) - 눈에 띄는 레이어들과 사실적인 모션은 계층을 형성하고 생명력을 불어넣으며 이해력을 높힌다. 



#### 1. Aesthetic Integrity 

aesthetic integrty는 보이는것과 행동하는것이 실제로 그 앱이 하는 일 (일련의 함수들)과 얼마나 일치하는지를 나타낸다. 예를 들면 serious 한 일을 하는 앱은 명확성있는 UI가 중요한 반면 immersive 한 게임은 황홀하게 어필하여 재미를 선사하는것이 중요하다. 

#### 2. Consistency

스탠다드에 맞추고, system-provided interface를 사용하고 유저가 생각하는대로 앱이 작동하도록  만드는 것이 중요하다.

####  3. Direct Manipulation

이해도를 높이기 위해 사용자가 onscreen에 event 를 trigger 했을때 바로 반응하도록 설계를 한다. 화면을 돌리거나, 스와이프를 했을때 바로 반응을 하도록 해야한다.

#### 4. Feedback

유저가 뭘 하면 즉각즉각 반응해라? 이것도 위의 것이랑 좀 내용이 겹치는것같은데 뭐라고 해야할지 잘 모르겠다. built-in iOS앱을 보면 유저가 어떤 액션을 취했을때 바로 지각할 수 있는 피드백이 주어진다. 어떤 엘레멘트들이 눌렸을때 하이라이트 되거나,  progress indicator(스피닝 wheel같은)는 오래 걸리는 작업을 안내해준다. 또한 애니메이션과 사운드를 이용해 어떤 action에 대한 result를 알려준다.

#### 5. Metaphors

현실세계에 있는 실제 사물 혹은 액션들이 바로 metaphor 이라고 할 수 이다. 스위치를 끄는 행위나, 밀어서 밑의 것을 올려보는 행위 등 이런것들은 유저들이 스크린에서 앱과 interact할 때 하는 일들이고 모두 현실세계로 부터 온 metaphor들 이다. 책 넘기는 듯한 애니메이션도 포함되겠다.

#### 6. User Control

앱 보다는 사람이 앱에 대한 컨트롤이 있어야 한다. App이 suggest 나 warn을 할 수 있어도 take over control 해서는 절대로 안된다. 최고의 앱들은 유저들이 unwanted outcome이 나오는것을 미리 사전에 다 방지한다. 유저가 자신이 앱에대한 full 권한이 있는것처럼 느끼게 하기 위해서는 자주 사용하는 혹은 주로 노출되는 엘레먼트들을 예상가능하고 familiar 하게, 그리고 destructive(지우는 등의) 액션은 다시 한 번 확인해주는 등 하면 된다. 



### iOS 10에서 새로운것

1. Search Screen 에 위젯을 추가할 수 있다. 사용자가 직접 추가할 수도 있음
2. 메세지 앱과 integration이 된다. App 안에 메세지 integrate할 수 있다는 뜻인듯?
3. Siri integration 된다
4. notification extended, 알림 왔을때 스와이프다운하거나 3d터치하면 더 많은 일을 할 수 있다. 예를들면 캘리더 앱은 새로운 일정 추가하기 가능!



### Interface Essentials

대부분 iOS App들은 UIKit에서 나온 컴포넌트들로 built된다. **UIKit**은 *a programming framework that defines common interface elements.* 이다. consistent 하면서도 high level of customizaiton 을 가능케 한댄다.

1. **Bars** 사람들이 현재 어느 위치에 있는지 네비게이션을 제공한다. 
2. **Views** 가장 중요한 컨텐츠가 담긴다. 텍스트, 그래픽 애니메이션 등등 스크롤 인서트 딜리트 어레인지먼트 암튼 뭔지 앎
3. **Controls** 버튼, 스위치, text를 쓰는 textfield, progress indicators 모두 다 예시임

UIKit은 interface 뿐만 아니라 앱에서 쓸 수 있는 functionality 또한 포함되어 있다. 예를들면 이 프레임워크를 통해, gesture, 즉 user action에 대해 respond를 할 수 있고 drawing accessibiltiy 혹은 프린팅 등을 사용할 수도 있다. 

또한 여러분은 ApplePay 나 HealthKit and ResearchKit 등을 사용할 수 있다. 하지만 애플페이는 한국에서는 아직 겁나 쓸모없어보이네요 ㅜ



## Intercation

### 3D Touch

**Peek and Pop** 은 꾹 누르고 있으면 페이지나 링크나 파일이나 사진이나 뭐든 프리뷰 보여주는거임. 어느정도 쎄게 누른 상태에서 더 쎄게 누르면 아예 그 화면으로 진입함, 하지면 손을 떄버리면 그냥 다시 사라짐. 여기서 주의할 점은 peek 하는 것을 충분히 크게 만들어줄 것이다. 그리고 한 번 사용할거면 모든곳에 사용해라, 안그러면 유저들이 헷갈린다. 또 한 가지 중요한 점은 Peek and Pop 은 없어도 앱의 기능상 아무런 지장이 없는 기능이어야 한다. 

 

### Accessibility

주로 몸이 불편한 사람들을 위해 재공하는 기능들. *Transparenty reduction, Voiceover, ButtonShapes* 가 있다.

설정에 있는 accessibitily preferencess를 만지면, 앱도 자동으로 adapt 해야 한다. UIKit을 사용하면 자동으로 된다. 만약 costom fonts 나 등 다른것이 사용되었다면 잘 적용되는지 보아야 한다. 직접 한번 테스팅 해봐라. 



### Audio

사람들이 어던 사운드에 어떤것을 예상하고, 어떤식으로 반응할지 알아야 한다. 

*Slient* 모드 에서 울릴수 있는건 mediaplayback, 알람소리, 오디오,비디오 메시징 뿐이다.
*Volume* 사용자가 지정한 볼륨에 모든 앱은 동일하게 작동해야한다. (물론 알람소리를 이에 독립적이다. 따로 설정하는게 있다.)
*Headphones* 가 꽂힐때는 자동으로 변환되어야 하며, 플러그 되었을때는 자동으로 pause가 되어야 한다.

앱이 자동적으로 볼륨을 조절할수는 있지만 가장 final outcome은 시스템볼륨에 맞춰져야 한다.

오디오 출력을 rerouting 시켜줄 상황해서는 이를 시켜주도록해라. airplay headphones, bluetooth 등

되도록 짧은 알림이나 진동은 내장되어있는 시스템 사운드를 사용해라(카톡은 안하는데? ㅋㅋ) 

> [System Sound Services](https://developer.apple.com/reference/audiotoolbox/1657326-system_sound_services).

볼륨 조정을 위한 가장 이상적인 방법은 볼륨조정을 하기위한 view를 만든는 것이다 (슬라이드바가 있는)

**오디오 출력의 우선순위를 생각해라** 당신의 앱의 오디오 출력이 상당히 중요하다면, 다름 앱에 의해서 override되지 않게 제대로 설계해라 (스타벅스 앱이 이걸 엉망으로 해놔서 개빡친다 ㅎㅎ 맨날 꺼짐 )

> [Audio Session Programming Guide](https://developer.apple.com/library/content/documentation/Audio/Conceptual/AudioSessionProgrammingGuide/Introduction/Introduction.html).



- 만약 오디오를 틀고 있는 도중 잠시 다른 앱으로 부터 방해가 일어났더라도, 이가 끝났다면 다시 playback을 해라 
- 내 앱의 일시적을 나는 사운드가 종료되었을때는 다른 앱에게 이를 알려야 한다.
- 앱의 오디오 controls가 동작해야될 때만 동작해라 - 다른앱꺼까지 꺼버리지 말아라.



### Authentication

앱 내에서 authentication 이 필요한 부분은, 어떤 경험을 개인화 하거나(이부분은 좀 더 제대로 된 해석이 필요하다) 새로운 기능들에 접근하거나, 구입을 하거나, 데이터를 동기화 할때이다. 만약 authentication 을 해야 한다면, sign-in process를 빠르게 진행시켜라.
**Sign-in 이 필요하더라도 최대한 미뤄라** 예를들면 쇼핑몰의 경우, 로그인을 해야하더라도, 물품을 좀 구경시켜준다음에 결제단계까지 가서 로그인을 시키던지 해라. 유저들이 굉장히 이 과정을 귀찮아해서 앱을 버릴지도 모른다.

**Authentication의 장점과 어떻게하는지를 설명해라** 장점….이라… 딱히 없는듯ㅠ 그냥 아직까지 이 방법 뿐임

**textfield에 따라 각각 다른 키보드를 보여줘라** 이메일 칸에는 이메일키보드, 번호칠때는 번호 키보드 등 이거 굉장히 중요함.



### Data Entry

데이터를 입력해야할때, 상당히 귀찮다. 너무 많은 양의 데이터 입력은 사용자를 개빡치게 한다. 

- 따라서 객관식으로 주거나, 시스템이나 사용자 계정으로부터 자동수집가능한건 자동수집해라.
- Default value들을 줄 수 있으면 줘라 - 날짜 시간 선택에서 오늘의 날짜 표시라던가 말이다.
- 필수 항목만 입력하면 넘어갈 수 있도록 하고, 다음 단계로 넘어가도 됨을 표시해주는 것도 중요하다.
- 유저가 입력하는 즉시에 vaildation을 체크해라, 틀렸으면 바로 수정하게
- 진짜 필요한 정보만 text field로 받아내라
- 테이블이나,  pickers 즉 객관식으로 선택지를 줄때, 최대한 navigation 을 쉽게 해라
- placeholder 이나 힌트를 줘서 빨리빨리 입력하게 도와줘라



### Feedback

앱이 유저에게 피드백을 주면 유저는 앱이 현재 뭘하는중이고, 자신이 다음에 취할수 있는 행동이 뭐고, 어떤 액션에 대한 결과를 생각할 수 있다. 

- 인터페이스에 가능하면, 적당한 양의 app status나 어쨋든 피드백을 재공해라. 메일의 경우 toolbar에 status info를 제공한다. 이 정보는 view에 있는 정보와 충돌하지 않으면서도, 언제나 체크할 수 이다. 
- 쓸대없는 alert는 보내지 말아라.
- **햅틱 피드백을 가능하면 보내라**(본적 없는데 사용하면 흥미로울듯) - 아주 얕은 두번의 빠른 두 진동은 예를들면 *success* 를 나타낸다. 차의 잠금을 헤제하거나 은행해서 deposit을 하거나 말이다.  하지만 필요할때만 사용해라. success 외에도 *warning* 이나 *failure*도 좋은 예시이다. 또한 햅틱에 의존해서는 안되고 다른 알림 경로가 항상 있어야 한다.
- 햅틱이 일어나기 전 시스템은 ready 상태여야 한다. delay가 생기면 안되기 때문이다.
- 사운드랑 햅틱이랑 같이 써보기도 해라.



### Filehandling

유저는 기본적으로 파일 system 에 대해서 생각하지 않아도 되어야 한다. 만약 앱이 파일을 다루는 앱이라면 file handling을 진짜 최소화 시켜라. 

- **파일을 항상 자동으로 세이브해라** 일정한 interval, 다른 앱으로 넘어갈때, 등에 자동저장을 시키면된다. 어쨋든 사용자가 수동으로 파일을 저장하게 하지 말아라. save 랑 cancel 이 있다고 쳐도, 이미 있는 파일을 수정하거나, 꼭 필요 할때만 유효하게 만든다.

- 파일을 로컬화 하지말고 되도록 cloud에 올릴 수 있는한 죄다 올려라.

- 직관적이고 그래피컬한 파일 브라우져 인터페이스를 제공해라 

- 앱을 뜨지 않고 파일을 프리뷰할 수 있게 해줘라

- **적절한 상황에서는, 다른 앱과 파일을 공유할 수 있게 해라.** 

  > [document provider extension](https://developer.apple.com/ios/human-interface-guidelines/extensions/document-providers/)
  >
  >  [Document Picker Programming Guide](https://developer.apple.com/library/content/documentation/FileManagement/Conceptual/DocumentPickerProgrammingGuide/Introduction/Introduction.html)





### First Launch Experience

런칭 화면은 새로운 사용자들이 당신의 앱에 빠지게 할 첫 번째 기회이며, 다시 오는 사람들을 끌어들일 수 있는 시간이다.

런칭하면은 재밌고 빠르고 교육적이어야 한다!

- **런칭 스크린을 제공하라**  앱이 시동걸리자마자 런칭스크린이 나와야 빠르고 잘만들어졌다는 느낌을 준다. 그다음 빠르게 첫화면으로 전환한다. [Launch Screen](https://developer.apple.com/ios/human-interface-guidelines/graphics/launch-screen/).
- **제대로된 오리엔테이션으로 런칭을 하라** 중력센서로 인해서 landscape모드에 있어도 앱의 지원에 따라 런칭화면을 두개로할지 하나로 할지 정해라, [Layout](https://developer.apple.com/ios/human-interface-guidelines/visual-design/layout).
- **빠른 전환** 로딩화면이나 메뉴나 설명충이 되지 마라. 유저가 바로바로 앱을 사용할 수 있도록 해라.
- **도움이 필요할때는 줘라** 게임에서 막혔을때 - 나는 게임 안만듬
- **튜토리얼에서는 최대한 중요한것만 해라** 가이드라인은 최소화 하고, 유저가 직접 쓰면서 익히도록 만드는 것이 최고다.
- **set up information은 유저에게 요청하지 않도록 한다** 그냥 앱이 작동하길 사람들은 바란다. 
- **licening agreenments 나 권리포기각서를 보여주는 행위를 최대한 없에라** 이건 app store에 있으면 되고 app내부에는 안보이는 곳 설정 뒤에 꼭꼭 숨겨놓으면 된다.
- **앱을 다시 킬떄는 Previous state를 restore 하라** 다시 사람들이 똑같은과정을 밟게해선 당연히 안된다.
-  **계속 앱 평가해달라고 징징대거나 너무 빨리 평가해달라고 하지 말아라** 이거 ㄹㅇ 안지키면 개빡친다
- **유저에게 리부팅 하라고 하지 말아라** 이것도 개빡침





### Gestures

사람들은 ios기기와 터치화면의 제스쳐를 통해 상호작용을 한다. 이건 스크린에 담긴 물체들과 유저간의 직접적인 조작과 긴밀한 커넥션이 있음을 말한다. 따라서 일종의 스탠다드를 지키는 것이 광장히 중요하다. 예시는 다음과 같다.

*Tap, Drag, Scroll, Swipe*- 스와이프는 항목 밀어서 삭제하기 등이 있다. 

*double tab, pinch, touch&hold, shake* 

* 시스템적인 제스쳐는 막아서는 안된다. 예를들면 컨트롤센터나 알림센터를 여는 행위와 다른 제스쳐와 겹치면 안된다.


* 숏컷 제스쳐는 상당히 중요하다 - 예를들면 네비게이션 바가 있음에도 불구하고 한쪽으로 swipe해서 다른 한 화면으로 넘어가는 기능 같이 말이다 (이거 좀 유용하고 좋음)
* multi-finger gesture 를 사용해서 유저 경험을 향상시킬 수 있으면 향상시켜라



### Loading

컨텐츠가 로딩중일때는 static한 화면은 유저를 혼란 혹은 빡침속에 넣을 수 있다. 따라서 유저들은 앱을 떠나버릴 수도 있으니 조심해야 한다. 

* 확실히 로딩중이라는 표시를 해주어야 한다.  spinner, 혹은 explicit progress - 즉 진행상황에 대해서 알려줘라
* 로딩타임중에 다른곳으로 관심사를 이끄는것도 좋은 방법이다. 즉 로딩화면을 customize 해라
* 최대한 로딩시간을 줄이고 컨텐츠를 빠르게 보여주라. 최대한 화면을 빠르게 보여준 후, 아직 로딩이 안된 부분만 표시하는것도 나쁘지 않는 방법이다. 되도록이면, **백그라운드에 다음에 올 순서의 컨텐츠를 미리 로딩시켜놓아라**. 유저가 애니메이션을보거나 다른 레벨 혹은 메뉴에서 네비게이팅을 할 때 말이다. [Progress Indicators](https://developer.apple.com/ios/human-interface-guidelines/ui-controls/progress-indicators/).



### Modality

