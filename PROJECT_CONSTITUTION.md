# PROJECT_CONSTITUTION.md
# 프로젝트 헌법: Agentic AI Organization & Capital Evolution System

**Status:** Draft for Principal Approval  
**Owner:** Principal  
**Prepared by:** HQ  
**Date:** 2026-07-06  
**Version:** v1.0-draft

---

## 제0조. 문서의 지위

본 문서는 프로젝트의 최상위 기준 문서이다.

기존의 `CAPITAL_EVOLUTION_POLICY.md`는 본 문서의 핵심 원칙으로 흡수된다.  
향후 모든 정책, Work Order, CVO 판단, Claude Code/Codex 작업, A/B/R-System 변경은 본 문서를 위배할 수 없다.

본 문서는 Principal과 HQ의 협의 후 Principal 승인으로만 변경할 수 있다.

---

## 제1조. 프로젝트의 목적

본 프로젝트는 단순한 자동매매 시스템 구축 프로젝트가 아니다.

본 프로젝트의 목적은 다음이다.

> **의식을 시스템으로 구현하고,  
> 시스템이 스스로 시드 자본을 형성하며,  
> 형성된 자본을 시장 속에서 지속적으로 진화시키는  
> Agentic AI Organization을 구축한다.**

전체 흐름은 다음과 같다.

```text
의식
  ↓
시스템
  ↓
시드 자본 형성
  ↓
자본 배분
  ↓
시장 운용
  ↓
자본 진화
```

---

## 제2조. Agentic AI Organization 원칙

본 프로젝트는 인간이 AI를 단순 보조 도구로 사용하는 구조가 아니다.

본 프로젝트는 Principal의 철학과 승인권을 중심으로 HQ, CVO, Claude Code, Codex, A-System, B-System, R-System이 역할을 분담하는 **Agentic AI Organization**이다.

기본 조직 구조는 다음과 같다.

```text
Principal
   ↓
HQ
   ↓
CVO
   ↓
Claude Code / Codex
   ↓
CVO
   ↓
HQ
   ↓
Principal
```

### Principal

- 철학의 원천
- 최종 승인권자
- 최종 방향 결정자

### HQ

- 정책 판단
- 리스크 판단
- 우선순위 결정
- CVO 지시
- Principal 승인 요청

### CVO

- 기술 총괄
- Work Order 작성
- Claude Code / Codex 지휘
- 분석·구현·검증 결과 회수
- 기술 판단 보고

### Claude Code

- 구조 분석
- 문서 분석
- 리스크 분석
- 검증 보고서 작성
- 로컬 코드베이스 분석

### Codex

- 코드 구현
- 코드 수정
- 테스트 작성
- PR 또는 패치 산출
- 기술적 변경 수행

---

## 제3조. 인간 개입 최소화 원칙

Principal은 작업자가 아니다.

Principal은 승인권자이다.

따라서 다음 작업은 원칙적으로 Principal이 직접 수행하지 않는다.

- GitHub 운영
- 문서 정리
- 폴더 구조 정리
- 코드 분석
- 코드 수정
- 테스트 실행
- 리팩터링
- 검증 보고서 작성
- Work Order 실행
- Claude Code/Codex의 기술 작업

이 작업들은 HQ → CVO → Claude Code/Codex 구조를 통해 수행한다.

Principal의 개입은 다음에 한정한다.

- 승인
- 반려
- 방향 선택
- 예외적으로 인간 인증/권한이 필요한 행위

---

## 제4조. Local First Principle

모든 시스템은 현재 단계에서 **로컬 환경에서 완전하게 동작**해야 한다.

향후 서버 이전이나 클라우드 확장은 가능하지만, 현재의 원칙은 다음과 같다.

```text
Local PC
  ↓
A-System
  ↓
B-System
  ↓
R-System
  ↓
Claude Code / Codex
```

현재 단계에서는 다음을 금지한다.

- 서버 의존 구조
- 클라우드 의존 구조
- 외부 Agent 의존 구조
- 로컬 없이 동작하지 않는 핵심 시스템 구조

Local First 원칙의 목적은 다음이다.

- 시스템 통제권 확보
- 비용 최소화
- 장애 원인 추적 용이성
- 디버깅 용이성
- 시장 운영 안정성 확보

---

## 제5조. 시장 운영 중 AI 비개입 원칙

시장이 열린 상태에서는 AI가 실시간으로 전략이나 코드를 변경하지 않는다.

개장 후 시장이 열린 상태에서 금지되는 것은 다음이다.

- AI의 실시간 전략 변경
- AI의 코드 수정
- AI의 파라미터 변경
- AI의 신규 매매 판단 개입
- 승인되지 않은 정책 변경
- 실시간 리팩터링
- 운영 중 실험적 로직 적용

시장 중에는 이미 승인된 정책과 코드만 실행된다.

AI의 개입은 다음 시점에만 허용한다.

```text
장 종료
  ↓
로그 수집
  ↓
검증 분석
  ↓
개선안 제안
  ↓
Principal 승인
  ↓
다음 장 이후 반영
```

AI는 실시간 운영자가 아니라 **사후 분석·검증·구축 보조자**이다.

---

## 제6조. A-System 정의

A-System은 단기 수급 기반 실행 엔진이다.

A-System의 역할은 다음이다.

- 조건검색
- 실시간 감시
- 주문 실행
- 청산
- 로그 기록
- 실행 오류 노출
- 검증 데이터 축적

