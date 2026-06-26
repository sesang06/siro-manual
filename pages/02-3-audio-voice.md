# 02-3. 오디오·음성

![오디오·음성 패널](../assets/ui/panel-audio-voice.png)

마이크 입력(STT), AI 목소리(TTS), Live2D 립싱크까지 한 탭에서 설정합니다.

## 권장 구성

| | **방송·스트리밍** | **집에서 써보기·연습** |
|--|-------------------|------------------------|
| **STT** | **OpenAI Realtime** | **faster-whisper (로컬)** |
| **TTS** | **MiniMax** | **tts 모듈** (GPT-SoVITS) |
| **비용** | OpenAI·MiniMax API 사용량 (유료) | STT/TTS API **무료** (LLM API는 별도) |
| **특징** | 말하는 중에도 글자가 올라오고, TTS 지연·품질이 방송에 유리 | NVIDIA GPU로 로컬 처리. 설정은 단순하지만 GPU·VRAM 부담 |

[[TIP("스트리머")]]
설정 항목이 많아도 **Realtime STT + MiniMax TTS** 조합을 권장합니다. 방송 중 GPU를 SoVITS·Whisper에 쓰지 않아도 되고, 인식·합성 반응이 빠릅니다.
[[/TIP]]

[[TIP("일반 유저")]]
돈 들이지 않고 써보려면 **Whisper + GPT-SoVITS(`tts 모듈`)** 만 켜면 됩니다. LLM(Gemini 등) API 키만 있으면 STT/TTS 추가 과금 없이 동작합니다.
[[/TIP]]

## 입력 장치

**오디오 드라이버** — Windows에서는 보통 WASAPI를 씁니다. 장치가 안 보이면 다른 항목을 시도해 보세요.

**마이크 (STT)** — 음성 인식에 쓸 마이크를 고릅니다. 이어폰·USB 마이크 연결 후 **마이크 목록 새로고침**을 눌러 목록을 갱신하세요.

마이크 목록만은 프로그램 실행 중에도 새로고침할 수 있습니다.

## STT (음성 인식)

마이크로 들어온 소리를 텍스트로 바꿉니다. **방송 → OpenAI Realtime**, **무료 로컬 → faster-whisper** (위 **권장 구성** 표 참고).

**제공자**

- **faster-whisper (로컬)** — PC에서 Whisper 모델을 돌립니다. API 비용 없음, NVIDIA GPU 권장. **일반·연습용 1순위.**
- **OpenAI Realtime** — 클라우드 실시간 STT. 말하는 동안 글자가 바로 올라옵니다. **방송·스트리밍용 1순위.**

**Whisper 모델** (로컬 선택 시) — `tiny`부터 `large-v3`까지. 클수록 정확하지만 느리고 VRAM을 더 씁니다. `small` 정도가 무난한 출발점입니다.

**OpenAI Realtime** (클라우드 선택 시)

- **OpenAI API 키** — AI 모델 탭의 OpenAI 키와 연동됩니다.
- **Realtime 모델** — `gpt-realtime-whisper`
- **지연/정확도** — `minimal`~`xhigh`. 낮을수록 빠르고, 높을수록 끝맺음·문장 경계가 정확해집니다.

**STT 테스트 시작** — **프로그램 시작 전**에 마이크가 잘 잡히는지 확인합니다. 버튼을 누르고 말하면 **인식 결과** 칸에 텍스트가 나옵니다.

![screenshot](../assets/gdoc/img_023.png)
![screenshot](../assets/gdoc/img_024.png)

Whisper는 **말을 멈춘 뒤** 결과가 나오고, Realtime은 **말하는 중**에도 표시됩니다.

## TTS (음성 합성)

AI 대사를 실제 목소리로 만듭니다.

**모듈** — `없음` / `슈퍼톤` / `MiniMax` / `tts 모듈`(GPT-SoVITS 로컬). **방송용은 MiniMax**, **무료 로컬은 `tts 모듈`** 을 권장합니다. 모듈에 따라 TTS 영역과 **보이스 설정** 패널이 바뀝니다.

## Supertone (슈퍼톤)

클라우드 TTS **슈퍼톤**을 쓸 때의 설정입니다. (MiniMax 대안 — 방송용 1순위는 위 **권장 구성**의 MiniMax)

### API 키 발급 (웹)

