# Live2D (라투디)

**라투디** 탭에서 Unity에 표시할 Live2D 모델·표정·의상·재생 설정을 관리합니다.

## 모델

- **모델 업로드** — `.zip` 번들 또는 외부 Cubism 모델
- 업로드 후 Unity 클라이언트에 모델이 전송·로드됩니다
- 캐릭터 폴더를 바꾸면 탭 내용이 해당 캐릭터 설정으로 동기화됩니다

## 표정·감정

- LLM 응답의 감정 태그에 따라 표정이 바뀝니다
- **감정–표정 매핑** UI에서 감정별 Live2D expression을 연결할 수 있습니다
- **감정별 추가 프롬프트**는 AI 기능 탭에서 편집

## 의상 (Outfit)

- 안경·뿔·고양이 귀 등 토글 가능한 의상 파트
- UI에서 변경하면 디스크·Unity에 즉시 반영
- AI 응답의 `<glasses_on>` 같은 태그로도 변경 가능

## 재생 설정

| 항목 | 설명 |
|------|------|
| 볼륨 | Unity AudioSource 볼륨 |
| Mouth gain | 립싱크 입 움직임 강도 |

변경 시 Unity로 즉시 전송됩니다.

## Live2D 관리자

고급 설정(HTTP expression 토글 등)은 **Live2D 관리자** 다이얼로그에서 다룹니다.

## Unity 연동

Python이 behavior 명령을 WebSocket으로 보내면 Unity가 표정·의상·자막을 갱신합니다. Unity가 실행 중이어야 합니다.

[Unity 클라이언트](07-unity-client.md)
