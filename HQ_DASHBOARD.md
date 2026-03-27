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

## P1-D 판정 기준 (고정)
- **snapshot freshness는 연속 freshness가 아니라 window-based로 판정**
- 오전 창(B 실행 직후):
  - A가 최신 snapshot을 읽음 (`snapshot_ts` 당일 갱신)
  - `snapshot_age_sec` 정상 범위 회복
  - 창 직후 stale 지속/반복 시 FAIL
- 마감 창(B 실행 직후):
  - A가 최신 snapshot을 다시 읽음 (`snapshot_ts` 재갱신)
  - `snapshot_age_sec` 정상 범위 회복
- 두 창 사이 시간대의 age 증가 / stale 진입은 운영모드상 허용
- P1-D(window-based): ✅ DONE `(A#ISSUE-pass)`

## B 운영 모드 (현재)
- **1일 2회 단기 실행(오전/마감) 유지**
  - 오전: 장 시작 후 약 10분 실행
  - 마감: 장 마감 전/직후 약 10분 실행
  - 장중 A는 읽기 전용(SHADOW), 정책 영향 0
- B 운영: `1일 2회(오전/마감)`
- P1-D freshness: `window-based 판정`
- overall: `HOLD`
- TODAY/NEXT: `오전 창 검증`, `마감 창 검증` 포인터만 유지

## Architecture (권장)
- **A만 Kiwoom OpenAPI를 직접 연결** (브로커 / 실시간 데이터 소유)
- **B와 R은 A가 만든 데이터** (예: `intraday_1m.db` 또는 A snapshot)를 읽어 계산
- 결과는 파일 / DB / 메시지로 **A가 읽음**
- 구조: **B → A ← R** (단, Kiwoom 세션은 A 단일)

## NOW
- B 운영: `1일 2회(오전/마감)` baseline 유지
- P1-D(window-based): `DONE`
- Next track: `A 단독 성과 구조 1차 분석/조정`
- Strategy / policy change: `HOLD until analysis`

## NEXT
- [ ] A 단독 성과 구조 1차 분석 리포트(Val) `(A#ISSUE-xx)`
- [ ] A 성과 구조 기반 “최소 조정안” 제안(HQ 판단용) `(A#ISSUE-yy)`
- [ ] B-L2(OBS-only) v0.1 스키마/샘플 제출 `(B#PR-xx 또는 B#ISSUE-yy)`
- [ ] B-L2(OBS-only) 구조 검증 판정(Val) `(B#ISSUE-zz)`

## STATUS
- intraday_1m DB write path: `PASS 수준`
- P1-D snapshot freshness (window-based): `DONE`
- overall: `PASS`

## TODAY
- [ ] A 단독 성과 구조 1차 분석 리포트(Val) `(A#ISSUE-xx)`
- [ ] A 성과 구조 기반 “최소 조정안” 제안(HQ 판단용) `(A#ISSUE-yy)`
- [ ] B-L2(OBS-only) v0.1 스키마/샘플 제출 `(B#PR-xx 또는 B#ISSUE-yy)`
- [ ] B-L2(OBS-only) 구조 검증 판정(Val) `(B#ISSUE-zz)`

### Evidence Pointers
- A-System: `A#ISSUE-xx`, `A#ISSUE-yy`
- B-System:
- R-System:

## LINKS
### Public SSOT
- Dashboard: [HQ_DASHBOARD.md](./HQ_DASHBOARD.md)

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

## UPDATE LOG
- 2026-03-20: Replaced outdated Gate3a/P2 wording with current A-System P1 intraday fail track. Evidence pointer: A#PR-8, A#ISSUE-xx
- 2026-03-23: Added P1 intraday_1m FIX/validation pointer checklist to TODAY/NEXT per HQ instruction. Evidence-only update.
- 2026-03-24: Added constitution-level Operating Order, current B operating mode (Stage A), and recommended architecture to HQ_DASHBOARD. Kept split status and evidence-pointer-only policy.
- 2026-03-25: Fixed SSOT wording to B daily-two-run mode and P1-D snapshot freshness window-based validation. Evidence-pointer-only update.
- 2026-03-26: Fixed SSOT to B daily-two-run mode and P1-D window-based validation. Kept evidence-pointer-only policy and split status.
SSOT Update Log 1줄
- 2026-03-27: P1-D PASS close, move to A performance analysis track.
- 2026-03-27: Added B-L2(OBS-only) v0.1 schema/sample and structure-validation checklist to SSOT with evidence pointers only.
