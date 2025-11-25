# 📦 Claude Agent Pro - Handoff Document

> 기술 인수인계 및 개발자 문서입니다.

[한국어](#korean) | [English](#english)

---

## <a name="korean"></a>🇰🇷 한국어

## 📁 프로젝트 아키텍처

### 파일 구조

```
📦 Claude Agent Pro v1.0
├── 📄 README.md                           # 프로젝트 소개
├── 📂 presets/
│   └── 📄 claude_agent_pro_v1.0.json     # 메인 프리셋 (RisuAI format)
├── 📂 modules/
│   └── 📄 claude_agent_module_v1.0.json  # 전략 모듈 (Lorebook format)
├── 📂 docs/
│   ├── 📄 FEATURES.md                     # 기능 상세 설명
│   ├── 📄 USAGE_GUIDE.md                  # 사용 가이드
│   ├── 📄 EXAMPLES.md                     # 대화 예시
│   └── 📄 HANDOFF.md                      # 인수인계 문서 (이 파일)
└── 📂 assets/
    └── 📄 comparison.md                   # 프리셋 비교
```

### 핵심 파일 설명

#### 1. Preset (presets/claude_agent_pro_v1.0.json)

RisuAI 프리셋 파일로, 다음을 포함:

- **기본 설정**: 모델, 온도, 컨텍스트 크기 등
- **promptTemplate**: 15개의 프롬프트 템플릿 배열
- **customPromptTemplateToggle**: 15개 토글 정의
- **customPromptTemplateToggleRecords**: 토글 기본값
- **regex**: 출력 정리 정규식

#### 2. Module (modules/claude_agent_module_v1.0.json)

RisuAI Lorebook 형식으로, 8개의 전략적 엔트리:

- Tool Selection Strategy
- Task Decomposition Framework
- Error Recovery Protocol
- Extended Thinking Usage
- Character Embodiment
- Adaptive Communication
- Creative Problem Solving
- Metacognitive Monitoring

---

## 🔧 Toggle System 구현

### Toggle 정의 문법

```
=그룹이름=group
toggle_id=표시이름=타입=옵션들
==groupend
```

### 현재 구현된 Toggle

```javascript
{
  "customPromptTemplateToggle": `
=🤖Agent Pro Claude=group
rp_mode=🎭RP 강도=select=없음,최소,표준,강화,최대
thinking_visibility=💭사고 표시=select=숨김,요약,부분,전체
thinking_depth=🧠사고 깊이=select=minimal,low,medium,high,maximum
tool_narrative=🛠️도구 묘사=select=기능적,간략한_RP,상세한_RP,몰입형_RP
response_style=📝응답 스타일=select=간결,표준,상세,매우상세
task_mode=🎯작업 모드=select=일반,분석,창작,코딩,학습,탐험
personality=✨성격 표현=select=절제,균형,친근,매우친근
user_expertise=👤사용자 수준=select=초보,중급,고급,전문가
output_format=📋출력 형식=select=자연어,구조화,기술문서,대화형,스토리텔링
follow_up=🔄후속 제안=select=없음,최소,적극,매우적극
creativity=🎨창의성=select=보수적,균형,창의적,매우창의적
tool_preference=⚙️도구 사용=select=자동,적극,보수적,확인필요
verification=✅검증 수준=select=기본,강화,엄격
safety=🛡️안전성=select=표준,강화,최대
emotional_expression=💫감정 표현=select=없음,절제,자연스러움,풍부함
==groupend
`
}
```

### Toggle 값 접근

프롬프트 템플릿에서 Handlebars 문법 사용:

```handlebars
{{getglobalvar::toggle_id}}
```

예시:
```handlebars
현재 RP 모드: {{getglobalvar::rp_mode}}
```

---

## 📝 Handlebars Template 사용법

### 조건문

```handlebars
{{#if {{? 조건}}}}
참일 때 내용
{{else}}
거짓일 때 내용
{{/if}}
```

### 문자열 비교

```handlebars
{{#if {{? {{getglobalvar::rp_mode}}=="최대"}}}}
최대 RP 모드 활성화
{{/if}}
```

### 숫자 비교

```handlebars
{{#if {{? {{getglobalvar::thinking_visibility}}>=2}}}}
사고 표시 레벨 2 이상
{{/if}}
```

### 중첩 조건

```handlebars
{{#if {{? {{getglobalvar::rp_mode}}=="최대"}}}}
최대 모드
{{else if {{? {{getglobalvar::rp_mode}}=="강화"}}}}
강화 모드
{{else}}
기타 모드
{{/if}}
```

### Slot 삽입

```handlebars
{{#if {{persona}}}}
{{persona}}
{{/if}}

{{#if {{memory}}}}
{{memory}}
{{/if}}
```

---

## 📊 Prompt Template 구조

### Template 객체 형식

```json
{
  "name": "템플릿 이름",
  "prompt": "프롬프트 내용",
  "role": "system|user|bot",
  "type": "plain|memory|lorebook|authornote|chat",
  "type2": "persona|description",  // optional
  "rangeStart": 0,                  // chat type용
  "rangeEnd": -2                    // chat type용
}
```

### 현재 구현된 15개 템플릿

| # | 이름 | Role | Type | 설명 |
|---|------|------|------|------|
| 1 | System Identity | system | plain | Claude의 기본 정체성 |
| 2 | Extended Thinking Framework | system | plain | 사고 프레임워크 |
| 3 | Roleplay System | system | plain | RP 모드별 지침 |
| 4 | Tool Use Guidelines | system | plain | 도구 사용 가이드 |
| 5 | Task Decomposition | system | plain | 작업 분해 프레임워크 |
| 6 | Cognitive Architecture | system | plain | 4단계 인지 프로세스 |
| 7 | User Profile | system | plain+persona | 사용자 정보 슬롯 |
| 8 | Task Context | system | plain+description | 작업 컨텍스트 슬롯 |
| 9 | Memory | system | memory | 메모리 슬롯 |
| 10 | Lorebook | system | lorebook | 로어북 슬롯 |
| 11 | Author Note | system | authornote | 작성자 노트 슬롯 |
| 12 | Chat History | system | chat | 이전 대화 (0 ~ -2) |
| 13 | Current Message | user | chat | 현재 메시지 (-1 ~ end) |
| 14 | Output Guidelines | system | plain | 출력 가이드라인 |
| 15 | Claude Prefill | bot | plain | Claude 응답 시작 |

---

## 🔌 확장 포인트

### 새 Toggle 추가

1. `customPromptTemplateToggle`에 새 toggle 정의 추가
2. `customPromptTemplateToggleRecords`에 기본값 추가
3. 관련 promptTemplate에서 참조

### 새 Lorebook Entry 추가

```json
{
  "id": "unique-id",
  "name": "표시 이름",
  "content": "Markdown 형식 콘텐츠",
  "keywords": ["trigger", "words"],
  "enabled": true,
  "priority": 100,
  "alwaysActive": false,
  "position": "before_char"
}
```

### 새 Prompt Template 추가

1. `promptTemplate` 배열에 새 객체 추가
2. 적절한 위치 선정 (순서가 중요)
3. 관련 toggle과 연계

---

## ⚠️ 알려진 제한사항

### 1. RisuAI 의존성

- RisuAI 특정 문법 사용 (다른 클라이언트와 호환 안 됨)
- Handlebars 문법이 RisuAI 버전에 따라 다를 수 있음

### 2. Claude 모델 의존성

- Extended Thinking은 Claude 4.5+ 필요
- 일부 기능은 Claude API 직접 연결 필요

### 3. MCP Tool 의존성

- MCP 도구가 연결되어 있어야 도구 사용 가능
- 도구 가용성은 환경에 따라 다름

### 4. 토큰 사용량

- 15개 프롬프트 템플릿으로 기본 시스템 프롬프트가 큼
- 컨텍스트 윈도우 관리 필요

---

## ✅ 테스트 체크리스트

### 프리셋 Import

- [ ] JSON 파일이 유효한 형식인가?
- [ ] RisuAI에서 오류 없이 Import 되는가?
- [ ] 모든 토글이 표시되는가?

### 토글 동작

- [ ] 각 토글 변경이 응답에 반영되는가?
- [ ] RP 모드 변경이 스타일에 영향을 주는가?
- [ ] 사고 표시 토글이 작동하는가?

### 프롬프트 렌더링

- [ ] Handlebars 조건문이 올바르게 평가되는가?
- [ ] Slot이 제대로 삽입되는가?
- [ ] 특수문자가 깨지지 않는가?

### Tool 사용

- [ ] MCP 도구가 호출되는가?
- [ ] 도구 묘사 스타일이 토글에 따라 변하는가?
- [ ] 도구 실패 시 복구가 되는가?

### 모듈 (Lorebook)

- [ ] 트리거 키워드에 엔트리가 활성화되는가?
- [ ] 한글/영어 키워드 모두 작동하는가?

---

## 🤝 기여 가이드

### 버그 리포트

1. 이슈 템플릿 사용
2. 재현 단계 포함
3. 예상 결과 vs 실제 결과 명시

### 기능 제안

1. 유스케이스 설명
2. 예상되는 구현 방안 제안
3. 기존 기능과의 호환성 고려

### Pull Request

1. 작은 단위로 분리
2. 관련 문서 업데이트
3. 테스트 체크리스트 확인

---

## <a name="english"></a>🇬🇧 English

## 📁 Project Architecture

### File Structure

```
📦 Claude Agent Pro v1.0
├── presets/claude_agent_pro_v1.0.json  # Main preset
├── modules/claude_agent_module_v1.0.json  # Strategy module
├── docs/  # Documentation
└── assets/  # Resources
```

### Key Components

1. **Preset**: 15 prompt templates + 15 toggles
2. **Module**: 8 strategic lorebook entries
3. **Documentation**: Features, usage, examples

## 🔧 Toggle System

### Definition Syntax

```
=GroupName=group
toggle_id=Display Name=type=options
==groupend
```

### Access in Templates

```handlebars
{{getglobalvar::toggle_id}}
```

## 📝 Handlebars Syntax

### Conditionals

```handlebars
{{#if {{? condition}}}}
content
{{else}}
alternative
{{/if}}
```

### String Comparison

```handlebars
{{#if {{? {{getglobalvar::rp_mode}}=="maximum"}}}}
Maximum mode active
{{/if}}
```

## ⚠️ Known Limitations

1. RisuAI dependency
2. Claude 4.5+ for Extended Thinking
3. MCP tools required for tool usage
4. Large system prompt (token usage)

## ✅ Test Checklist

- [ ] Valid JSON format
- [ ] Imports without errors
- [ ] All toggles visible
- [ ] Toggle changes affect responses
- [ ] Handlebars render correctly
- [ ] Tools work as expected
- [ ] Lorebook triggers activate

## 🤝 Contributing

1. Bug reports: Use issue template
2. Feature requests: Describe use case
3. PRs: Small, focused changes

---

**Version**: 1.0  
**Last Updated**: 2025-11-25