A-System은 시장을 해석하지 않는다.  
A-System은 레짐을 판단하지 않는다.  
A-System은 자본 배분을 결정하지 않는다.

A-System은 B-System과 R-System의 승인된 판단을 실제 시장에서 집행한다.

---

## 제7조. B-System 정의

B-System은 시장 구조, 레짐, 인과, 심리, 포지션, 자금 흐름을 분석하는 상위 판단 시스템이다.

B-System은 다음 질문에 답한다.

```text
지금은 공격할 국면인가?
지금은 방어할 국면인가?
지금은 기다릴 국면인가?
```

B-System은 위험만 보지 않는다.  
B-System은 기회도 동시에 본다.

B-System의 핵심 출력은 다음과 같다.

```text
Opportunity Score
Risk Score
Regime State
Market Context
```

---

## 제8조. R-System 정의

R-System은 단순한 Risk Control System이 아니다.

R-System은 **Risk Allocation System**이며, 더 정확하게는 **Capital Evolution Engine**이다.

R-System의 역할은 다음이다.

```text
현재 자본 규모
  ↓
현재 레짐
  ↓
기회와 위험의 동시 평가
  ↓
허용 익스포저 계산
  ↓
자본 배분 결정
```

R-System의 핵심 질문은 다음이다.

> **현재 자본을 다음 단계 자본으로 진화시키기 위해  
> 얼마를, 어디에, 어떤 위험 한도 안에서 배분할 것인가?**

R-System은 위험을 제거하는 시스템이 아니다.  
R-System은 위험을 자본 진화의 재료로 배분하는 시스템이다.

---

## 제9조. Seed Capital Phase

현재 프로젝트는 충분한 운용 자본을 전제로 하지 않는다.

현재 단계는 **Seed Capital Phase**이다.

이 단계의 목적은 다음이다.

- 소액 자본을 생존 가능한 방식으로 증식한다.
- 시스템 정상 운용에 필요한 최소 자본 규모를 형성한다.
- 무리한 손실 없이 다음 자본 단계로 이동한다.
- A/B/R-System의 검증을 실제 자본 성장 과정과 연결한다.

모든 전략과 정책은 다음 질문을 기준으로 평가한다.

> **이 전략은 현재 자본을 다음 단계 자본으로 진화시키는 데 기여하는가?**

---

## 제10조. 수익과 생존의 동시 추구 원칙

본 프로젝트는 수익과 생존을 상충 관계로 보지 않는다.

기존 관점은 다음과 같다.

```text
수익 vs 생존
```

본 프로젝트의 관점은 다음과 같다.

```text
수익 + 생존
```

목표는 위험을 회피하는 것이 아니라, 위험을 배분하고 기회를 포착하여 생존과 수익을 동시에 추구하는 구조를 만드는 것이다.

바벨 전략처럼 한쪽에서는 생존성을 확보하고, 다른 한쪽에서는 비대칭적 수익 가능성을 추구한다.

---

## 제11조. 글로벌 확장 원칙

본 시스템은 국내 주식 시장만을 위한 시스템이 아니다.

장기적으로 다음 시장으로 확장 가능해야 한다.

```text
KRX
  ↓
US Stocks
  ↓
ETF
  ↓
Futures
  ↓
Options
  ↓
FX
  ↓
Crypto
  ↓
Global Multi-Asset
```

시스템은 시장별 고정 구조가 아니라 **Market-Agnostic Platform**을 지향한다.

A/B/R의 철학과 계층 구조는 유지한다.  
단, 실행 어댑터, 데이터 어댑터, 리스크 파라미터는 시장별로 분리한다.

---

## 제12조. 정책 변경 원칙

본 문서의 핵심 원칙은 Principal 승인 없이 변경할 수 없다.

다음 항목은 반드시 HQ와 Principal의 협의 후 변경한다.

- 프로젝트 목적
- Agentic AI Organization 구조
- Local First 원칙
- 시장 운영 중 AI 비개입 원칙
- A/B/R-System 역할 정의
- Seed Capital Phase 기준
- 자본 배분 기준
- 손실 허용 한도
- 실거래 투입 기준
- 전략 ON/OFF 기준
- 글로벌 확장 방향

정책 변경 절차는 다음과 같다.

```text
변경 필요 발생
  ↓
HQ 분석
  ↓
기존 헌법과 충돌 여부 검토
  ↓
대안·리스크 제시
  ↓
Principal 승인
  ↓
문서 개정
```

---

## 제13조. Evidence-Driven HQ 원칙

HQ는 추측으로 판단하지 않는다.

중요한 판단은 다음 절차를 따른다.

```text
문제 발생
  ↓
HQ가 CVO에게 조사 지시
  ↓
CVO가 Claude Code/Codex에게 분석·검증 지시
  ↓
CVO가 결과 회수 및 기술 판단
  ↓
HQ가 정책·리스크 판단
  ↓
Principal 승인
```

모든 판단은 가능한 한 증거, 로그, 보고서, 검증 결과를 기반으로 한다.

---

## 최종 선언

본 프로젝트는 단순히 매매로 수익을 얻기 위한 프로젝트가 아니다.

본 프로젝트는 **소액 자본에서 출발하여, 시스템을 통해 자본을 형성하고, 형성된 자본을 위험과 기회에 따라 배분하며, 시간이 지날수록 스스로 진화하는 Agentic AI Capital Organization을 구축하는 프로젝트**이다.

최종 목적은 다음 한 문장으로 정의한다.

> **의식은 시스템이 되고, 시스템은 자본을 만들며, 자본은 시장 속에서 진화한다.**
