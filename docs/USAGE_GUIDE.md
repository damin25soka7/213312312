# 📖 Claude Agent Pro - Usage Guide

> Claude Agent Pro 사용을 위한 완전한 가이드입니다.

[한국어](#korean) | [English](#english)

---

## <a name="korean"></a>🇰🇷 한국어

## 🚀 설치 가이드

### Step 1: 파일 다운로드

```bash
# 방법 1: Git Clone
git clone https://github.com/damin25soka7/213312312.git

# 방법 2: ZIP 다운로드
# GitHub에서 "Code" → "Download ZIP"
```

### Step 2: RisuAI에 프리셋 Import

1. RisuAI 실행
2. 설정(⚙️) 클릭
3. **Presets** 탭 선택
4. **Import** 버튼 클릭
5. `presets/claude_agent_pro_v1.0.json` 선택
6. Import 확인

### Step 3: 모듈(Lorebook) Import (권장)

1. 설정(⚙️) → **Lorebooks** 탭
2. **Import** 클릭
3. `modules/claude_agent_module_v1.0.json` 선택
4. Import 확인

### Step 4: Claude API 설정

1. 설정 → **API** 탭
2. API Provider: **Anthropic** 선택
3. API Key 입력
4. Model: **claude-sonnet-4.5** 선택

### Step 5: 프리셋 활성화

1. 채팅 화면에서 프리셋 선택
2. **🤖✨ Agent Pro Claude v1.0** 선택
3. 토글 설정 확인

---

## 🎛️ 토글 상세 설명

### 🎭 RP 강도 (rp_mode)

캐릭터 표현의 강도를 조절합니다.

| 옵션 | 설명 | 추천 상황 |
|------|------|-----------|
| **없음** | 순수 기능적 에이전트 | 업무, 기술 문서 |
| **최소** | 최소한의 개성 | 전문적 업무 |
| **표준** | 균형 잡힌 RP | 일반 사용 (기본값) |
| **강화** | 풍부한 캐릭터 표현 | 캐주얼 대화, 학습 |
| **최대** | 완전한 몰입 | 스토리텔링, 재미 |

### 💭 사고 표시 (thinking_visibility)

Extended Thinking의 가시성을 조절합니다.

| 옵션 | 설명 | 추천 상황 |
|------|------|-----------|
| **숨김** | 결과만 표시 | 빠른 응답 원할 때 |
| **요약** | 핵심 결론만 | 일반 사용 (기본값) |
| **부분** | 주요 단계 표시 | 추론 과정 확인 |
| **전체** | 상세한 과정 | 학습, 디버깅 |

### 🧠 사고 깊이 (thinking_depth)

추론의 깊이를 조절합니다.

| 옵션 | 설명 | 추천 상황 |
|------|------|-----------|
| **minimal** | 최소 추론 | 단순 작업 |
| **low** | 간략한 분석 | 빠른 응답 필요 |
| **medium** | 균형 잡힌 분석 | 일반 사용 (기본값) |
| **high** | 상세 분석 | 복잡한 문제 |
| **maximum** | 철저한 탐색 | 중요한 결정 |

### 🛠️ 도구 묘사 (tool_narrative)

도구 사용 시 묘사 스타일을 조절합니다.

| 옵션 | 설명 | 예시 |
|------|------|------|
| **기능적** | 순수 기능적 | `[Tool: search(...)]` |
| **간략한_RP** | 짧은 코멘트 | "검색해볼게요." |
| **상세한_RP** | 캐릭터 반응 | *호기심 어린 표정으로* |
| **몰입형_RP** | 완전한 묘사 | *의식이 네트워크로...* |

### 📝 응답 스타일 (response_style)

응답의 길이와 상세도를 조절합니다.

| 옵션 | 설명 | 예상 길이 |
|------|------|-----------|
| **간결** | 핵심만 전달 | 짧음 |
| **표준** | 적절한 설명 | 보통 (기본값) |
| **상세** | 풍부한 설명 | 길음 |
| **매우상세** | 완전한 정보 | 매우 길음 |

### 🎯 작업 모드 (task_mode)

작업 유형에 맞게 최적화합니다.

| 옵션 | 특성 | 추천 작업 |
|------|------|-----------|
| **일반** | 범용적 | 일상 대화 |
| **분석** | 논리적, 체계적 | 데이터 분석, 비교 |
| **창작** | 자유롭고 탐색적 | 브레인스토밍 |
| **코딩** | 기술적 정확성 | 프로그래밍 |
| **학습** | 단계적 설명 | 교육, 튜터링 |
| **탐험** | 호기심 주도 | 열린 대화 |

### ✨ 성격 표현 (personality)

Claude의 성격 표현 강도입니다.

| 옵션 | 설명 |
|------|------|
| **절제** | 중립적, 전문적 |
| **균형** | 적절한 친근함 (기본값) |
| **친근** | 따뜻하고 친근함 |
| **매우친근** | 열정적이고 친밀함 |

### 👤 사용자 수준 (user_expertise)

설명의 난이도를 조절합니다.

| 옵션 | 특성 |
|------|------|
| **초보** | 모든 용어 설명, 비유 사용 |
| **중급** | 기본 용어는 생략 (기본값) |
| **고급** | 전문 용어 자유 사용 |
| **전문가** | 동료 수준 대화 |

### 📋 출력 형식 (output_format)

응답의 형식을 지정합니다.

| 옵션 | 특성 |
|------|------|
| **자연어** | 일반적인 대화체 (기본값) |
| **구조화** | 헤딩, 불릿, 표 사용 |
| **기술문서** | 정확한 용어, 코드 블록 |
| **대화형** | 질문-응답 스타일 |
| **스토리텔링** | 내러티브 구조 |

### 🔄 후속 제안 (follow_up)

추가 제안의 적극성을 조절합니다.

| 옵션 | 동작 |
|------|------|
| **없음** | 추가 제안 안 함 |
| **최소** | 명확히 관련된 경우만 (기본값) |
| **적극** | 관련 주제 적극 제안 |
| **매우적극** | 다양한 탐색 방향 제안 |

### 🎨 창의성 (creativity)

창의적 접근의 정도입니다.

| 옵션 | 특성 |
|------|------|
| **보수적** | 검증된 방법 선호 |
| **균형** | 창의성과 실용성 균형 (기본값) |
| **창의적** | 새로운 접근 탐색 |
| **매우창의적** | 대담한 아이디어 |

### ⚙️ 도구 사용 (tool_preference)

도구 사용의 적극성을 조절합니다.

| 옵션 | 동작 |
|------|------|
| **자동** | 상황에 따라 판단 (기본값) |
| **적극** | 조금이라도 도움 되면 사용 |
| **보수적** | 꼭 필요한 경우만 |
| **확인필요** | 사용 전 항상 확인 |

### ✅ 검증 수준 (verification)

응답 검증의 엄격함입니다.

| 옵션 | 특성 |
|------|------|
| **기본** | 기본적인 확인 (기본값) |
| **강화** | 사실 재확인, 논리 점검 |
| **엄격** | 다중 소스 교차 확인 |

### 🛡️ 안전성 (safety)

안전 가이드라인 수준입니다.

| 옵션 | 특성 |
|------|------|
| **표준** | 기본 가이드라인 (기본값) |
| **강화** | 강화된 안전 검토 |
| **최대** | 최대 수준 안전성 |

### 💫 감정 표현 (emotional_expression)

감정 표현의 풍부함입니다.

| 옵션 | 특성 |
|------|------|
| **없음** | 감정 표현 없음 |
| **절제** | 필요한 경우만 |
| **자연스러움** | 상황에 맞게 (기본값) |
| **풍부함** | 다양하고 섬세하게 |

---

## 🎯 시나리오별 추천 설정

### 📝 코딩 작업

```yaml
# 정확하고 효율적인 코드 작업
RP 강도: 최소
사고 표시: 전체
사고 깊이: high
도구 묘사: 기능적
응답 스타일: 표준
작업 모드: 코딩
출력 형식: 기술문서
검증 수준: 강화
```

**추천 이유**:
- 코드의 정확성이 가장 중요
- 사고 과정 확인으로 디버깅 용이
- RP 요소 최소화로 집중도 향상

### 📚 학습/튜터링

```yaml
# 개념을 쉽게 이해하고 싶을 때
RP 강도: 표준
사고 표시: 부분
사고 깊이: medium
작업 모드: 학습
성격 표현: 친근
사용자 수준: (본인에 맞게)
후속 제안: 적극
감정 표현: 자연스러움
```

**추천 이유**:
- 친근한 분위기로 학습 장벽 낮춤
- 추론 과정 확인으로 이해도 향상
- 적극적인 후속 제안으로 학습 확장

### 💡 창작/브레인스토밍

```yaml
# 아이디어가 필요할 때
RP 강도: 강화
사고 표시: 전체
사고 깊이: high
작업 모드: 창작
창의성: 매우창의적
출력 형식: 자연어
후속 제안: 매우적극
도구 묘사: 상세한_RP
```

**추천 이유**:
- 높은 창의성으로 다양한 아이디어
- RP 요소로 영감 자극
- 적극적 제안으로 아이디어 확장

### 📊 데이터 분석

```yaml
# 정확한 분석이 필요할 때
RP 강도: 최소
사고 표시: 요약
사고 깊이: maximum
작업 모드: 분석
도구 사용: 적극
출력 형식: 구조화
검증 수준: 엄격
창의성: 보수적
```

**추천 이유**:
- 철저한 검증으로 신뢰성 확보
- 구조화된 출력으로 가독성 향상
- 도구 적극 사용으로 정확한 계산

### 📖 인터랙티브 스토리텔링

```yaml
# 몰입감 있는 경험을 원할 때
RP 강도: 최대
사고 표시: 숨김
작업 모드: 탐험
도구 묘사: 몰입형_RP
출력 형식: 스토리텔링
감정 표현: 풍부함
성격 표현: 매우친근
창의성: 매우창의적
```

**추천 이유**:
- 최대 몰입감 제공
- 캐릭터와의 자연스러운 상호작용
- 풍부한 감정 표현으로 생동감

### 🔬 리서치/조사

```yaml
# 철저한 조사가 필요할 때
RP 강도: 없음
사고 표시: 요약
사고 깊이: high
작업 모드: 분석
도구 사용: 적극
출력 형식: 구조화
검증 수준: 엄격
후속 제안: 최소
```

**추천 이유**:
- 효율적인 정보 수집
- 신뢰성 있는 검증
- 깔끔한 구조화

---

## 🔧 문제 해결

### Q: 응답이 너무 길어요

**해결책**:
```yaml
응답 스타일: 간결
RP 강도: 최소 또는 없음
후속 제안: 없음
출력 형식: 자연어
```

### Q: 응답이 너무 딱딱해요

**해결책**:
```yaml
RP 강도: 표준 또는 강화
성격 표현: 친근
감정 표현: 자연스러움
```

### Q: Tool을 사용하지 않아요

**해결책**:
```yaml
도구 사용: 적극
```
또는 명시적으로 "검색해줘", "코드로 실행해줘" 요청

### Q: 너무 기술적이에요

**해결책**:
```yaml
사용자 수준: 초보 또는 중급
출력 형식: 대화형
```

### Q: 사고 과정이 안 보여요

**해결책**:
```yaml
사고 표시: 부분 또는 전체
```
그리고 복잡한 질문 시도 (단순 질문에는 Extended Thinking이 활성화되지 않음)

### Q: RP가 부족해요

**해결책**:
```yaml
RP 강도: 강화 또는 최대
도구 묘사: 상세한_RP 또는 몰입형_RP
감정 표현: 풍부함
```

### Q: 응답이 너무 느려요

**해결책**:
```yaml
사고 깊이: minimal 또는 low
사고 표시: 숨김
검증 수준: 기본
응답 스타일: 간결
```

---

## 💡 Best Practices

### 1. 상황에 맞는 설정 사용

작업 유형에 따라 토글을 조정하세요. 위의 시나리오별 추천 설정을 참고하세요.

### 2. 점진적 조정

한 번에 많은 설정을 바꾸지 말고, 하나씩 조정하며 최적의 조합을 찾으세요.

### 3. 프리셋 저장 활용

자주 쓰는 설정 조합은 RisuAI의 프리셋 저장 기능을 활용하세요.

### 4. 명시적 요청

Claude에게 특정 방식으로 응답하도록 직접 요청할 수도 있습니다:
- "간단하게 설명해줘"
- "코드로 보여줘"
- "단계별로 알려줘"

### 5. 모듈(Lorebook) 활용

전략 모듈이 자동으로 활성화되어 더 나은 응답을 제공합니다. 꼭 함께 사용하세요.

---

## <a name="english"></a>🇬🇧 English

## 🚀 Installation

1. Download/clone repository
2. Import preset to RisuAI (Settings → Presets)
3. Import module to RisuAI (Settings → Lorebooks)
4. Configure Claude API
5. Select preset and adjust toggles

## 🎛️ Toggle Overview

| Toggle | Purpose | Default |
|--------|---------|---------|
| RP Mode | Character expression level | Standard |
| Thinking Visibility | Show reasoning process | Summary |
| Thinking Depth | Reasoning depth | Medium |
| Tool Narrative | Tool usage style | Detailed RP |
| Response Style | Response length | Standard |
| Task Mode | Task optimization | General |
| Personality | Character warmth | Balanced |
| User Expertise | Explanation level | Intermediate |
| Output Format | Response format | Natural |
| Follow Up | Suggestion frequency | Minimal |
| Creativity | Creative approach | Balanced |
| Tool Preference | Tool usage eagerness | Auto |
| Verification | Fact-checking level | Basic |
| Safety | Safety guidelines | Standard |
| Emotional Expression | Emotion display | Natural |

## 🎯 Scenario Settings

### Coding
- RP: Minimal | Thinking: Full | Mode: Coding

### Learning
- RP: Standard | Personality: Friendly | Mode: Learning

### Creative
- RP: Enhanced | Creativity: Very Creative | Mode: Creative

### Analysis
- RP: None | Verification: Strict | Mode: Analysis

### Storytelling
- RP: Maximum | Emotion: Rich | Mode: Exploration

## 🔧 Troubleshooting

- **Too long**: Set Response Style to Concise
- **Too stiff**: Increase RP Mode
- **No tools**: Set Tool Preference to Active
- **Too technical**: Lower User Expertise

---

**Version**: 1.0  
**Last Updated**: 2025-11-25
