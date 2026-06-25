# 오디오·음성

**오디오·음성** 탭에서 마이크(STT)와 TTS·보이스를 설정합니다.

## 입력 장치

| 항목 | 설명 |
|------|------|
| 오디오 드라이버 | WASAPI 등 호스트 API |
| 마이크 (STT) | 음성 인식에 사용할 입력 장치 |
| 마이크 목록 새로고침 | 장치 연결 후 목록 갱신 |

## STT (음성 인식)

### faster-whisper (로컬)

- PC에서 오프라인 인식 (GPU 권장)
- **Whisper 모델** — `small` 기본, 클수록 정확하지만 느림
- 발화 **종료 후** 전사 결과가 나옵니다

### OpenAI Realtime

- OpenAI API 키 필요
- **gpt-realtime-whisper** — 실시간 partial 인식
- **지연/정확도** — `low`~`xhigh`, 낮을수록 빠름

### STT 테스트

프로그램 **시작 전**에 **STT 테스트 시작**으로 마이크·인식 품질을 확인할 수 있습니다.

## TTS (음성 합성)

| 모듈 | 설명 |
|------|------|
| **tts 모듈** | GPT-SoVITS 로컬 서버 (보이스 클론) |
| **Supertone** | 클라우드 TTS (API 키 + 보이스 ID) |
| **MiniMax** | 클라우드 TTS (API 키 + voice_id) |

모듈별 **보이스 설정** 패널(탭 하단)에서:

- 참조 음성·보조 보이스 (GPT-SoVITS)
- Supertone/MiniMax 보이스 목록·클론·테스트
- 재생 볼륨·입 움직임 gain

설정은 **자동 저장**됩니다.

## 실행 제어 연동

| 옵션 | 설명 |
|------|------|
| 방송인이 말하는 동안 AI가 말하지 않음 | STT로 사용자 발화 감지 시 AI TTS 중단 |
| AI 발화 중 마이크 음소거 | AI가 말할 때 STT 입력 일시 중지 |

## 재시작 필요 항목

다음은 변경 후 **프로그램을 다시 시작**해야 적용됩니다.

- STT 제공자 (Whisper ↔ OpenAI)
- TTS 모듈 종류
- Whisper 모델 크기

## 라투디와의 관계

Unity 재생 볼륨·mouth gain은 [Live2D](pages/10-live2d.md) 탭과 Unity 클라이언트에서 조절합니다.
