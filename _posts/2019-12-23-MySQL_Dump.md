---
title: "Dummy Data"
date: 2019-12-23 00:00:00 -0400
categories: jekyll update
---

### MySQL 백업(덤프)

Command Propmpt의 MySQL 로그인 진입 전의 설치된 디렉토리 ~ bin> 에서 백업 명령어를 사용한다.

    c:~> cd c:/Program Files/MySQL/MySQL Server 5.7/bin>

__특정 데이터 베이스만 백업__

    mysqldump -u[사용자ID] -p DB명 > 백업파일명.sql

  - 백업파일 저장 경로도 함께 지정할 수 있다.

      - 예 ) C드라이브 바탕화면에 바로 저장하려면

                mysqldump -uroot -p 백업DB명 > c:\백업파일명.sql

**전체 데이터 베이스 백업**

    mysqldump -uroot -p --all-databases > 파일명.sql

### MySQL 복원
데이터베이스를 미리 생성하고 진행해야 한다

    mysql -u[사용자ID] -p 복구DB명(전체 백업시 x) < 백업파일명.sql
    mysql -u[사용자ID] -p DB명 Table명 < 파일명.sql

> dump란?<br>
데이터 테이블의 구조와 레코드를 저장하는 방법.<br>
백업할 때도 사용 가능하다.<br>
text형식 query문으로 저장되기 때문에 수정, 추가, 복구가 용이하다.

Access is denied.<br>
에러가 뜬다면 Command Prompt(CMD)를 관리자 권한으로 실행한다.
