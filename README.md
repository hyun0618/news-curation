
# 📰 실시간 뉴스 큐레이션

**"지금, 가장 핫한 키워드는?"**  
실시간 뉴스 수집 → 키워드 분석 → 트렌디한 뉴스 피드 제공  
Redis, WebSocket, JWT까지 완전한 실전 백엔드 스택으로 구현한 **프로젝트**

---

## 🔧 Stack

`Spring Boot` `Spring Security` `JPA` `MySQL`  
`Redis` `WebSocket (STOMP)` `JWT` `Swagger` `AWS EC2`

---

## ⚙️ What it does

| 기능 | 설명 |
|------|------|
| 🔐 회원가입 / 로그인 | JWT 인증 기반 사용자 인증 시스템 |
| 📰 뉴스 수집 | 외부 API 연결 → 최신 뉴스 자동 수집 (스케줄링) |
| 🔍 키워드 분석 | 제목 기반 키워드 추출 → Redis에 랭킹 저장 |
| 🚀 실시간 전송 | 인기 키워드를 WebSocket으로 실시간 전송 |
| 🧑‍💻 마이페이지 | 내가 본 뉴스, 좋아요, 관심 키워드 관리 |
| 📄 Swagger | API 테스트 및 명세 자동 생성 |

---

## 🧪 API 테스트

- Swagger UI: 

---

## 🌍 배포

- AWS EC2: Linux + Nginx + Spring Boot JAR 실행
- 도메인 연결 + SSL (선택 적용 가능)

---

## 📁 Structure

```
├── src
│   ├── controller
│   ├── service
│   ├── domain
│   ├── repository
│   └── config
├── resources
│   ├── application.yml
│   └── templates
├── docs
│   ├── schema.sql
│   └── erd.png
└── README.md
```

---

## 🧠 What I Learned

- Redis를 통해 **트래픽 대응 & 캐시 구조** 경험
- WebSocket 기반 **실시간 데이터 흐름** 이해
- JWT + Security 필터 체인 설계 및 적용
- API 명세 자동화 & GitHub 기반 협업 구조

---

## 💬 Contact

📧 email: 
