# 문제 해결

## Unity WebSocket
**증상:** `Connected to server at ws://localhost:8765`가 안 나옴, TTS·자막 없음

**확인:**

1. Unity 클라이언트(siro-launcher)가 **먼저** 실행 중인지
2. Python **프로그램 시작**을 눌렀는지
3. 8765 포트를 다른 프로그램이 쓰지 않는지

## STT가 동작하지 않음

**증상:** 말해도 AI가 반응하지 않음

**확인:**

1. **마이크 뮤트**가 꺼져 있는지
2. **오디오·음성** 탭에서 올바른 마이크 선택
3. **STT 테스트** (프로그램 시작 전)로 인식 확인
4. OpenAI Realtime: API 키·인터넷 연결
5. Whisper: CUDA/CPU 부하 — 더 작은 모델 시도

**OpenAI Realtime:** delta는 오는데 최종 텍스트가 없을 때 — 말을 멈춘 뒤 1~2초 대기 (침묵 후 commit). `debug` 켜고 로그 확인.

## AI 발화 중 마이크

**AI 발화 중 마이크 음소거**가 켜져 있으면 TTS 동안 STT가 꺼집니다. 끄거나 TTS 종료 후 다시 시도하세요.

## TTS / GPT-SoVITS

**증상:** AI는 응답하지만 소리가 없음

**확인:**

1. Unity 연결
2. `tts 모듈` 사용 시 GPT-SoVITS 서버 기동 여부 (로그 확인)
3. **라투디** / 보이스 패널 볼륨
4. Supertone/MiniMax: API 키·voice_id

## 자막이 너무 빨리 사라짐

Unity `SubtitleManager` 설정:

- TTS **재생 중**에는 현재 문장 유지
- **재생 종료 후** 약 5초 유지 (Inspector `subtitleLifetime`)

한 번에 **한 문장만** 표시됩니다.

## 자막이 두 문장 겹침

최신 Unity 빌드에서는 문장마다 **교체** 표시됩니다. 구버전이면 siro-launcher 업데이트.

## 댓글/후원 무반응

1. **방송** 탭에서 해당 체크박스 ON
2. URL이 올바른지 (위플랩 오버레이 전체 URL)
3. AI가 말하는 중이면 큐에 대기 — TTS 끝난 뒤 처리
4. 상세 설정에서 필터·차단 키워드 확인

## API 키 / LLM 오류

- **AI 모델** 탭 API 키 확인
- `debug` 체크 후 콘솔 로그
- 모델명 deprecated 여부 — 최신 기본 모델 사용

## 설정이 저장되지 않음

UI 값은 대부분 자동 저장됩니다. **재시작 필요** 항목(모델·STT provider·TTS 모듈)은 프로그램을 다시 시작해야 합니다.

## Qdrant / 메모리

장기 메모리 사용 시 Qdrant가 `localhost:6333`에서 실행 중이어야 합니다. [설치](pages/05-install.md) 참고.

## 더 도움이 필요할 때

- [변경 이력](pages/16-changelog.md) — 최근 수정 사항
- 배포 버전: Hugging Face 버킷의 `version.yaml` 메타
