# 허예준 | Heo Yejun

**LLM Systems · Python · Data Analysis**

LLM 기반 시스템과 데이터 분석 프로젝트를 만들고 있습니다.
데이터 수집부터 판단·검증·자동화까지 연결하고, 설계의 근거와 한계를 코드와 문서로 남깁니다.

## 대표 프로젝트

| 프로젝트 | 무엇을 만드는가 | 주요 기술 |
| --- | --- | --- |
| [SIMA](https://github.com/YJEFFf/Stock-Investment-Multi-Agent) | LLM 분석과 코드 기반 리스크 검증을 분리한 주식 투자 판단 시스템 | Python · Pydantic · Flask · AWS EC2 |
| [DNB](https://github.com/YJEFFf/DNB) | 뉴스 수집 → LLM 주요 뉴스 선정·요약 → 텔레그램 알림 자동화 | Python · Claude API · GitHub Actions |
| [화성시 자전거 출퇴근 분석](https://github.com/YJEFFf/hwaseong-bike-commute-2026) | 끊긴 자전거망과 공장 일자리 접근성을 분석한 팀 프로젝트 | Python · Pandas · Shapely · SciPy |

### SIMA · 멀티에이전트 투자 판단

차트·뉴스·공시를 독립적으로 분석하고, 강세·약세 논거를 종합한 뒤 코드가 주문 승인 여부를 검증합니다.

- **설계:** 매수 신호가 없는 날도 정상 결과로 처리하며, 분석 재시도로 신호를 채우지 않습니다.
- **구현:** 구조화된 데이터 계약, 결정론적 리스크 게이트, 체결 대조·복구, 운영 기록을 보는 PWA.
- **검증:** KIS 모의투자와 실시간 표본을 바탕으로 평가합니다. 예측력·수익성이 입증된 시스템으로 제시하지 않습니다.

[설계 배경](https://github.com/YJEFFf/Stock-Investment-Multi-Agent/blob/main/docs/PLAN.md) · [테스트](https://github.com/YJEFFf/Stock-Investment-Multi-Agent/tree/main/tests) · [평가 기록](https://github.com/YJEFFf/Stock-Investment-Multi-Agent/tree/main/docs/evaluations)

### DNB · 매일 아침 뉴스 브리핑

네이버 뉴스의 5개 종합일간지 기사 목록을 모으고, Claude가 제목·언론사·시각을 바탕으로 주요 뉴스를 선정·요약합니다.

- **자동화:** GitHub Actions의 예약 실행과 날짜를 지정한 수동 실행을 지원합니다.
- **구현:** 날짜별 수집, 링크 중복 제거, 출처번호를 실제 기사 링크로 변환, 긴 알림 분할 전송.
- **범위:** 기사 본문을 읽는 요약기가 아니라 제목 기반 브리핑입니다.

[실행 안내](https://github.com/YJEFFf/DNB#로컬에서-실행하기) · [파이프라인](https://github.com/YJEFFf/DNB/blob/main/src/main.py) · [워크플로우](https://github.com/YJEFFf/DNB/blob/main/.github/workflows/daily-news.yml)

### 길은 있는데 왜 차로 출근할까 · 교통 데이터 분석

공식 GIS와 OpenStreetMap을 결합해 자전거망의 단절, 공장 일자리 접근성, 연결 개선 시나리오를 분석했습니다.

- **팀:** 북적북적 · 장준용, 허예준 / 2026 AI 교통 데이터 분석 공모전 제출 프로젝트.
- **참여:** 선행 연구·원자료 점검, 분류 규칙·시나리오 작성, 교차 검수.
- **결과:** 공개 제출본 기준 연결 덩어리 383개, 자전거 15분 직선거리 안의 공장 일자리 중 자전거망으로 닿는 몫 3.7%. 거리 기반 분석이며 실제 통근 수요를 측정한 값은 아닙니다.

[분석 방법](https://github.com/YJEFFf/hwaseong-bike-commute-2026/blob/main/METHOD.md) · [집계 결과](https://github.com/YJEFFf/hwaseong-bike-commute-2026/tree/main/commute/results) · [재현 조건](https://github.com/YJEFFf/hwaseong-bike-commute-2026/blob/main/REPRODUCE.md) · [참여·AI 활용 기록](https://github.com/YJEFFf/hwaseong-bike-commute-2026/blob/main/AI_USAGE.md)

## 프로젝트에서 다루는 기술

| 영역 | 기술과 적용 |
| --- | --- |
| LLM 시스템 | Python, Pydantic, 구조화된 출력, 데이터 소스별 분석, 코드 기반 검증 |
| 서비스·자동화 | Flask, REST API, AWS EC2, cron, GitHub Actions, PWA |
| 데이터 분석 | Pandas, NumPy, Shapely, PyProj, SciPy, Matplotlib |
| 검증·기록 | pytest, 모의 응답 테스트, 민감도 분석, 데이터 출처·재현 조건 문서화 |

## 이어지는 작업

- [AI-Investing-Agent](https://github.com/YJEFFf/AI-Investing-Agent): 차트 이미지 기반 초기 투자 에이전트. 반복 분석의 설계 한계를 정리하고 SIMA로 재설계했습니다.
- [hwaseong-bike-to-work](https://github.com/YJEFFf/hwaseong-bike-to-work): 자전거 출퇴근과 채용공고의 자차 조건을 함께 다룬 분석 저장소. 위 공모전 제출본과는 분석 범위·스냅샷이 다릅니다.
