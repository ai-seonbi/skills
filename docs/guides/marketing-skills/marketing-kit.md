# 마케팅 AI 스킬 10개: 무엇이 있고 무엇부터 쓸까

마케팅 작업에 쓸 수 있는 AI 스킬 10개를 한 번에 정리했습니다. 설치 수가 많은 순서로 후보를 고르고, 각 스킬의 원문 지침을 읽어 종합 등급과 추천 이유를 붙였습니다. 스킬마다 쓰는 상황, 넣을 정보, 받는 결과, 설치 명령, 시작 예제 프롬프트가 있습니다. AI 스킬이 처음이라면 바로 아래 안내부터 읽으세요.

## AI 스킬이 처음이라면

**스킬이란.** 특정 작업의 절차와 확인할 점을 적어 둔 지시문 묶음입니다. `SKILL.md` 파일 하나와 필요한 참고 파일로 이루어지고, AI 도구가 작업에 맞는 스킬을 골라 쓰거나 내가 이름으로 직접 부릅니다. [Claude Code 공식 문서](https://code.claude.com/docs/en/skills)는 관련 있을 때 Claude가 스킬을 쓰고 `/스킬이름`으로 직접 부를 수도 있다고 설명합니다. [Codex 공식 문서](https://developers.openai.com/codex/skills)는 `/skills`나 `$`로 스킬을 언급하고, 작업이 스킬 설명과 맞으면 Codex가 스킬을 고를 수 있다고 설명합니다.

**필요한 것.**

1. 스킬을 쓰는 AI 도구 하나. [Claude Code](https://code.claude.com/docs/en/setup)는 Pro·Max·Team·Enterprise·Console 계정이 필요하며 무료 claude.ai 요금제에는 포함되지 않습니다. [Codex CLI](https://developers.openai.com/codex/cli)는 처음 실행할 때 ChatGPT 계정이나 다른 인증 방법으로 로그인합니다. Codex의 요금제별 사용 조건은 이번에 확인하지 않았습니다.
2. [Node.js](https://nodejs.org/en/download). 아래 설치 명령의 `npx skills`가 [skills 패키지](https://www.npmjs.com/package/skills)를 실행하며, 1.7.1 버전은 Node.js 22.20.0 이상을 요구합니다.
3. 작업할 폴더 하나. 스킬은 기본적으로 그 폴더(프로젝트)에 설치됩니다.

**시작 순서.** macOS·Linux 터미널 기준입니다. Windows 설치 명령은 각 공식 문서의 Windows 안내를 따르세요.

```sh
# 1. AI 도구 설치 (둘 중 하나)
curl -fsSL https://claude.ai/install.sh | bash          # Claude Code
curl -fsSL https://chatgpt.com/codex/install.sh | sh     # Codex CLI

# 2. 작업 폴더에서 스킬 설치 (예: copywriting)
npx skills add coreyhaines31/marketingskills --skill copywriting --agent claude-code --copy

# 3. 같은 폴더에서 AI 도구 실행 후 로그인
claude      # Codex는 codex
```

실행한 뒤 아래 예제 프롬프트의 `[ ]`를 내 상품·고객 정보로 바꿔 붙여 넣으세요. Claude Code에서는 `/copywriting`처럼 스킬 이름으로 직접 부를 수도 있습니다. Codex를 쓴다면 설치 명령의 `--agent claude-code`를 `--agent codex`로 바꿉니다. [skills CLI 문서](https://github.com/vercel-labs/skills#supported-agents)에 따르면 프로젝트 설치 위치는 Claude Code가 `.claude/skills/`, Codex가 `.agents/skills/`이며, `-g`를 붙이면 모든 프로젝트에서 쓰도록 사용자 폴더에 설치합니다. `--copy`는 링크 대신 파일을 복사합니다.

**한 번 적어 두면 좋은 것.** 10개 원문 모두 시작 전에 `.agents/product-marketing.md`(또는 `.claude/product-marketing.md`)가 있으면 먼저 읽고, 거기 없는 정보만 묻도록 적혀 있습니다. 상품·고객·차별점·근거를 이 파일에 정리해 두면 여러 스킬에서 같은 질문을 덜 받습니다.

공식 문서 확인일은 2026-10-07입니다. 도구의 설치 방법과 요금제는 바뀔 수 있으니 설치 전에 위 링크를 다시 확인하세요.

## 이렇게 골랐어요

1. **설치 수**: skills.sh가 CLI 설치를 집계한 누적 횟수입니다. 많이 설치됐다는 관심의 신호라 후보를 고르고 같은 등급 안의 순서를 정하는 데만 썼습니다. 고유 사용자 수, 만족도, 출력 품질, 마케팅 성과를 뜻하지 않고 등급을 올리는 근거로 쓰지 않았습니다. 예를 들어 설치 3위인 marketing-psychology는 C입니다.
2. **지침의 구체성**: 원문 SKILL.md가 무엇을 물어보고(입력), 어떤 순서로 작업하고(절차), 무엇을 내놓고(산출물), 결과를 어떻게 확인하는지(점검 기준)를 이어서 안내하는지 읽었습니다. 출력을 실행해 채점한 것은 아닙니다.
3. **업무 쓸모(유용성)**: 마케팅을 맡은 사람이 그 작업을 얼마나 자주 하는지, 특별한 준비물(운영 사이트·대량 데이터·구독 사업) 없이 시작할 수 있는지, 받은 결과를 바로 쓸 수 있는지를 본 판단입니다. 준비물이 많다는 이유로 지침 품질을 낮추지 않고, 조건을 이유에 적었습니다.

세 기준을 숫자 점수로 합산하지 않았습니다. 설치 수가 많아도 지침에 결과 형식이나 점검 기준이 없으면 높은 등급을 주지 않았고, 지침이 좋아도 특정 사업에서만 쓰면 그 조건을 이유에 적었습니다.

- **S · 먼저 써볼 추천**: 대상 업무의 효용이 분명하고 입력부터 산출물·검사까지 지침이 구체적이어서 우선 추천할 근거가 있다.
- **A · 추천 · 일부 보완**: 업무의 효용과 핵심 절차가 분명하며 일부 판단·검사 항목은 보완하면 좋다.
- **B · 조건 맞으면**: 활용 가치가 있으나 필요한 입력·절차·검사 중 중요한 부분을 추가해야 하거나, 특정 사업 조건에서만 쓸 수 있다.
- **C · 아이디어 참고용**: 아이디어를 참고할 가치는 있으나 핵심 업무를 진행할 지침을 상당 부분 보완해야 한다.

## 발행 전 원문 재확인 · 2026-10-10

릴스의 후보와 설치 수는 2026-10-07 집계입니다. 공개 전 10개 SKILL.md를 다시 비교했습니다. 아래 변화는 입력·절차를 보강하며, 이 자료의 일반 마케팅 입문자 기준 종합 티어는 유지합니다. 실제 출력을 실행한 성과 비교는 아닙니다.

- **seo-audit 2.2.0**: 검색 8~20위 페이지 개선, 제목 태그, 지역 검색 참고 문서 연결이 추가됐습니다.
- **content-strategy 2.1.3**: 검색형 글을 쓰기 전 기존 상위 글에 없는 정보를 하나 정하도록 추가됐습니다.
- **ai-seo 2.7.6**: 구매 인지 단계별 질문, 인용 결과를 수정 작업으로 연결하는 안내, 목적별 참고 문서 경로가 추가됐습니다.
- **ad-creative 2.10.0**: 고객 인지 단계에 맞춘 텍스트 광고 제목과 모바일 시각 명세 참고 경로가 추가됐습니다.
- **lead-magnets 2.1.0**: 소유한 강의·자료를 설치 가능한 스킬로 묶는 참고 경로가 추가됐습니다.
- **cold-email 2.2.0**: 발송 준비·여러 채널의 연락 순서·답장 대응이 추가됐습니다. 이전 자료의 “발송 안내가 없다”는 설명을 수정했습니다. 결과 형식과 근거 생성 방지의 보완점은 남습니다.
- **churn-prevention 2.0.2**: 버전 표기만 바뀌었습니다. copywriting·programmatic-seo·marketing-psychology의 본문은 이전 확인본과 같습니다.

이번 재확인은 10개 SKILL.md 본문과 변경점의 범위입니다. 새로 연결된 참고 파일 전체, 제시된 수치의 실증, 실제 출력 결과는 검증 범위에 넣지 않았습니다. 아래 설치 명령은 설치 시점의 최신 내용을 가져오므로, 이후에는 이 확인본과 달라질 수 있습니다.

## 전체 티어

| 등급 | 하는 일 | 받는 결과 | 스킬 | 설치 수 (2026-10-07) |
|---|---|---|---|---|
| S | 홈페이지·상품 페이지 문구 쓰기 | 구간별 문구·고른 이유·대안 | [copywriting](https://www.skills.sh/coreyhaines31/marketingskills/copywriting) | 217.4K |
| A | 사이트 검색 문제 찾기 | 문제·근거·수정 순서 | [seo-audit](https://www.skills.sh/coreyhaines31/marketingskills/seo-audit) | 221.5K |
| A | 콘텐츠 주제 고르기 | 주제 묶음·우선순위 표 | [content-strategy](https://www.skills.sh/coreyhaines31/marketingskills/content-strategy) | 151.9K |
| A | AI 답변 인용 점검 | 인용 확인표·개선안 | [ai-seo](https://www.skills.sh/coreyhaines31/marketingskills/ai-seo) | 137.7K |
| A | 광고 문구 여러 안 만들기 | 각도별 문구·글자 수 검사 | [ad-creative](https://www.skills.sh/coreyhaines31/marketingskills/ad-creative) | 122.8K |
| A | 무료 자료 기획하기 | 자료 형식·목차·측정 계획 | [lead-magnets](https://www.skills.sh/coreyhaines31/marketingskills/lead-magnets) | 104.0K |
| B | 검색 페이지 여러 개 설계 | 페이지 틀·출시 점검표 | [programmatic-seo](https://www.skills.sh/coreyhaines31/marketingskills/programmatic-seo) | 140.5K |
| B | 첫 제안 메일 쓰기 | 첫 메일·후속 메일 방향 | [cold-email](https://www.skills.sh/coreyhaines31/marketingskills/cold-email) | 118.1K |
| B | 구독 해지 대응 만들기 | 해지 흐름·복구 메일 | [churn-prevention](https://www.skills.sh/coreyhaines31/marketingskills/churn-prevention) | 112.1K |
| C | 설득 심리 아이디어 참고 | 설득 원리 후보 | [marketing-psychology](https://www.skills.sh/coreyhaines31/marketingskills/marketing-psychology) | 153.6K |

## 스킬별 추천 이유와 시작 예제

### S · 홈페이지·상품 페이지 문구 쓰기 · copywriting

**추천 이유.** 필요한 고객 정보와 근거를 먼저 묻고, 문구와 고른 이유·대안을 준 뒤 근거 없는 주장을 [NEED]로 표시하는 점검까지 있어 가장 먼저 추천한다.

- 이럴 때: 홈페이지·랜딩·상품 페이지 문구는 마케팅 업무에서 자주 필요하고 상품·고객 정보만으로 시작할 수 있다.
- 넣을 정보: 페이지 종류와 원하는 행동 하나, 고객의 문제·망설임·표현, 상품의 차이와 근거(수치·후기), 유입 경로를 먼저 묻는다.
- 작업 절차: 명확성·혜택·구체성 원칙에 따라 첫 화면과 핵심 구간을 구성하고 페이지 종류별 지침과 CTA 지침을 적용한다.
- 받는 결과: 구간별 페이지 문구, 핵심 선택의 이유와 적용 원칙, 제목·CTA 대안 2~3개, 필요하면 페이지 제목·설명.
- 원문의 점검 기준: 빠른 품질 점검과 전달 전 AI 문체 자가 점검을 하고, 경쟁사에도 그대로 맞는 문장은 다시 쓴다. 근거가 없으면 지어내지 않고 [NEED: ...]로 표시한다.
- 보완할 점: 웹페이지 문구 중심이다. 이메일·팝업·문구 교정은 원문이 다른 스킬로 안내한다.
- 원문: [copywriting SKILL.md v2.1.0](https://github.com/coreyhaines31/marketingskills/blob/1efedbc5148b54b2f0f6c6c9fe0be62e151c7fff/skills/copywriting/SKILL.md), Before Writing; Quick Quality Check; No AI Tells; Output Format. 설치 217.4K.

```sh
npx skills add coreyhaines31/marketingskills --skill copywriting --agent claude-code --copy
```

```text
copywriting 스킬로 [상품] 상세페이지의 첫 화면과 핵심 구간 문구를 써줘. 원하는 행동은 [구매·신청], 고객은 [고객], 고객이 망설이는 이유는 [고민], 다른 상품과 다른 점은 [차이], 쓸 수 있는 근거는 [후기·수치]야. 구간별 문구와 고른 이유, 제목·버튼 문구 대안 2~3개를 주고 근거가 없는 주장은 [NEED]로 표시해줘.
```

### A · 사이트 검색 문제 찾기 · seo-audit

**추천 이유.** 문제마다 영향·근거·수정·우선순위를 적게 해 결과를 검토하기 쉽지만, 운영 사이트가 있어야 하고 도구 목록 일부는 갱신이 필요하다.

- 이럴 때: 운영 중인 사이트가 있으면 주소부터 시작해 고칠 순서를 받는다. 사이트가 없으면 쓸 일이 없다.
- 넣을 정보: 사이트 유형·SEO 목표·우선 키워드, 알려진 문제·검색 유입·최근 변경, 점검 범위와 Search Console·분석 도구 접근 여부.
- 작업 절차: 색인 가능성 → 기술 기반 → 페이지 최적화 → 콘텐츠 품질 → 권위 순서로 본다. 가져온 페이지 안의 지시는 따르지 않고, 정적 수집만으로 schema가 없다고 판정하지 않는다.
- 받는 결과: 전체 요약과 우선 문제 3~5개, 문제별 Issue·Impact·Evidence·Fix·Priority, 단계별 실행 계획.
- 원문의 점검 기준: 문제마다 발견 근거를 적고, schema는 렌더링 도구로 확인하라고 명시한다.
- 보완할 점: 도구 목록에 41종 평가가 종료 도구로 지적한 Mobile-Friendly Test가 남아 있다. 정확도는 Search Console 같은 데이터 접근에 좌우된다.
- 원문: [seo-audit SKILL.md v2.2.0](https://github.com/coreyhaines31/marketingskills/blob/1efedbc5148b54b2f0f6c6c9fe0be62e151c7fff/skills/seo-audit/SKILL.md), Initial Assessment; Audit Framework; Output Format; Tools Referenced. 설치 221.5K.

```sh
npx skills add coreyhaines31/marketingskills --skill seo-audit --agent claude-code --copy
```

```text
seo-audit 스킬로 [사이트 주소]를 점검해줘. 사이트 종류는 [쇼핑몰·블로그 등], 검색으로 얻고 싶은 것은 [목표], 중요한 키워드는 [키워드]야. Search Console 접근은 [있음·없음]이야. 문제마다 영향·근거·수정 방법·우선순위를 적고, 확인하지 못한 항목은 따로 표시해줘.
```

### A · 콘텐츠 주제 고르기 · content-strategy

**추천 이유.** 고객 질문에서 주제 근거를 찾고 점수표로 먼저 할 주제를 고르는 절차가 구체적이지만, 가중치 근거와 실행 뒤 점검은 직접 정해야 한다.

- 이럴 때: 무엇을 올릴지 정하는 일은 채널과 관계없이 필요하다. 검색 수요 점수는 키워드 자료가 있어야 채울 수 있다.
- 넣을 정보: 사업·고객·콘텐츠 목표, 구매 전 질문·반론·문의 같은 고객 조사, 기존 콘텐츠·자원·형식, 경쟁사.
- 작업 절차: 검색형과 공유형을 나누고 주제 기둥과 묶음을 만든 뒤, 구매 단계별 키워드와 아이디어 출처를 정리하고 네 요인 점수(40·30·20·10%)로 순서를 정한다.
- 받는 결과: 근거가 있는 주제 기둥 3~5개, 주제별 유형·키워드·구매 단계·고객 조사 근거, 주제 연결 지도.
- 원문의 점검 기준: 점수표로 주제를 고른다. 가중치의 근거와 실행 뒤 다시 조정하는 기준은 원문에 없다.
- 보완할 점: 가중치는 원문이 정한 값이다. 이 레포의 2026-09-21 실제 시연(이전 커밋의 v2.1.1)에서는 첫 출력이 검색형·공유형 분류와 구매 단계를 빠뜨려 형식 보완을 요청했다.
- 원문: [content-strategy SKILL.md v2.1.3](https://github.com/coreyhaines31/marketingskills/blob/1efedbc5148b54b2f0f6c6c9fe0be62e151c7fff/skills/content-strategy/SKILL.md), Before Planning; Prioritizing Content Ideas; Output Format. 설치 151.9K.

```sh
npx skills add coreyhaines31/marketingskills --skill content-strategy --agent claude-code --copy
```

```text
content-strategy 스킬로 다음 달 콘텐츠 주제를 정해줘. 상품은 [상품], 고객은 [고객], 목표는 [유입·문의 등], 고객이 자주 묻는 질문은 [질문 3개], 만들 수 있는 형식은 [릴스·블로그 등]이야. 주제 기둥 3개와 우선 주제 5개를 점수표로 보여주고, 각 주제의 고객 질문 근거를 적어줘.
```

### A · AI 답변 인용 점검 · ai-seo

**추천 이유.** 질문을 여러 AI에서 반복 확인하고 페이지 점검표로 개선점을 찾는 방법이 구체적이지만, 최종 보고서 형식과 효과 확인은 직접 정해야 한다.

- 이럴 때: 내 페이지나 글이 있고 AI 검색에서 언급되고 싶을 때 쓴다. 여러 AI 서비스를 직접 확인하는 시간이 든다.
- 넣을 정보: 중요한 질문, 현재 AI 답변 노출 여부, 콘텐츠 유형·도메인·schema, 목표, 경쟁사.
- 작업 절차: 핵심 질문 10~20개를 Google AI Overview·ChatGPT·Perplexity에서 확인하고, 인용 패턴과 페이지 추출 가능성을 점검한 뒤 AI 봇 접근을 용도별로 본다. 개선은 구조·권위·노출 세 축으로 나눈다.
- 받는 결과: 질문별 인용 여부 표, 페이지별 통과·실패 점검표, 개선안, 월간 추적 기록.
- 원문의 점검 기준: AI 답변은 매번 달라지므로 질문마다 3~5회 실행하고 표본 수와 함께 인용률을 비교하라고 명시한다.
- 보완할 점: 최종 보고서 형식은 정해져 있지 않다. 개선안이 인용 증가로 이어졌는지 확인하는 방법은 약하다.
- 원문: [ai-seo SKILL.md v2.7.6](https://github.com/coreyhaines31/marketingskills/blob/1efedbc5148b54b2f0f6c6c9fe0be62e151c7fff/skills/ai-seo/SKILL.md), Before Starting; AI Visibility Audit; Optimization Strategy; Monitoring AI Visibility. 설치 137.7K.

```sh
npx skills add coreyhaines31/marketingskills --skill ai-seo --agent claude-code --copy
```

```text
ai-seo 스킬로 [페이지 주소]가 AI 답변에 인용될 준비가 됐는지 점검해줘. 고객이 AI에 물을 질문은 [질문 5개], 경쟁사는 [경쟁사]야. 질문별 확인 표, 페이지 점검표의 통과·실패, 개선안 우선순위를 주고 직접 확인한 결과와 제안을 구분해줘.
```

### A · 광고 문구 여러 안 만들기 · ad-creative

**추천 이유.** 각도별 변형과 매체별 글자 수 검사까지 구체적이지만, 처음 만들 때는 실제 근거만 쓰도록 직접 요청해야 한다.

- 이럴 때: 광고를 준비할 때 여러 안을 빠르게 만든다. 원문의 매체 규격은 Google·Meta·LinkedIn·TikTok·X 중심이다.
- 넣을 정보: 광고 매체·형식, 상품·핵심 가치·차이, 대상·인지 단계·고민, 개선할 때의 성과 데이터, 브랜드·규정 제약.
- 작업 절차: 처음 만들기·성과 기반 개선·대량 제작·소재 전략 네 방식이 있다. 문구는 각도 3~5개를 정하고 각도별 변형을 만든 뒤 매체 글자 수를 검사하고 업로드 형식으로 정리한다.
- 받는 결과: 각도별 제목·설명과 글자 수, 일괄 업로드 CSV, 대량 제작의 날짜별 폴더와 근거 색인, 개선 보고서.
- 원문의 점검 기준: 글자 수 초과를 표시하고 줄인 대안을 주며, 중복·정책 위반 가능성을 걸러내고 AI 문체를 점검한다.
- 보완할 점: 지어낸 주장·수치 금지와 근거 표시는 대량 제작 방식에 명시돼 있다. 처음 만들기 방식의 예시에는 수치·사회적 증거 문구가 들어 있다.
- 원문: [ad-creative SKILL.md v2.10.0](https://github.com/coreyhaines31/marketingskills/blob/1efedbc5148b54b2f0f6c6c9fe0be62e151c7fff/skills/ad-creative/SKILL.md), Before Starting; How This Skill Works; Grounded Inputs; Generating Ad Copy; Output Formats. 설치 122.8K.

```sh
npx skills add coreyhaines31/marketingskills --skill ad-creative --agent claude-code --copy
```

```text
ad-creative 스킬로 [Meta·Google 등] 광고 문구를 만들어줘. 상품은 [상품], 대상은 [고객], 고객의 고민은 [고민], 쓸 수 있는 근거는 [후기·수치]야. 각도 3개별로 제목·설명 변형을 만들고 글자 수를 표시해줘. 내가 준 근거 밖의 수치나 후기는 쓰지 마.
```

### A · 무료 자료 기획하기 · lead-magnets

**추천 이유.** 고객 고민에서 자료 형식·목차·받는 방법·측정까지 한 번에 설계하지만, 원문의 기준치는 출처가 없어 내 수치로 바꿔야 한다.

- 이럴 때: 댓글·DM으로 자료를 주고 팔로워나 연락처를 얻는 방식에 바로 연결된다.
- 넣을 정보: 사업·고객·해결하는 문제, 현재 연락처 수집 방법, 다시 쓸 자료와 전문성, 목표·구매 단계·자원.
- 작업 절차: 구체적 문제 하나와 구매 단계에 맞추는 원칙에서 출발해 자료 유형, 받을 정보와 공개 범위, 랜딩·전달, 홍보, 측정을 차례로 정한다.
- 받는 결과: 자료 형식·주제·대상 단계·제작 부담, 목차, 받는 방법과 입력 항목, 배포 계획, 측정 지표와 첫 A/B 시험.
- 원문의 점검 기준: 핵심 지표와 좋은 리드의 신호, 먼저 시험할 항목을 제시한다.
- 보완할 점: 전환율 기준치와 '입력 항목 하나당 5~10% 감소' 같은 수치는 본문에 출처가 없다.
- 원문: [lead-magnets SKILL.md v2.1.0](https://github.com/coreyhaines31/marketingskills/blob/1efedbc5148b54b2f0f6c6c9fe0be62e151c7fff/skills/lead-magnets/SKILL.md), Before Planning; Gating Strategy; Measuring Success; Output Format. 설치 104.0K.

```sh
npx skills add coreyhaines31/marketingskills --skill lead-magnets --agent claude-code --copy
```

```text
lead-magnets 스킬로 댓글을 남긴 사람에게 줄 무료 자료를 기획해줘. 고객은 [고객], 가장 큰 고민은 [고민], 연결할 상품은 [상품], 다시 쓸 수 있는 자료는 [기존 글·템플릿]이야. 자료 형식과 목차, 받는 방법, 측정할 지표와 첫 시험 하나를 제안해줘.
```

### B · 검색 페이지 여러 개 설계 · programmatic-seo

**추천 이유.** 데이터로 페이지 틀과 출시 전 점검까지 연결하지만, 대량 페이지를 만들 데이터와 사이트가 있어야 쓰고 품질 판단 기준은 보완해야 한다.

- 이럴 때: 지역·비교·템플릿처럼 같은 형식의 페이지를 많이 만들 데이터와 사이트가 있을 때 쓴다. 처음 마케팅을 맡은 단계에서는 쓸 상황이 적다.
- 넣을 정보: 상품·대상·전환 목표, 검색 패턴·페이지 수·검색량 분포, 경쟁 상황, 보유 데이터.
- 작업 절차: 페이지별 고유 가치와 자체 데이터 원칙에서 출발해 12가지 유형 중 하나를 고르고, 키워드 패턴·데이터 요건·템플릿·내부 링크·색인 전략·구축 플랫폼을 정한다.
- 받는 결과: 기회 분석·구현 계획·콘텐츠 지침, URL·제목·본문 개요·schema가 담긴 페이지 템플릿.
- 원문의 점검 기준: 출시 전 콘텐츠·기술·내부 링크·색인 체크리스트와 출시 후 색인율·순위·유입 관찰 항목이 있다.
- 보완할 점: 체크리스트의 품질 항목이 '고유한 가치', '읽기 쉬움'처럼 판단 기준 없이 적혀 있다.
- 원문: [programmatic-seo SKILL.md v2.1.0](https://github.com/coreyhaines31/marketingskills/blob/1efedbc5148b54b2f0f6c6c9fe0be62e151c7fff/skills/programmatic-seo/SKILL.md), Initial Assessment; Core Principles; Implementation Framework; Quality Checks; Output Format. 설치 140.5K.

```sh
npx skills add coreyhaines31/marketingskills --skill programmatic-seo --agent claude-code --copy
```

```text
programmatic-seo 스킬로 검색 페이지 묶음을 설계해줘. 반복되는 검색 패턴은 [예: 지역+서비스], 보유 데이터는 [항목과 예시 3개], 사이트와 CMS는 [사이트·도구]야. 페이지 템플릿과 페이지마다 달라지는 정보를 정하고, 샘플 3개와 출시 전 점검표를 만들어줘.
```

### B · 첫 제안 메일 쓰기 · cold-email

**추천 이유.** 받는 사람·제안·근거를 묻고 첫 메일부터 발송·답장 대응까지 안내하지만, 근거를 지어내지 않는 규칙과 최종 결과 형식은 직접 보완해야 한다.

- 이럴 때: 협업·제휴·영업 제안을 직접 보낼 때 쓴다.
- 넣을 정보: 받는 사람과 고른 이유, 원하는 결과, 제공 가치, 근거(성과·사례), 채용·투자·게시물 같은 조사 신호.
- 작업 절차: 동료처럼 쓰기, 문장마다 이유 갖기, 문제와 연결된 개인화, 작은 요청 하나를 원칙으로 상황별 구조를 고르고 짧은 제목과 3~5회 후속 메일을 설계한다.
- 받는 결과: 첫 메일과 제목, 후속 메일 방향. 별도의 출력 형식 절은 없다.
- 원문의 점검 기준: 사람이 쓴 듯한지, 내가 받으면 답할지 등 다섯 가지 확인 질문과 피할 표현 목록.
- 보완할 점: 입력이 부족해도 쓰라고 하면서 근거·개인화를 지어내지 말라는 규칙은 없다. v2.2.0에는 발송 전 목록 검증과 수신 거부 안내 등이 추가됐지만, 내 사업에 맞는 발송 조건은 따로 확인해야 한다.
- 원문: [cold-email SKILL.md v2.2.0](https://github.com/coreyhaines31/marketingskills/blob/1efedbc5148b54b2f0f6c6c9fe0be62e151c7fff/skills/cold-email/SKILL.md), Before Writing; Structure; Quality Check; What to Avoid; Before You Send; When They Reply. 설치 118.1K.

```sh
npx skills add coreyhaines31/marketingskills --skill cold-email --agent claude-code --copy
```

```text
cold-email 스킬로 [상대 회사·직무]에게 보낼 첫 제안 메일을 써줘. 이 사람을 고른 이유는 [확인한 정보], 제안은 [제안], 원하는 답은 [짧은 통화·답장], 근거는 [성과·사례]야. 제목 3안과 본문 1안을 쓰고, 내가 준 정보 밖의 사실이나 성과는 만들지 마.
```

### B · 구독 해지 대응 만들기 · churn-prevention

**추천 이유.** 구독 서비스라면 해지 이유별 대응과 결제 실패 복구·측정까지 구체적이지만, 구독 사업에서만 쓰고 목표 수치는 내 데이터로 바꿔야 한다.

- 이럴 때: 구독 서비스를 운영할 때만 해당한다.
- 넣을 정보: 해지율·구독자 수·고객당 월 매출, 결제 서비스·주기·일시정지 가능 여부, 사용 데이터·해지 이유, B2B/B2C·법적 제약.
- 작업 절차: 자발적 해지와 결제 실패를 나누고 해지 흐름(설문 → 이유별 제안 → 확인), 위험 신호·건강 점수, 결제 실패 복구(재시도·안내 메일), 지표·코호트·A/B 순서로 설계한다.
- 받는 결과: 해지 흐름과 이유별 제안, 결제 실패 안내 메일 순서, 측정 지표. 별도의 출력 형식 절은 없다.
- 원문의 점검 기준: 지표 공식과 코호트 분석, 변수 하나씩 바꾸는 A/B 시험, 해지를 숨기지 말라는 주의.
- 보완할 점: 저장률 25~35% 같은 목표 수치는 본문에 출처가 없다. 결과물 형식이 정해져 있지 않다.
- 원문: [churn-prevention SKILL.md v2.0.2](https://github.com/coreyhaines31/marketingskills/blob/1efedbc5148b54b2f0f6c6c9fe0be62e151c7fff/skills/churn-prevention/SKILL.md), Before Starting; How This Skill Works; Cancel Flow Design; Metrics & Measurement; Common Mistakes. 설치 112.1K.

```sh
npx skills add coreyhaines31/marketingskills --skill churn-prevention --agent claude-code --copy
```

```text
churn-prevention 스킬로 해지 흐름을 설계해줘. 서비스는 [구독 서비스], 결제는 [월·연, 결제 도구], 주요 해지 이유는 [이유 3개], 가능한 선택지는 [일시정지·요금 변경 등]이야. 해지 설문, 이유별 제안, 결제 실패 안내 메일 순서, 측정할 지표를 만들고 해지 버튼은 쉽게 찾을 수 있게 유지해줘.
```

### C · 설득 심리 아이디어 참고 · marketing-psychology

**추천 이유.** 설치 수는 3위지만 심리 원리 사전에 가깝고 결과 형식과 점검 기준이 없어, 다른 작업에 아이디어를 더하는 참고용으로 추천한다.

- 이럴 때: 소개글·광고의 설득 아이디어를 찾을 때 참고할 수 있다.
- 넣을 정보: 제품 마케팅 맥락. 바꾸려는 행동·고객의 믿음·구매 단계·막는 요인은 질문 목록으로 제시한다.
- 작업 절차: 적용할 모델 고르기 → 원리 설명 → 마케팅 적용 → 윤리적 실행 제안의 4단계와 약 70개 심리·사고 모델 사전.
- 받는 결과: 정해진 결과 형식이 없다.
- 원문의 점검 기준: 결과를 점검하는 기준이 없다. 희소성은 실제일 때만 쓰라는 정도의 주의가 있다.
- 보완할 점: 'Rule of 7(약 7번 접촉해야 전환)' 같은 일반화가 근거와 적용 한계 없이 적혀 있다.
- 원문: [marketing-psychology SKILL.md v2.0.0](https://github.com/coreyhaines31/marketingskills/blob/1efedbc5148b54b2f0f6c6c9fe0be62e151c7fff/skills/marketing-psychology/SKILL.md), How to Use This Skill; Quick Reference; Task-Specific Questions. 설치 153.6K.

```sh
npx skills add coreyhaines31/marketingskills --skill marketing-psychology --agent claude-code --copy
```

```text
marketing-psychology 스킬로 고객이 구매를 망설이는 이유를 분석해줘. 상품은 [상품], 바꾸고 싶은 행동은 [구매·신청], 고객의 고민은 [고민]이야. 맞는 심리 원리 3개와 이유, 소개글에 넣을 문장 예시를 주고, 실제 후기나 한정 조건이 없으면 쓰지 마.
```

예제 프롬프트는 각 원문이 먼저 묻는 정보와 결과 형식에 맞춰 만든 시작 예제입니다. `[ ]`를 실제 정보로 바꾸고, 원문이 묻는 추가 질문에 답하면 더 구체적인 결과를 받습니다.

## 선정 범위와 출처

- 후보: 2026-10-07 [skills.sh Marketing 분류](https://www.skills.sh/topic/marketing)에 표시된 21개 스킬의 개별 페이지 설치 수를 20:23 KST에 조회해 상위 10개를 골랐습니다. 11위 social-content는 67.0K였습니다. 시장 전체 순위가 아닙니다.
- 설치 수: [skills.sh FAQ](https://www.skills.sh/docs/faq#how-is-the-leaderboard-ranked)가 설명하는 CLI 설치 집계입니다. 고유 사용자 수나 업무 성과가 아닙니다.
- Stars: 10개 모두 [coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills) 저장소에 있어 Stars 53,533(2026-10-07 GitHub API)를 함께 씁니다. [GitHub 안내](https://docs.github.com/en/get-started/exploring-projects-on-github/saving-repositories-with-stars)처럼 저장소를 보관하고 제작자에게 감사를 표시하는 기능이라 스킬별 비교와 등급에는 넣지 않았습니다.
- 원문: 2026-10-10 재확인한 main 커밋 [1efedbc](https://github.com/coreyhaines31/marketingskills/tree/1efedbc5148b54b2f0f6c6c9fe0be62e151c7fff/skills)의 SKILL.md를 읽었습니다. references 폴더의 보조 문서 전체는 검토 범위에 넣지 않았습니다.
- 등급은 원문 지침과 업무 쓸모를 읽은 판단이며, 출력 품질이나 마케팅 성과를 측정한 순위가 아닙니다.
