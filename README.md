# 📞 AI-based Emergency Consultation Triage System (긴급 상담 트리아지 시스템)

> **Upstage AI Initiative 2025 Hackathon Project** > **Team:** 늘어진 고양이 (Stretched Cat)  
> **Role:** PM (Product Manager), Presenter, Workflow Facilitator  
> **Period:** 2025.11.12 ~ 2025.11.20

---

## 📖 Project Overview (프로젝트 개요)

이 프로젝트는 **긴급 상담 시 발생하는 '병목 현상'과 '휴먼 에러'를 방지하기 위한 AI 트리아지(Triage) 시스템**입니다 
상담원이 수동으로 처리하던 정보 수집 및 전파 과정을 자동화하여, 골든타임을 확보하는 것을 목표로 합니다.

### 🛑 Problem Statement (문제 정의)
오송 지하차도 침수 사고나 이태원 참사와 같은 재난 상황에서 다음과 같은 문제가 반복됨을 확인했습니다.
1.  **정보 누락 및 지연**: 상담원이 듣고, 타이핑하고, 판단하는 과정에서 발생하는 병목 현상.
2.  **휴먼 에러**: 긴급 상황에서 상담원의 당황, 심리적 압박으로 인한 판단 오류 및 책임 회피성 정보 누락.

### 🎯 Solution (해결책)
* **행정 업무의 AI 자동화**: STT(음성 변환), 긴급도 분류, 기관 전파 등 '행정 업무'는 AI가 백그라운드에서 실시간 처리.
* **상담사의 역할 재정의**: 상담사는 행정 업무에서 해방되어, 오직 **"사람을 살리는 대화(심리 안정, 상황 통제)"**에만 집중.

---

## 🛠 Tech Stack (기술 스택)

| Category | Technology | Usage |
| --- | --- | --- |
| **Workflow** | **n8n** | 노드 기반 워크플로우 자동화 및 파이프라인 설계 |
| **LLM** | **Upstage Solar Pro 2** | L1~L3 위험도 등급화 및 상황 판단 (비중 60% 이상) |
| **STT** | **AWS Transcribe** | 실시간 통화 음성의 텍스트 변환 |
| **NLP** | **NER (Named Entity Recognition)** | 위치 정보 및 긴급 유형 자동 추출 |

---

## ⚙️ System Architecture (시스템 구조)

이 시스템은 입력된 음성 데이터가 **n8n 워크플로우**를 통과하며 실시간으로 분석 및 전파되는 구조입니다.

![Workflow System Structure](./workflow.png)

### 핵심 로직 상세

1.  **STT & NER**: AWS Transcribe로 텍스트 변환 후, AI가 신고자의 **위치**와 **긴급 유형**을 자동 추출합니다.
2.  **Solar Pro 2 Risk Grading**: 사전 정의된 기준표(Table Sheet)를 바탕으로 AI가 상황을 분석해 \*\*L1(경미)부터 L3(심각)\*\*까지 위험도를 등급화합니다.
3.  **Auto-Propagation (일괄 전파)**: 위험도에 따라 Switch Node가 작동하여, 경찰/소방 등 유관 기관 API로 상황을 즉시 전파합니다.

-----

## 🧑‍💻 My Contributions (나의 기여)

**Role: PM & Presenter** 단순한 기술 구현을 넘어, \*\*"왜 이 기술이 필요한가?"\*\*에 대한 당위성을 설계하고 팀의 방향성을 제시했습니다.

### 1\. Narrative & Logic Design

  * **문제 해결의 철학 정립**: "기술이 행정을 맡고, 인간은 인간적인 대화에 집중한다"는 핵심 가치(Value Proposition)를 도출하여 프로젝트의 설득력을 높였습니다.
  * **시나리오 기반 기획**: 오송 및 이태원 사례를 분석하여, 실제 재난 상황에서 시스템이 어떻게 병목을 해결하는지 시나리오를 설계했습니다.

### 2\. Workflow Management

  * **R\&R 최적화**: 팀원들의 역할을 '데이터(테이블 시트)'와 '파이프라인(워크라인)'으로 구분하여 개발 속도를 단축했습니다.
  * **트러블 슈팅**: 개발 도중 발생한 연동 문제를 해결하기 위해 기능을 단순화하고 핵심 로직(위험도 분류)에 집중하는 의사결정을 내렸습니다.

### 3\. Presentation

  * 현직자 및 심사위원을 대상으로, 복잡한 로직보다는 **골든타임 확보**라는 비즈니스 임팩트를 강조하는 프레젠테이션을 진행했습니다.

-----

## 🚀 Retrospective (회고)

### "기술은 도구일 뿐, 핵심은 사람이다"

이 프로젝트를 통해 AI 기술(Solar Pro, n8n)은 결국 **인간의 고유한 가치를 지키기 위한 도구**임을 깨달았습니다.

  * **Insight**: 모든 것을 자동화하는 것이 정답이 아니라, AI가 '반복적인 행정'을 맡아줄 때 비로소 인간 상담사가 '공감과 판단'이라는 본질적 영역에 집중할 수 있음을 확인했습니다.
  * **Growth**: PM으로서 팀원들이 각자의 기술적 역량을 발휘하도록 돕는 조율자 역할과, 제품의 최종 가치를 포장하여 전달하는 설득자(Presenter)로서의 역량을 길렀습니다.

-----

## 📂 Project Materials

* **Presentation PDF**: [발표 자료 PDF 보기](./presentation.pdf)
* **Presentation Script**: [발표 대본 보기](./PRESENTATION_SCRIPT.md)

