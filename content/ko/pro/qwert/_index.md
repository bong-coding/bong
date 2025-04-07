---
title: 사람인 크롤링
date: 2024-11-30
---

## https://github.com/bong-coding/server.git
### 이 프로젝트는 Node.js와 Express.js를 사용하여 정보들을 크롤링하여 만든 채용 정보 플랫폼의 RESTful API. MongoDB를 데이터베이스로 사용하며, JWT를 통한 인증 및 Swagger를 통한 API 문서화를 제공함. 전북대 클라우드 서버로 배포 

---

# 📄 Saramin API

사람인 웹사이트의 채용 정보를 크롤링하고, 사용자 인증 및 채용 공고 관리, 지원/북마크 기능 등을 제공하는 **Node.js 기반 RESTful API 서버**입니다.

> Express.js, MongoDB, JWT, Swagger 기반으로 구축하였으며, 실시간 API 테스트와 보안 기능도 포함되어 있습니다.

---

## ✔️ 프로젝트 소개

- **Node.js + Express.js** 기반의 백엔드 REST API 서버
- **MongoDB Compass**를 통한 데이터 저장
- **JWT 인증** 기반 사용자 관리
- **Cheerio + Axios**로 사람인 웹사이트 크롤링
- **Swagger**를 활용한 API 문서화 및 테스트
- **HTTPS (SSL 인증서)** 기반 보안 서버 구성

---

## ✔️ 주요 기능 요약

### ✔️ 회원 관리 API (`/auth`)
- `POST /auth/register` : 이메일 형식 검증 + 비밀번호 암호화 + 중복 체크
- `POST /auth/login` : 로그인 + JWT 토큰 발급 + 실패 처리
- `GET /auth/profile` : 인증된 사용자 정보 조회
- `PUT /auth/profile` : 사용자 정보 수정 (비밀번호 포함)
- `DELETE /auth/profile` : 회원 탈퇴

---

### 📄 채용 공고 API (`/jobs`)
- `GET /jobs` : 채용 목록 조회 (검색, 필터링, 페이지네이션 지원)
- `GET /jobs/:id` : 공고 상세 정보 조회 + 조회수 증가

---

### 📝 지원 관리 API (`/applications`)
- `POST /applications` : 지원 등록 (중복 방지 포함)
- `GET /applications` : 지원 내역 조회 (상태별 필터링, 날짜 정렬)
- `DELETE /applications/:id` : 지원 취소 (조건 확인 후 상태 변경)

---

### 🌟 북마크 API (`/bookmarks`)
- `POST /bookmarks` : 북마크 추가 또는 제거 (토글 방식)
- `GET /bookmarks` : 북마크 목록 조회 (페이지네이션, 최신순 정렬)

---

## 🔐 인증 및 보안

- **JWT 인증**  
  - Access / Refresh Token 발급 및 갱신
  - 인증된 사용자만 접근 가능한 라우터 보호
- **보안 미들웨어**
  - `helmet` : HTTP 보안 헤더 설정
  - `cors` : CORS 정책 설정
  - `express-validator` : 입력 값 검증
  - `express-rate-limit` : 요청 속도 제한

---

## 🛠 설치 및 실행

### 1. 의존성 설치
```bash
npm install
```
###2. 실행
- 크롤링 실행
```bash
npm run crawl
```
### 3. HTTPS 서버 실행
```bash
sudo node app.js
```
### 중요 SSL 인증서 생성(테스트용)
```bash
openssl req -nodes -new -x509 -keyout server.key -out server.crt -days 365
```
인증서 파일경로는 app.js처럼 실행이 될 것임
```javascript
const key = fs.readFileSync('/home/ubuntu/key.pem');
const cert = fs.readFileSync('/home/ubuntu/cert.pem');
```
---
## 🧾 주요 라이브러리

| 목적             | 라이브러리                              |
|------------------|------------------------------------------|
| 서버 구성         | `express`                                |
| 웹 크롤링         | `axios`, `cheerio`                       |
| 인증             | `jsonwebtoken`, `bcryptjs`               |
| 보안 강화         | `helmet`, `cors`, `express-rate-limit`  |
| DB 연결          | `mongoose`                               |
| 문서화           | `swagger-ui-express`                     |
| 환경 변수 관리    | `dotenv`                                 |
| 로깅             | `winston`                                |

---
### 프로젝트 구조
```bash
├── app.js              # 메인 서버 파일 (SSL 포함)
├── routes/             # 라우터 모듈
├── controllers/        # 요청 처리 로직
├── models/             # Mongoose 모델 정의
├── middlewares/        # 인증/보안 관련 미들웨어
├── utils/              # 유틸 함수
├── crawlers/           # 사람인 크롤러 구현부
├── config/             # 환경 설정 및 Swagger 설정
├── .env                # 환경 변수 파일

```