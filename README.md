# AI seonbi · 디자인 작업 스킬

원하는 느낌은 있는데 말로 설명하기 어렵다면, AI에게 참고할 디자인을 찾고 같은 내용의 여러 시안을 보여 달라고 요청하세요. 사람은 눈으로 보고 고르고, AI는 수정과 기록을 돕습니다.

이번 제작 과정을 다시 쓸 수 있도록 정리한 무료 배포판 `design-guide`입니다.

공식 자료 안내: https://ai-seonbi.github.io/skills/design-guide/

## 처음이라면

1. [사용하는 AI 도구별 시작 방법](guides/start-here.md)을 고릅니다.
2. [전체 자료 ZIP](https://github.com/ai-seonbi/skills/releases/download/v0.1.0/ai-design-guide.zip)을 받습니다. 스킬·가이드·실제 요청·비교 이미지가 들어 있습니다.
3. [첫 요청 예시](skills/design-guide/references/request-examples.md)로 나의 작업을 시작합니다.

설치 전에 [대화로 먼저 체험](guides/try-in-chat.md)할 수도 있습니다. Claude 앱에는 [스킬 전용 ZIP](https://github.com/ai-seonbi/skills/releases/download/v0.1.0/design-guide-v0.1.0.zip)을 사용하세요. 앱별 지원·검증 범위는 시작 가이드에 적었습니다.

## 터미널에서 설치

작업할 프로젝트 폴더에서 사용하는 도구의 명령 하나를 실행하세요.

```sh
# Codex
npx skills add ai-seonbi/skills --skill design-guide --agent codex --copy

# Claude Code
npx skills add ai-seonbi/skills --skill design-guide --agent claude-code --copy
```

설치 뒤 Codex에서는 `$design-guide`, Claude Code에서는 `/design-guide`로 요청합니다. 기존 동명 스킬이 있으면 덮어쓰기 전에 비교하세요. 명령은 외부 skills CLI를 사용하며, 앱 업로드용 명령과는 다릅니다.

## 무엇을 하나요?

참고 디자인 조사 → 같은 내용의 시안 비교 → 사람이 선택 → 유지할 것과 바꿀 것을 나눠 수정 → 확정한 기준 기록.

[스킬 원문](skills/design-guide/SKILL.md)과 [실제 비교·수정 예시](examples/README.md)를 공개합니다. 제작 당시 개인 설정 전체를 복사한 것이 아니며, 같은 결과물을 보장하지 않습니다. 예시의 실제 제작 자료와 설명용 재현 범위도 구분했습니다.

버전별 파일과 SHA-256 체크섬은 [Releases](https://github.com/ai-seonbi/skills/releases)에서 확인할 수 있습니다.
