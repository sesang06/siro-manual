# 02-1. AI·화면

**AI 모델**, **캐릭터**, **AI 기능**, **화면 캡처** 탭을 설명합니다.

## AI 모델 탭

| 항목 | 설명 |
|------|------|
| 메인 모델 | 시청자·스트리머 발화에 대한 응답 생성 |
| 서브모델 | 요약·Idle 의도 계획 등 보조 작업 |
| 임베딩 | 장기 메모리 벡터 검색 (chatgpt / gemini) |
| API 키 | 선택한 제공자별 키 |

[[TIP("재시작 필요")]]
모델 종류·모델명 변경은 프로그램 재시작 후 적용됩니다.
[[/TIP]]

## 캐릭터 탭

| 항목 | 설명 |
|------|------|
| 캐릭터 폴더 | `setting_doc/<이름>/` — 프롬프트·메모리·보이스 등 |
| 시나리오 | `$SCENARIO` 프롬프트 변수 |
| 주제 / 요약 | `$TOPIC`, `$SUMMARY` |
| 프롬프트 편집 | `prompt.txt` GUI 편집 |
| 스트리머 이름 | `$USER_NAME` |

캐릭터 전환 시 Live2D·보이스·의상 UI가 함께 바뀝니다 (**재시작** 권장).

### 캐릭터 프롬프트·시나리오

![screenshot](../assets/gdoc/img_044.png)

- **프롬프트 편집** — 캐릭터 성격·말투의 베이스 텍스트
- **시나리오 선택** — 현재 방송 상황을 덧붙이는 설정
- **레퍼런스 문답** — 응답 예시 (`reference.jsonl`)

![screenshot](../assets/gdoc/img_045.png)
![screenshot](../assets/gdoc/img_046.png)
![screenshot](../assets/gdoc/img_047.png)

설정 변경 후 **프로그램 종료 → 재시작**해야 반영됩니다.

### 감정 기복

캐릭터에 현재 감정을 부여하고, 감정별 추가 프롬프트를 설정합니다.

![screenshot](../assets/gdoc/img_048.png)
![screenshot](../assets/gdoc/img_049.png)
![screenshot](../assets/gdoc/img_050.png)
![screenshot](../assets/gdoc/img_051.png)

## AI 기능 탭

| 기능 | 설명 |
|------|------|
| 캐릭터 레퍼런스 | 과거 Q&A 예시 검색 후 프롬프트에 삽입 |
| 레퍼런스 편집 | `reference.jsonl` 문답 추가 |
| 장기 메모리 | mem0 + Qdrant로 대화 기억 |
| 세션 요약 | 방송 후 `$SUMMARY` 자동 갱신 |
| Idle 자동 발화 | 침묵 시 캐릭터가 먼저 말함 |
| 풀 프롬프트 출력 | 디버그 로그 (개발·트러블슈팅용) |

Idle·메모리·레퍼런스·debug는 **실행 중 즉시 반영**됩니다.

### Idle 자동 발화

1. **자동 발화 활성화** 체크
2. **기본 침묵 임계값 (초)** — 이 시간 동안 조용하면 발화 후보
3. **랜덤 편차 (%)** — 매번 임계값에 난수 적용

## 화면 캡처

**화면 캡처** 탭에서 AI가 «보고 있는 화면»을 설정합니다. 멀티모달 LLM이 활성화되면 캡처 이미지가 응답 생성에 포함됩니다.

| 모드 | 설명 |
|------|------|
| 카메라/화면 | 웹캠 또는 특정 창·모니터 캡처 |
| 직접 입력 | 오버레이 창에 텍스트·이미지를 직접 입력 |

- **이미지 인식 사용** — 켜면 응답 시점에 화면 캡처를 LLM에 전달
- **한번에 첨부할 이미지 수** — 최근 프레임 연속 인식 (4장 ≈ 6초)
- **이미지 화질** — 저화질=빠름, 고화질=정확

[[TIP("TIP")]]
이미지 인식을 켜면 LLM 과금·레이턴시가 증가합니다. 계속 대화 시 시간당 약 $1 수준입니다.
[[/TIP]]

![screenshot](../assets/gdoc/img_036.png)

### 직접 입력 모드

![screenshot](../assets/gdoc/img_037.png)
![screenshot](../assets/gdoc/img_038.png)

1. 캡처 모드를 **직접 입력**으로 선택합니다.
2. **캡처 영역 표시**를 누르면 오버레이 창이 나타납니다.
3. 게임 화면 등에 영역을 드래그해 맞춥니다.

### 카메라 / OBS Virtual Camera

한 프로그램이 카메라를 점유하면 OBS 등 다른 프로그램은 사용할 수 없습니다. OBS **가상 카메라**를 활용하세요.

[UTF-8 로캘 설정 (네이버 블로그)](https://blog.naver.com/404errorkr/223834100569) — 비디오 장치 로딩 오류 시 **Unicode UTF-8** 베타 옵션 확인.

![screenshot](../assets/gdoc/img_039.png)
![screenshot](../assets/gdoc/img_040.png)
![screenshot](../assets/gdoc/img_041.png)
![screenshot](../assets/gdoc/img_042.png)
![screenshot](../assets/gdoc/img_043.png)

캡처 모드·이미지 인식·캡처 대상 변경은 **프로그램 실행 중에도 즉시 반영**됩니다.
