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
  - 오전: 장 시작 전 preopen truth + 장 시작 직후 refresh
  - 마감: 장 마감 전/직후 evidence 정리
  - 장중 A는 **읽기 전용(SHADOW)**, 정책 영향 0

## Architecture (권장)
- **A만 Kiwoom OpenAPI를 직접 연결** (브로커 / 실시간 데이터 소유)
- **B와 R은 A가 만든 데이터** (예: `intraday_1m.db` 또는 A snapshot)를 읽어 계산
- 결과는 파일 / DB / 메시지로 **A가 읽음**
- 구조: **B → A ← R** (단, Kiwoom 세션은 A 단일)

## NOW
- A / 1차 단일 변수 테스트: `시가 대비 괴리율 4% 컷`
- A / 목적: `덜 잃게 하는 필터 유효성 검증`
- A / tonight hotfix scope fixed:
  - `timeout -> BLOCK` 연결 끊기
  - `_daily_ohlc_cache[key] = None` 저장 차단
  - code version / timestamp / hash 강제 기록
- A / tomorrow preopen must-have:
  - canary 1회
  - WAL 포함 evidence 수집 유지
- A / this-week separate track:
  - request_id end-to-end unification
  - state-cache transition
  - grace-timeout real use
  - repeated final-decision suppression

- B / stale structure improved
- B / same-day truth generation: `NORMAL`
- B / current focus:
  - session raw truth separation
  - ZIP automation criteria
  - AUX auto-include criteria
  - B_AM raw-log inclusion
  - raw-first evidence pack criteria
  - backlog separation rule
- B / expansion discussion in recovery-track body: `FORBIDDEN`

## NEXT
원칙:
- 완료 항목: 반드시 Evidence 포인터 포함
- 진행 중 항목: 포인터가 있으면 함께 표기
- 포인터가 없으면 완료 표시 금지

- [ ] A tonight scope ①②③ fixed in SSOT `(A#ISSUE-xx)`
- [ ] A preopen canary + WAL evidence procedure fixed `(A#ISSUE-yy)`
- [ ] A this-week structural refactor track separated `(A#ISSUE-zz)`

- [ ] B preopen / refresh / canary wording fixed `(B#ISSUE-aa)`
- [ ] B session raw truth separation rule fixed `(B#ISSUE-bb)`
- [ ] B ZIP automation / AUX / raw-first evidence pack rule fixed `(B#ISSUE-cc)`
- [ ] B backlog separation rule fixed `(B#ISSUE-dd)`

## STATUS
- A / 1차 단일 변수 테스트(4% 컷): `IN PROGRESS`
- A / tonight hotfix scope: `FIXED`
- A / preopen canary + WAL evidence: `REQUIRED`
- A / structural refactor items: `SEPARATE TRACK`

- B / stale structure: `IMPROVED`
- B / same-day truth generation: `NORMAL`
- B / evidence pack completion: `IN PROGRESS`
- B / expansion ideas in recovery-track body: `FORBIDDEN`

- overall: `IN PROGRESS`

## TODAY
원칙:
- 완료 항목: 반드시 Evidence 포인터 포함
- 진행 중 항목: 포인터가 있으면 함께 표기
- 포인터가 없으면 완료 표시 금지

- [ ] A tonight scope ①②③ fixed `(A#ISSUE-xx)`
- [ ] A preopen canary + WAL evidence procedure fixed `(A#ISSUE-yy)`
- [ ] A this-week structural refactor track separated `(A#ISSUE-zz)`

- [ ] B preopen / refresh / canary wording fixed `(B#ISSUE-aa)`
- [ ] B session raw truth separation rule fixed `(B#ISSUE-bb)`
- [ ] B ZIP automation / AUX / raw-first evidence pack rule fixed `(B#ISSUE-cc)`

## TOMORROW
- [ ] Recheck NOW / NEXT / STATUS
- [ ] Refresh evidence pointers
- [ ] Close or carry over unfinished checklist items

## LINKS
### Public SSOT
- Dashboard: [HQ_DASHBOARD.md](./HQ_DASHBOARD.md)

### Evidence Pointers
- A-System: `A#ISSUE-xx`, `A#ISSUE-yy`, `A#ISSUE-zz`
- B-System: `B#ISSUE-aa`, `B#ISSUE-bb`, `B#ISSUE-cc`, `B#ISSUE-dd`
- R-System:

## RULES
### Allowed
- Status summary
- Today / Tomorrow checklist
- System status (✅ / 🟡 / ⛔ or PASS / HOLD / DONE / IN PROGRESS)
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
- 2026-03-27: P1-D PASS close, move to A performance analysis track.
- 2026-03-27: Added B-L2(OBS-only) v0.1 schema/sample and structure-validation checklist to SSOT with evidence pointers only.
- 2026-03-28: Added Entry Cap experiment tracking and Ops Incident recurrence-prevention pointers to SSOT.
- 2026-03-28: Added B-L2 OBS-only runtime PASS pointer and AM/EOD time-separated evidence pending pointer to SSOT.
- 2026-03-30: Recorded B-L2 OBS-only runtime PASS and time-separated AM/EOD evidence completed. A/R escalation remains on hold.
- 2026-03-31: Closed Entry Cap exp1(cap=20) as implementation PASS / effect HOLD, and moved tracking to exp2(cap=12).
- 2026-04-02: A Entry Cap #2(cap=12) remains implementation PASS / effect HOLD with additional adverse evidence; B Gate observer-only evidence PASS, L2 runtime runner FAIL(Fix needed), Geo parallel observer-only track HOLD.
- 2026-04-03: A moved from Entry Cap #2 review to two-step fast test (exit first, entry later); B remains stabilization-first with Gate PASS, L2 candidate, Geo #16 HOLD.
- 2026-04-04: Added A single-variable test tracking for 4% gap-from-open cut with fixed conditions, success criteria, and auto-extension rule.
- 2026-04-09: Fixed A tonight-scope-only rule and separated this-week structural refactor items into a distinct track.
- 2026-04-09: Fixed B recording-system priorities around session raw truth, ZIP automation, AUX/raw-first evidence pack, and backlog separation.
