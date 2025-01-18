---
title: 사람인 크롤링
date: 2024-11-30
---

## https://github.com/bong-coding/server.git
### 이 프로젝트는 Node.js와 Express.js를 사용하여 정보들을 크롤링하여 만든 채용 정보 플랫폼의 RESTful API. MongoDB를 데이터베이스로 사용하며, JWT를 통한 인증 및 Swagger를 통한 API 문서화를 제공함. 전북대 클라우드 서버로 배포 

Ⅰ) 기술 스택    
- Javascript
- Express.js
- Node.js
- Mongo DB


Ⅱ) 주요 기능  
EST API 개발
-기본 CRUD 기능: 각 리소스에 대한 Create, Read, Update, Delete 기능 제공.
회원 관리 API (/auth):
- 회원 가입 (POST /auth/register): 이메일 형식 검증, 비밀번호 암호화, 중복 회원 검사, 사용자 정보 저장.
-로그인 (POST /auth/login): 사용자 인증, JWT 토큰 발급, 로그인 이력 저장, 실패 시 에러 처리.
- 회원 정보 수정 (PUT /auth/profile): 인증 미들웨어 적용, 비밀번호 변경, 프로필 정보 수정.
- 회원 정보 조회 (GET /auth/profile): 인증된 사용자의 프로필 정보 제공.
- 회원 탈퇴 (DELETE /auth/profile): 인증된 사용자의 계정 삭제.
채용 공고 API (/jobs):
- 공고 목록 조회 (GET /jobs): 페이지네이션, 검색, 필터링 기능 제공.
- 공고 상세 조회 (GET /jobs/:id): 공고의 상세 정보 제공, 조회수 증가.
지원 관리 API (/applications):
- 지원하기 (POST /applications): 인증 확인, 중복 지원 체크, 지원 정보 저장.
- 지원 내역 조회 (GET /applications): 사용자별 지원 목록 제공.
- 지원 취소 (DELETE /applications/:id): 인증 확인, 취소 가능 여부 확인, 상태 업데이트.
북마크 API (/bookmarks):
- 북마크 추가/제거 (POST /bookmarks): 인증 확인, 북마크 토글 처리.
- 북마크 목록 조회 (GET /bookmarks): 사용자별 북마크 목록 제공, 페이지네이션 및 정렬.
d. 인증 및 보안 구현
JWT 기반 인증:
- Access Token 발급 및 검증: 로그인 시 Access Token 발급, 미들웨어를 통한 검증.
- Refresh Token 구현: 로그인 시 Refresh Token 발급.
- 토큰 갱신 메커니즘: 별도의 엔드포인트에서 Refresh Token을 사용하여 새로운 Access Token 발급.
보안 미들웨어:
- 인증 미들웨어: 보호된 라우트에 대한 접근 제어.
- 입력 데이터 검증: express-validator를 사용한 데이터 검증.
- Rate Limiting: express-rate-limit을 사용하여 API 요청 속도 제한.
기타 보안 강화:
- Helmet: HTTP 헤더 보안 설정.
- CORS 설정: 교차 출처 리소스 공유 제어.
주요 엔드포인트별 구현 내용
a. 회원 관리 API (/auth)
회원 가입 (POST /auth/register):
- 이메일 형식 검증.
- 비밀번호 암호화.
- 중복 회원 검사.
- 사용자 정보 저장.
로그인 (POST /auth/login):
-사용자 인증.
- JWT 토큰 발급.
- 로그인 실패 시 에러 처리.
회원 정보 수정 (PUT /auth/profile):
- 인증 미들웨어 적용.
- 비밀번호 변경 및 프로필 정보 수정.
회원 정보 조회 (GET /auth/profile):
- 인증된 사용자의 정보 제공.
회원 탈퇴 (DELETE /auth/profile):
- 인증된 사용자의 계정 삭제.
b. 채용 공고 API (/jobs)
공고 목록 조회 (GET /jobs):
- 페이지네이션 처리 (기본 페이지 크기: 20).
- 검색 및 필터링 기능 제공.
공고 상세 조회 (GET /jobs/:id):
- 공고의 상세 정보 제공.
- 조회수 증가 기능 구현.
c. 지원 관리 API (/applications)
지원하기 (POST /applications):
- 인증 확인.
- 중복 지원 체크.
- 지원 정보 저장.
지원 내역 조회 (GET /applications):
- 사용자별 지원 목록 제공.
- 상태별 필터링 및 날짜별 정렬.
지원 취소 (DELETE /applications/:id):
- 인증 확인.
- 취소 가능 여부 확인.
- 지원 상태 업데이트.
d. 북마크 API (/bookmarks)
북마크 추가/제거 (POST /bookmarks):
- 인증 확인.
- 북마크 토글 처리 (추가 또는 제거).
- 북마크 목록 조회 (GET /bookmarks):
- 사용자별 북마크 목록 제공.
- 페이지네이션 및 최신순 정렬.
