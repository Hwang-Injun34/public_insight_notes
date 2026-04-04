# 📁 Public Insight 노트

> 정책 데이터를 “검색”이 아닌 **관계 기반 탐색**으로 전환한 플랫폼  
> 지식 그래프 기반 정책 데이터 서비스 **PublicInsight**의 구조, 기술 스택, 핵심 구현을 정리한 프로젝트 문서

---

## 🧾 프로젝트 정보
- 프로젝트 형태: 2인 팀 프로젝트 (캡스톤디자인 / 학술제)
- 개발 기간: 2025.04 ~ 2025.11
- 수상 내역: 2025 캡스톤디자인 학술제 최우수상 수상 (전체 00팀 중 상위 %)
- 서비스: https://public-insight.co.kr/
- 시연 영상: https://youtu.be/ToBQldXWTEY

🔗 GitHub  
- https://github.com/Hwang-Injun34/public_insight

---

## 📌 프로젝트 개요
PublicInsight는 분산된 정책 데이터를 통합하고, 지식 그래프 기반으로 관계를 연결하여  
사용자가 정책을 탐색하고 이해할 수 있도록 돕는 플랫폼입니다.

기존 정책 서비스는 키워드 검색 중심으로 동작하여 정책 간 관계와 맥락을 파악하기 어렵다는 한계가 있습니다.  
이를 해결하기 위해 Knowledge Graph + NLP + 추천 시스템을 결합한 구조를 설계 및 구현하였습니다.

---

## 🚨 문제 정의
- 정책 데이터가 기관별로 분산되어 있음
- 키워드 검색 중심 → 맥락 기반 탐색 어려움
- 사용자 맞춤형 추천 기능 부족

---

## 💡 해결 전략
- Neo4j 기반 지식 그래프 구축
- 정책 간 관계(유사 정책, 대상, 조건 등) 연결
- Node2Vec 임베딩 기반 유사도 계산
- KoBART 기반 문서 요약
- 사용자 행동 로그 기반 개인화 추천 시스템 구축
- 인터랙티브 그래프 UI를 통한 탐색 경험 개선

---

## 🏗️ 시스템 아키텍처
![architecture](https://github.com/user-attachments/assets/e749be56-d526-46db-991b-ac34b035c27c)

---

## 🔄 데이터 파이프라인
PublicInsight는 수집된 정책 데이터를 지식 그래프로 변환하고,  
이를 기반으로 추천 및 탐색 기능을 제공하는 구조로 설계되었습니다.

1. **데이터 수집**
   - 다양한 정책 데이터 수집 (정형 / 비정형)

2. **전처리 및 NLP 처리**
   - 텍스트 정제 및 키워드 추출
   - KoBART 기반 문서 요약

3. **지식 그래프 생성**
   - 정책 간 관계 추출
   - Neo4j 기반 그래프 구조화

4. **그래프 임베딩**
   - Node2Vec을 활용한 벡터화
   - 정책 간 유사도 계산

5. **추천 시스템**
   - 유사 정책 추천
   - 사용자 행동 기반 개인화 추천

6. **서비스 제공**
   - FastAPI 서버를 통한 데이터 제공
   - Next.js 기반 인터랙티브 UI

![pipeline](https://github.com/user-attachments/assets/d5f7e6b2-ee68-406c-be54-2350d214aa23)

---

## ⚙️ 주요 기능

### 1. 지식 그래프 기반 탐색
- 정책 간 관계 시각화
- 노드 확장형 인터랙션
- 마인드맵 형태 UI 제공

### 2. 그래프 기반 추천 시스템
- Node2Vec 임베딩 활용
- 정책 간 유사도 기반 추천
- 숨겨진 관계 탐색 가능

### 3. AI 기반 문서 요약
- KoBART 모델 활용
- 긴 정책 문서를 핵심 위주로 요약
- 정보 접근성 향상

### 4. 사용자 행동 기반 추천
- 검색 / 클릭 / 북마크 로그 수집
- Seed 노드 기반 개인화 추천
- 사용자 관심사 예측

---

## 👤 역할 분담

### 👤 남궁명수
- 전체 인프라 설계 및 서버 구축
- Docker / Nginx 기반 배포 환경 구성
- FastAPI 백엔드 아키텍처 설계
- JWT 인증 및 미들웨어 구현
- 정책 데이터 크롤링 및 수집 파이프라인 구현
- Elasticsearch 기반 검색 시스템 설계 및 구현
- 사용자 / 관리자 기능 개발

🔗 GitHub  
- 개인 역할 총 정리 및 회고 (추가 예정)

---

## 🛠 기술 스택

### Backend
- FastAPI
- SQLAlchemy

### Frontend
- Next.js
- TypeScript

### Database
- MySQL
- Neo4j (Graph DB)

### Search & Cache
- Elasticsearch
- Redis

### AI / ML
- Node2Vec
- KoBART
- Scikit-learn
- Kiwi

### Infrastructure
- Docker
- Docker Compose
- Nginx

---

## 🗂 정리 방식
- ▶️ 시연 영상: YouTube
- 📄 보고서: PDF
- 📗 개념 정리: Notion
- 🔗 코드: GitHub
