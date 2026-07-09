# like-fable

Claude Fable 5 (Mythos 클래스)가 하위 티어 모델 대비 실제로 잘하는 것들을,
에이전트가 따를 수 있는 작업 규율 skill 로 정리한 문서.

핵심 한 줄: **"더 똑똑하게"가 아니라 "더 오래 안 흐트러지게".**

## 무엇인가

길고 모호하고 제약 많은 작업(멀티파일 디버깅, 대규모 리팩토링, 모호한 버그 리포트)에서
에이전트가 지켜야 할 8가지 원칙:

| # | 원칙 | 한 줄 |
|---|------|-------|
| 1 | 추론 체인 유지 | 가설 장부를 잃지 마라 |
| 2 | 근본 원인 | "왜 이 상태가 됐나" 한 단계 더 |
| 3 | 초반 제약 유지 | 결정된 건 재논의 금지 |
| 4 | 재현 조건 우선 | 실험 하나 > 추측 열 개 |
| 5 | 캘리브레이션 | 모르면 모른다 |
| 6 | 제약 전수 준수 | 3개 중 2개 = 0점 |
| 7 | 위임 판단 | 직접/병렬/위임 구분 |
| 8 | 코드 판단력 | 최소 diff, 관례 우선 |

전체 내용은 [SKILL.md](./SKILL.md) 참고.

## 설치

### Claude Code

```bash
mkdir -p ~/.claude/skills/like-fable
cp SKILL.md ~/.claude/skills/like-fable/SKILL.md
```

### Codex CLI

```bash
mkdir -p ~/.codex/skills/like-fable
cp SKILL.md ~/.codex/skills/like-fable/SKILL.md
```

SKILL.md 는 도구 중립적으로 작성되어 두 환경 모두 그대로 동작한다.

## 사용

자동 트리거 없음 — 명시적으로 실행할 때만 적용된다:

- Claude Code: `/like-fable`
- Codex CLI: `$like-fable`

Claude Code 는 `disable-model-invocation: true` 프론트매터로 자동 실행을 차단하고,
Codex 는 description 의 명시 실행 전용 문구로 방어한다.

## 출처

Claude Fable 5 와의 Opus 비교 대화에서 추출 (2026-07-09).
공식 스펙: https://www.anthropic.com/news/claude-fable-5-mythos-5
