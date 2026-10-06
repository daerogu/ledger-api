# ledger-api

클라우드컴퓨팅실습 W4 과제로 구현한 가계부 API입니다.

FastAPI와 SQLAlchemy를 사용해 API를 구현하고,
Supabase PostgreSQL과 연동한 뒤 Render에 배포했습니다.

## 배포 주소

- Render: https://ledger-api-7ghl.onrender.com
- Swagger Docs: https://ledger-api-7ghl.onrender.com/docs
- GitHub: https://github.com/daerogu/ledger-api

## 기술 스택

- FastAPI
- SQLAlchemy
- PostgreSQL
- Supabase
- Render
- Pydantic

## 주요 기능

### 1. 계좌 관리
- 계좌 생성
- 계좌 목록 조회
- 특정 계좌 조회

### 2. 거래 관리
- 거래 생성
- 거래와 계좌 연결
- 거래와 카테고리 연결

### 3. 관계형 데이터 처리
- Account - Transaction 간 Foreign Key 관계
- SQLAlchemy `relationship` 사용
- 계좌 상세 조회 시 거래 목록 중첩 응답

### 4. 카테고리별 집계
- 지출 거래만 조회
- 카테고리별 금액 합계
- 카테고리별 거래 건수 집계
- SQLAlchemy `GROUP BY` 사용

## 주요 API

| Method | Endpoint | 설명 |
|---|---|---|
| POST | `/accounts` | 계좌 생성 |
| GET | `/accounts` | 전체 계좌 조회 |
| GET | `/accounts/{account_id}` | 특정 계좌 조회 |
| POST | `/transactions` | 거래 생성 |
| GET | `/accounts/{account_id}/detail` | 계좌 및 거래 목록 조회 |
| GET | `/stats/by-category` | 카테고리별 지출 집계 |

## 프로젝트 구조

```text
ledger-api/
├── main.py
├── database.py
├── models.py
├── schemas.py
├── requirements.txt
└── .gitignore