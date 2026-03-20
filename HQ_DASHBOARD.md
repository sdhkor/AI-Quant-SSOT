# HQ Dashboard (Public SSOT)

> Public SSOT for cross-system operations.
> Scope: status summary, next actions, checklist, evidence pointers only.
> Excluded: accounts, permissions, security details, sensitive policy, raw logs, DB, private links.
> 공개 SSOT에는 민감정보/권한/원본로그/Private 링크를 기록하지 않는다.
> Evidence는 번호 포인터만 기록한다.
> SSOT 체크박스 항목은 Evidence 포인터(A#ISSUE/PR, B#ISSUE/PR, R#ISSUE/PR) 없으면 완료로 인정하지 않음.

## NOW
- Public SSOT repo / dashboard / update log 운영 중
- A-System P1 intraday_1m main/opsafe: `FAIL / Fix needed`
- Goal: find break point `(P1-A~D)` within 1 trading day
- Strategy/profit discussion: `HOLD`
- Ops rules/docs expansion: `FREEZE`

## NEXT
- [ ] Dev Fix PR 생성 및 포인터 연결 `(A#PR-xx)`
- [ ] Val Validation Issue 생성 및 포인터 연결 `(A#ISSUE-yy)`
- [ ] P1-A~D 중 실제 단절 지점 확정 `(A#ISSUE-yy)`
- [ ] TODAY / STATUS / Evidence pointer 갱신

## STATUS
- A-System: ⚠️ `FAIL / Fix needed`
- B-System: HOLD
- R-System: HOLD
- PM-Ops: tracking / pointer update only

## TODAY
- [ ] `P1 intraday_1m main/opsafe: FAIL / Fix needed` 반영
- [ ] `Goal: find break point (P1-A~D)` 반영
- [ ] Evidence pointer 갱신
- [ ] Update log 코멘트 기록

## LINKS
### Public SSOT
- Dashboard: [HQ_DASHBOARD.md](./HQ_DASHBOARD.md)

### Evidence Pointers
- A-System: `A#PR-xx`, `A#ISSUE-yy`
- B-System:
- R-System:

## RULES
### Allowed
- Status summary
- Today / Next checklist
- System status
- Evidence pointer numbers only

### Forbidden
- Account information
- Permission information
- Security details
- Sensitive policy details
- Raw logs
- DB path/content
- Private repo links
- Credential / collaborator / ruleset related content
