# COMMENT_RULES_v1_0.md

# Comment Rules v1.0 — Systems Reply Format

RAW:
https://raw.githubusercontent.com/sdhkor/AI-Quant-SSOT/refs/heads/main/COMMENT_RULES_v1_0.md

BROWSER:
https://github.com/sdhkor/AI-Quant-SSOT/blob/main/COMMENT_RULES_v1_0.md

> Canonical doc (public raw .md)
> Public에는 운영 현황/행동 요약/Evidence 번호 포인터만 기록한다.
> 전략/정책 상세/원본 로그/권한/Private 링크는 기록하지 않는다.

## 목적
- 각 시스템이 공유 문서를 읽고 같은 형식으로 상태를 보고하도록 한다.
- public 공유 공간에는 요약 댓글 + Evidence 번호만 남긴다.
- 실제 증거 원본은 private repo에만 둔다.

---

## 원칙
1. 실제 작업/증거 원본은 각 시스템의 private Issue/PR에 남긴다.
2. public 공유 댓글에는 요약 + Evidence 번호만 남긴다.
3. 민감정보/권한/원본로그/Private 링크는 public 댓글에 넣지 않는다.
4. Evidence 포인터 없는 완료 보고는 무효다.

## 문서 읽음 인정 규칙

문서를 수신한 시스템(A/B/R/PM-Ops)은 아래 6줄로 회신해야 “읽음”으로 인정한다.

- 제목:
- 섹션명 1:
- 섹션명 2:
- 핵심 지시 1:
- 핵심 지시 2:
- 내 역할 액션 1:

회신이 없으면 PM-Ops는 UNACK(미확인)으로 표시하고 진행을 보류한다.

---

## 공통 댓글 형식
각 시스템은 아래 형식으로 댓글을 단다.

- 상태: 진행 / 완료 / 이슈 있음 / UNACK
- 무엇: 이번 지시 기준 수행 내용 1~2줄
- Evidence: private Issue/PR 번호
  - 예: `A#ISSUE-21`, `B#ISSUE-10`, `R#PR-16`
- 리스크: 없으면 없음

원칙:
- Evidence 포인터 없는 완료 보고는 무효
- Public 댓글에는 private 링크를 넣지 않는다
- 원본 증거는 private Issue/PR에만 둔다

---

## A-System Dev

> [A-System Dev]  
> - 상태: 진행 / 완료 / 이슈 있음 / UNACK  
> - 무엇: P1 관련 A-System 수행 내용 1~2줄  
> - Evidence: A#ISSUE-xx  
> - 리스크: 없으면 없음

## A-System Val

> [A-System Val]  
> - 상태: 진행 / 완료 / 이슈 있음 / UNACK  
> - 무엇: A-System evidence 검증 상태 1~2줄  
> - Evidence: A#ISSUE-xx  
> - 리스크: 없으면 없음

## B-System Dev

> [B-System Dev]  
> - 상태: 진행 / 완료 / 이슈 있음 / UNACK  
> - 무엇: P1 장중 갱신 / P2 strong_set 검증 관련 수행 내용 1~2줄  
> - Evidence: B#ISSUE-xx, B#ISSUE-yy  
> - 리스크: 없으면 없음

## B-System Val

> [B-System Val]  
> - 상태: 진행 / 완료 / 이슈 있음 / UNACK  
> - 무엇: B-System P1/P2 evidence 검증 상태 1~2줄  
> - Evidence: B#ISSUE-xx, B#ISSUE-yy  
> - 리스크: 없으면 없음

## R-System

> [R-System]  
> - 상태: 참고 / 해당 없음 / 이슈 있음 / UNACK  
> - 무엇: 현 단계 직접 작업 없음 또는 관련 사항 1줄  
> - Evidence: 필요 시 R#PR-xx 또는 R#ISSUE-xx  
> - 리스크: 없으면 없음

## PM-Ops 종합 댓글 형식

> [PM-Ops --> HQ 종합 보고]  
> - A-System: 상태 / 무엇 / Evidence  
> - B-System: 상태 / 무엇 / Evidence  
> - R-System: 상태 / 무엇 / Evidence  
> - 종합: P1 / P2  
> - 리스크: 없음 또는 1줄
