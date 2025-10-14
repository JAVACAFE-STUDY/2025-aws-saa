# Particify.de CSV 임포트 가이드

Particify.de는 실시간 퀴즈 호스팅 플랫폼으로, CSV 파일을 통해 대량의 퀴즈 문제를 쉽게 임포트할 수 있습니다.

## 📋 목차
1. [CSV 파일 구조 이해](#csv-파일-구조-이해)
2. [Particify 계정 설정](#particify-계정-설정)
3. [CSV 파일 임포트 방법](#csv-파일-임포트-방법)
4. [퀴즈 실행 및 관리](#퀴즈-실행-및-관리)
5. [문제 해결](#문제-해결)

## 📊 CSV 파일 구조 이해

현재 프로젝트의 CSV 파일들은 다음과 같은 구조를 가지고 있습니다:

### 필수 컬럼
- `format`: 문제 유형 (예: CHOICE)
- `body`: 문제 본문ParticifyCSVImportGuide
- `additionalText`: 추가 설명 (선택사항)
- `options`: 선택지 (A, B, C, D, E 등)
- `correctOptions`: 정답 선택지
- `multiple`: 다중 선택 여부
- `abstentionsAllowed`: 기권 허용 여부
- `duration`: 문제당 시간 제한

### 예시 CSV 구조
```csv
format,body,additionalText,options,correctOptions,multiple,abstentionsAllowed,duration
CHOICE,"Sample-Q1

한 회사가 여러 가용 영역에 걸쳐 VPC 에서 퍼블릭 3 티어 웹 애플리케이션을 실행합니다...",,"A) 퍼블릭 서브넷에서 NAT 게이트웨이를 구성합니다. 
B) 인터넷 트래픽에 대한 NAT 게이트웨이 경로가 있는 사용자 지정 라우팅 테이블을 정의하고 이를 애플리케이션 티어의 프라이빗 서브넷과 연결합니다
C) EC2 인스턴스에 탄력적 IP 주소를 할당합니다.
D) 인터넷 트래픽에 대한 인터넷 게이트웨이 경로가 있는 사용자 지정 라우팅 테이블을 정의하고 이를 애플리케이션 티어의 프라이빗 서브넷과 연결합니다. 
E) 프라이빗 서브넷에서 NAT 인스턴스를 구성합니다","A) 퍼블릭 서브넷에서 NAT 게이트웨이를 구성합니다. 
B) 인터넷 트래픽에 대한 NAT 게이트웨이 경로가 있는 사용자 지정 라우팅 테이블을 정의하고 이를 애플리케이션 티어의 프라이빗 서브넷과 연결합니다",true,true,30
```

## 🔧 Particify 계정 설정

### 1. 계정 생성
1. [Particify.de](https://particify.de) 웹사이트 방문
2. "Sign Up" 또는 "회원가입" 클릭
3. 이메일 주소와 비밀번호 입력
4. 이메일 인증 완료

### 2. 프로필 설정
1. 로그인 후 프로필 페이지 이동
2. 사용자명, 표시명 등 기본 정보 입력
3. 언어 설정 (한국어 선택 가능)

## 📤 CSV 파일 임포트 방법

1. 로그인 후 첫 유저 화면에서 `+Create Room` 버튼 클릭 후 적당한 이름을 넣어서 생성
   - https://ars.particify.de/user
<img width="1675" height="915" alt="image" src="https://github.com/user-attachments/assets/9690ba7a-0ba3-4159-88e6-3d1e3a582ee7" />


2. 생성된 Room 페이지에서, Question series의 `+Create question series` 버튼을 클릭하여 임시 퀴즈 생성 및 퀴즈페이지 진입
<img width="1668" height="1129" alt="image" src="https://github.com/user-attachments/assets/bdb485a7-ed7c-4711-b1ca-d8cb1c7bd08d" />


3. 퀴즈 페이지에서 중간 상단 세로점3개 클릭 후 `Import Contents` > 업로드할 csv 파일 선택
<img width="1658" height="1275" alt="image" src="https://github.com/user-attachments/assets/eb0ed92e-c3b8-4993-b3a7-4c35a16e1364" />

- 현재 프로젝트의 CSV 파일들:
   - `01-week1/w1_74837906_20251013-1803.csv`   
   - `02-week2/w2_98242636_20251013-1804.csv`   
   - `03-week3/w3_54115264_20251013-1804.csv`   
   - `04-week4/w4_00051265_20251013-1805.csv`   
   - `05-week5/w5_02389796_20251013-1801.csv`   
   ...   


## 🎯 퀴즈 실행 및 관리

1. 우측 상단 `Present` 버튼으로 세션?퀴즈? 시작 > Publish
<img width="1661" height="1268" alt="image" src="https://github.com/user-attachments/assets/2eaaf35d-11f1-462e-b9e1-bb1a6b9016ea" />


2. 우측 `Share room` 버튼 또는 Q를 클릭하여 접속 링크를 확인하고, 시크릿 창등 별도 브라우저에서 접속
<img width="1662" height="1272" alt="image" src="https://github.com/user-attachments/assets/735e236b-8b4b-4199-8ccc-1fb99ef1ff65" />


3. 링크 참가 후 퀴즈 진행


4. 타이머 설정
- 스터디환경처럼 문제마다 시간제한 걸려면 room 내부에서 톱니바퀴 `live mode`활성화 필요
- 이후 룸 페이지?관리자페이지? 에서 관리자가 문제마다 `p`(publish) 및 `s`(start) 하여야 클라이언트페이지에서 응답가능
  
  <img width="1671" height="1279" alt="image" src="https://github.com/user-attachments/assets/4e2d3978-1a4a-457c-a3bf-21f9abc17382" />




---
이 가이드를 따라하면 Particify 플랫폼에서 CSV 파일을 활용하여 효율적으로 퀴즈를 생성하고 관리할 수 있습니다. 추가 질문이나 도움이 필요하시면 언제든 문의해 주세요!

