# 실행 방법 안내

## 실행 방법 안내

![screenshot](assets/gdoc/img_002.png)

동영상 설치 방법은 [https://youtube.com/live/bX-o5H6UAUE](https://youtube.com/live/bX-o5H6UAUE) 를 참고해 주십시오.

![screenshot](assets/gdoc/img_003.png)
- ai_vtuber 파일을 실행해 주십시오.

![screenshot](assets/gdoc/img_004.png)
- 첫 실행 시 위와 같은 화면이 나타납니다.

#### 주요 실행 설정
- 크로마키 ON/OFF: 초록색 크로마키로 표출될지, 바탕화면 게임처럼 그냥 오버레이될지 설정입니다.
- ‘AI 발화 중단/재개’ 프로그램 구동 중에 AI가 발화를 잠시 중단하고 싶을 때 사용하는 기능입니다.
- ‘마이크 뮤트’: 방송인의 마이크가 ai에게 들어지 않게 하는 기능입니다.
- ‘방송인이 말하면 ai가 아가리’: AI가 발화 중에 방송인이 말하면 AI가 즉시 발화를 중단합니다.
- ‘AI 발화 중 마이크 음소거’: AI가 발화 중에는 방송인이 말하는 내용이 AI에게 전달되지 않습니다.

#### 1. 시로AI와 채팅하기

시로는 OpenAI Chatgpt, Google Gemini, Claude, GROK, OLLAMA를 모델로 지원합니다.

단, 레이턴시가 빠르고 과금 사용량이 적은, 제미나이를 추천 드립니다.
- Gemini 키 발급

AI Studio에 방문합니다.

[https://aistudio.google.com/app/apikey?hl=ko](https://aistudio.google.com/app/apikey?hl=ko)

‘API 키 만들기’ 를 선택합니다.

![screenshot](assets/gdoc/img_005.png)

주어진 키를 복사합니다.

![screenshot](assets/gdoc/img_006.png)

(선택) 제미나이는 무료로 사용 가능하나, 무료 버전은 사용량 제한이 있습니다. 만약 사용량 제한 없이 사용하고 싶으시면 ‘결제 설정’을 눌러 결제 정보를 등록하면 됩니다.  그냥 무료로 사용하실거면 결제 설정이 필요하지 않습니다.

![screenshot](assets/gdoc/img_007.png)
- (선택) Gemini 키를 채팅에 설정

‘모델 종류’ 를 gemini로 바꾸고, gemini 키를 입력합니다.

‘채팅 열기’ 를 눌러 바뀐 모델을 확인합니다.

![screenshot](assets/gdoc/img_008.png)
- OpenAI 키 발급 (선택)

OpenAI API 웹사이트에 접속합니다.

[https://platform.openai.com/docs/overview](https://platform.openai.com/docs/overview)

![screenshot](assets/gdoc/img_009.png)

우측 상단에서 ‘Log in’ 혹은 ‘Sign up’을 이용해 계정을 발급합니다.

OpenAI Billing 페이지에 이동합니다.

[https://platform.openai.com/settings/organization/billing/overview](https://platform.openai.com/settings/organization/billing/overview)

![screenshot](assets/gdoc/img_010.png)

신용카드를 등록해 크레딧을 충전합니다. 충전 최소 금액은 5달러입니다.

OpenAI API Keys 페이지에 이동합니다.

[https://platform.openai.com/settings/organization/api-keys](https://platform.openai.com/settings/organization/api-keys)

![screenshot](assets/gdoc/img_011.png)

‘Create new secret key’ 를 누르고 Project를 선택합니다.

![screenshot](assets/gdoc/img_012.png)

생성된 키를 복사합니다.

![screenshot](assets/gdoc/img_013.png)
- OpenAI 키를 채팅에 설정 (선택)

프로그램에서 ‘openai 키’ 에 복사하고 ‘채팅 열기’를 누릅니다.

![screenshot](assets/gdoc/img_014.png)

텍스트를 입력하고, ‘보내기’를 누릅니다.

![screenshot](assets/gdoc/img_015.png)

설정한 시스템 프롬프트에 따라서 시로AI가 답변합니다.

![screenshot](assets/gdoc/img_016.png)

아래 내역은 선택으로 ChatGPT 이외의 LLM을 사용하는 방법을 설명합니다.
- (선택) Claude 키 발급

[https://console.anthropic.com/](https://console.anthropic.com/) 에 방문해 회원 가입을 처리합니다.

![screenshot](assets/gdoc/img_017.png)

Settings - Billing에 들어가 신용카드를 등록하고 크레딧을 충전합니다.

[https://console.anthropic.com/settings/billing](https://console.anthropic.com/settings/billing)

![screenshot](assets/gdoc/img_018.png)

API Keys로 들어가 ‘Create Key’를 누릅니다.

[https://console.anthropic.com/settings/keys](https://console.anthropic.com/settings/keys)

![screenshot](assets/gdoc/img_019.png)

Key name을 자유롭게 입력하고 생성합니다.

![screenshot](assets/gdoc/img_020.png)

생성한 키를 복사합니다.

![screenshot](assets/gdoc/img_021.png)
- (선택) Claude 키를 채팅에 설정

‘모델 종류’ 를 claude로 바꾸고, claude 키를 입력합니다.

‘채팅 열기’ 를 눌러 바뀐 모델을 확인합니다.

![screenshot](assets/gdoc/img_022.png)

#### 2. 시로AI와 대화하기
- 목소리 없는 세팅

‘마이크’ 를 주 마이크로 설정하고 ‘프로그램 시작’을 누릅니다.

![screenshot](assets/gdoc/img_023.png)

검은색 화면에 ‘듣기 시작’ 화면이 출력되면 마이크에 대고 대화를 시작합니다.

마이크 인식에는 두가지 모드가 있습니다:
- faster-whisper (로컬) : 자신의 컴퓨터 gpu 자원을 이용하여 마이크 음성을 인식하는 모드입니다. ‘Stt 모델 크기’ 가 클수록 인식률이 좋고 딜레이가 길어집니다.
- OpenAI RealTime: OpenAI사에 청크를 보내 인식하는 기술입니다. Openai API 키가 필요합니다.

![screenshot](assets/gdoc/img_024.png)

시로의 반응이 검은색 화면에 출력됩니다.

![screenshot](assets/gdoc/img_025.png)

아래 내역은 선택으로 tts 모듈을 연결하여 목소리도 출력하는 법을 설명합니다.
- (선택) 딥러닝 목소리 출력하기 (무료)
- 최초 로딩 시에 딜레이가 발생하므로, 프로그램이나 컴퓨터를 몇 번 껐다 켜면 되는 상황이 보고되고 있습니다. 참고해 주십시오.

![screenshot](assets/gdoc/img_026.png)
- ‘tts 모듈’ 을 선택합니다.
- ‘프로그램 시작’을 누릅니다.
- 아래와 같은 화면이 출력될 때까지 잠시 기다려 주신 뒤에, 대화를 진행해 주십시오. 첫 로딩 시에는 출력이 안 될 수 있는데, 프로그램을 껐다가 켜서 다시 시도해 주십시오.

![screenshot](assets/gdoc/img_027.png)

#### 시로 보이스 다운로드 양식

퍼블릭으로 배포되는 시로 보이스는, 저작권이 없는 프리 보이스로, 제 라이브 방송에서 사용하는 목소리와는 차이가 있습니다.

제가 라이브에서 사용하는 보이스는 스트리머/유투버들에게만 제공하고 있으니,

제 메일이나 디스코드 등으로 활동명을 보내 주시면, 메일로 공유해 드리도록 하겠습니다.

(개인적으로 다른 목소리를 구하셔서 교체하는 데에는 별도의 허가가 필요하지 않습니다)

이 목소리를 음성 변경 버튼을 눌러 교체해주시면 됩니다.

![screenshot](assets/gdoc/img_028.png)

![screenshot](assets/gdoc/img_029.png)
- (선택) Supertone 키 발급 & 목소리 출력하기 (유료)

SuperTone 콘솔 사이트에 들어갑니다.

[https://console.supertoneapi.com/](https://console.supertoneapi.com/)

Sign up 혹은 Sign in을 진행합니다.

![screenshot](assets/gdoc/img_030.png)

API Keys에 들어갑니다.

![screenshot](assets/gdoc/img_031.png)

‘Create New Key’ 를 클릭합니다.

![screenshot](assets/gdoc/img_032.png)

생성된 키를 복사합니다.

![screenshot](assets/gdoc/img_033.png)

결제 창에서 슈퍼톤을 과금합니다.

결제 창 : [https://play.supertone.ai/subscription](https://play.supertone.ai/subscription)

![screenshot](assets/gdoc/img_034.png)
- ‘Supertone 키’ 를 입력합니다.
- 오디오 모듈 설정을 ‘슈퍼톤’ 으로 바꿉니다.
- ‘프로그램 시작’ 을 누릅니다.

![screenshot](assets/gdoc/img_035.png)
- 슈퍼톤의 ‘나만의 보이스 만들기’ 의 Voice ID를 입력하면, 목소리를 커스텀하여 조작할 수 있습니다.

#### 3. 시로가 이미지를 인식하게 하기

‘이미지 인식’ 을 체크하면, ‘이미지 인식 화면’ 이 뜨게 됩니다.

이 이미지 인식 화면이 시로가 인식하는 영역입니다.

‘이미지 인식’ 부분을 체크하는 순간 openai/제미나이에 과금되는 요금이 증가하고 레이턴시가 증가합니다. 계속 말을 걸 경우, 1시간 기준 1달러 정도가 소모됩니다.

![screenshot](assets/gdoc/img_036.png)

한번에 첨부할 이미지 수: 이전 녹화 프레임에서 몇 장을 보낼지 설정하는 기능입니다. 4장정도 설정해 주면 최근 6초간의 이미지를 연속화면처럼 인식할 수 있습니다.

이미지 화질: 저화질일수록 인식률이 나쁜 대신 응답이 빠르고, 고화질이면 인식률이 좋은 대신 응답이 느립니다.
- 직접 인식 모드

이미지 인식 화면을 직접 끌어내어 인식하는 모드입니다.

![screenshot](assets/gdoc/img_037.png)

이미지 인식 화면을 드래그해서 게임 화면 등에 조정합니다.

![screenshot](assets/gdoc/img_038.png)

‘프로그램 시작’을 누릅니다.

프로그램이 구동 중일 경우, ‘프로그램 종료’를 눌러 종료시킨 후 재차 ‘프로그램 시작’ 을 누릅니다.

이제 프로그램이 화면 속 이미지를 인식합니다.
- 카메라에서 선택 모드

카메라에서 이미지를 받아오는 모드입니다.

캡처보드 등에서 이미지를 받아올 수도 있으나,

한 프로그램이 한 카메라를 점유하는 순간, 다른 프로그램은 카메라를 인식할 수 없습니다.

즉, 이 프로그램에서 직접 캡처보드로 게임 화면을 인식하는 경우, obs에 카메라를 인식할 수 없습니다.

(추가 문제 해결)

Traceback (most recent call last): File "capture\video_capture_selector.py", line 15, in run SystemError:  returned a result with an exception set
식의 오류가 뜨면서 비디오 장치 로딩이 굳은 경우,

[https://blog.naver.com/404errorkr/223834100569](https://blog.naver.com/404errorkr/223834100569)
를 참고하시고 시스템 로컬에서 Beta : 세계 언어 지원을 위해 Unicode UTF-8 사용을 체크해 주세요.

![screenshot](assets/gdoc/img_039.png)

이 문제를 해결하기 위해서, ‘OBS Virtual Camera’ 기능을 활용합니다.

OBS에서 ‘가상 카메라 시작’ 옆에 ‘톱니바퀴’ 아이콘을 클릭합니다.

![screenshot](assets/gdoc/img_040.png)

출력 유형을 선택합니다.

이 출력 유형은 소스 목록 중 어느 것이라도 다 가능합니다.

그러므로, 굳이 캡처보드가 아니더라도,

플레이하는 게임의 프로그램 화면을 소스로 선택하는 것도 가능합니다.

![screenshot](assets/gdoc/img_041.png)

‘가상 카메라 시작’ 을 누릅니다.

![screenshot](assets/gdoc/img_042.png)

프로그램에서 ‘OBS Virtual Camera’를 선택합니다.

![screenshot](assets/gdoc/img_043.png)

#### 4. 시로의 성격과 시나리오를 조정하기

시로의 설정, 성격, 시나리오를 조정할 수 있습니다.

유저 이름: 시로가 유저를 어떻게 호칭할지를 정하는 부분입니다.

프롬프트 편집: 시로의 설정의 베이스가 되는 텍스트 파일을 수정할 수 있도록 여는 버튼입니다.

레퍼런스 문답 편집: 응답의 예시가 되는 문답 예제입니다. 많이 넣을수록 더 세밀한 조정이 됩니다.

시나리오 선택: 기본이 되는 시로의 설정에 더 덧붙일, 현재 상황 등을 선택할 수 있는 박스입니다.

시나리오 폴더 열기: 시나리오 폴더 안의 텍스트 파일을 추가하면, 시나리오를 더 선택할 수 있습니다. 상황에 따라 여분의 시나리오를 선택하고, 다음 프로그램 실행 때 시나리오가 갱신됩니다.

프로그램이 구동 중일 경우, ‘프로그램 종료’를 눌러 종료시킨 후 재차 ‘프로그램 시작’ 을 눌러야 설정이 반영됩니다.

![screenshot](assets/gdoc/img_044.png)
- 캐릭터 프롬프트 조정

아래는 캐릭터 프롬프트입니다.
- 한 턴에 시로의 대화 분량
- 방송인으로서 자신의 설정
- 시로의 성격

등을 자유롭게 추가하여 조정하시길 바랍니다.

![screenshot](assets/gdoc/img_045.png)
- 캐릭터 시나리오 조정

시나리오는 폴더의 모든 텍스트를 감지하며, 첫 실행 이후에 감지합니다. 방송 전에 미리 시나리오를 여러개 준비하시며, 방송 도중에 프로그램을 재실행하면서 시나리오를 바꿔 보시길 바랍니다.

![screenshot](assets/gdoc/img_046.png)

아래 샘플 시나리오에서는 시청자들의 댓글을 어떻게 반응을 할 지,

그리고 현재 어떤 방송을 하고 있는지 등을 설명했습니다.

방송 주제에 맞게 미리 조정하여 쓰시길 바랍니다.

![screenshot](assets/gdoc/img_047.png)
- 캐릭터 레퍼런스 조정

![screenshot](assets/gdoc/img_048.png)

예시 문답을 지정하는 파일입니다.

이 프로그램은 내부적으로 감정 표현, 의상 변경 등을 단순화된 명령어로 처리하고 있습니다. 그런 명령어를 효과적으로 처리하기 위해 이런 문답으로 성격을 추가적으로 부여합니다.
- 캐릭터 감정 기복 조정

캐릭터에 현재 감정을 부여하고, 현재 감정 상태에 따라서 추가 성격을 부여하는 프롬프트입니다.

![screenshot](assets/gdoc/img_049.png)

![screenshot](assets/gdoc/img_050.png)

각 감정에 맞는 프롬프트를 입력해 주십시오.

![screenshot](assets/gdoc/img_051.png)

필요 시, 예를 들어서 후원을 받으면 joy가 1 오른다 등으로 특수한 감정 규칙을 추가할 수 있습니다.
