# 02-3. 오디오·음성

![오디오·음성 패널](../assets/ui/panel-audio-voice.png)

## 입력 장치

| UI 라벨 | 설명 | 즉시 반영 |
|---------|------|-----------|
| 오디오 드라이버 | WASAPI 등 호스트 API | X |
| 마이크 (STT) | 음성 인식 입력 장치 | X |
| 마이크 목록 새로고침 | 장치 연결 후 목록 갱신 | O |

## STT (음성 인식)

| UI 라벨 | 설명 | 즉시 반영 |
|---------|------|-----------|
| 제공자 | `faster-whisper (로컬)` / `OpenAI Realtime` | X |
| Whisper 모델 | `tiny`~`large-v3` (클수록 정확·느림) | X |
| OpenAI API 키 | Realtime STT용 | X |
| Realtime 모델 | `gpt-realtime-whisper` | X |
| 지연/정확도 | `minimal`~`xhigh` | X |
| STT 테스트 시작 | 프로그램 시작 **전** 마이크 테스트 | O |
| 인식 결과 | 테스트 출력 | O |

![screenshot](../assets/gdoc/img_023.png)
![screenshot](../assets/gdoc/img_024.png)

## TTS (음성 합성)

| UI 라벨 | 설명 | 즉시 반영 |
|---------|------|-----------|
| 모듈 | `없음` / `슈퍼톤` / `MiniMax` / `tts 모듈` | X |
| Supertone 키 | 클라우드 TTS | X |
| MiniMax API 키 / API Base URL | MiniMax TTS | X |

## 보이스 설정 (모듈별)

모듈 선택에 따라 아래 패널이 바뀝니다.

| 항목 | 설명 |
|------|------|
| 주요 보이스 / 보조 보이스 | GPT-SoVITS 참조 음성 |
| Voice ID / 보이스 목록 | Supertone·MiniMax |
| 재생 볼륨·입 움직임 gain | Unity 립싱크 (일부 즉시 반영) |

![screenshot](../assets/gdoc/img_026.png)
![screenshot](../assets/gdoc/img_027.png)

#### Supertone (선택)

[Supertone Console](https://console.supertoneapi.com/) · [Supertone 결제](https://play.supertone.ai/subscription)

![screenshot](../assets/gdoc/img_030.png)
![screenshot](../assets/gdoc/img_035.png)
![screenshot](../assets/gdoc/img_028.png)
![screenshot](../assets/gdoc/img_029.png)

[[TIP("재시작 필요")]]
STT 제공자·Whisper 모델·TTS 모듈·보이스 변경은 **프로그램 재시작** 후 적용됩니다.
[[/TIP]]

[[02-9. 실행 제어|실행 제어]]의 STT 관련 체크박스와 연동됩니다.
