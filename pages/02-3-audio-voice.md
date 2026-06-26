# 02-3. 오디오·음성

![오디오·음성 패널](../assets/ui/panel-audio-voice.png)

마이크 입력(STT), AI 목소리(TTS), Live2D 립싱크까지 한 탭에서 설정합니다.

## 입력 장치

**오디오 드라이버** — Windows에서는 보통 WASAPI를 씁니다. 장치가 안 보이면 다른 항목을 시도해 보세요.

**마이크 (STT)** — 음성 인식에 쓸 마이크를 고릅니다. 이어폰·USB 마이크 연결 후 **마이크 목록 새로고침**을 눌러 목록을 갱신하세요.

마이크 목록만은 프로그램 실행 중에도 새로고침할 수 있습니다.

## STT (음성 인식)

마이크로 들어온 소리를 텍스트로 바꿉니다.

**제공자**

- **faster-whisper (로컬)** — PC에서 Whisper 모델을 돌립니다. API 비용 없음, NVIDIA GPU 권장.
- **OpenAI Realtime** — 클라우드 실시간 STT. 말하는 동안 글자가 바로 올라옵니다.

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

**모듈** — `없음` / `슈퍼톤` / `MiniMax` / `tts 모듈`(GPT-SoVITS 로컬). 모듈에 따라 아래 **보이스 설정** 패널이 바뀝니다.

- **Supertone 키** — 슈퍼톤 클라우드 TTS
- **MiniMax API 키** · **API Base URL** — MiniMax TTS (기본 URL `https://api.minimax.io/v1`)

## 보이스 설정

TTS 모듈 아래 **보이스 설정** 영역에서 캐릭터 목소리를 고릅니다.

### GPT-SoVITS (`tts 모듈`)

**주요 보이스** — 참조 wav 파일. **보이스 대사** — 그 wav에 대응하는 텍스트. **보조 보이스** — 감정·톤을 바꿀 때 추가 참조.

![screenshot](../assets/gdoc/img_026.png)
![screenshot](../assets/gdoc/img_027.png)

### Supertone · MiniMax

API 키 입력 후 **목록 새로고침**으로 보이스 목록을 불러옵니다. **샘플로 보이스 클론**으로 짧은 녹음으로 새 보이스를 만들 수도 있습니다.

[Supertone Console](https://console.supertoneapi.com/) · [Supertone 결제](https://play.supertone.ai/subscription)

![screenshot](../assets/gdoc/img_030.png)
![screenshot](../assets/gdoc/img_035.png)
![screenshot](../assets/gdoc/img_028.png)
![screenshot](../assets/gdoc/img_029.png)

### 재생 설정 (Live2D)

캐릭터 **볼륨**, **입 움직임 감도**, **입 부드러움**을 조절합니다. **프로그램 실행 중에도** 슬라이더 변경이 바로 반영됩니다.

## 실행 제어와의 연동

[실행 제어](https://wikidocs.net/372534) 패널의 「방송인이 말하는 동안 AI가 말하지 않음」「AI 발화 중 마이크 음소거」는 STT·TTS 동작과 함께 쓰입니다.

[[TIP("재시작 필요")]]
STT 제공자·Whisper 모델·TTS 모듈·보이스 파일 변경은 **프로그램 재시작** 후 적용됩니다.
[[/TIP]]
