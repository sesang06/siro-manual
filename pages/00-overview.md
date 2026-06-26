# 00. 개요

시로 AI 버튜버는 **대화·음성 인식·음성 합성·Live2D 캐릭터 표시**를 한 프로그램으로 제공하는 AI 버튜버 방송 도구입니다. 실행하면 캐릭터 창이 함께 뜹니다.

[[TIP("시작하기")]]
처음이시면 **[01. 시작하기](https://wikidocs.net/372516)** 순서로 읽어 주세요.
[[/TIP]]

## 구성 요소

| 구성 | 역할 |
|------|------|
| **AI 버튜버 실행 프로그램** | LLM 대화, STT, TTS, Live2D·자막·오버레이, 채팅·후원 연동 |
| **GPT-SoVITS** (선택) | 로컬 TTS 엔진 — `tts 모듈` 사용 시 자동 기동 |

## 다운로드

- [Hugging Face — sesang06/siro_vtuber](https://huggingface.co/buckets/sesang06/siro_vtuber)
- **`siro_ai.zip`** (일반 GPU), **`siro_ai_50.zip`** (50xx대 GPU)

![Hugging Face 다운로드](../assets/gdoc/hf_siro_vtuber_bucket.png)

## 빠른 시작

1. [01. 시작하기](https://wikidocs.net/372516) — 요구사항·설치·API 키·첫 실행
2. **프로그램 시작** 클릭
3. 마이크로 말하면 AI가 응답합니다

## 메뉴얼 구성

| 섹션 | 내용 |
|------|------|
| [시작하기](https://wikidocs.net/372516) | 설치·실행·첫 사용 |
| [UI 설정](https://wikidocs.net/372517) | 앱 패널별 설정 (AI·캐릭터·방송 등) |
| [문제 해결](https://wikidocs.net/372522) | 트러블슈팅·[변경 이력](https://wikidocs.net/372523) |
| [파인튜닝 협조](https://wikidocs.net/372487) | [JSONL 편집기](https://editor-two-virid.vercel.app/)에서 대화 예시 교정 — 추후 시로 AI 파인튜닝 자료로 사용 |

## 도움이 필요할 때

- [문제 해결](https://wikidocs.net/372522)
- [변경 이력](https://wikidocs.net/372523)

## 파인튜닝 협조 요청

시로 AI의 **말투·성격·대화 품질**을 더 좋게 만들기 위해, 방송·테스트 대화를 JSONL 형태로 모아 **파인튜닝 학습 데이터**로 쓸 예정입니다. 지금은 웹 편집기에서 예시를 함께 다듬어 주시면 큰 도움이 됩니다.

**[JSONL 편집기](https://editor-two-virid.vercel.app/)** 에 접속해 USER·ASSISTANT 턴을 읽고, 어색한 표현·OOC(캐릭터 붕괴)·오타를 고쳐 주세요. **승인·반영된 수정분은 추후 시로 AI 파인튜닝 자료에 포함**됩니다.

![JSONL 편집기](../assets/gdoc/finetune_jsonl_editor.png)

### 편집기 사용 요약

| 영역 | 설명 |
|------|------|
| **파일 목록** (좌측) | `1.jsonl` ~ `21.jsonl` — 대화 묶음별 파일 |
| **예시 목록** (중앙) | 한 파일 안의 대화 예시. `#1`, `#2` … 항목을 골라 편집 |
| **편집 영역** (우측) | USER / ASSISTANT 턴별 텍스트 수정, 턴 추가·삭제 |

- **게스트 모드** — 로그인 없이 편집 가능. 저장하면 **승인 대기(pending)** 상태로 올라가며, 검토 후 반영됩니다.
- **즉시 저장** — `Ctrl+S` (또는 우측 상단 버튼)
- **예시 삭제** — `Ctrl+D`
- **이동** — `Ctrl+J` 또는 이전/다음 버튼으로 예시 간 이동

[[TIP("협조 부탁")]]
시로답게 들리도록 ASSISTANT 턴 위주로 봐 주셔도 좋습니다. 말투가 어색하거나 설정과 맞지 않으면 고쳐 주시고, **저장**까지 눌러 주세요. 여러 사람이 동시에 다른 예시를 편집할 수 있습니다.
[[/TIP]]
