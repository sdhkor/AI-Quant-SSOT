# HQ Dashboard (Public SSOT)

> Public SSOT for cross-system operations.
> Scope: status summary, next actions, checklist, evidence pointers only.
> Excluded: accounts, permissions, security details, sensitive policy, raw logs, DB, private links.
> 공개 SSOT에는 민감정보/권한/원본로그/Private 링크를 기록하지 않는다.
> Evidence는 번호 포인터만 기록한다.
> SSOT 체크박스 항목은 Evidence 포인터(A#ISSUE/PR, B#ISSUE/PR, R#ISSUE/PR) 없으면 완료로 인정하지 않음.

## Operating Order (Constitution-level)
1. **P1-D (snapshot freshness) 해결** → 데이터 진실성 복구
2. **A 단독 성과 구조 1차 분석/조정** (거래 빈도 / 손익 분포 / 비용 구조)
3. **P3 (감속 ENFORCE) 아주 약하게 적용** (예: cap=0.8 / 0.6)
4. **그 다음에야 B/R 기여도 분석** (구간별 비교, 전후 비교)
5. **마지막으로 정책 조정** (리스크 / 감속 강도)

## B 운영 모드 (현재)
- **1일 2회 단기 실행(오전/마감) 유지**
  - 오전: 장 시작 후 약 10분 실행
  - 마감: 장 마감 전/직후 약 10분 실행
  - 장중 A는 **읽기 전용(SHADOW)**, 정책 영향 0

## Architecture (권장)
- **A만 Kiwoom OpenAPI를 직접 연결** (브로커 / 실시간 데이터 소유)
- **B와 R은 A가 만든 데이터** (예: `intraday_1m.db` 또는 A snapshot)를 읽어 계산
- 결과는 파일 / DB / 메시지로 **A가 읽음**
- 구조: **B → A ← R** (단, Kiwoom 세션은 A 단일)

## NOW
- Public SSOT repo / dashboard / update log 운영 중
- A-System README / START HERE linked
- B-System README / START HERE linked
- R-System README / START HERE linked
- B 운영 baseline: `1일 2회(오전/마감)`
- P1-D snapshot freshness (window-based): `DONE`
- Current A track: `Entry Cap (#1: daily entry cap=20) experiment`
- Ops Incident: `separated / minimal recurrence-prevention principles fixed`
- B-L2 Dual Engine OBS-only v0.1 runtime: `PASS`
- A 적용 / R 승격 / 행동 정책 연결: `보류 유지`

## NEXT
원칙:
- 완료 항목: 반드시 Evidence 포인터 포함
- 진행 중 항목: 포인터가 있으면 함께 표기
- 포인터가 없으면 완료 표시 금지

- [ ] A Entry Cap PR 적용 `(A#PR-xx)`
- [ ] A Entry Cap 1~3일 효과 리포트(Val) `(A#ISSUE-yy)`
- [ ] Ops Incident 재발방지(원칙 3개) 박제 `(A#ISSUE-zz)`
- [ ] B-L2 OBS-only runtime PASS `(B#ISSUE-14 / B#PR-15)`
- [ ] B-L2 time-separated AM/EOD evidence pending `(B#ISSUE-aa)`

## STATUS
- intraday_1m DB write path: `PASS 수준`
- P1-D snapshot freshness (window-based): `DONE`
- A Entry Cap experiment: `IN PROGRESS`
- Ops Incident handling: `SEPARATED`
- B-L2 OBS-only runtime: `PASS`
- A 적용 / R 승격 / 행동 정책 연결: `보류 유지`
- overall: `IN PROGRESS`

## TODAY
원칙:
- 완료 항목: 반드시 Evidence 포인터 포함
- 진행 중 항목: 포인터가 있으면 함께 표기
- 포인터가 없으면 완료 표시 금지

- [ ] A Entry Cap PR 적용 `(A#PR-xx)`
- [ ] A Entry Cap 1~3일 효과 리포트(Val) `(A#ISSUE-yy)`
- [ ] Ops Incident 재발방지(원칙 3개) 박제 `(A#ISSUE-zz)`
- [ ] B-L2 OBS-only runtime PASS `(B#ISSUE-14 / B#PR-15)`
- [ ] B-L2 time-separated AM/EOD evidence pending `(B#ISSUE-aa)`

## TOMORROW
- [ ] Recheck NOW / NEXT / STATUS
- [ ] Refresh evidence pointers
- [ ] Close or carry over unfinished checklist items

## LINKS
### Public SSOT
- Dashboard: [HQ_DASHBOARD.md](./HQ_DASHBOARD.md)

### Evidence Pointers
- A-System: `A#PR-xx`, `A#ISSUE-yy`, `A#ISSUE-zz`
- B-System: `B#ISSUE-14`, `B#PR-15`, `B#ISSUE-aa`
- R-System:

## UPDATE LOG
- 2026-03-27: P1-D PASS close, move to A performance analysis track.
- 2026-03-28: Added Entry Cap experiment tracking and Ops Incident recurrence-prevention pointers to SSOT.
- 2026-03-28: Added B-L2 OBS-only runtime PASS pointer and AM/EOD time-separated evidence pending pointer to SSOT.

## RULES
### Allowed
- Status summary
- Today / Tomorrow checklist
- System status (✅ / 🟡 / ⛔ or PASS / HOLD / DONE)
- Evidence pointer numbers only
- Example: `A#PR-12`, `B#ISSUE-7`, `R#PR-3`

### Forbidden
- Account information
- Permission information
- Security details
- Sensitive policy details
- Raw logs
- DB path/content
- Private repo links
- Credential / collaborator / ruleset related content


## UPDATE LOG
- 2026-03-20: Replaced outdated Gate3a/P2 wording with current A-System P1 intraday fail track. Evidence pointer: A#PR-8, A#ISSUE-xx
- 2026-03-23: Added P1 intraday_1m FIX/validation pointer checklist to TODAY/NEXT per HQ instruction. Evidence-only update.
- 2026-03-24: Added constitution-level Operating Order, current B operating mode (Stage A), and recommended architecture to HQ_DASHBOARD. Kept split status and evidence-pointer-only policy.
- 2026-03-25: Fixed SSOT wording to B daily-two-run mode and P1-D snapshot freshness window-based validation. Evidence-pointer-only update.
- 2026-03-26: Fixed SSOT to B daily-two-run mode and P1-D window-based validation. Kept evidence-pointer-only policy and split status.
SSOT Update Log 1줄
- 2026-03-27: P1-D PASS close, move to A performance analysis track.
- 2026-03-27: Added B-L2(OBS-only) v0.1 schema/sample and structure-validation checklist to SSOT with evidence pointers only.
- 2026-03-28: Added Entry Cap experiment tracking and Ops Incident recurrence-prevention pointers to SSOT.
- 2026-03-28: Added B-L2 OBS-only runtime PASS pointer and AM/EOD time-separated evidence pending pointer to SSOT.
