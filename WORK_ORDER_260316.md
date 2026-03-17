# Work Order 260316 — SSOT ↔ Evidence 1:1

RAW:
https://raw.githubusercontent.com/sdhkor/AI-Quant-SSOT/refs/heads/main/WORK_ORDER_260316.md

BROWSER:
https://github.com/sdhkor/AI-Quant-SSOT/blob/main/WORK_ORDER_260316.md

> Canonical doc (public raw .md)
> Public에는 운영 현황/행동 요약/Evidence 번호 포인터만 기록한다.
> 전략/정책 상세/원본 로그/권한/Private 링크는 기록하지 않는다.

## SSOT
- Latest (raw): https://raw.githubusercontent.com/sdhkor/AI-Quant-SSOT/main/HQ_DASHBOARD.md
- Browser: https://github.com/sdhkor/AI-Quant-SSOT/blob/main/HQ_DASHBOARD.md

## 목적
- 각 시스템 대화창에 긴 지시를 반복 복붙하지 않는다.
- 이번 작업의 기준 순서와 완료 인정 기준을 고정한다.
- SSOT ↔ Evidence 1:1 연결 규칙에 따라 완료 판단한다.

---

## 운영 원칙
1. SSOT 체크박스 항목은 Evidence 포인터 없으면 완료로 인정하지 않음
2. Public SSOT에는 민감정보/권한/원본로그/Private 링크 금지
3. Evidence는 번호 포인터만 기록
   - 예: `A#ISSUE-21`, `B#ISSUE-10`, `R#PR-16`
4. 원본 증거는 각 private repo의 Issue/PR에만 둠
5. 포인터 없는 완료 보고는 무효

---

## 다음 진행 순서

### 1) P1 마감 증거 Issue 생성/정리
목표:
- B 장중 갱신 1회
- A 장중 재로드 1회
- snapshot_age 회복 / mtime / 관련 로그를 private Issue 1개 또는 연결된 2개 Issue로 정리

필수:
- A-System Evidence 번호 확보
- B-System Evidence 번호 확보

완료 인정 조건:
- SSOT TODAY 항목에 실제 번호 포인터 반영

예시:
- `A#ISSUE-xx`
- `B#ISSUE-yy`

---

### 2) P2 준비용 strong_set 입력 검증 Issue 생성
목표:
- 의미 변경 금지
- 관측/로그만 수행
- 아래 3가지를 private Issue 1개에 기록
  - 종목 수 / 샘플 출력
  - intraday 최신 timestamp
  - builder 필터 조건 점검

필수:
- B-System private Issue 번호 확보

완료 인정 조건:
- SSOT TODAY/NEXT 항목에 실제 포인터 번호 반영

예시:
- `B#ISSUE-zz`

---

### 3) PM-Ops 작업
- 실제 번호 수신 후 `HQ_DASHBOARD.md`의 placeholder 포인터를 실제 번호로 교체
- 예:
  - `P1 freshness 증거 확보 (A#ISSUE-21, B#ISSUE-18)`
  - `P2 strong_set 입력 검증 이슈 생성 (B#ISSUE-19)`
- 실제 번호 없는 항목은 `[x]`로 바꾸지 않음

---

### 4) Update Log 기록
- `SSOT Update Log`에 변경 기록 코멘트 1개 추가
- 기록 내용:
  - 무엇을 바꿨는지
  - 어떤 포인터가 연결됐는지
  - 리스크(없으면 없음)

---

## 역할별 즉시 액션

### A-System Dev / Val
- P1 관련 private Issue 생성/업데이트
- 장중 재로드 / snapshot_age 회복 / mtime 증거 정리
- PM-Ops에 `A#ISSUE-번호` 전달

### B-System Dev / Val
- P1 관련 private Issue 생성/업데이트
- 장중 갱신 증거 정리
- P2 strong_set 입력 검증용 private Issue 생성
- PM-Ops에 `B#ISSUE-번호` 전달

### R-System
- 현재 단계는 참고만
- 별도 SSOT 포인터 추가가 생기면 `R#PR-번호` 또는 `R#ISSUE-번호` 전달

### PM-Ops
- 실제 번호 수신 후 `HQ_DASHBOARD.md` 갱신
- `SSOT Update Log` 코멘트 기록
- HQ에 최소형 완료 보고

---

## 완료 인정 기준
아래 3개가 모두 있어야 완료로 인정:
1. private Issue/PR 존재
2. SSOT에 실제 번호 포인터 연결
3. Update Log 기록 완료

---

## Reference
- Roles Fixed: https://raw.githubusercontent.com/sdhkor/AI-Quant-SSOT/refs/heads/main/ROLES_FIXED_v1_0.md
- Comment Rules: https://raw.githubusercontent.com/sdhkor/AI-Quant-SSOT/refs/heads/main/COMMENT_RULES_v1_0.md