1. [Supertone API](https://supertoneapi.com/) 접속 → **Sign up** 또는 **Sign in**

![Supertone API 가입](../assets/gdoc/img_030.png)

2. [Supertone API Console](https://console.supertoneapi.com/) 로그인 → 좌측 **API Keys** 메뉴

![Console — API Keys 메뉴](../assets/gdoc/img_031.png)

3. **+ Create New Key** 클릭

![Create New Key](../assets/gdoc/img_032.png)

4. **Save your Key** 창에서 키를 **복사**합니다. 창을 닫으면 다시 볼 수 없습니다.

![키 복사](../assets/gdoc/img_033.png)

TTS·보이스 클론 사용에는 크레딧이 필요합니다. [Supertone Play — Subscription](https://play.supertone.ai/subscription)에서 크레딧·요금제를 확인·구매할 수 있습니다.

![Subscription / 크레딧](../assets/gdoc/img_034.png)

### 프로그램에 입력

1. **오디오·음성** 탭 → **TTS (음성 합성)** → **모듈**에서 **슈퍼톤** 선택
2. **Supertone 키**에 복사한 API 키 붙여넣기

![Supertone API·보이스 설정](../assets/ui/panel-audio-supertone.png)

### 보이스 맞추기 (Supertone)

| 단계 | UI | 설명 |
|------|-----|------|
| 1 | **Supertone 보이스** → **목록 새로고침** | API 키가 맞으면 계정에 등록된 보이스 목록을 불러옵니다 |
| 2 | **사용 보이스** 콤보 | 기본 제공 보이스 중 하나를 선택합니다 |
| 3 | **샘플로 보이스 클론** (선택) | wav/mp3(3MB 이하) 업로드 → **보이스 이름**·**설명** 입력 → **샘플 업로드 후 클론**. STARTER tier 이상 필요 |
| 4 | **속도** | 0.5~2.0. 말하기 빠르기 조절 |
| 5 | **테스트 문장** + **테스트** | 프로그램 시작 전에도 선택한 보이스로 미리듣기 가능 |

클론 후에는 목록에 새 보이스가 추가되며, **사용 보이스**에서 고른 뒤 **테스트**로 확인하세요.

## MiniMax

클라우드 TTS **MiniMax**. **방송·스트리밍용 TTS 1순위**입니다.

### 요금 — 가장 저렴하게 시작하기

TTS 크레딧은 **[MiniMax Audio — Subscription](https://www.minimax.io/audio/subscribe)** 에서 구독하는 것이 보통 가장 쌉니다.

![MiniMax Monthly Starter Pack — 약 5달러/월](../assets/gdoc/minimax_audio_subscribe.png)

- **Monthly Starter Pack (약 5달러/월)** — 소규모 방송·테스트에 무난한 시작점. 위 페이지에서 **Monthly** 선택 후 **Starter** 플랜
- 종량제만 쓸 경우 [Billing — Balance](https://platform.minimax.io/user-center/payment/balance)에서 잔액 충전

Speech API 키는 아래 **API Platform**에서 발급하고, TTS 사용량·구독은 **Audio Subscription** 페이지에서 관리합니다.

### API 키 발급 (웹)

1. [MiniMax API Platform](https://platform.minimax.io/) 접속 → **Sign Up** 또는 **Console** → 로그인 화면

![MiniMax 로그인](../assets/gdoc/minimax_02_login.png)

2. Google·GitHub 또는 이메일로 가입·로그인 후 좌측 **API Keys** → **Create new secret key** → 키 이름 입력 후 생성

![Prerequisites — Get a Key](../assets/gdoc/minimax_docs_prep.png)

3. 표시된 **Secret Key**를 즉시 복사합니다 (재표시되지 않음)

4. (선택) 종량제 잔액은 [Billing — Balance](https://platform.minimax.io/user-center/payment/balance)에서 충전합니다. **월 구독 Starter Pack**은 [MiniMax Audio — Subscription](https://www.minimax.io/audio/subscribe)을 권장합니다.

공식 가이드: [MiniMax API — Prerequisites](https://platform.minimax.io/docs/guides/quickstart-preparation)

### 프로그램에 입력

1. **오디오·음성** 탭 → **TTS (음성 합성)** → **모듈**에서 **MiniMax** 선택
2. **MiniMax API 키** 붙여넣기

![MiniMax API·보이스 설정](../assets/ui/panel-audio-minimax.png)

### 보이스 클론 (웹)

캐릭터·본인 목소리를 쓰려면 **[MiniMax Audio — Voice Cloning](https://www.minimax.io/audio/voices-cloning)** 에서 클론하세요. (프로그램 내 **샘플로 보이스 클론**보다 웹 UI를 권장합니다.)

![MiniMax Voice Cloning](../assets/gdoc/minimax_audio_voices_cloning.png)

1. [Voice Cloning](https://www.minimax.io/audio/voices-cloning) 접속 → MiniMax Audio 계정으로 로그인
2. **Import audio** — wav/mp3 등 **최대 20MB** 파일 업로드, 또는 **Record audio**로 **10~60초** 녹음
3. 조용한 환경·한 명만 말한 **깨끗한 샘플** 사용 (잡음·리버브·다중 화자는 품질 저하)
4. (선택) **Advanced Settings** — 배경 잡음 제거·억양 최적화
5. 클론 완료 후 생성된 **voice_id**를 기억해 두거나, 아래처럼 프로그램에서 **목록 새로고침**으로 불러옵니다

### 보이스 맞추기 (MiniMax)

| 단계 | UI | 설명 |
|------|-----|------|
| 1 | **MiniMax 보이스** → **목록 새로고침** | system 보이스 + [Voice Cloning](https://www.minimax.io/audio/voices-cloning)에서 만든 클론 ID 목록 |
| 2 | **사용 보이스** | 기본 보이스 또는 웹에서 클론한 voice_id 선택 |
| 3 | **모델** | `speech-2.8-hd`(고음질) / `speech-2.8-turbo`(빠름) |
| 4 | **속도** | 0.5~2.0 |
| 5 | **테스트 문장** + **테스트** | 선택한 보이스로 즉시 미리듣기 |

웹에서 클론한 뒤 **목록 새로고침**을 눌러야 새 voice_id가 콤보에 나타납니다.

## GPT-SoVITS (`tts 모듈`)

로컬 GPT-SoVITS TTS입니다. **API 비용 없이** 쓰려면 **tts 모듈**을 선택하세요. 프로그램이 서버를 자동 기동합니다. NVIDIA GPU·VRAM이 필요합니다.

1. **오디오·음성** 탭 → **TTS (음성 합성)** → **모듈**에서 **tts 모듈** 선택
2. 아래 **GPT-SoVITS 보이스** 패널에서 레퍼런스를 지정

![GPT-SoVITS 보이스 설정](../assets/ui/panel-audio-sovits.png)

### 보이스 맞추기 (GPT-SoVITS)

GPT-SoVITS는 **짧은 참조 wav + 그 wav의 대사 텍스트**로 목소리를 흉내 냅니다. wav 파일은 캐릭터 폴더의 `setting_doc/{캐릭터명}/voice/`에 두거나, **찾아보기**로 고르면 자동으로 그 폴더에 복사됩니다.

| 항목 | 설명 |
|------|------|
| **주요 보이스** | 합성의 기준이 되는 **참조 wav** 파일명. **10초 이내**·잡음 적은 한 문장 녹음이 가장 무난합니다 |
| **보이스 대사** | 그 wav에 **실제로 말한 내용**을 글자 그대로 입력. 대사와 음성이 어긋나면 품질이 떨어집니다 |
| **보조 보이스** | (선택) 다른 톤·감정의 wav를 **추가**해 두면, 상황에 따라 참조를 바꿀 때 씁니다. **추가** / **선택 삭제**로 관리 |

#### 짧은 녹음으로 테스트하기

1. 마이크·녹음 앱 등으로 **5~10초** 짧게 한 문장을 녹음해 wav로 저장합니다.
2. **주요 보이스** → **찾아보기**로 그 wav를 선택합니다.
3. **보이스 대사**에 녹음한 문장을 그대로 적습니다.
4. **테스트 문장**에 다른 문장을 넣고 **테스트**를 누릅니다.

**테스트**는 **프로그램 시작 전**에도 동작합니다. 누르면 GPT-SoVITS 서버가 잠시 기동되고, 캐릭터 창(Unity)이 연결되어 있으면 스피커로 재생됩니다. 마음에 들면 **프로그램 시작** 후 방송에 그대로 사용하면 됩니다.

설정은 입력·변경 시 **자동 저장**됩니다. 모듈·wav·대사를 바꾼 뒤에는 **프로그램 재시작**이 필요합니다.

## 재생 설정 (Live2D)

캐릭터 **볼륨**, **입 움직임 감도**, **입 부드러움**을 조절합니다. **프로그램 실행 중에도** 슬라이더 변경이 바로 반영됩니다.

## 실행 제어와의 연동

[실행 제어](https://wikidocs.net/372534) 패널의 「말하기 모드」「AI 발화 중 마이크 음소거」는 STT·TTS 동작과 함께 쓰입니다.

[[TIP("재시작 필요")]]
STT 제공자·Whisper 모델·TTS 모듈·보이스 파일 변경은 **프로그램 재시작** 후 적용됩니다.
[[/TIP]]
