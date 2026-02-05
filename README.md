# 🤖 진피티 (JinPT) - Discord AI Assistant
<img src="https://github.com/user-attachments/assets/20c1f617-87e6-4628-9418-ba415c45ecfb" width="150" />


진피티는 **Google Gemini 2.5 Flash / 3.0 Flash (Preview)** 모델을 탑재한 똑똑하고 친근한 디스코드 AI 어시스턴트입니다. 최신 **Google Interactions API**를 사용하여 도구 호출(Tool Calling)과 상태 관리(State Management)를 효율적으로 처리하며, 협업에 최적화된 다양한 기능을 제공합니다.

---

## ✨ 주요 기능

### 1. 📅 스마트 일정 관리 (Schedule Management)
- **자연어 파싱**: "내일 오후 3시에 미팅 있어", "모레 밤 10시까지 기획서 제출" 등 일상적인 대화에서 일정을 자동으로 추출합니다.
- **자동 알림**: 등록된 일정은 예정된 시간에 맞춰 채널에 임베드(Embed) 알림 메시지를 보냅니다.
- **안전한 데이터 관리**: 로컬 JSON(`data/schedules.json`)을 기반으로 채널별 일정을 안전하게 저장하고 관리합니다.

### 2. 🧠 계층형 대화 기억 시스템 (Tiered Memory)
단순한 히스토리를 넘어, 효율적인 맥락 유지를 위해 3단계 메모리 시스템을 사용합니다:
- **단기 기억 (Short-term)**: 최근 대화 100건을 그대로 기억합니다.
- **중기 기억 (Medium-term)**: 단기 기억이 가득 차면 AI가 핵심 내용을 요약하여 보관합니다.
- **장기 기억 (Long-term)**: 중기 요약본들이 쌓이면 이를 다시 한번 압축하여 영구적인 맥락으로 유지합니다.
- 모든 데이터는 로컬 JSON(`data/chat_histories.json`)에 저장되어 봇 재시작 후에도 유지됩니다.

### 3. 🎯 문맥 기반 AI 리액션
- 대화의 흐름과 감정을 분석하여 가장 적절한 이모티콘(🤔, 🔥, 🙌 등)을 선택해 메시지에 자동으로 리액션을 추가합니다.
- 상황에 맞는 반응으로 봇과의 대화에 생동감을 더합니다.

### 4. 🔗 URL 자동 분석 및 요약
- 메시지에 링크(http/https)가 포함되면 AI가 웹 페이지의 내용을 읽고 분석합니다.
- 핵심 내용을 2-3문장으로 요약하고, 현재 프로젝트와 관련된 인사이트를 제공합니다.

### 5. 🖥️ 자동 코드 리뷰 및 피드백
- `Pygments` 라이브러리를 통해 메시지 내의 코드를 자동으로 감지합니다.
- 단순 텍스트와 코드를 엄격하게 구분하며, 감지된 코드에 대해 **버그 위험성, 개선 포인트(Best Practice)** 등을 MZ 말투로 친절하게 피드백합니다.

### 6. 📝 지식 베이스 및 기록 저장
- "기억해줘", "메모해둬" 등의 요청이 있으면 대화 맥락을 요약하여 `data/trouble_shooting.md` 파일에 마크다운 형식으로 기록합니다.
- 축적된 기록은 향후 AI의 답변 정확도를 높이는 지식 베이스로 활용됩니다.

### 7. 🛠️ 강력한 도구 통합 (Tools & MCP)
- **Google Search**: 실시간 웹 검색을 통해 최신 정보를 답변에 반영합니다.
- **Code Execution**: 복잡한 계산이나 데이터 처리가 필요한 경우 직접 코드를 실행하여 결과를 보여줍니다.
- **MCP (Model Context Protocol)**: 외부 서비스와의 연동을 위한 MCP 서버 설정을 지원합니다.

---

## 🛠️ 기술 스택
- **언어**: Python 3.13
- **핵심 라이브러리**: `discord.py`, `google-genai` (Interactions API)
- **AI 모델**: Google Gemini 2.5 Flash / 3.0 Flash Preview
- **데이터 저장**: JSON (Schedules, Chat History), Markdown (Troubleshooting)

---

## 🤝 프로젝트 정보
- **개발자**: 홍진욱
- **소유자**: 박주원
- **라이선스**: Private Project
