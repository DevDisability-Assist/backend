# [발달 장애인 대기 지원 프로그램] mariaDB 클라우드 서버

## 접속 정보 및 환경설정

| 항목            | 상세 내용                                                  |
| :-------------- | :--------------------------------------------------------- |
| **DBMS**        | MariaDB                                                    |
| **OS 환경**     | Linux(Ubuntu-24.04-base) kernel version : 6.8.0-60-generic |
| **Host (IP)**   | 49.50.139.18 (NCP 공인 IP)                                 |
| **DB Port**     | 3306                                                       |
| **SSH Port**    | 22                                                         |
| **DB 사용자**   | dev01 (개발용 계정)                                        |
| **DB 스키마**   | dev                                                        |
| **방화벽 설정** | DB담당자(김동우)에게 **팀원 공인 IP** 등록 요청 필요       |

## DB 접속 환경 변수 파일("dbConfig.env")

모든 담당자는 프로젝트 루트에 **`dbConfig.env`** 파일을 생성하고, 아래의 **예시(`dbConfig.env.example`)**를 참고하여 본인의 환경에 맞는 실제 값을 입력합니다.

**⚠️ 주의:** `dbConfig.env` 파일은 `.gitignore`에 등록되어 있으며, 실제 비밀번호가 포함되므로 **절대 Git에 커밋하거나 푸시하지 않습니다.**

```dotenv
# dbConfig.env.example (이 파일을 복사하여 dbConfig.env를 만드세요)
DB_HOST=49.50.139.18
DB_PORT=3306
DB_USERNAME=dev01
DB_PASSWORD=T2@samSuNg%js
DB_DATABASE=dev
```

## 데이터베이스 사용 규정 및 원칙

접근 권한 : dev01 계정은 개발/테스트용 계정 (root 계정 접근 금지)

스키마 변경 : 테이블 구조(스키마) 변경이 필요한 경우 담당자(김동우)와 팀원에게 공유.

테스트 데이터 : 테스트 데이터는 `dev` DB에서만 CREATE/ALTER/DROP, 다른 팀원의 작업에 영향을 주지 않도록 담당 기능 범위 내에서만 작업하도록 안내.

영향 범위 제한 : 다른 팀원이 작업 중인 테이블의 데이터는 함부로 수정하거나 삭제하지 않도록 합니다. 대량의 테스트 데이터 삽입(INSERT)은 팀원들에게 미리 공지 후 진행합니다.

## 초기 DB 설정 (SQL 쿼리문)

실행 방법: MySQL Workbench의 dev 데이터베이스에 접속한 후,
project1/database/sqls/create.sql (github에 커밋)파일을 열어 해당 쿼리 전체를 실행합니다.

## 기타 도구 및 자료

ERD파일참조 : https://www.erdcloud.com/d/KYYKifcugH8u2YkRm
서버 접속 도구 : MobaXterm
DB 클라이언트 : MySQL Workbench

```


```
