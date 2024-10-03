---
title: 소켓통신 카카오톡 클론코딩
date: 2022-03-30
---
### 코드 분실로 사진과 텍스트로 대체 하겠습니다.
 소켓으로 양방향 통신을 배워 카카오톡을 만들어 보고 싶어 만들어봤습니다.

Ⅰ) 기술 스택
사용 언어
- TypeScript

Client
- React V16
- React Router V5
- Redux
- Redux-saga
- Styled-components
- Socket.io-client
- Webpack

Server
- Node.js - Express
- Sequelize
- Socket.io
- MySQL

Ⅱ)  주요 기능
- 프로필 창에서 상태메시지, 배경사진, 프로필 사진 등을 변경할 수 있음
- 사용자들이 채팅방을 만들어 1:1 대화가 가능, 채팅이 온 것을 사용자가 알 수 있도록 읽지 않은 채팅 숫자를 화면에 표시함
- 무한 스크롤을 이용하여, 채팅방에서 스크롤을 위로 올리며, 이전 채팅 나타남
- 친구추가, 검색,차단, 채팅메뉴 설정

Ⅲ) 프로젝트 구현기술
- CRA(create-react-app)를 통해 프로젝트를 진행하지 않고, Webpack을 이용하여 직접 개발환경을 설정하였습니다.
 