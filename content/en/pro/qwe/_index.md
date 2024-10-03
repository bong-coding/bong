---
title: 은행 데이터베이스
date: 2021-12-10
---

### 코드 분실로 사진과 텍스트로 대체 하겠습니다.

<!--more-->
 델파이와 sql developer를 연동시켜 실행

Ⅰ) 기술 스택
사용 언어
- sqldeveloper
- 델파이

Ⅱ) 주요기능
- 계좌개설
- 고객간 계좌이체간 비밀번호 3회 오류시 계좌 잠김
- 동일 은행간 계좌이체 시 수수료 무료
- 계좌유형을 저축으로 만들시 금액별로 금리 적

기본적인 은행 업무를 수행하는 데이터베이스를 구축

- 예금계좌는 고객의 통장을 관리하기 위한 개체
- 예금계좌 거래내역은 각 예금 계좌의 대한 입출금 내역을 관리하기 위한 개체
- 하나의 입금이나 출금 내역은 거래별로 날짜를 남겨서 출력함

------------------ER다이어 그램----------------------------- 
- 은행은 예금 및 카드 서비스를 고객에게 제공
- 고객 주민번호를 부여하여 식별하며 고객명, 고객주소, 생년월일,이메일, 전화번호,직업 등 의 정보를 가지게 함
- 카드(업무)는 고유의 카드ID(번호)를 부여하여 식별하며 카드 신청일자, 한도금액,결제일자,카드종류,주민번호,계좌ID정보를 가짐

------------------테이블 구조------------------------------- 


■ Customer (security_number, name, address, birthday, email, phone, job) : 기본키(security_number)
■ Card (card_id, request_date, max_out, pay_date, card_type, security_number, account_id) : 기본키(card_id), 외래키(account_id)
■ Account (account_id, account_type, balance, request_card, open_date, name, phone, email, security_number) : 기본키(account_id), 외래키(security_number)
■ Transaction (transaction_id, account_id, transaction_date, transaction_type, information, amount, balance) : 기본키(transaction_id), 외래키(account_id)

■ 은행 업무 관리 데이터베이스 테이블
- 고객 (주민번호, 이름, 주소, 생일, 이메일, 전화번호, 직업)
- 카드 (카드번호, 신청일자, 카드한도, 결제일자, 카드종류, 주민번호, 계좌번호)
- 계좌 (계좌번호, 계좌종류, 예금잔고, 카드신청여부, 예금개설일자, 예금자이름, 전화번호, 이메일, 주민번호)
- 거래 (거래번호, 계좌번호, 입출금날짜, 예금구분, 예금내용, 거래금액, 예금잔고)


