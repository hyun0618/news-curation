
# 📘 뉴스 큐레이션 서비스 (1인 백엔드 프로젝트)

실시간 뉴스 데이터를 수집하여 인기 키워드 분석 및 사용자 맞춤형 뉴스를 제공하는 백엔드 중심의 개인 프로젝트입니다.  
JWT 인증, Redis 캐시, WebSocket 실시간 통신 등 실무 기술을 반영하였습니다.

---

## 🛠 개발 개요

- **개발 기간**: 2025.06.18 ~ 2025.07.31
- **개발 환경**: IntelliJ IDEA (Community Edition), Spring Boot, MySQL, Redis, EC2
- **주요 기술**: Spring Boot, Spring Security, JPA, JWT, Redis, WebSocket, Swagger

---

## 🧩 주요 기능 명세

| 기능 | 설명 | 엔드포인트 |
|------|------|-------------|
| 회원가입 | 이메일/비밀번호로 계정 생성 | `POST /api/signup` |
| 로그인 | JWT 기반 인증 | `POST /api/login` |
| 뉴스 수집 | 외부 API 연동 (스케줄링) | 내부 서비스 |
| 뉴스 조회 | 최신/키워드 기반 뉴스 목록 | `GET /api/news` |
| 키워드 분석 | 제목 기반 키워드 추출 및 집계 | 내부 서비스 |
| 인기 키워드 조회 | Redis 캐시 기반 인기어 제공 | `GET /api/keywords/popular` |
| 마이페이지 | 사용자별 뉴스 기록 조회 | `GET /api/user/mypage` |
| 실시간 키워드 전송 | WebSocket으로 인기 키워드 전달 | `WebSocket /topic/keywords` |
| API 문서화 | Swagger 연동 | `/swagger-ui/index.html` |

---

## 🗃 ERD 기반 테이블 정의서 (MySQL)

```sql
CREATE TABLE users (
    id BIGINT AUTO_INCREMENT PRIMARY KEY,
    email VARCHAR(255) NOT NULL UNIQUE,
    password VARCHAR(255) NOT NULL,
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE news (
    id BIGINT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(500) NOT NULL,
    content TEXT,
    url VARCHAR(1000),
    published_at DATETIME
);

CREATE TABLE keyword (
    id BIGINT AUTO_INCREMENT PRIMARY KEY,
    word VARCHAR(100) NOT NULL UNIQUE,
    count INT DEFAULT 0
);
...
```

(※ 전체 테이블 정의는 `/docs/schema.sql` 또는 DB 툴 참고)

---

## 🌐 배포 환경

- AWS EC2 + RDS
- Spring Boot JAR 실행
- Swagger 문서 자동 배포

---

## ✨ 회고 & 성장 포인트

- Redis 캐시 구조를 통한 **조회 성능 최적화**
- WebSocket을 활용한 **실시간 알림 시스템 구축**
- JWT 인증과 Spring Security 흐름의 깊은 이해
