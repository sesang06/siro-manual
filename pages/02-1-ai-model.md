# 02-1. AI 모델

![AI 모델 패널](../assets/ui/panel-ai-model.png)

| UI 라벨 | 설명 | 즉시 반영 |
|---------|------|-----------|
| 메인 모델 종류 (응답 생성) | 시청자·스트리머 발화에 쓸 LLM (Gemini, ChatGPT 등) | X |
| 메인 모델명 | 모델 ID (`response_model`) | X |
| 서브모델 종류 (레퍼런스·요약) | Idle 의도·요약 등 보조 LLM | X |
| 서브모델명 | 서브모델 ID | X |
| 임베딩 모델 (메모리 벡터 검색) | `chatgpt` / `gemini` | X |
| OpenAI API 키 | ChatGPT·Realtime STT·임베딩 | X |
| Gemini API 키 | Gemini LLM | X |
| Claude API 키 | Claude LLM | X |
| Grok API 키 | Grok LLM | X |
| Hugging Face 토큰 | 일부 모델 다운로드 | X |

[[TIP("재시작 필요")]]
모델 종류·모델명·임베딩 변경은 **프로그램 재시작** 후 적용됩니다.
[[/TIP]]

API 키 발급 절차는 [[01. 시작하기|시작하기]]의 API 키 설정을 참고하세요.
