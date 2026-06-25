# 02-2. 캐릭터

![캐릭터 패널](../assets/ui/panel-character.png)

| UI 라벨 | 설명 | 즉시 반영 |
|---------|------|-----------|
| 응답 및 TTS 언어 | 응답·TTS 언어 (`ko` / `en` / `ja`) | X |
| 유저 이름 (프롬프트의 $USER_NAME) | 스트리머 호칭 | X |
| 캐릭터 이름 (프롬프트의 $CHARACTER_NAME) | AI 캐릭터 이름 | X |
| 캐릭터 설정 폴더 (프롬프트·메모리) | `setting_doc/<이름>/` | X |
| 설정 폴더 열기 | 탐색기에서 폴더 열기 | — |
| 프롬프트 편집 | `prompt.txt` GUI 편집 | X |
| 시작 시나리오 파일 | `$SCENARIO`에 들어갈 텍스트 | X |
| 시나리오 폴더 열기 / 목록 새로고침 | 시나리오 파일 관리 | — |

캐릭터 폴더를 바꾸면 [[02-7. 라투디|라투디]]·[[02-3. 오디오·음성|보이스]] UI도 함께 바뀝니다.

### 프롬프트·시나리오·레퍼런스 (편집 다이얼로그)

![screenshot](../assets/gdoc/img_044.png)

- **프롬프트 편집** — 성격·말투 베이스
- **시나리오** — 현재 방송 상황 (`$SCENARIO`)
- **레퍼런스 문답** — `reference.jsonl` 예시

![screenshot](../assets/gdoc/img_045.png)
![screenshot](../assets/gdoc/img_046.png)
![screenshot](../assets/gdoc/img_047.png)

### 감정별 추가 프롬프트

[[02-5. AI 기능|AI 기능]] 패널의 **감정별 추가 프롬프트 편집**에서 설정합니다.

![screenshot](../assets/gdoc/img_048.png)
![screenshot](../assets/gdoc/img_049.png)
![screenshot](../assets/gdoc/img_050.png)
![screenshot](../assets/gdoc/img_051.png)

[[TIP("재시작 필요")]]
캐릭터 폴더·시나리오·프롬프트 변경은 **프로그램 재시작** 후 반영됩니다.
[[/TIP]]
