# 시로 AI 설치 가이드

[[TIP("업데이트 안내")]]
**2026-05-04** 의상 체인지가 동작하지 않는 버그를 수정했습니다. 이전에 다운받으신 분은 새로 다운받으시길 바랍니다.
[[/TIP]]
## 시로 AI 소개

![screenshot](assets/gdoc/img_000.jpg)

(게임 훈수두는 AI 버튜버 미소녀 만드는 법)
- 시로AI는 실시간으로 유튜브, 치지직, 투네이션의 후원과 댓글, 그리고 스트리머의 목소리, 이미지를 인식하여 반응하는 AI 컴퍼니언입니다.
- 유저가 자신의 Live2D 모델, 목소리, 성격 설정을 함으로써 
자신만의 AI 컴퍼니언을 방송에 활용할 수 있도록 지원합니다.
- 제미나이, 클로드, chatgpt, ollama, grok을 베이스 LLM으로 지원합니다.
- 사용자의 지시에 따라 캐릭터의 의상, 외형, 움직임, 감정을 실시간으로 변경 및 표현합니다.
- 의상: 저지, 타이트핏, 긴팔, 반팔
- 외형: 고양이귀, 안경, 뿔, 장발, 단발
- 움직임: 어지러움, 끄덕임, 좌우로 흔들기, 윙크
- 감정: 놀람, 분노, 슬픔, 즐거움, 흥분, 부끄러움

## Live2D 애니메이션 / 모션 관련

개발진 중 리깅 작가가 없어, idle animation / 감정별 애니메이션 / 모션이 약간 부자연스럽습니다. 시로AI 에 기본으로 탑재될 만한 애니메이션이 있으시면 제공해 주시면 감사하겠습니다.

## 프로그램 경로에 한글, 공백 금지

프로그램 경로에 걸쳐 한국어나 공백을 지워 주세요. 상위 폴더들도 마찬가지입니다.

## 사용자 폴더 이름이 한글이면 구동 불가

[https://www.youtube.com/watch?v=jBRkP4AV5rI](https://www.youtube.com/watch?v=jBRkP4AV5rI)  같은 걸 보시면서 영문으로 윈도우 계정을 변경하셔야 동작합니다.


### 다운로드

**엔비디아 GPU 50xx번대 제외 버전**

- [Google Drive](https://drive.google.com/file/d/1435v88zbfrqKQPtfU8W8xytnVzfPv2Nk/view?usp=sharing)
- [Hugging Face (대체)](https://huggingface.co/buckets/sesang06/siro_vtuber/tree/main/siro_ai.zip)

**엔비디아 GPU 50xx번대 버전**

- [Google Drive](https://drive.google.com/file/d/107Zrf5Y2sNoLtuAAsus19ez62SqqaHs3/view?usp=drive_link)
- [Hugging Face (대체)](https://huggingface.co/buckets/sesang06/siro_vtuber/tree/main/siro_ai_50.zip)

## 문의용 디스코드

![screenshot](assets/gdoc/img_001.png)

프로그램 문의 / 피드백: [Discord](https://discord.com/invite/Dj9nBPCZv6) · [over.horizon.dev@gmail.com](mailto:over.horizon.dev@gmail.com)

프로그램 업데이트는 디스코드 공지로 진행합니다.

## 요구조건 안내
- 권장사양
- NVIDIA GPU
- 램 24GB 이상
- 제미나이 API Key 사용
- 이어폰 사용 필수
- 시로의 목소리가 다시 재인식되는 에코를 막기 위해서입니다.
- 이용 조건
- 모델 무단 배포 금지
Live2D 모델과 음성 소스의 저작권은 각 제작자에게 있으며, 허가 없이 사용하는 행위 및 무단 배포는 금지합니다.
- 보이스 및 모델의 비정상적 용도 사용 금지
예: AI 외의 용도로 사용하는 경우, 개인 방송에 그대로 사용하는 등 (개인 방송에 AI시로의 구동용으로 사용하는 건 가능, 시로의 Live2D를 이용하여 연기하는 건 불가)
- 구동 시 제미나이 API 키가 각 서비스 사에 청구되는데, 이 비용은 각자 부담하셔야 합니다. 
방송용으로 적극적으로 사용했을 때, 한시간에 0.5달러~1달러가 소모됩니다
- 이용 허가 / 불가 예시
- 허가되는 경우
- 유투브, 치지직, 트위치, 숲 등에서 시로AI와 같이 방송
- 방송 중에 제 3 게임에 대한 광고를 받아 수익을 창출함
- 방송 중에 후원을 받음
- 방송 편집본을 유투브에 올려서 수익을 창출함
- 시로의 프롬프트, Live2D 캐릭터, 목소리를 설정하여 시로가 아닌 다른 페로소나로 별도로 사용
- 불허되는 경우
- 시로AI의 Live2D 아바타를 booth 등에 배포
- 시로AI의 Live2D 아바타를 직접 방송인 본인이 페르소나로 사용하여 연기
- 방송인 협력 지원
- 방송에 시로AI를 사용하는 것은 별도의 허가가 필요하지 않으며, 시로AI로 이용한 방송, 유투브, 키리누키 등은 자유롭게 가능합니다.
- 시로AI를 사용한 방송에서 얻은 후원금 및 조회수로 인한 수익, 시로AI와 같이 한 방송 광고로 인한 광고 수입을 요구하지 않습니다.
- 방송인에게 한정해서 설치 지원과 목소리 모듈지원을 해드리고 있습니다. 이에 대한 문의는 디스코드나 [over.horizon.dev@gmail.com](mailto:over.horizon.dev@gmail.com) 으로 주시길 바랍니다.
- 방송인에 한정해서 Live2D 모델이나 목소리 모듈, 성격 교체 등도 가능합니다. 이에 대한 문의는 [over.horizon.dev@gmail.com](mailto:over.horizon.dev@gmail.com) 으로 주시길 바랍니다. 단, Live2D 모델은 본인이 구해 오셔야 교체 가능합니다.
