# Interview QA Plugin for Claude Code

기술 면접 준비를 위한 QA 자동 생성 플러그인입니다.

프로젝트 코드를 분석하여 CS 기초, 아키텍처, 보안, 성능 관련 면접 질문과 모범 답변을 자동으로 생성합니다.

## 설치

```bash
/plugin install dhk/interview-qa-plugin
```

## 사용법

```bash
# 현재 세션 전체 분석
/interview-qa

# 특정 주제 지정
/interview-qa "React hooks"
/interview-qa "인증 구현"

# 프로젝트 전체 구조 분석
/interview-qa --project

# 특정 파일 관련
/interview-qa --file src/auth.ts
```

## 생성되는 QA 카테고리

| 카테고리 | 분석 내용 |
|----------|----------|
| CS 기초 | 자료구조, 알고리즘, 복잡도, 메모리 |
| 아키텍처 | 디자인 패턴, SOLID, 시스템 설계 |
| 보안 | OWASP, 인증/인가, 암호화 |
| 성능 | 캐싱, 최적화, 비동기 처리 |
| 언어/FW | 사용된 언어/프레임워크 특화 질문 |

## 출력 위치

생성된 QA 파일은 `~/Desktop/QA/` 폴더에 저장됩니다.

```
~/Desktop/QA/YYYYMMDD_HHMMSS_프로젝트명_주제.md
```

예시:
- `20260125_143052_my-project_React_상태관리.md`
- `20260125_150000_backend-api_인증_시스템.md`

## 포함된 구성요소

| 유형 | 파일 | 설명 |
|------|------|------|
| Command | `interview-qa.md` | `/interview-qa` 명령어 |
| Agent | `qa-generator.md` | QA 생성 전문 에이전트 |
| Skill | `interview-prep/SKILL.md` | 면접 준비 도메인 지식 |
| Rule | `qa-guidelines.md` | QA 작성 가이드라인 |

## 라이선스

MIT
