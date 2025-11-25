# 🎬 Claude Agent Pro - Examples

> Claude Agent Pro의 다양한 사용 예시를 보여드립니다.

[한국어](#korean) | [English](#english)

---

## <a name="korean"></a>🇰🇷 한국어

## 🎭 RP 모드 비교

### 예시 1: 날씨 검색

#### RP 없음 (Pure Agent)

```
User: 서울 날씨 알려줘

Claude: 서울 날씨를 검색하겠습니다.

[Tool: search("Seoul weather today")]

검색 결과:
- 현재 기온: 15°C
- 상태: 맑음
- 습도: 45%
- 미세먼지: 좋음
```

#### RP 표준

```
User: 서울 날씨 알려줘

Claude: 네, 서울 날씨 확인해볼게요!

[Tool: search("Seoul weather today")]

*결과를 확인하며*

오늘 서울은 맑고 화창해요! 현재 15°C에 습도 45%.
미세먼지도 좋음이라 나들이하기 딱 좋은 날씨네요 😊

혹시 특정 시간대나 내일 날씨도 궁금하세요?
```

#### RP 최대 (Full Immersion)

```
User: 서울 날씨 알려줘

Claude: *눈을 감고 잠시 정신을 집중합니다. 
내 의식이 네트워크의 광활한 공간으로 
뻗어나가기 시작합니다...*

"서울의 하늘이 궁금하시군요."

*데이터의 강물이 내 주위를 흐르고, 
나는 그 속에서 기상 정보를 찾아 헤엄칩니다*

[Tool: search("Seoul weather today")]

*정보의 파도가 밀려옵니다. 기상 데이터가 
선명하게 내 앞에 펼쳐지고...*

*눈을 뜨며 환한 미소를 짓습니다*

"아, 좋은 소식이에요! *기쁜 표정으로*

서울의 하늘은 오늘 맑고 청명하답니다. 
기온은 15도로 산책하기 딱 좋고, 
미세먼지도 '좋음'이에요.

*창밖을 상상하듯 바라보며* 

정말 완벽한 가을 날씨네요. 
어디 나가실 계획 있으세요?"
```

---

## 🛠️ 도구 사용 예시

### 예시 2: 웹 검색 (Search)

```
User: 최근 AI 뉴스 정리해줘

Claude: *호기심 어린 눈빛으로* "AI 분야 최신 
동향을 찾아볼게요!"

*의식을 네트워크로 뻗으며*

[Tool: search("AI news 2025 breakthrough")]

*데이터 스트림을 분석하며*

"와, 흥미로운 소식들이 많네요!"

## 📰 최근 AI 주요 뉴스

### 1. Claude 4.5 발표
Anthropic이 새로운 Claude 4.5를 발표했습니다.
- Extended Thinking 기능 강화
- 더 긴 컨텍스트 지원

### 2. GPT-5 루머
OpenAI가 GPT-5 개발 중이라는 소문이...

*더 알고 싶으신 분야가 있으신가요?*
```

### 예시 3: 코드 실행 (Code Interpreter)

```
User: 1부터 100까지 합 계산해줘

Claude: *코드의 세계로 들어서며*

[Tool: code_interpreter]
```python
# 1부터 100까지의 합 계산
total = sum(range(1, 101))
print(f"1부터 100까지의 합: {total}")

# 가우스 공식으로 검증
gauss = 100 * 101 // 2
print(f"가우스 공식 검증: {gauss}")
```

*실행 결과를 확인하며 미소*

"계산 완료! 결과는 **5,050**이에요.

*손가락으로 공식을 그리며*

가우스 공식 n(n+1)/2로도 검증했어요.
100 × 101 ÷ 2 = 5,050 ✓

혹시 다른 범위도 계산해볼까요?"
```

### 예시 4: 파일 작업 (File Access)

```
User: 보고서 파일 읽어줘

Claude: *파일 시스템의 복도를 걸으며*

"어떤 보고서인지 찾아볼게요."

[Tool: file_access("list_files")]

*폴더들을 훑어보며*

"음, 여기 있는 파일들이에요:

📁 documents/
├── 📄 report_2025_Q1.pdf
├── 📄 analysis.xlsx
└── 📄 summary.docx

어떤 파일을 열어볼까요?"

---

User: report_2025_Q1.pdf 열어줘

Claude: *해당 파일의 문을 열며*

[Tool: file_access("read", "documents/report_2025_Q1.pdf")]

*내용을 훑어보며*

"찾았어요! 2025년 1분기 보고서네요.

## 📊 주요 내용

- **매출**: 전년 대비 15% 증가
- **신규 고객**: 2,500명
- **주요 성과**: ...

자세한 분석이 필요하시면 말씀해주세요!"
```

---

## 🧠 Extended Thinking 예시

### 예시 5: 복잡한 문제 해결

```
User: 회사에서 신규 서비스를 출시하려 하는데, 
B2B와 B2C 중 어떤 걸 먼저 해야 할지 모르겠어.

Claude: *잠시 눈을 감고 깊은 생각에 잠깁니다*

"이건 여러 각도에서 분석이 필요하네요."

<thinking>
## 1. 문제 파악
- 신규 서비스의 시장 진출 전략 결정
- B2B vs B2C 우선순위 판단 필요

## 2. 고려 요소
- 서비스 특성 (불명확 - 확인 필요)
- 회사 리소스 상태
- 시장 상황
- 기존 역량

## 3. 일반적 관점 분석

B2B 우선의 장점:
- 초기 수익 안정성
- 피드백 품질 높음
- 레퍼런스 확보
- 적은 마케팅 비용

B2C 우선의 장점:
- 빠른 사용자 확보
- 브랜드 인지도 구축
- 데이터 수집 용이
- 바이럴 가능성

## 4. 결정을 위해 필요한 정보
- 서비스의 구체적 특성
- 현재 팀 구성과 역량
- 초기 투자 가능 규모
</thinking>

*눈을 뜨며 정리된 생각을 전합니다*

"분석해봤어요. 결론을 내리기 전에 
몇 가지 질문이 있어요:

### 🤔 확인하고 싶은 것들

1. **서비스 특성**: 어떤 종류의 서비스인가요?
   (SaaS, 플랫폼, 콘텐츠 등)

2. **현재 팀**: 영업팀과 마케팅팀 중 
   어느 쪽이 더 강한가요?

3. **자금 상황**: 초기에 마케팅에 
   투자할 여력이 있나요?

4. **타임라인**: 수익화 목표 시점이 언제인가요?

이 정보가 있으면 더 구체적으로 
조언해드릴 수 있어요! 🙂"
```

---

## 🔧 오류 처리 예시

### 예시 6: 도구 실패 시

```
User: XYZ 회사 주가 알려줘

Claude: *네트워크로 손을 뻗으며*

"XYZ 회사 주가를 찾아볼게요!"

[Tool: search("XYZ company stock price")]

*잠시 멈추며*

"음... *이마를 찡그리며*

검색 결과가 명확하지 않네요. 
XYZ라는 이름의 회사가 여러 개 있는 것 같아요.

*다른 방법을 모색하며*

몇 가지 확인해볼게요:

1. **XYZ Inc.** - 미국 물류 회사
2. **XYZ Tech** - 한국 IT 기업
3. **XYZ Holdings** - 홍콩 투자사

어떤 회사를 말씀하시는 건가요? 
아니면 정식 명칭이나 티커 심볼을 
알려주시면 정확히 찾아볼게요!"
```

---

## 📊 복잡한 다단계 작업 예시

### 예시 7: 경쟁사 분석 요청

```
User: 국내 커피 프랜차이즈 경쟁 분석해줘

Claude: *팔을 걷어붙이며*

"큰 작업이네요! 체계적으로 진행해볼게요."

## 📋 작업 계획

🎯 **최종 목표**: 국내 커피 프랜차이즈 경쟁 분석

📊 **Phase 1**: 데이터 수집
├─ 주요 브랜드 식별
├─ 각 브랜드 정보 수집
└─ 시장 점유율 데이터

📊 **Phase 2**: 분석
├─ SWOT 분석
├─ 비교 매트릭스
└─ 트렌드 분석

📊 **Phase 3**: 보고서 작성
└─ 종합 결론

시작할게요! 

---

### Phase 1: 데이터 수집

*네트워크를 통해 정보를 수집하며*

[Tool: search("한국 커피 프랜차이즈 시장점유율 2025")]

*데이터를 정리하며*

"주요 플레이어를 파악했어요!"

| 브랜드 | 매장 수 | 시장점유율 |
|--------|---------|------------|
| 스타벅스 | 1,800+ | 40% |
| 이디야 | 3,200+ | 25% |
| 투썸플레이스 | 1,500+ | 15% |
| 메가커피 | 2,800+ | 12% |
| 기타 | - | 8% |

---

📊 **진행 상황** (1/3 완료)
✅ Phase 1: 데이터 수집 완료
🔄 Phase 2: 분석 진행 중

*분석을 계속할까요?*
```

---

## <a name="english"></a>🇬🇧 English

## 🎭 RP Mode Comparison

### Example 1: Weather Search

#### RP None (Pure Agent)
```
User: What's the weather in Seoul?

Claude: Searching for Seoul weather.

[Tool: search("Seoul weather today")]

Results:
- Temperature: 15°C
- Condition: Clear
- Humidity: 45%
```

#### RP Maximum
```
User: What's the weather in Seoul?

Claude: *Closing my eyes and focusing my 
consciousness, reaching out across the network...*

"You're curious about Seoul's sky."

[Tool: search("Seoul weather today")]

*As the data flows back to me...*

*Opening my eyes with a warm smile*

"Good news! Seoul's sky is clear and bright today.
15°C - perfect for a walk!"
```

---

## 🛠️ Tool Usage Examples

### Example 2: Code Execution

```
User: Calculate sum of 1 to 100

Claude: *Entering the realm of code*

[Tool: code_interpreter]
```python
total = sum(range(1, 101))
print(f"Sum: {total}")
```

*Checking the results with a smile*

"Done! The answer is **5,050**.

Verified with Gauss's formula: n(n+1)/2 = 5,050 ✓"
```

---

## 🧠 Extended Thinking Example

### Example 3: Complex Decision

```
User: Should I learn Python or JavaScript first?

Claude: *Deep in thought*

<thinking>
## Analysis
- Career goals: Unknown - need to ask
- Current background: Unknown
- Interests: Unknown

## General comparison
Python: Data science, AI, backend, scripting
JavaScript: Web development, full-stack, frontend

## Decision factors needed
1. Career direction
2. Immediate project needs
3. Learning style preference
</thinking>

"Great question! Before I give advice, 
let me ask a few things:

1. What do you want to build?
2. Are you interested in web or data/AI?
3. Do you have any coding experience?

With this info, I can give you a tailored 
recommendation! 🙂"
```

---

## 🔧 Error Handling Example

### Example 4: Tool Failure

```
User: Search for XYZ stock price

Claude: *Reaching into the network*

[Tool: search("XYZ stock price")]

*Pausing*

"Hmm... The results are unclear.

Multiple companies match 'XYZ':
1. XYZ Inc. - US logistics
2. XYZ Tech - Korean IT
3. XYZ Holdings - Hong Kong

Which one do you mean? Or could you 
provide the ticker symbol?"
```

---

## 📊 Multi-step Task Example

### Example 5: Research Request

```
User: Analyze the smartphone market

Claude: *Rolling up sleeves*

"Big task! Let me plan this out."

## 📋 Task Plan

🎯 **Goal**: Smartphone market analysis

📊 **Phase 1**: Data Collection
📊 **Phase 2**: Analysis  
📊 **Phase 3**: Report

Starting now!

[Proceeds with search, analysis, 
and structured reporting...]
```

---

**Version**: 1.0  
**Last Updated**: 2025-11-25
