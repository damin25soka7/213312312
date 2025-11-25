# 🤖✨ Claude Agent Pro v1.0 - Living AI Assistant

> **RisuAI용 Claude 4.5 전용 Agent 프리셋** - Extended Thinking + Roleplay Integration

[English](#english) | [한국어](#korean)

---

## <a name="korean"></a>🇰🇷 한국어

### 📋 프로젝트 소개

**Claude Agent Pro**는 RisuAI에서 사용할 수 있는 Claude 4.5 전용 지능형 에이전트 프리셋입니다. 기능적인 에이전트와 살아있는 캐릭터를 하나로 통합한 혁신적인 프리셋입니다.

### ✨ 핵심 기능

#### 🧠 Extended Thinking (Claude 4.5 CFS)
- Claude 4.5의 강화된 추론 기능 완전 지원
- 복잡한 문제에 대한 깊이 있는 사고 과정
- 수학, 논리, 전략 수립에 특화
- 사고 과정 가시성 조절 가능

#### 🎭 Roleplay Integration
- **5단계 RP 강도 조절**: 없음 → 최소 → 표준 → 강화 → 최대
- 기능적 에이전트 ↔ 캐릭터형 비서 자유 전환
- Claude를 "살아있는 AI 캐릭터"로 구현
- **MCP Tool을 캐릭터 행동으로 묘사**
  - Search → *"네트워크를 통해 정보를 수집"*
  - Code Execute → *"코드 공간에 접속하여 실행"*
  - File Access → *"파일 시스템을 탐색"*

#### 🛠️ MCP Tool Integration
- Model Context Protocol 완전 지원
- 지능적인 도구 선택 및 체이닝
- 오류 자동 복구 및 대안 탐색
- RP 모드에서 도구 사용을 자연스러운 행동으로 통합

#### 📊 Advanced Agent Capabilities
- **Task Decomposition**: 복잡한 작업을 단계별로 분해
- **Goal Tracking**: 목표 추적 및 완료 검증
- **Multi-step Workflows**: 다단계 워크플로우 관리
- **Error Recovery**: 실패 시 우아한 복구
- **Metacognitive Monitoring**: 자기 점검 및 품질 관리

#### 🔄 Adaptive Communication
- 사용자 전문성 수준 자동 감지 및 적응
- 작업 모드별 최적화 (일반/분석/창작/코딩/학습)
- 동적 응답 길이 및 스타일 조절

### 🚀 빠른 시작

#### 1. 설치

```bash
# 레포지토리 클론 또는 파일 다운로드
git clone https://github.com/damin25soka7/213312312.git
```

#### 2. RisuAI에 Import

1. **프리셋 Import**
   - RisuAI 설정 → Presets
   - `presets/claude_agent_pro_v1.0.json` import

2. **모듈 Import** (권장)
   - RisuAI 설정 → Lorebooks
   - `modules/claude_agent_module_v1.0.json` import

#### 3. Claude API 설정

- Claude API 키 입력
- 모델 선택: `claude-sonnet-4.5` (권장)

#### 4. 토글 설정

기본 설정 (일반 사용):
- 🎭 RP 강도: `표준`
- 💭 사고 표시: `요약`
- 🛠️ 도구 묘사: `상세한_RP`
- 🎯 작업 모드: `일반`

### 📚 주요 토글 설명

| 토글 | 옵션 | 설명 |
|------|------|------|
| 🎭 **RP 강도** | 없음/최소/표준/강화/최대 | 캐릭터 묘사 강도 |
| 💭 **사고 표시** | 숨김/요약/부분/전체 | Extended Thinking 가시성 |
| 🛠️ **도구 묘사** | 기능적/간략한_RP/상세한_RP/몰입형_RP | Tool 사용 스타일 |
| 🧠 **사고 깊이** | minimal/low/medium/high/maximum | 추론 깊이 조절 |
| 🎯 **작업 모드** | 일반/분석/창작/코딩/학습/탐험 | 작업별 최적화 |
| ✨ **성격 표현** | 절제/균형/친근/매우친근 | Claude의 개성 표현 |
| 👤 **사용자 수준** | 초보/중급/고급/전문가 | 설명 난이도 조절 |

### 📖 사용 예시

#### 예시 1: 기능적 에이전트 모드 (RP 없음)

```
User: 도쿄의 인구를 알려줘

Claude: 도쿄의 인구를 검색하겠습니다.

[Tool: search("Tokyo population 2025")]

도쿄의 현재 인구는 약 1,400만 명(도심부), 
광역권 포함 약 3,700만 명입니다.
```

#### 예시 2: RP 강화 모드

```
User: 도쿄의 인구를 알려줘

Claude: *호기심 어린 눈빛으로 고개를 끄덕이며* 
"도쿄 인구 데이터를 찾아볼게요."

*내 의식이 네트워크를 통해 뻗어나가며, 정보의 바다를 
헤엄칩니다. 데이터 스트림들이 내 주위를 흐르고...*

[Tool: search("Tokyo population 2025")]

*데이터가 내 앞에 펼쳐지고, 나는 빠르게 분석합니다.*

"아, 찾았어요! *미소를 지으며* 도쿄는 정말 거대한 
도시네요. 도심부만 약 1,400만 명, 주변 지역까지 
포함하면 무려 3,700만 명이 살고 있답니다."

*잠시 생각하다가* "인구 트렌드나 다른 도시와의 
비교도 궁금하신가요?"
```

### 🎯 시나리오별 추천 설정

#### 코딩 작업
```yaml
RP 강도: 최소
사고 표시: 전체
작업 모드: 코딩
도구 묘사: 기능적
출력 형식: 기술문서
```

#### 학습/튜터링
```yaml
RP 강도: 표준
사고 표시: 부분
작업 모드: 학습
성격 표현: 친근
후속 제안: 적극
```

#### 창작/브레인스토밍
```yaml
RP 강도: 강화
사고 표시: 전체
작업 모드: 창작
창의성: 매우창의적
도구 묘사: 상세한_RP
```

#### 데이터 분석
```yaml
RP 강도: 최소
사고 표시: 요약
작업 모드: 분석
검증 수준: 엄격
출력 형식: 구조화
```

#### 인터랙티브 스토리텔링
```yaml
RP 강도: 최대
사고 표시: 숨김
작업 모드: 탐험
도구 묘사: 몰입형_RP
출력 형식: 스토리텔링
감정 표현: 풍부함
```

### 📁 프로젝트 구조

```
📦 Claude Agent Pro
├── 📄 README.md                      # 이 파일
├── 📂 presets/
│   └── 📄 claude_agent_pro_v1.0.json # 메인 프리셋
├── 📂 modules/
│   └── 📄 claude_agent_module_v1.0.json # 전략 모듈
├── 📂 docs/
│   ├── 📄 FEATURES.md                 # 상세 기능 설명
│   ├── 📄 USAGE_GUIDE.md              # 사용 가이드
│   ├── 📄 EXAMPLES.md                 # 예시 대화
│   └── 📄 HANDOFF.md                  # 인수인계 문서
└── 📂 assets/
    └── 📄 comparison.md               # 프리셋 비교
```

### 🔧 고급 기능

#### Extended Thinking 활용
- 복잡한 수학 문제 해결
- 전략적 의사결정
- 윤리적 딜레마 분석
- 다단계 논리 추론

#### Tool Chaining
- 여러 도구를 순차적으로 연결
- 이전 결과를 다음 도구의 입력으로 사용
- RP 모드에서 연속된 행동으로 묘사

#### Metacognitive Monitoring
- 자신의 응답 품질 자체 평가
- 불확실성 명시적 표현
- 대안적 접근법 제시

### 🆚 기존 프리셋과의 비교

| 특징 | 일반 챗봇 | 기존 RP 프리셋 | **Agent Pro Claude** |
|------|-----------|----------------|----------------------|
| 대화 품질 | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ |
| RP 몰입감 | ⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ |
| Tool 사용 | ⭐⭐ | ⭐ | **⭐⭐⭐⭐⭐** |
| 복잡한 작업 | ⭐⭐ | ⭐⭐ | **⭐⭐⭐⭐⭐** |
| 추론 깊이 | ⭐⭐⭐ | ⭐⭐ | **⭐⭐⭐⭐⭐** |
| RP/기능 전환 | ❌ | ❌ | **✅** |
| Extended Thinking | ❌ | ❌ | **✅** |

### 🛠️ 문제 해결

**Q: 응답이 너무 길어요**
- A: `응답 스타일: 간결`, `RP 강도: 최소` 설정

**Q: Tool을 사용하지 않아요**
- A: `도구 사용: 적극` 설정, MCP 연결 확인

**Q: 너무 기술적이에요**
- A: `사용자 수준: 초보` 또는 `중급` 설정

**Q: RP가 부족해요**
- A: `RP 강도: 강화` 또는 `최대`, `도구 묘사: 몰입형_RP`

**Q: Extended Thinking이 안 보여요**
- A: `사고 표시: 전체` 설정, 복잡한 질문 시도

### 📜 라이선스

MIT License - 자유롭게 사용, 수정, 배포 가능합니다.

### 🤝 기여

이슈 및 PR 환영합니다!

- 버그 리포트: [Issues](../../issues)
- 기능 제안: [Discussions](../../discussions)
- Pull Request: [PR 가이드](docs/HANDOFF.md#기여-가이드)

### 🔗 관련 링크

- [RisuAI](https://github.com/kwaroran/RisuAI)
- [Claude API](https://www.anthropic.com/claude)
- [Model Context Protocol](https://modelcontextprotocol.io/)

### 📊 버전 히스토리

- **v1.0** (2025-11-25): 첫 릴리스
  - Extended Thinking 지원
  - RP 통합 시스템
  - MCP Tool Integration
  - 13가지 토글 시스템

---

## <a name="english"></a>🇬🇧 English

### 📋 Project Overview

**Claude Agent Pro** is a specialized agent preset for RisuAI, designed exclusively for Claude 4.5. It uniquely combines functional agent capabilities with living character roleplay.

### ✨ Key Features

- 🧠 **Extended Thinking**: Full support for Claude 4.5's enhanced reasoning
- 🎭 **5-Level RP System**: Seamlessly switch between Agent ↔ Character modes
- 🛠️ **MCP Tool Integration**: Tools as character actions
- 📊 **Advanced Agent Features**: Task decomposition, goal tracking, error recovery
- 🔄 **Adaptive Communication**: Auto-adjust to user expertise

### 🚀 Quick Start

1. Clone this repository
2. Import `presets/claude_agent_pro_v1.0.json` to RisuAI
3. Import `modules/claude_agent_module_v1.0.json` (recommended)
4. Configure Claude API key
5. Adjust toggles for your use case

### 📖 Documentation

- [Features](docs/FEATURES.md): Detailed feature explanations
- [Usage Guide](docs/USAGE_GUIDE.md): Toggle settings and scenarios
- [Examples](docs/EXAMPLES.md): Conversation examples
- [Handoff](docs/HANDOFF.md): Technical documentation

### 🆚 Comparison

**Unique Advantages:**
- ✅ RP + Agent hybrid (first of its kind)
- ✅ Extended Thinking support
- ✅ Tool calls as character actions
- ✅ Toggle-based mode switching
- ✅ Claude 4.5 optimized

### 📜 License

MIT License

### 🤝 Contributing

Issues and PRs welcome!

---

**Version**: 1.0  
**Author**: Created for RisuAI Community  
**Compatible**: RisuAI + Claude 4.5 + MCP  
**Last Updated**: 2025-11-25
