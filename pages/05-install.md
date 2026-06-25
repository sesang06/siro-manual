# 설치

## 1. 실행 프로그램 다운로드

1. [Hugging Face 버킷](https://huggingface.co/buckets/sesang06/siro_vtuber)에 접속합니다.
2. GPU에 맞는 zip을 받습니다.
   - 일반: `siro_ai.zip`
   - RTX 50-series 등: `siro_ai_50.zip`
3. 원하는 폴더에 **압축을 해제**합니다. (예: `C:\siro_ai\`)

[[TIP("TIP")]]
경로에 한글이나 특수문자가 없을수록 안정적입니다.
[[/TIP]]
## 2. API 키 설정

압축 해제 후 `setting_doc` 폴더에 설정 파일이 있습니다.

1. `setting_doc/config.yaml.example`이 있으면 `config.yaml`로 복사합니다.
2. `setting_doc/config.yaml`을 텍스트 에디터로 엽니다.
3. 사용할 LLM·STT·TTS에 맞는 API 키를 입력합니다.

```yaml
# 예시 (실제 키는 본인 것으로 교체)
api_key: "YOUR_GEMINI_API_KEY"
openai_api_key: "YOUR_OPENAI_KEY"
model_type: gemini
```

캐릭터별 설정은 `setting_doc/siro/config.yaml`에도 있습니다. UI에서 변경하면 자동 저장됩니다.

[[WARNING("보안")]]
`config.yaml`에는 API 키가 들어갑니다. 공개 저장소나 스트림 화면에 노출하지 마세요.
[[/WARNING]]
## 3. Unity 클라이언트

Live2D 표시·자막·오디오 재생은 Unity 클라이언트가 담당합니다. [Unity 클라이언트](07-unity-client.md) 절차에 따라 **siro-launcher**를 준비하세요.

## 4. 첫 실행

[첫 실행](06-first-run.md)으로 진행합니다.

## 업데이트

새 zip을 받아 기존 폴더를 덮어쓰기 전에 `setting_doc` 백업을 권장합니다. [설정 관리](12-settings.md)의 내보내기 기능을 사용할 수 있습니다.
