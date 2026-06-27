# 02-2. 캐릭터

![캐릭터 패널](../assets/ui/panel-character.png)

캐릭터의 말투·성격·방송 상황(시나리오)을 정하는 탭입니다. setting_doc 아래 캐릭터별 폴더와 연결됩니다.

## 언어·이름

<p><strong>응답 및 TTS 언어</strong> — AI가 말하는 언어와 TTS 발음 언어입니다 (한국어 / English / 日本語 등).</p>

<p><strong>유저 이름</strong> — 프롬프트 변수 <span class="tex2jax_ignore">$USER_NAME</span>에 들어갑니다. AI가 스트리머를 부를 때 쓰는 이름입니다.</p>

<p><strong>캐릭터 이름</strong> — <span class="tex2jax_ignore">$CHARACTER_NAME</span>. 캐릭터 자신의 이름입니다.</p>

## 캐릭터 설정 폴더

**캐릭터 설정 폴더 (프롬프트·메모리)** 드롭다운에서 siro 같은 캐릭터를 고릅니다. setting_doc/{캐릭터명}/ 아래에 프롬프트·시나리오·레퍼런스·메모리가 묶여 있습니다.

폴더를 바꾸면 [라투디](https://wikidocs.net/372532)·[보이스](https://wikidocs.net/372528) UI도 그 캐릭터 기준으로 함께 바뀝니다.

<p><strong>폴더 파일 (예: setting_doc/siro/)</strong></p>

<ul>
<li><strong>prompt.txt</strong> — 시스템 프롬프트 본문 (매크로 사용)</li>
<li><strong>scenario/</strong> — 방송 상황 txt — <span class="tex2jax_ignore">$SCENARIO</span>에 삽입</li>
<li><strong>topic.txt</strong> — 한 줄짜리 대화 주제 목록 — <span class="tex2jax_ignore">$TOPIC</span>에서 1줄 랜덤</li>
<li><strong>reference.jsonl</strong> — 말투·문답 예시 — <span class="tex2jax_ignore">$REFERENCE</span> 벡터 검색</li>
<li><strong>summary_log.txt</strong> — 세션 요약 (자동 갱신) — <span class="tex2jax_ignore">$SUMMARY</span></li>
<li><strong>character_mix/</strong> — 성격 변주용 txt — <span class="tex2jax_ignore">$character_mix</span> 랜덤 1개</li>
<li><strong>conversation_history/</strong> — 대화 기록 (일별 jsonl)</li>
<li><strong>db/</strong> — 장기 메모리 저장 (자동 생성)</li>
<li><strong>설정 폴더 열기</strong> — 탐색기에서 해당 폴더를 엽니다.</li>
<li><strong>프롬프트 편집</strong> — prompt.txt를 GUI로 편집합니다. 성격·말투·규칙의 기본 틀입니다.</li>
</ul>

<p><img src="https://static.wikidocs.net/images/page/372527/gh_599c1a2ec2e5.png" alt="프롬프트 편집 다이얼로그"></p>

<h3>prompt.txt 매크로</h3>

<p>프롬프트 편집 창 상단 <strong>사용 가능한 매크로</strong>와 동일합니다. <span class="tex2jax_ignore">$이름</span> 형태로 적으면 <strong>LLM에 보내기 직전</strong>에 실제 값으로 치환됩니다.</p>

<ul>
<li><span class="tex2jax_ignore">$USER_NAME</span> — <strong>캐릭터</strong> 탭 <strong>유저 이름</strong>. 시나리오 txt 안에서도 사용 가능.</li>
<li><span class="tex2jax_ignore">$CHARACTER_NAME</span> — <strong>캐릭터</strong> 탭 <strong>캐릭터 이름</strong>. 시나리오 txt 안에서도 사용 가능.</li>
<li><span class="tex2jax_ignore">$SCENARIO</span> — <strong>시작 시나리오</strong> 드롭다운에서 고른 txt 전체. 「없음」이면 빈 문자열.</li>
<li><span class="tex2jax_ignore">$OUTFIT_STATE</span> — 의상 on/off 태그 묶음. glasses_off, horn_off, cat_ear_on 등 — <strong>프로그램 시작 시</strong> 스냅샷.</li>
<li><span class="tex2jax_ignore">$SUMMARY</span> — summary_log.txt 내용. <strong>AI 기능</strong> → 「대화 후 세션 요약 자동 갱신」 켜야 갱신됨.</li>
<li><span class="tex2jax_ignore">$TOPIC</span> — topic.txt에서 <strong>1줄</strong> 무작위 선택. 유저가 새 주제를 안 꺼낼 때 힌트.</li>
<li><span class="tex2jax_ignore">$REFERENCE</span> — reference.jsonl에서 유사 문답 검색. <strong>AI 기능</strong> → 「캐릭터 레퍼런스 문서 검색 참조」 + <strong>한번에 참조하는 레퍼런스 수</strong>.</li>
<li><span class="tex2jax_ignore">$MEMORY</span> — 장기 메모리에서 유사한 기억 (최대 5건). <strong>AI 기능</strong> → 「장기 메모리」 + 임베딩용 API 키.</li>
<li><span class="tex2jax_ignore">$EMOTION_STATE</span> — 감정 수치 요약. 예: joy:high, anger:low — 값 2 미만은 생략, 전부 미만이면 neutral.</li>
<li><span class="tex2jax_ignore">$SENTENCE_NUMBER</span> — 이번 응답 목표 문장 수. 1·2·3 중 <strong>응답마다</strong> 랜덤.</li>
<li><span class="tex2jax_ignore">$character_mix</span> — character_mix/ 안 txt <strong>1개</strong> 무작위. 폴더·파일 없으면 빈 문자열. 프롬프트에 직접 넣어야 함.</li>
</ul>

<p><span class="tex2jax_ignore">$OUTFIT_STATE</span> 예: glasses_off, horn_off, cat_ear_on, longhair_on, longSleeveTee</p>

<p><strong>치환 시점 요약</strong></p>

<ul>
<li><strong>프로그램 시작 시</strong> (ChatBot 초기화): <span class="tex2jax_ignore">$USER_NAME, $CHARACTER_NAME, $SCENARIO, $OUTFIT_STATE</span> → 이후 prompt.txt 본문은 메모리에 고정.</li>
<li><strong>매 응답마다</strong>: <span class="tex2jax_ignore">$SUMMARY, $SENTENCE_NUMBER, $character_mix, $EMOTION_STATE, $TOPIC, $REFERENCE, $MEMORY</span>.</li>
</ul>

<p><span class="tex2jax_ignore">$EMOTION_STATE</span>와 별개로, <strong>감정별 추가 프롬프트</strong>는 지배 감정이 일정 수준 이상일 때 system 프롬프트 <strong>끝에 문단으로 덧붙습니다</strong> (매크로 아님). 편집은 <a href="https://wikidocs.net/372530">AI 기능</a> 탭.</p>

<p><strong>예시 (prompt.txt 발췌)</strong></p>

<pre><code>[Topic Setting]
'$USER_NAME'가 별다른 주제를 제시하지 않았을 때, 다음 주제 중 하나를 선택하여 대화를 이어가라.
$TOPIC

[Example Dialogue]
$REFERENCE

[$USER_NAME와 $CHARACTER_NAME의 대화 내역]
$SUMMARY

[$CHARACTER_NAME의 기억]
$MEMORY

Your initial outfit state is: $OUTFIT_STATE
Your current emotional state is: $EMOTION_STATE
답변은 반드시 $SENTENCE_NUMBER문장으로 구성하라.
</code></pre>

<h2>시작 시나리오</h2>

<p><strong>시작 시나리오 파일</strong> — 지금 방송에서 어떤 상황인지 AI에게 알려 주는 텍스트입니다. <span class="tex2jax_ignore">$SCENARIO</span>에 삽입됩니다. 예: 「게임 방송 중」, 「시청자와 수다」.</p>

<ul>
<li><strong>시나리오 폴더 열기</strong> — 시나리오 txt 파일들이 있는 폴더를 엽니다.</li>
<li><strong>목록 새로고침</strong> — 파일을 추가·삭제한 뒤 드롭다운 목록을 다시 읽습니다.</li>
</ul>

<p><img src="https://static.wikidocs.net/images/page/372527/gh_34bcae9b3e40.png" alt="시작 시나리오 — 드롭다운 선택"></p>
<p><img src="https://static.wikidocs.net/images/page/372527/gh_684c738e250a.png" alt="시나리오 폴더 — txt 파일 목록"></p>
<p><img src="https://static.wikidocs.net/images/page/372527/gh_c71f75ab358f.png" alt="시나리오 목록 새로고침"></p>

<h2>레퍼런스·감정 프롬프트</h2>

<p>문답 예시(레퍼런스)와 감정별 추가 문장은 <strong>AI 기능</strong> 탭에서 편집합니다. 자세한 설명과 스크린샷은 <a href="https://wikidocs.net/372530">AI 기능</a> 페이지를 보세요.</p>

<ul>
<li><strong>레퍼런스 문답 편집</strong> — reference.jsonl에 「이런 질문엔 이렇게 답한다」 예시를 쌓습니다.</li>
<li><strong>감정별 추가 프롬프트 편집</strong> — 기쁨·화남 등 상태마다 system 프롬프트에 덧붙일 문장을 넣습니다.</li>
</ul>

[[TIP("재시작 필요")]]
캐릭터 폴더·시나리오·프롬프트를 바꾼 뒤 **프로그램 재시작**이 필요합니다.
[[/TIP]]
