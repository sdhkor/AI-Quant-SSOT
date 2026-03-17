# Roles Fixed v1.0 (Dev / Val / PM-Ops / HQ) — Constitution-level

RAW:
https://raw.githubusercontent.com/sdhkor/AI-Quant-SSOT/refs/heads/main/ROLES_FIXED_v1_0.md

BROWSER:
https://github.com/sdhkor/AI-Quant-SSOT/blob/main/ROLES_FIXED_v1_0.md

> Canonical doc (public raw .md)
> Public에는 운영 현황/행동 요약/Evidence 번호 포인터만 기록한다.
> 전략/정책 상세/원본 로그/권한/Private 링크는 기록하지 않는다.

목적:
- Dev/Val 역할 모호성 제거
- 산출물(Artifacts)로 역할을 강제: Dev=CHANGE, Val=VERDICT
- SSOT↔Evidence 1:1 규칙과 결합해 드리프트/감사 리스크 제거

---

## 1) Dev (Developer) — produces CHANGE

정체성:
Dev는 “변경(CHANGE)”를 만든다.

Dev가 하는 일:
- 코드/설정/문서/관측 로그/리포트 생성 로직 등 변경 제작
- 브랜치 생성 → 커밋 → PR 생성/수정

Dev 금지:
- PASS/FAIL 판정 금지
- “Gate 완료/보류” 결론 선언 금지
- ruleset/권한 변경 실행 금지(필요 시 HQ 상신만)

Dev 필수 산출물(DoD):
- PR 1개
- PR 본문 3줄:
  - 무엇
  - 근거(테스트·로그)
  - 리스크(영향·롤백)

---

## 2) Val (Validation) — produces VERDICT

정체성:
Val은 “판정(VERDICT)”을 만든다.

Val이 하는 일:
- PR 리뷰(코드 변경 없이)
- 검증 실행/재현/리포트 작성
- Gate 판정: PASS / FAIL / HOLD(보류)

Val 금지:
- 기능/로직 코드 변경 금지(프로덕션 로직 금지)
- (예외) 테스트 전용 파일/검증 스크립트는 가능하나 기능/의미 변경 금지

Val 필수 산출물(DoD):
- Validation Issue 1개(private repo)
- 최소 5요소:
  1. 검증 대상(PR/commit/run_id)
  2. 체크리스트
  3. 결과(증거 링크/파일 경로)
  4. 판정(PASS/FAIL/HOLD)
  5. 다음 액션(필요 증거 1~3개)

---

## 3) PM-Ops — produces LINK/STATUS (no decisions)

PM-Ops가 하는 일:
- SSOT(NOW/NEXT/STATUS/TODAY) 갱신
- 링크/번호/퍼머링크 정리
- 일정/체크리스트 운영

PM-Ops 금지:
- 정책 판단
- 승인 결정
- ruleset/권한 변경 실행

---

## 4) HQ (Human) + HQ Proxy (assistant)

최종결정권:
- HQ(사용자)

HQ Proxy(assistant):
- 쟁점/선택지/리스크 정리
- 사용자 최종결정 확인
- 지시문 발행

---

## 5) SSOT ↔ Evidence 1:1 강제 (상시)

- SSOT 체크박스 항목은 Evidence 포인터 없으면 완료로 인정하지 않음
- Public SSOT에는 민감정보/원본로그/Private 링크 금지
- Evidence는 번호 포인터만:
  - A#ISSUE/PR
  - B#ISSUE/PR
  - R#ISSUE/PR
- 원본 증거는 private repo Issue/PR에만 저장

권장 체인:
SSOT 포인터 → private Issue/PR → reports JSON/요약 → raw log(필요 시)

---

## Quick one-liner

Dev=CHANGE(PR) / Val=VERDICT(Validation Issue) / PM-Ops=SSOT updates / HQ=Decision

---

## Reference

- Shared Comment Rules:
  https://github.com/sdhkor/AI-Quant-SSOT/issues/3
- Work Order:
  https://github.com/sdhkor/AI-Quant-SSOT/issues/2
- Roles discussion / migration issue:
  https://github.com/sdhkor/AI-Quant-SSOT/issues/4
