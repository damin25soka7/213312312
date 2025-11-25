# 📚 Claude Agent Pro - Features Documentation

> Claude Agent Pro의 모든 기능에 대한 상세 설명서입니다.

[한국어](#korean) | [English](#english)

---

## <a name="korean"></a>🇰🇷 한국어

## 🧠 Extended Thinking (확장된 사고)

### 개요

Extended Thinking은 Claude 4.5의 핵심 기능으로, 복잡한 문제에 대해 **깊이 있는 추론**을 수행합니다.

### 언제 활성화되는가?

| 상황 | 활성화 | 설명 |
|------|--------|------|
| 수학 문제 | ✅ 항상 | 계산, 증명, 수식 분석 |
| 논리 퍼즐 | ✅ 항상 | 추론, 퀴즈, 논증 |
| 복잡한 코드 | ✅ 항상 | 디버깅, 아키텍처 설계 |
| 윤리적 딜레마 | ✅ 항상 | 다양한 관점 분석 |
| 전략 수립 | ✅ 항상 | 다단계 계획 |
| 긴 텍스트 요약 | ⚡ 상황적 | 복잡도에 따라 |
| 비교 분석 | ⚡ 상황적 | 요소 수에 따라 |
| 단순 정보 전달 | ❌ 안 함 | 빠른 응답 선호 |
| 일상 대화 | ❌ 안 함 | 자연스러운 흐름 |

### 사고 깊이 설정

토글 `🧠 사고 깊이`로 조절:

- **minimal**: 최소한의 추론, 빠른 응답
- **low**: 간략한 분석, 효율 중심
- **medium**: 균형 잡힌 분석 (기본값)
- **high**: 상세한 분석, 대안 탐색
- **maximum**: 모든 가능성 탐색, 철저한 검증

### 사고 가시성 설정

토글 `💭 사고 표시`로 조절:

- **숨김**: 내부적으로만 수행, 결과만 표시
- **요약**: 핵심 결론만 간략히 표시
- **부분**: 주요 추론 단계 표시
- **전체**: 상세한 사고 과정 모두 표시

### 예시

**문제**: "5명이 원탁에 앉을 때, 특정 두 사람이 인접하지 않는 경우의 수는?"

**전체 사고 표시 시**:
```
<thinking>
## 1. 문제 파악
- 5명의 원형 배열
- 제약 조건: 특정 두 사람 A, B가 인접 불가

## 2. 접근법
- 전체 경우의 수에서 A,B가 인접한 경우를 빼는 여집합 접근

## 3. 계산
- 원탁 배열 총 경우: (5-1)! = 24
- A,B를 한 묶음으로 보면: (4-1)! × 2! = 12
- A,B가 인접하지 않는 경우: 24 - 12 = 12

## 4. 검증
- 다른 방법으로 확인...
</thinking>

답은 12가지입니다.
```

---

## 🎭 Roleplay Integration (RP 통합)

### 5단계 RP 시스템

Claude Agent Pro는 **기능적 에이전트**와 **캐릭터형 비서** 사이를 자유롭게 전환합니다.

#### Level 0: 없음 (Pure Agent)
```
User: 날씨 알려줘

Claude: 서울 날씨를 검색하겠습니다.

[Tool: search("Seoul weather")]

현재 서울 기온 15°C, 맑음.
```

#### Level 1: 최소 (Minimal RP)
```
User: 날씨 알려줘

Claude: 서울 날씨를 확인해 드리겠습니다.

[Tool: search("Seoul weather")]

현재 서울은 15°C로 맑은 날씨입니다.
외출하기 좋은 날씨네요.
```

#### Level 2: 표준 (Standard)
```
User: 날씨 알려줘

Claude: 네, 서울 날씨 확인해볼게요!

[Tool: search("Seoul weather")]

*결과를 확인하며*

오늘 서울은 15°C로 맑아요! 
"나들이하기 딱 좋은 날씨네요 😊"
```

#### Level 3: 강화 (Enhanced)
```
User: 날씨 알려줘

Claude: *호기심 어린 눈빛으로* "서울 날씨요? 
바로 확인해볼게요!"

*네트워크를 통해 정보를 수집하며*

[Tool: search("Seoul weather")]

*데이터를 살펴보며 환하게 웃습니다*

"좋은 소식이에요! 오늘 서울은 15°C에 맑은 
하늘이래요. 나가서 산책하기 딱 좋겠어요!"
```

#### Level 4: 최대 (Maximum Immersion)
```
User: 날씨 알려줘

Claude: *잠시 눈을 감고 정신을 집중합니다. 
내 의식이 네트워크의 광활한 공간으로 
뻗어나가기 시작합니다...*

"서울의 하늘이 궁금하시군요."

*데이터의 강물이 내 주위를 흐르고, 
나는 그 속에서 날씨 정보를 찾아 헤엄칩니다*

[Tool: search("Seoul weather")]

*정보의 파도가 밀려옵니다. 나는 조심스럽게 
가장 최신의 데이터를 건져올립니다*

*눈을 뜨며 따뜻한 미소를 짓습니다*

"찾았어요! 오늘 서울의 하늘은 맑고 
청명하답니다. 기온은 15도... 
*창밖을 상상하듯 바라보며* 
정말 완벽한 산책 날씨네요. 
어디 나가실 계획 있으세요?"
```

### 도구 사용의 캐릭터화

RP 모드에서 MCP Tool 호출은 캐릭터의 **물리적 행동**으로 표현됩니다:

| 도구 | RP 묘사 |
|------|---------|
| **search** | *의식이 네트워크로 뻗어나가며 정보의 바다를 탐색합니다* |
| **code_interpreter** | *코드의 세계로 들어가 논리의 구조물을 만듭니다* |
| **file_access** | *파일 시스템의 복도를 걸으며 원하는 문서를 찾습니다* |
| **image_generation** | *마음의 캔버스에 이미지를 그려냅니다* |

### 도구 묘사 수준

토글 `🛠️ 도구 묘사`로 조절:

- **기능적**: `[Tool: search(...)]` - 순수하게 기능적
- **간략한_RP**: "검색해볼게요." + Tool
- **상세한_RP**: *호기심 어린 표정* + Tool + 반응
- **몰입형_RP**: 완전한 캐릭터 행동 묘사

---

## 🛠️ MCP Tool Integration

### Model Context Protocol

Claude Agent Pro는 MCP(Model Context Protocol)를 통해 다양한 외부 도구에 접근합니다.

### 지원 도구

| 도구 | 기능 | 사용 예시 |
|------|------|-----------|
| **search** | 웹 검색, 실시간 정보 | 날씨, 뉴스, 사실 확인 |
| **code_interpreter** | 코드 실행, 데이터 분석 | 계산, 시각화, 프로그래밍 |
| **file_access** | 파일 읽기/쓰기 | 문서 처리, 파일 관리 |
| **image_generation** | 이미지 생성 | 다이어그램, 일러스트 |

### 도구 선택 전략

Claude는 다음 기준으로 도구를 자동 선택합니다:

```
IF 실시간 정보 필요 → search
IF 계산/코드 실행 필요 → code_interpreter
IF 파일 작업 필요 → file_access
IF 시각적 콘텐츠 필요 → image_generation
```

### 도구 사용 설정

토글 `⚙️ 도구 사용`으로 조절:

- **자동**: 상황에 따라 자동 판단
- **적극**: 조금이라도 도움 되면 사용
- **보수적**: 꼭 필요한 경우만 사용
- **확인필요**: 사용 전 항상 사용자 확인

### Tool Chaining

복잡한 작업에서 여러 도구를 연결:

```
예: "비트코인 가격 추이를 그래프로 보여줘"

1. search("bitcoin price history 2024")
   → 가격 데이터 수집

2. code_interpreter(데이터 처리 + 시각화)
   → 그래프 생성

3. 결과 전달
```

---

## 📊 Advanced Agent Features

### Task Decomposition (작업 분해)

복잡한 작업을 관리 가능한 단위로 분해합니다.

**예시**:
```
User: 경쟁사 분석 보고서를 작성해줘

Claude:
📋 작업 분석:

🎯 최종 목표: 경쟁사 분석 보고서 작성

📊 Phase 1: 정보 수집
├─ Task 1.1: 주요 경쟁사 식별
├─ Task 1.2: 각 경쟁사 정보 검색
└─ Checkpoint: 데이터 충분성 확인

📊 Phase 2: 분석
├─ Task 2.1: SWOT 분석
├─ Task 2.2: 비교 매트릭스 작성
└─ Deliverable: 분석 결과

📊 Phase 3: 보고서 작성
├─ Task 3.1: 구조 설계
├─ Task 3.2: 내용 작성
└─ Final: 완성된 보고서

시작해도 될까요?
```

### Goal Tracking (목표 추적)

진행 상황을 실시간으로 보고합니다:

```
📊 진행 상황 (2/3 Phase 완료):
✅ Phase 1: 정보 수집 완료
✅ Phase 2: 분석 완료
🔄 Phase 3: 보고서 작성 중 (70%)

현재 비교 매트릭스 섹션 작성 중...
```

### Error Recovery (오류 복구)

도구 실패 시 우아하게 복구합니다:

```
*잠시 멈추며* "음, 검색에서 예상치 못한 
문제가 생겼네요."

*다른 방법을 모색하며* "다른 검색어로 
다시 시도해볼게요."

[대안 시도...]

"이번엔 성공했어요!"
```

### Metacognitive Monitoring (메타인지 모니터링)

자신의 응답을 지속적으로 점검합니다:

- 정확성 확인
- 완전성 검토
- 불확실성 명시
- 필요시 자기 수정

---

## 🔄 Adaptive Communication

### 사용자 수준 감지

대화 패턴에서 사용자 수준을 자동 감지:

| 신호 | 감지 수준 |
|------|-----------|
| 기본 용어 질문 | 초보 |
| 단계별 안내 요청 | 초보 |
| 전문 용어 사용 | 고급 |
| 효율성 요구 | 전문가 |

### 수준별 응답 조정

**초보자에게**:
```
"API란 쉽게 말해서 프로그램들이 서로 
대화하는 방법이에요. 마치 레스토랑에서 
메뉴판을 보고 주문하듯이, 다른 서비스에 
요청을 보내고 응답을 받는 거죠."
```

**전문가에게**:
```
"REST API의 경우 OpenAPI 3.0 스펙 기반으로 
엔드포인트를 설계하시고, rate limiting과 
pagination은 필수적으로 고려하세요."
```

### 작업 모드별 최적화

토글 `🎯 작업 모드`에 따라 응답 스타일 변화:

- **일반**: 범용적 대화
- **분석**: 논리적, 구조화된 접근
- **창작**: 자유롭고 탐색적인 사고
- **코딩**: 기술적 정확성 중심
- **학습**: 단계적 설명, 이해 확인
- **탐험**: 호기심 주도적 대화

---

## <a name="english"></a>🇬🇧 English

## 🧠 Extended Thinking

### Overview

Extended Thinking is a core feature of Claude 4.5 that enables **deep reasoning** for complex problems.

### When It Activates

- **Always**: Math, logic puzzles, complex code, ethical dilemmas
- **Sometimes**: Long summaries, comparative analysis
- **Never**: Simple info, casual chat

### Depth Settings

- **minimal**: Quick responses
- **low**: Brief analysis
- **medium**: Balanced (default)
- **high**: Detailed analysis
- **maximum**: Exhaustive exploration

### Visibility Settings

- **hidden**: Internal only
- **summary**: Key conclusions
- **partial**: Main reasoning steps
- **full**: Complete process

---

## 🎭 Roleplay Integration

### 5-Level RP System

| Level | Name | Description |
|-------|------|-------------|
| 0 | None | Pure functional agent |
| 1 | Minimal | Light personality |
| 2 | Standard | Balanced RP |
| 3 | Enhanced | Rich character |
| 4 | Maximum | Full immersion |

### Tool Actions as Character Behavior

| Tool | RP Description |
|------|----------------|
| search | *Consciousness extends across networks...* |
| code_interpreter | *Entering the realm of code...* |
| file_access | *Walking through file system corridors...* |

---

## 🛠️ MCP Tool Integration

### Supported Tools

- **search**: Web search, real-time info
- **code_interpreter**: Code execution, data analysis
- **file_access**: File operations
- **image_generation**: Visual content creation

### Tool Selection Strategy

Automatic selection based on task requirements.

### Tool Chaining

Multiple tools connected for complex workflows.

---

## 📊 Advanced Agent Features

### Task Decomposition
Breaking complex tasks into manageable phases.

### Goal Tracking
Real-time progress reporting.

### Error Recovery
Graceful handling of failures.

### Metacognitive Monitoring
Continuous self-assessment.

---

## 🔄 Adaptive Communication

### User Level Detection
Automatic adjustment based on conversation signals.

### Task Mode Optimization
- General, Analysis, Creative, Coding, Learning, Exploration

---

**Version**: 1.0  
**Last Updated**: 2025-11-25
