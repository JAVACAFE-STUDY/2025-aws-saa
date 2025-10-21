# 목차
- [이번주의 주요 서비스](#이번주의-주요-서비스)
  - [AWS Snowfamily](#aws-snowfamily)
  - [AWS DataSync](#aws-datasync)
  - [AWS Elastic Load Balancing (ELB)](#aws-elastic-load-balancing-elb)
  - [AWS Web Application Firewall (WAF)](#aws-web-application-firewall-waf)
- [자주 물어보는 내용](#자주-물어보는-내용)
  - [AWS로 데이터를 보내는 여러 가지 방법들](#aws로-데이터를-보내는-여러-가지-방법들)
  - [로드발란서](#로드발란서)

---

# 이번주의 주요 서비스

## AWS Snowfamily
[AWS Snow 패밀리](https://docs.aws.amazon.com/ko_kr/whitepapers/latest/how-aws-pricing-works/aws-snow-family.html)    
AWS Snow 패밀리는 **대용량 데이터 마이그레이션**이나 **비연결 환경의 엣지 컴퓨팅**을 지원하기 위한 물리적 디바이스 제품군이다.  
네트워크가 제한적이거나 데이터가 매우 큰 경우, 인터넷을 통한 전송 대신 장비를 배송해 데이터를 이전한다.

- **Snowcone**  
  - 초소형·휴대형 엣지 디바이스 (8TB 스토리지, 배터리 구동 가능)  
  - 원격지나 차량, 산업현장 등에서 데이터 수집·처리에 적합

- **Snowball Edge**  
  - 80TB급 데이터 이관 및 엣지 컴퓨팅 장비  
  - **Storage Optimized / Compute Optimized** 버전 선택 가능  
  - 로컬에서 Lambda·EC2 인스턴스 실행 가능 (엣지 분석용)

- **Snowmobile**  
  - 100PB 단위 초대용량 데이터 마이그레이션용 트레일러 트럭  
  - 수십~수백PB 단위 데이터 이전에 사용  
  - 보안 트럭 내 AES-256 암호화 및 GPS 추적 제공

**활용 예시**  
- 온프레미스 데이터센터의 100TB~PB급 영상·분석데이터 이전  
- 네트워크 100Mbps 이하 환경에서 AWS로 마이그레이션  
- 전송 중 보안이 필요한 물리적 데이터 이동


## AWS Datasync
[AWS DataSync는 온프레미스와 AWS 스토리지 서비스 사이에서 데이터 이동을 자동화 및 가속화하는 안전한 온라인 서비스입니다.](https://aws.amazon.com/ko/datasync/) 

온프레미스 NAS, 파일 시스템, 또는 다른 클라우드 스토리지에서  
**S3 / EFS / FSx / Snowball / Outposts 등으로 데이터를 전송**하는 자동화 서비스.

- 온라인 데이터 마이그레이션 및 동기화에 최적화  
- 파일 시스템 메타데이터(POSIX 권한, 타임스탬프 등) 유지  
- SSL/TLS 전송 암호화 및 데이터 무결성 검증 지원  
- 스케줄 기반 증분 동기화 가능  
- CloudWatch 및 EventBridge로 전송 모니터링 가능  

**비교 포인트**
| 항목 | Snowball | DataSync |
|------|-----------|----------|
| 방식 | 오프라인 장치 배송 | 네트워크 기반 온라인 |
| 용량 | 10TB~PB | 수십GB~수TB |
| 목적 | 대규모/네트워크 제한 환경 | 정기적·지속적 동기화 |
| 대표 사례 | 공모전 제출용 대용량 이미지 이관 | 사내 NAS → S3 주기적 백업 |


## AWS Elastic Load Balancing (ELB)
[네트워크 트래픽을 분산하여 애플리케이션 확장성 개선](https://aws.amazon.com/ko/elasticloadbalancing/)

ELB는 들어오는 트래픽을 여러 EC2 인스턴스, 컨테이너, IP 대상으로 **자동 분산**하여  
**가용성·확장성·복원력**을 향상시키는 서비스이다.


- **Application Load Balancer (ALB)**  
  - L7 (HTTP/HTTPS) 트래픽 처리  
  - 도메인·경로 기반 라우팅 / WebSocket / WAF 연동  
  - REST API, 웹 애플리케이션에 적합  

- **Network Load Balancer (NLB)**  
  - L4 (TCP/UDP) 수준에서 초저지연 처리  
  - 수백만 TPS 처리 가능, 고성능 네트워크 서비스용  

- **Gateway Load Balancer (GLB)**  
  - 보안/방화벽 장비(Virtual Appliance) 트래픽 전달용  

- **Classic Load Balancer (CLB)**  
  - 구세대 버전 (단일 레이어, 점진적 폐지 권장)

**활용 예시**
- ALB: 여러 마이크로서비스로 구성된 웹서비스 트래픽 분산  
- NLB: 게임/IoT 서버의 실시간 TCP 세션 처리  
- GLB: VPC 보안 어플라이언스 트래픽 라우팅

## AWS Web Application Firewall (WAF)
[AWS WAF를 사용하면 SQL 인젝션 또는 크로스 사이트 스크립팅(XSS)과 같은 일반적인 공격 패턴을 차단하는 보안 규칙을 생성할 수 있습니다.](https://aws.amazon.com/ko/waf/)

- AWS WAF는 웹 애플리케이션 방화벽(Web Application Firewall)로, SQL 인젝션, 크로스 사이트 스크립팅(XSS) 등의 일반적인 공격으로부터 웹 애플리케이션을 보호한다.    
- ALB, API Gateway, CloudFront, AppSync 등의 AWS 리소스에 직접 연결하여 동작한다.

- 핵심 기능
  - 조건 기반 규칙 생성 (IP, URI, Header, QueryString 등)
  - 사전 정의된 Managed Rule Group 사용 가능 (AWS·서드파티 제공)
  - 요청당 로깅 및 차단·허용·카운트 동작 설정 가능
  - CloudWatch 및 Kinesis Data Firehose를 통한 실시간 모니터링
- 주요 사용 사례
  - 웹사이트/REST API의 SQLi, XSS, DDoS(애플리케이션 계층) 공격 방어
  - 특정 국가/지역/봇 요청 차단
  - 로그인 페이지 Brute-force 공격 차단
  - API Gateway 앞단 보안 계층으로 구성
- 활용 예시
  - ALB 또는 CloudFront에 연결해 웹 공격 방어
  - API Gateway 기반 REST API를 보호하여 SQLi/XSS 차단
  - Managed Ruleset(AWSManagedRulesCommonRuleSet)으로 빠른 정책 구축

# 자주 물어보는 내용

## AWS로 데이터를 보내는 여러 가지 방법들

데이터의 **규모**, **전송 주기**, **네트워크 환경**에 따라 적절한 방식을 선택해야 합니다.

| 전송 방식 | 주요 서비스 | 특징 | 권장 사용 시나리오 |
|------------|--------------|------|---------------------|
| **온라인 전송** | DataSync / S3 Transfer Acceleration | 네트워크 기반, 빠른 병렬 전송 | 수십~수백GB 단위, 지속적 업로드 |
| **오프라인 전송** | Snowball / Snowmobile | 네트워크 불가 환경, 물리적 장치 배송 | TB~PB 단위 데이터 이전 |
| **API 업로드** | S3 PutObject / Presigned URL | 앱/웹 클라이언트에서 직접 전송 | 사용자 업로드, 로그 데이터 |
| **실시간 스트림** | Kinesis / Firehose / IoT Core | 지속적 센서·로그 수집 | 로그, IoT, 거래 데이터 수집 |
| **하이브리드 전송** | Storage Gateway | 온프레미스 캐시 + 클라우드 백엔드 | 파일서버와 클라우드 병행 |
| **전용 회선** | AWS Direct Connect | 온프레미스 ↔ AWS 간 전용 네트워크 연결 |
| **데이터베이스 동기화** | AWS DMS (Database Migration Service) | 네트워크 기반, DB간 데이터 실시간 동기화 또는 마이그레이션 | 온프렘<>AWS DB, 이기종 DB간 전송 |


**정리**
- 네트워크 속도가 충분 → **DataSync / Transfer Acceleration**
- 속도/기간이 제한적 → **Snowball**
- 실시간 처리 필요 → **Kinesis / Firehose**
- 지속 백업 + 로컬 캐시 → **Storage Gateway**

---

## 로드발란서

| 구분 | 계층 | 주요 기능 | 활용 사례 |
|------|------|-----------|------------|
| **ALB** | L7 | HTTP/HTTPS 기반, 고급 라우팅(호스트/경로/헤더 등) | 웹앱, API 서버 |
| **NLB** | L4 | TCP/UDP, 낮은 지연시간, 고정 IP 지원 | 게임 서버, IoT |
| **GLB** | L3/L4 | 보안/방화벽용 어플라이언스 연결 | 침입탐지, 보안 게이트웨이 |
| **CLB** | L4/L7 | 구형 통합형 로드밸런서 | 레거시 환경 | 

**부가 기능**
- Health Check (상태 모니터링)
- Auto Scaling Group 연동
- HTTPS 인증서 관리 (ACM 연동)
- Target Group 단위 트래픽 분리

**요약**
- HTTP/HTTPS 트래픽 → ALB  
- TCP/UDP 실시간 서비스 → NLB  
- 보안 장비 라우팅 → GLB  
