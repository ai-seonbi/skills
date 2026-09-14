# design-guide: 사용하는 AI 도구부터 고르세요

이 자료는 디자인을 찾고, 비교하고, 고르고, 기록하는 작업 순서를 담았습니다. AI 모델이나 이미지 생성 서비스를 설치하는 파일은 아닙니다. 같은 그림을 보장하지 않으며, 시안 선택과 피드백은 사람이 합니다.

## 무엇을 받으면 되나요?

아래 `v0.1.0` ZIP은 당시 배포한 한국어 본문을 보존합니다. [터미널 설치](#터미널에서-설치하기)는 현재 `main`의 영어 스킬 지침과 참조 문서를 받습니다. 두 경로는 배포 버전과 문서 언어가 다릅니다. 이 페이지의 [첫 작업 요청](#첫-작업-요청)은 한국어로 제공됩니다.

- 스킬·설명·실제 예시를 함께 보려면 [전체 자료 ZIP](https://github.com/ai-seonbi/skills/releases/download/v0.1.0/ai-design-guide.zip)을 받으세요.
- Claude 앱에 올리려면 [스킬 전용 ZIP](https://github.com/ai-seonbi/skills/releases/download/v0.1.0/design-guide-v0.1.0.zip)을 받으세요. 전체 자료 ZIP과 다릅니다.
- 설치 없이 먼저 해보려면 [대화용 체험 지침](try-in-chat.md)을 사용하세요.

2026-09-12 공식 문서의 경로를 확인했고, skills CLI 1.5.25로 임시 프로젝트에 Codex·Claude Code용 파일을 설치해 원본과 일치하는지 검사했습니다. 각 제품을 열어 자동 발견·호출하는 과정과 Claude·ChatGPT 앱 업로드는 아직 검증하지 않았습니다. 에이전트가 지침을 직접 읽고 만든 비교 시연은 별도입니다.

## Claude 앱

1. 현재 계정의 `Settings > Capabilities`에서 코드 실행·파일 생성이 활성화돼 있는지 확인합니다. 조직 계정은 관리자 설정이 적용될 수 있습니다.
2. `Customize > Skills > + > Create skill > Upload a skill`을 엽니다.
3. 스킬 전용 `design-guide-v0.1.0.zip`을 업로드하고 켭니다. ZIP 안의 구조는 `design-guide/SKILL.md`와 `design-guide/references/`입니다.
4. 새 작업에서 ‘design-guide 스킬로 아래 작업을 진행해줘’라고 요청합니다.

메뉴가 없으면 현재 계정 설정을 [Claude 공식 안내](https://support.claude.com/en/articles/12512180-use-skills-in-claude)와 대조하세요. 설치가 안 된 상태에서 파일 첨부만으로 스킬 설치가 완료됐다고 보지는 않습니다.

## Claude Code

전체 자료 ZIP을 풀고 `skills/design-guide` 폴더 전체를 작업 프로젝트의 `.claude/skills/` 아래에 복사합니다. Finder에서 숨김 파일은 `Command + Shift + .`로 표시할 수 있습니다.

```text
내-프로젝트/
└── .claude/skills/design-guide/
    ├── SKILL.md
    └── references/
```

그 프로젝트에서 Claude Code를 열고 `/design-guide`로 시작합니다. 원래 같은 이름의 폴더가 있으면 덮어쓰지 말고 먼저 비교하세요. [Claude Code 공식 문서](https://code.claude.com/docs/en/skills).

## Codex CLI·IDE

전체 자료에서 같은 `design-guide` 폴더를 프로젝트의 `.agents/skills/` 아래에 복사합니다.

```text
내-프로젝트/
└── .agents/skills/design-guide/
    ├── SKILL.md
    └── references/
```

해당 프로젝트의 Codex에서 `/skills` 목록을 확인하고 `$design-guide`로 작업을 요청합니다. 보이지 않으면 프로젝트 위치와 폴더 구조를 확인하고 Codex를 다시 시작합니다. [OpenAI 공식 스킬 안내](https://learn.chatgpt.com/docs/build-skills).

## 터미널에서 설치하기

작업할 프로젝트 폴더에서 사용하는 도구에 맞는 명령 하나를 실행하세요. 기존 동명 스킬이 있으면 먼저 비교하세요.

```sh
# Codex
npx skills add ai-seonbi/skills --skill design-guide --agent codex --copy

# Claude Code
npx skills add ai-seonbi/skills --skill design-guide --agent claude-code --copy
```

`skills add`는 [외부 설치 도구](https://github.com/vercel-labs/skills)입니다. ChatGPT·Claude 앱에 자동으로 업로드하지 않습니다. 터미널이 익숙하지 않으면 위의 폴더 복사 방식이나 [대화 체험](try-in-chat.md)을 사용하세요.

## ChatGPT

OpenAI는 ChatGPT 데스크톱의 독립형 Skills와 플러그인에 포함된 Skills를 안내합니다. Skills 메뉴가 보이면 현재 앱의 추가 경로를 따르고 `@` 선택기에서 사용할 스킬을 확인하세요. 이 배포 ZIP의 실제 업로드 형식·계정 자격은 확인 전이므로 Claude용 ZIP을 그대로 올리면 된다고 안내하지 않습니다. [공식 스킬 안내](https://learn.chatgpt.com/docs/build-skills).

메뉴가 없거나 먼저 체험하려면 [대화용 지침](try-in-chat.md)을 새 대화에 붙여 넣으세요. Project를 사용할 수 있다면 지침과 관련 파일을 프로젝트에 둘 수도 있습니다. 이 방식은 네이티브 Skill 설치와 다릅니다. [공식 Projects 안내](https://learn.chatgpt.com/docs/projects).

## 첫 작업 요청

```text
이 디자인 가이드로 [만들 것]을 디자인해줘.
보는 사람은 [대상], 전달할 내용은 [내용].
원하는 느낌은 [방향]이고, 꼭 유지할 것은 [조건]이야.

참고할 디자인과 적용할 부분부터 정리해줘.
같은 내용의 서로 다른 시안을 눈으로 비교할 수 있게 보여줘.
내가 고르기 전에는 하나로 확정하지 마.
```

원하는 느낌이 불명확해도 괜찮습니다. 만들 것과 보는 사람부터 알려주세요. 다음에는 ‘B로 할게. 색은 그대로 두고 제목만 더 크게. 전후를 나란히 보여줘’처럼 유지할 것과 바꿀 것을 함께 말합니다.

결정 뒤에는 ‘고른 안과 수정 내용을 기록해줘. 다음 작업을 시작할 때 그 기록부터 읽어줘’라고 요청하세요. 파일을 저장할 수 없는 채팅에서는 기록을 복사해 직접 보관하고 다음 대화에 넣습니다.
