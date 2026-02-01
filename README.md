# Interview QA Plugin for Claude Code

기술 면접 준비를 위한 QA 자동 생성 플러그인입니다.

프로젝트 코드를 분석하여 CS 기초, 아키텍처, 보안, 성능 관련 면접 질문과 모범 답변을 자동으로 생성합니다.

## 설치

```bash
/plugin install interview-qa@ekgp4949
```

## 명령어

### `/interview-qa` - QA 자동 생성

세션 내용이나 프로젝트를 분석하여 기술 면접용 QA를 생성합니다.

#### 기본 사용법

```bash
/interview-qa                    # 현재 세션 전체 분석
/interview-qa "React hooks"      # 특정 주제만 분석
/interview-qa "인증 구현"
```

#### 옵션

| 옵션 | 설명 | 예시 |
|------|------|------|
| (없음) | 현재 세션의 모든 대화와 작업 분석 | `/interview-qa` |
| `"주제"` | 지정한 주제와 관련된 내용만 분석 | `/interview-qa "상태 관리"` |
| `--last` | 가장 최근 작업만 분석 | `/interview-qa --last` |
| `--file` | 특정 파일과 관련된 내용 분석 | `/interview-qa --file src/auth.ts` |
| `--project` | 프로젝트 전체 구조 분석 | `/interview-qa --project` |
| `--project <경로>` | 특정 경로만 분석 | `/interview-qa --project src/` |

#### 사용 예시

```bash
# 방금 구현한 기능에 대한 QA 생성
/interview-qa --last

# 인증 모듈 파일 기반 QA 생성
/interview-qa --file src/services/auth.ts

# 프로젝트 전체 아키텍처 QA 생성
/interview-qa --project

# src 폴더만 분석하여 QA 생성
/interview-qa --project src/
```

---

### `/interview-prep` - 면접 도메인 지식 로드

면접 준비에 필요한 핵심 개념과 답변 전략을 로드합니다.

#### 사용법

```bash
/interview-prep
```

#### 포함 내용

- **질문 유형별 답변 구조**: 개념 설명형, 비교형, 문제 해결형, 경험 기반형, 설계형
- **카테고리별 핵심 개념**: CS 기초, 아키텍처(SOLID, 디자인 패턴), 보안(OWASP), 성능
- **난이도별 예상 질문**: 주니어/미들/시니어
- **면접 팁**: DO와 DON'T

#### 활용 예시

```bash
# 면접 준비 지식 로드 후 특정 주제 질문
/interview-prep
> "이벤트 루프에 대해 면접에서 어떻게 설명하면 좋을까요?"

# STAR 기법으로 경험 정리
/interview-prep
> "OAuth 구현 경험을 STAR 기법으로 정리해주세요"
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
