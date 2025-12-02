---
created: 2025-12-02 
tags:
  - newsletter
  - claude 
source: "https://www.technologyreview.com/2025/11/27/1128465/moving-toward-lessops-with-vmware-to-cloud-migrations/"
model: Claude-Opus-4 
---

# Moving toward LessOps with VMware-to-cloud migrations

# 🔍 "서버 하나 던지고 끝"의 시대는 갔다 — AI 시대, MCP가 바꾸는 컨텍스트 공유의 판도

---

## [도입부 – Editor's Note]

AI 에이전트가 우리 삶 깊숙이 들어오고 있어요. 그런데 정작 이 AI들이 외부 도구나 데이터를 활용하려면? 여전히 개발자들이 일일이 커스텀 통합 코드를 짜야 하는 게 현실이에요.

Anthropic이 작년 말 공개한 **MCP(Model Context Protocol)**는 이 문제를 정면으로 겨냥했어요. "AI 모델에게 컨텍스트를 공급하는 방식을 표준화하자"는 거죠. 하지만 초기 버전은 로컬 서버에 의존하는 구조였고, 인증 체계도 빈약했어요.

그런데 최근 발표된 **2025-03-26 스펙 업데이트**는 완전히 다른 이야기를 하고 있어요. 원격 서버 지원, OAuth 2.1 기반 인증, 그리고 스트리밍 HTTP 전송까지. MCP가 드디어 **"프로덕션 레디"** 단계로 진입하고 있다는 신호입니다.

이 변화가 왜 중요한지, 그리고 한국의 개발자와 스타트업에게 어떤 기회를 열어주는지 깊이 들여다볼게요.

---

## [본론 – Deep Dive]

### 1️⃣ MCP의 본질: AI에게 "세상과 연결되는 창"을 주다

MCP를 이해하려면 먼저 AI 모델의 근본적 한계를 알아야 해요.

LLM은 학습 데이터라는 "과거의 스냅샷"에 갇혀 있어요. 실시간 주가, 최신 문서, 사내 데이터베이스 같은 **살아있는 컨텍스트**에 접근하려면 외부 시스템과의 연결이 필수죠.

> "MCP는 **앱이 LLM에게 컨텍스트를 제공하는 표준 방식**으로, AI 에이전트가 도구 및 데이터 소스와 통합하는 과정을 단순화합니다."

기존에는 이런 통합을 위해 OpenAI용 코드 따로, Claude용 코드 따로 작성해야 했어요. MCP는 이 비효율을 없애려는 시도예요. **USB 포트가 모든 주변기기를 표준화했듯이**, MCP는 AI-외부 시스템 연결을 표준화하려는 거죠.

---

### 2️⃣ 2025년 스펙 업데이트: 무엇이 달라졌나

![MCP Architecture Diagram](https://storage.googleapis.com/zenn-user-upload/deployed-images/bb7f98a84cd4f5d35ce66c0d.png?sha=1bb4d6a8b2f4e9eba59e23f04d33a4d4905b43da)

이번 업데이트의 핵심은 **"로컬에서 원격으로의