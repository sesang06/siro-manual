# Unity 클라이언트 (siro-launcher)

Python 프로그램은 **대화·음성 처리**만 담당하고, **화면에 보이는 Live2D·자막·음성 출력**은 Unity 클라이언트가 담당합니다.

## 역할

| 기능 | Unity |
|------|-------|
| Live2D 모델 표시 | O |
| 자막 (타이핑 효과) | O |
| TTS 오디오 재생 | O |
| 표정·의상·행동 | O |
| 채팅/후원 오버레이 말풍선 | O |

## 연결 방식

- Python → Unity: **WebSocket** `ws://localhost:8765`
- Python → Unity: 오디오 PCM 청크, behavior(표정·자막), overlay 이벤트

Unity를 **먼저** 실행한 뒤 Python 프로그램을 시작하는 것을 권장합니다.

## 실행 방법

1. siro-launcher 빌드(또는 배포 exe)를 실행합니다.
2. Live2D 모델이 로드된 SampleScene(또는 배포 씬)이 표시됩니다.
3. Python 프로그램을 실행하고 **프로그램 시작**을 누릅니다.
4. 연결되면 Python 로그에 `Connected to server at ws://localhost:8765`가 출력됩니다.

## 자막 동작

- 문장마다 **현재 말하는 문장 1개만** 화면에 표시됩니다.
- TTS **재생이 끝난 뒤** 마지막 자막이 약 5초간 유지된 후 사라집니다.
- STT interrupt 등으로 AI가 중단되면 자막이 즉시 지워질 수 있습니다.

## Live2D 모델

- Python **라투디** 탭에서 모델 업로드·표정·의상을 설정합니다.
- Unity는 WebSocket으로 behavior 명령을 받아 표정·의상을 반영합니다.

## 크로마키

Python **실행 제어** 패널의 **크로마키 ON/OFF**로 Unity 캡처 배경(그린 스크린) 모드를 전환할 수 있습니다. OBS 등에 창 캡처할 때 사용합니다.

## 문제 발생 시

- Unity가 꺼져 있으면 Python은 연결되지 않으며 TTS·자막이 동작하지 않습니다.
- 포트 8765를 다른 프로그램이 사용 중이면 충돌할 수 있습니다.

[문제 해결](15-troubleshooting.md)
