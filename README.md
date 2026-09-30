# 최혜주 | AI Developer Portfolio

> 사용자의 불편을 실제 동작하는 AI 시스템으로 만드는 개발자

텍스트 요약과 추천, 텍스트 조건부 이미지 생성, 멀티에이전트 시스템을 연구·개발하고 있습니다. 해결할 문제를 구체화하고, 데이터 처리부터 모델 학습·평가와 사용자 기능까지 하나의 흐름으로 연결하는 데 관심이 있습니다.

**[포트폴리오 PDF 보기](./포트폴리오.pdf)** · [GitHub](https://github.com/ICS-HYEJU) · [Email](mailto:juhye987@kumoh.ac.kr)

## 핵심 역량

| 분야 | 개발 경험 |
| --- | --- |
| LLM 기반 요약·추천 | KoBART 미세조정, 추상 요약 생성, 비유사도 기반 기사 추천 |
| 멀티모달 생성 AI | BioBERT 텍스트 조건부 의료영상 생성, DP-SGD와 LoRA 기반 학습 |
| Multi-Agent 시스템 | LangGraph 상태 공유·조건부 분기, Pydantic 출력 구조화, 검토·수정 흐름 설계 |
| 파이프라인 구현 | 기사 수집·요약·추천·웹 제공 연결, Docker·Linux 기반 개발 |

## 주요 프로젝트

### 1. TextSnack — 추상 요약 기반 기사 요약·추천 시스템

**긴 기사의 핵심을 빠르게 파악하고, 유사한 기사의 반복 노출을 줄이는 웹 서비스입니다.**

- **문제:** 방대한 기사량과 유사한 기사 중심의 추천으로 정보 탐색에 부담 발생
- **구현:** 기사 검색·수집 → KoBART 기반 추상 요약 → 요약문 간 유사도 계산 → 비유사도 기반 Top-N 기사 추천
- **문제 해결:** 요약 모델을 미세조정하고, 5개 추천 알고리즘을 비교해 다양성을 높이는 방식 선정
- **성과:** 요약문 품질 **18% 개선**, 추천 기사 다양성 **약 20% 개선**
- **기여도:** 개인 프로젝트 **100%**

`PyTorch` `Hugging Face` `KoBART` `BeautifulSoup` `Streamlit` `Docker`

관련 모델 학습 저장소: [KoBART-for-summary](https://github.com/ICS-HYEJU/KoBART-for-summary)

### 2. 텍스트 조건부 개인정보 보호 합성 의료영상 생성

**병변 정보를 생성 이미지에 반영하면서, 프라이버시 수준을 정량적으로 제어하는 흉부 X-ray 생성 파이프라인입니다.**

- **문제:** 민감정보 노출 위험으로 의료데이터 활용에 제약 발생
- **구현:** BioBERT 텍스트 임베딩과 Latent Diffusion Model을 연결하고, DP-SGD 기반 미세조정 적용
- **문제 해결:** 샘플별 기울기 연산으로 발생한 GPU 메모리 초과를 LoRA로 해결하고, 전체 파라미터의 **약 0.1%만 학습**
- **운용 구조:** 프라이버시 수준별 Adapter를 활용하는 생성 구조 설계
- **성과:** **ε=1에서 FID 3.4**, **ε=10에서 FID 2.8**
- **기여도:** 개인 연구 **100%** · 진행 중

`PyTorch` `BioBERT` `SwinViT` `Opacus` `DP-SGD` `PEFT / LoRA` `Docker` `Linux`

관련 연구 저장소: [PrivaText-CXR](https://github.com/ICS-HYEJU/PrivaText-CXR) · [DP-LDM](https://github.com/ICS-HYEJU/DP-LDM)

### 3. TripMAS — LangGraph 기반 Multi-Agent 여행 계획 시스템

**사용자의 여행 조건을 구조화하고, 지역 추천·일정 생성·검토를 여러 Agent가 협업해 수행하는 시스템입니다.**

- **문제:** 단일 LLM의 다단계 처리에서 요구조건 누락과 응답 불일치 발생
- **구현:** 사용자 요구 분석 → 지역 추천 → 일정 생성 → 계획 검토·수정
- **담당:** LangGraph와 GraphState 기반 실행 흐름, 조건부 분기 및 Agent 간 정보 전달 구조 설계
- **문제 해결:** Pydantic 스키마로 출력을 구조화해 JSON 응답 오류에 따른 파이프라인 중단 방지
- **검증:** **4개 시나리오 × 7개 평가항목**에서 모두 **14점 만점 중 13점 이상** 확보
- **성과:** 한국정보기술학회 대학생논문경진대회 **동상**
- **기여도:** 2인 팀 **50%**

`LangGraph` `LangChain` `Pydantic` `vLLM` `OpenAI API`

관련 설계·구현 저장소: [LangGraph-Multi-Agent-Travel-Planner](https://github.com/ICS-HYEJU/LangGraph-Multi-Agent-Travel-Planner)

## 논문 및 주요 수상

### 논문

- **LLM 생성 추상 요약문을 활용한 코사인 비유사도 기반 기사 추천 시스템 개발** — 한국통신학회논문지, 2026.02, Scopus
- **LangGraph 기반 멀티에이전트 여행 계획 시스템 설계 및 구현** — 한국정보기술학회, 2026.06, 공동 제1저자

### 수상

| 연도 | 대회·활동 | 수상 |
| --- | --- | --- |
| 2026 | 한컴이노스트림 Physical AI Vision-LLM | 우수상 |
| 2026 | 한국정보기술학회 대학생논문경진대회 | 동상 |
| 2024 | 국립금오공과대학교 창의설계경진대회 | 은상 |
| 2023 | 캠퍼스 특허 유니버시아드 | 우수상 |

## 협업 및 활동

- **Jetson Orin Nano 기반 멀티모달 차량 AI 비서 개발:** Vision-LLM 융합 시스템 구현
- **AI 반도체 아이디어 해커톤 멘토:** 참가팀의 AI 프로젝트 개발과 결과 설명 지원
- **캠퍼스 특허 유니버시아드:** 생성형 AI 관련 특허 분석 및 전략 수립
- **전공 동아리 E.C.C. 회장:** 교육과 팀 활동 운영
- **지능형컴퓨팅연구실 학부연구생:** 딥러닝 모델 구현 및 연구 경험

## 기술 스택

| 구분 | 기술 |
| --- | --- |
| 언어 | Python, C/C++ |
| 딥러닝 | PyTorch, TensorFlow, Hugging Face |
| 생성 모델·학습 | KoBART, BioBERT, Latent Diffusion Model, DP-SGD, LoRA |
| Agent | LangGraph, LangChain, Pydantic, vLLM |
| 서비스·개발 환경 | Streamlit, BeautifulSoup, Docker, Linux |

---

프로젝트별 구조, 실험 결과와 상세 활동은 **[포트폴리오 PDF](./포트폴리오.pdf)**에서 확인할 수 있습니다.
