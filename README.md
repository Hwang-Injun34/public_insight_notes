# 📁 Public Insight 노트

> 지식 그래프 기반 정책 데이터 플랫폼 PublicInsight의 설계, 구현, 실험 과정을 정리한 프로젝트 노트입니다.
> 이론 및 아키텍처 설계는 Notion 또는 PDF, 실습 코드 및 서비스 구현은 GitHub 저장소로 관리합니다.

---

## 🧾 프로젝트 정보
- 프로젝트 형태: 2인 팀 프로젝트(캡스톤디자인 / 학술제)
- 개발 기간: 2025.04 ~ 2025.11
- 수상 내역: 2025 캡스톤디자인 학술제 최우수상 수상(전체 00팀 중 상위 %)
- 서비스: https://public-insight.co.kr/
- 시연 영상: [youtube](https://youtu.be/ToBQldXWTEY?si=rhT2M7hTUg0e1V90)

🔗 **GitHub 저장소**  
- [public_insight](https://github.com/Hwang-Injun34/public_insight)

---

## 📌 프로젝트 개요
PublicInsight는 분산되어 있는 정책 데이터를 통합하고, 
지식 그래프 기반으로 관계를 연결하여 
사용자가 정책을 탐색하고 이해할 수 있도록 돕는 플랫폼입니다.

기존 정책 서비스는 키워드 검색 중심으로 동작하여
정책 간 관계나 맥락을 파악하기 어렵다는 한계가 있습니다.

이러한 문제를 해결하기 위해 
Knowledge Graph + NLP + 추천 시스템을 결합한 구조를 설게 및 구현하였습니다.

---

## 🚨 문제 정의
- 정책 데이터가 기관별로 분산되어 있음
- 키워드 검색 중심 → 맥락 기반 탐색 어려움
- 사용자 맞춤형 추천 기능 부족

## 💡 해결 전략
- 정책 데이터를 Neo4j기반 지식 그래프로 구조화
- 정책 간 관계(유사 정책, 대상, 조건 등) 연결
- Node2Vec 기반 임베딩으로 유사도 계산
- KoBART 기반 문서 요약으로 정보 접근성 향상
- 사용자 행동 로그 기반 개인화 추천 시스템 구축
- 인터랙티브 그래프 UI를 통한 탐색 경험 개선

---

## 🏗️ 시스템 아키텍처
<img width="1195" height="799" alt="Monitonng" src="https://github.com/user-attachments/assets/e749be56-d526-46db-991b-ac34b035c27c" />

---

## 데이터 흐름
1. 데이터 수집
2. 전처리 & NLP
3. 지식 그래프 생성 (Neo4j)
4. 그래프 임베딩 (Node2Vec)
5. 추천 시스템
6. FastAPI 서버
7. Next.js 프론트엔드(그래프 UI)

<img width="1391" height="798" alt="504612359-c1ded3fa-e229-4662-a3ba-08261974b0a0" src="https://github.com/user-attachments/assets/d5f7e6b2-ee68-406c-be54-2350d214aa23" />

---

## ⚙️ 주요 기능
### 1. 지식 그래프 기반 탐색
- 정책 간 관계 시가화
- 노드 확장형 인터랙션
- 마인드맵 형태 UI 제공

### 2. 그래프 기반 추천 시스템
- Node2Vec임베딩 활용
- 정책 간 유사도 기반 추천
- 숨겨진 관계 탐색 가능

### 3. AI 기반 문서 요약
- KoBART 모델 활용
- 긴 정책 문서를 핵심 위주로 압축
- 정보 접근성 향상

### 4. 사용자 행동 기반 추천
- 검색/클릭/북마크 로그 수집
- Seed 노드 기반 개인화 추천
- 사용자 관심사 예측

---

## 📊 데이터 파이프라인
- 다양한 정책 데이터 수집(정형/비정형)
- 텍스트 전처리 및 키워드 추출
- 관계 추출 및 그래프 생성
- Neo4j 자동 적재 파이프라인 구축

---

## 역할 분담
### 👤 본인(남궁명수)
- 홈 서버 구축 및 전체 인프라 설계
- Docker/Nginx 기반 서비스 배포 환경 구성
- FastAPI 기반 백엔드 아키텍처 설계
- JWT 인증 및 미들웨어 설계
- 정책 데이터 크롤링 및 수집 파이프라인 구현
- Elasticsearch 기반 검색 엔진 설계 및 구현
- 사용자 /관리자 기능 구현

🔗 **GitHub 저장소**  
- [개인 역할 총 정리 및 회고]()

---

## 🛠 기술 스택
### Backend
- FastAPI
- SQLAlchemy

### Frontend
- Next.js(React)
- TypeScript

### Database
- MySQL
- Neo4j(Graph DB)
- MySQL

### Search & Cache 
- Elasticsearch
- Redis

### AI/ML 
- Node2Vec
- KoBART
- Scikit-learn
- Kiwi

### infrastructure 
- Dokcer / Docker-compose
- Nginx

---

## 🗂 정리 방식
- ▶️ **시연 영상**: YouTube
- 📄 **이론 & 개념, 보고서**: PDF
- 📗 **이론 & 개념**: Notion
- 🔗  **실습 & 코드**: GitHub

