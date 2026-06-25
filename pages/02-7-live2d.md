# 02-7. 라투디

![라투디 패널](../assets/ui/panel-live2d.png)

## Live2D

| UI 라벨 | 설명 | 즉시 반영 |
|---------|------|-----------|
| 모델 가져오기 (ZIP)… | `.zip` 번들 업로드 | O |
| 저장된 모델 라이브러리 | 캐릭터별 모델 목록 | O |
| 불러오기 | 선택 모델 Unity 전송 | O |
| Unity에 업로드 | 가져온 ZIP 적용 | O |
| 원본 모델로 리셋 | 기본 모델 복원 | O |

![screenshot](../assets/gdoc/img_057.png)

Unity WebSocket으로 표정·의상·모델이 반영됩니다. [[01. 시작하기|Unity 클라이언트]]가 실행 중이어야 합니다.

## 의상

| UI 라벨 | 설명 | 즉시 반영 |
|---------|------|-----------|
| (캐릭터별 토글) | 안경·뿔·고양이 귀 등 | O |
| 셔츠 | 의상 variant | O |

UI·AI `<glasses_on>` 태그·디스크(`character_state.yaml`)가 동기화됩니다.

## 표정

| UI 라벨 | 설명 | 즉시 반영 |
|---------|------|-----------|
| 목록 새로고침 | Live2D expression 목록 | O |
| 전부 끄기 | expression off | O |

LLM 감정 태그 → [[02-5. AI 기능|감정→표정 매핑]]으로 expression 연결.

## 감정→표정 매핑

**감정→표정 매핑 편집…** — 감정 문자열과 Live2D expression 매핑.

## GPT-SoVITS 보이스 (라투디·보이스 연동)

![screenshot](../assets/gdoc/img_058.png)

[[02-3. 오디오·음성|오디오·음성]]의 보이스 패널에서 참조 음성을 설정합니다.

볼륨·립싱크 gain은 Unity 연결 시 **실행 중 즉시 반영**됩니다.
