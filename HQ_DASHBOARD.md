# HQ Dashboard (Public SSOT)

> Public SSOT for cross-system operations.
> Scope: status summary, next actions, checklist, evidence pointers only.
> Excluded: accounts, permissions, security details, sensitive policy, raw logs, DB, private links.
> 공개 SSOT에는 민감정보/권한/원본로그/Private 링크를 기록하지 않는다. Evidence는 번호 포인터만 기록한다.
> SSOT 체크박스 항목은 Evidence 포인터(A#ISSUE/PR, B#ISSUE/PR, R#ISSUE/PR) 없으면 완료로 인정하지 않음.

## NOW
- Public SSOT repo / dashboard / update log 운영 중
- A-System README / START HERE linked
- B-System README / START HERE linked
- R-System README / START HERE linked
- P1(Gate3a: SHADOW) 마감 증거 패키징 진행
- P2 착수 준비: strong_set 입력 검증 이슈 생성 예정(관측/로그만)
  
## NEXT
원칙:
- 완료 항목: 반드시 `(A#ISSUE-.. / B#ISSUE-.. / R#PR-..)` 포인터 포함
- 진행 중 항목: 포인터가 있으면 함께 표기
- 포인터가 없으면 완료 표시 금지

- [ ] P1(Gate3a: SHADOW) 마감 증거를 Issue 1개로 정리
- [ ] P2 준비용 strong_set 입력 검증 이슈 생성
- [ ] TODAY 체크리스트 상태 갱신 및 Update Log 코멘트 기록

## STATUS
- A-System: ✅
- B-System: ✅
- R-System: ✅
- PM-Ops: 🟡

## TODAY
원칙:
- 완료 항목: 반드시 `(A#ISSUE-.. / B#ISSUE-.. / R#PR-..)` 포인터 포함
- 진행 중 항목: 포인터가 있으면 함께 표기
- 포인터가 없으면 완료 표시 금지
  
- [x] Create HQ_DASHBOARD.md
- [x] Pin SSOT link in A-System README
- [x] Pin SSOT link in B-System README
- [x] Pin SSOT link in R-System README
- [x] Pin SSOT link in A-System START HERE issue
- [x] Pin SSOT link in B-System START HERE issue
- [x] Pin SSOT link in R-System START HERE issue
- [ ] P1(Gate3a: SHADOW) 마감 증거 확보: **B 장중 갱신 1회 + A 장중 재로드 1회**(snapshot_age 회복) 로그/mtime 증거를 Issue 1개로 정리
- [ ] P2 준비(센서 고정 원인): **strong_set 입력 검증 이슈 생성**(종목 수/샘플 출력, intraday 최신 timestamp, builder 필터 조건 점검) — 의미 변경 금지(관측/로그만)

## TOMORROW
- [ ] Recheck NOW / NEXT / STATUS
- [ ] Refresh evidence pointers
- [ ] Close or carry over unfinished checklist items

## LINKS
### Public SSOT
- Dashboard: [HQ_DASHBOARD.md](./HQ_DASHBOARD.md)

### Evidence Pointers
- A-System: A#PR- , A#ISSUE- , A#REPORT-
- B-System: B#PR- , B#ISSUE- , B#REPORT-
- R-System: R#PR- , R#ISSUE- , R#REPORT-

## RULES
### Allowed
- Status summary
- Today / Tomorrow checklist
- System status (✅/🟡/⛔)
- Evidence pointer numbers only
  - Example: A#PR-12, B#ISSUE-7, R#PR-3

### Forbidden
- Account information
- Permission information
- Security details
- Sensitive policy details
- Raw logs
- DB path/content
- Private repo links
- Credential / collaborator / ruleset related content
