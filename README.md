# 🛒 사용자 웹 로그 데이터 분석

## 📌 프로젝트 개요

Kaggle의 멀티 카테고리 이커머스 플랫폼 행동 데이터를 활용하여, 사용자의 웹 행동 패턴을 분석하고 서비스 개선을 위한 인사이트를 도출한 프로젝트입니다.

- **데이터 출처:** [Kaggle - E-Commerce Behavior Data from Multi Category Store](https://www.kaggle.com/datasets/mkechinov/ecommerce-behavior-data-from-multi-category-store)
- **분석 기간:** 2019년 10월 데이터
- **분석 목적:** 유저 행동 경로 파악 및 최종 목표(구매)까지의 개선점 도출

---

## 🗂️ 데이터 구조

| 컬럼명 | 설명 |
|---|---|
| `event_time` | 이벤트 발생 시각 |
| `event_type` | 이벤트 종류 (`view` / `cart` / `remove_from_cart` / `purchase`) |
| `product_id` | 상품 번호 |
| `price` | 상품 가격 |
| `user_id` | 고객 번호 |
| `user_session` | 세션 ID |

---

## 🔍 분석 내용

### 1. DAU / MAU
- 일별·월별 활성 사용자 수 집계
- 시계열 라인 차트로 트렌드 시각화

### 2. 체류 시간 분석
- 세션별 최초·최종 이벤트 시각 차이로 체류 시간 계산
- 일별 평균 체류 시간 추이 분석

### 3. 전환율 분석 (GMV Decomposition)
> GMV = DAU × 인당 상품조회수 × 구매전환율 × 상품주문단가

- 일별 GMV, 인당 조회수, 구매전환율, 평균 주문단가 산출 및 시각화

### 4. 퍼널 분석
- View → Cart → Purchase 단계별 이탈률 분석
- Plotly를 활용한 인터랙티브 퍼널 차트 시각화

### 5. 리텐션 분석
- 첫 방문일 기준 코호트 분류
- Day 1 / Day 3 / Day 7 리텐션율 추이 분석
- 히트맵 기반 코호트 리텐션 테이블 시각화

### 6. 코호트 리텐션 심화 분석
- 첫 방문 당일 조회 수에 따라 코호트 세분화
- 초기 조회 수가 높을수록 리텐션율이 높아지는 패턴 분석

---

## 🛠️ 사용 기술

| 분류 | 기술 |
|---|---|
| Language | Python |
| 데이터 처리 | pandas |
| 시각화 | matplotlib, seaborn, plotly |
| 쿼리 | SQL (SQLite) |
| 환경 | Jupyter Notebook, Google Colab |

---

## 📁 깃헙 구조

web_log_DA
- notebooks
  - images
  - output
---

## 💡 주요 인사이트

- **퍼널 이탈:** View 대비 Cart 전환율과 최종 Purchase 전환율 간 큰 낙폭 확인 → 장바구니 이후 이탈 구간 개선 필요
- **리텐션 패턴:** 첫 방문 당일 조회 수가 많을수록(31건 이상) 이후 리텐션율이 유의미하게 높음 → 첫 방문 경험 품질이 재방문에 핵심 영향
- **체류 시간 추이:** 일별 평균 체류 시간 변화를 통해 특정 이벤트/프로모션 효과 탐지 가능

## 데이터 및 산출물
💾[데이터](https://drive.google.com/file/d/1826TZ9mtsSkhrEYv6qitIkQXXUkbofI7/view?usp=sharing)
[대시보드](https://drive.google.com/file/d/1aJjX2MenOlR_qyDEZZhF2zLaUpzP8ppd/view?usp=sharing) ⬅️ 태블로
