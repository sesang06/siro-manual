# 오버레이

채팅·후원이 들어올 때 Unity 화면에 **말풍선 오버레이**를 표시할 수 있습니다.

## 표시 조건

- AI가 해당 댓글/후원에 **응답하기 시작할 때** overlay 이벤트가 Unity로 전송됩니다
- `show_comment_overlay` / `show_donation_overlay` (config 또는 상세 설정)

## 레이아웃

**후원, 댓글 상세 설정** 또는 config에서:

- **compact** 말풍선 레이아웃 — 좁은 화면용
- 오버레이 슬롯 위치 — Unity에서 드래그 후 저장

Python에서 `set_overlay_layout` / `reset_overlay_layout` 명령으로 Unity 레이아웃을 바꿀 수 있습니다.

## 자막과의 차이

| 요소 | 내용 |
|------|------|
| **자막** | AI가 **말하는 대사** (TTS와 동기) |
| **오버레이** | **시청자 채팅·후원** 말풍선 |

STT interrupt 시 `clear_overlay`만 보내지고 **자막은 별도** 동작합니다.

## 크로마키 방송

OBS 등에서 Unity 창을 캡처할 때 오버레이·자막이 함께 녹화됩니다. 크로마키 ON 시 배경만 제거됩니다.

## 문제 해결

- 오버레이가 안 보이면 Unity 연결·`show_*_overlay` 설정을 확인하세요
- 말풍선 위치가 어긋나면 Unity에서 **오버레이 드래그 위치 초기화** (WebSocket `reset_overlay_drag`)
