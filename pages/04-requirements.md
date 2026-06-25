# 시스템 요구사항

## Python 실행 프로그램 (AI 버튜버)

| 항목 | 권장 |
|------|------|
| OS | Windows 10/11 (64-bit) |
| GPU | NVIDIA GPU + CUDA (Whisper 로컬 STT, GPT-SoVITS 사용 시) |
| RAM | 16 GB 이상 권장 |
| 디스크 | 10 GB 이상 여유 (모델·캐릭터 데이터 포함) |
| 네트워크 | LLM·클라우드 STT/TTS 사용 시 인터넷 필요 |

## Unity 클라이언트

| 항목 | 권장 |
|------|------|
| OS | Windows 10/11 |
| GPU | Live2D 렌더링 가능한 그래픽 카드 |
| WebSocket | `localhost:8765` 포트 사용 (방화벽 예외 불필요한 경우가 많음) |

## API 키 (선택 조합)

사용하는 기능에 따라 아래 중 하나 이상이 필요합니다.

| 제공자 | 용도 |
|--------|------|
| Google Gemini | 메인 LLM (기본) |
| OpenAI | LLM, OpenAI Realtime STT, 임베딩 |
| Anthropic Claude | LLM |
| xAI Grok | LLM |
| Supertone | 클라우드 TTS |
| MiniMax | 클라우드 TTS |

로컬 Whisper STT + GPT-SoVITS TTS만 사용하면 LLM API 외 STT/TTS API는 생략할 수 있습니다.

## 선택 구성

- **Qdrant** — 장기 메모리 벡터 DB (메모리 기능 사용 시)
- **GPT-SoVITS 서버** — `tts 모듈` 선택 시 프로그램이 로컬 서버를 기동합니다
