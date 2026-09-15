# Contributing Guide

이 문서는 navi-project (fe / be / ai) 레포에서 공통으로 지키는 개발 규칙을 정리한 문서입니다.
세 레포 모두 동일한 규칙을 따릅니다.

## 1. 커밋 메시지 규칙

[Conventional Commits](https://www.conventionalcommits.org/) 형식을 따르고, **영어**로 작성합니다.

```
타입: 설명
```

### 사용 타입

| 타입 | 언제 쓰나 |
|---|---|
| `feat` | 새로운 기능 추가 |
| `fix` | 버그 수정 |
| `docs` | 문서만 변경 (README, 주석 등) |
| `refactor` | 기능 변화 없이 코드 구조만 개선 |
| `test` | 테스트 코드 추가/수정 |
| `chore` | 빌드 설정, 패키지, 프로젝트 세팅 등 |

### 작성 원칙

- 한 커밋 = 한 가지 작업 (여러 작업을 섞지 않기)
- 동사 원형으로 시작 (`add`, `fix`, `update` — `added`, `fixed` 아님)
- 타입 뒤 설명은 소문자로 시작
- 끝에 마침표 없음

### 예시

```
feat: add Gmail unread list API
fix: correct timezone bug in calendar sync
docs: add API contract guide to README
refactor: split CalendarService into smaller functions
test: add unit tests for mail summarizer
chore: set up initial project structure
```

## 2. 브랜치 이름 규칙

```
feature/기능명     예: feature/login-ui
fix/버그명         예: fix/calendar-crash
docs/문서명        예: docs/api-contract
```

## 3. 작업 흐름

1. `main`에서 새 브랜치 생성
   ```bash
   git checkout main
   git pull
   git checkout -b feature/기능명
   ```
2. 작업 후 커밋 (위 커밋 규칙 준수)
3. 브랜치 push
   ```bash
   git push -u origin feature/기능명
   ```
4. GitHub에서 Pull Request 생성 → 리뷰 요청 → merge

> `main`에 직접 push하지 않습니다. 단, 프로젝트 초기 세팅 단계에서는 예외로 허용합니다.

## 4. API 계약 관리

- FE-BE-AI 간 API는 각 레포의 `Contracts/` (또는 `contracts/`) 폴더에 OpenAPI 스펙(`openapi.yaml`)으로 관리합니다.
- 새 API를 추가하거나 변경할 때는 코드 작성 전에 계약 파일부터 업데이트합니다.
