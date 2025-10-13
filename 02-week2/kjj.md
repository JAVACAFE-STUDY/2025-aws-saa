# 목차
- [이번 주의 주요 서비스](#이번-주의-주요-서비스)
  - [Amazon Elastic Compute Cloud (EC2)](#amazon-elastic-compute-cloud-ec2)
  - [AWS Lambda](#aws-lambda)
  - [Amazon Simple Storage Service (S3)](#amazon-simple-storage-service-s3)
  - [Amazon Elastic Block Storage (EBS)](#amazon-elastic-block-storage-ebs)
  - [Amazon Elastic File System (EFS)](#amazon-elastic-file-system-efs)
  - [Amazon Simple Notification Service (SNS)](#amazon-simple-notification-service-sns)
  - [Amazon Simple Queue Service (SQS)](#amazon-simple-queue-service-sqs)
- [자주 물어보는 내용](#자주-물어보는-내용)
  - [EC2 가격 옵션](#ec2-가격-옵션)
  - [S3 Storage Class & Lifecycle Policy](#s3-storage-class--lifecycle-policy)
  - [SNS/SQS 활용](#snssqs-활용)
  - [스토리지 비교: EBS, EFS, S3](#스토리지-비교-ebs-efs-s3)
- [요약](#요약)

---

# 이번 주의 주요 서비스

## Amazon Elastic Compute Cloud (EC2)
[거의 모든 워크로드에 적합한 안전하고 크기 조정 가능한 컴퓨팅 용량](https://aws.amazon.com/ko/ec2/)

**Amazon EC2**는 클라우드에서 **크기 조절이 가능한 컴퓨팅 파워**를 제공하는 서비스입니다. 가상 서버(인스턴스)를 대여하여 애플리케이션을 실행하며, 운영체제, 스토리지, 네트워킹을 자유롭게 구성할 수 있습니다.
- **용도:** 웹/애플리케이션 서버, 데이터베이스 등 컴퓨팅 파워가 필요한 모든 작업.
- **특징:** 수요에 따라 인스턴스를 쉽게 확장하거나 축소할 수 있어 유연하고 비용 효율적입니다.

---

## AWS Lambda
[서버 또는 클러스터에 대한 걱정 없이 코드 실행](https://aws.amazon.com/ko/lambda/)

**AWS Lambda**는 서버를 프로비저닝하거나 관리할 필요 없이 코드를 실행하게 해주는 **서버리스 컴퓨팅 서비스**입니다. 특정 이벤트에 의해 코드가 실행되며, 사용한 컴퓨팅 시간에 대해서만 비용을 지불합니다.
- **용도:** 데이터 처리, API 백엔드, 실시간 파일 처리 등.
- **특징:** 서버 관리가 필요 없어 개발에 집중할 수 있으며, 자동으로 확장되어 트래픽 급증에도 대응할 수 있습니다.

---

## Amazon Simple Storage Service (S3)
[어디서나 원하는 양의 데이터를 검색할 수 있도록 구축된 객체 스토리지](https://aws.amazon.com/ko/s3/)

**Amazon S3**는 데이터를 **객체 형태로 저장**하는 스토리지 서비스입니다. 이미지, 동영상, 문서 등 모든 종류의 데이터를 버킷(Buckets)에 저장할 수 있습니다.
- **용도:** 웹사이트의 정적 파일, 백업, 빅데이터 분석용 데이터 레이크, 아카이빙.
- **특징:** 뛰어난 내구성(99.999999999%)과 가용성을 제공하며, 사용한 만큼만 비용을 지불합니다.

---

## Amazon Elastic Block Storage (EBS)
[어떤 규모로도 사용하기 쉬운 고성능 블록 스토리지](https://aws.amazon.com/ko/ebs/)

**Amazon EBS**는 EC2 인스턴스를 위한 **블록 스토리지**로, EC2 인스턴스에 연결하여 사용하는 가상 하드 드라이브와 같습니다.
- **용도:** EC2 인스턴스의 운영체제, 데이터베이스, 로그 파일 등.
- **특징:** 고성능을 제공하며, 블록 단위로 데이터를 저장해 특정 위치의 데이터를 빠르게 읽고 쓸 수 있습니다.

---

## Amazon Elastic File System (EFS)
[서버리스 방식의 완전 탄력적인 파일 스토리지](https://aws.amazon.com/ko/efs/)

**Amazon EFS**는 **여러 EC2 인스턴스에서 동시에 접근할 수 있는** 파일 스토리지 서비스입니다.
- **용도:** 여러 서버가 동일한 파일을 공유해야 하는 웹 콘텐츠 관리, 개발 환경, 빅데이터 분석 등.
- **특징:** 파일 시스템 인터페이스(NFS 프로토콜)를 사용합니다.

---

## Amazon Simple Notification Service (SNS)
[A2A 및 A2P 메시징을 위한 완전관리형 게시/구독 서비스](https://aws.amazon.com/ko/sns/)

**Amazon SNS**는 **푸시(Push) 기반의 메시징 서비스**로, 발행/구독(Pub/Sub) 모델을 사용합니다. 특정 '토픽(Topic)'에 메시지를 발행하면, 구독하는 모든 사용자나 서비스에게 전달됩니다.
- **용도:** 사용자에게 알림(문자, 이메일), 애플리케이션 상태 변화 알림, 여러 서비스에 동일 메시지 전송.

---

## Amazon Simple Queue Service (SQS)
[마이크로서비스, 분산 시스템 및 서버리스 애플리케이션을 위한 완전관리형 메시지 대기열](https://aws.amazon.com/ko/sqs/)

**Amazon SQS**는 **메시지 대기열(Queue) 서비스**입니다. 메시지를 임시로 저장하여, 메시지 생산자와 소비자 간의 연결을 끊어줍니다.
- **용도:** 마이크로서비스 간의 비동기 통신, 대량 요청 처리, 작업 분산 처리.

---

# 자주 물어보는 내용

## EC2 가격 옵션
EC2는 다양한 사용 패턴에 맞춰 여러 가격 옵션을 제공합니다.
- **온디맨드:** 사용한 만큼 시간당 또는 초당 비용을 지불합니다.
- **예약 인스턴스:** 1년 또는 3년 약정으로 최대 75%까지 할인받습니다.
- **스팟 인스턴스:** 미사용 EC2 용량을 경매로 최대 90%까지 저렴하게 이용합니다.
- **Savings Plans:** 유연한 할인 모델로, 사용량에 약정하여 할인을 받습니다.

<img width="1285" height="731" alt="143" src="https://github.com/user-attachments/assets/43bd7f17-2322-48e0-9314-afc6ab63ebe6" />

  
<img width="1428" height="732" alt="image" src="https://github.com/user-attachments/assets/08dc3ac8-7b6e-4a78-a7a3-a9c025129244" />

- https://aws.amazon.com/ko/blogs/compute/building-sustainable-efficient-and-cost-optimized-applications-on-aws/  
- 고정적인 워크로드는 예약/세이빙플랜에서 실행
- 유동적이며 중단되도 괜찮은 워크로드는 스팟에서 실행
- 유동적이며 중단되면 안되는 워크로드는 온디멘드 실행


<img width="895" height="457" alt="image" src="https://github.com/user-attachments/assets/3299fb43-2cf6-46ce-b170-216f6c7d13dc" />

- https://spot.io/resources/aws-ec2-pricing/effective-utilization-of-aws-savings-plans-and-ec2-spot-instances/
<img width="1200" height="579" alt="image" src="https://github.com/user-attachments/assets/706965a1-a53a-4786-a8bd-476738c415d6" />

- https://www.nops.io/blog/aws-savings-plan-vs-reserved-instances/

- 보통 이런식으로 워크로드를 분석해서 비용옵션 적용으로 저렴하게 해줄게 일부만 떼줘 하는 서비스형태도 있다

---

## S3 Storage Class & Lifecycle Policy

- S3는 다양한 스토리지 클래스를 제공한다. 요구사항에 맞게 성능/비용 효율적인 선택이 필요
  - S3 Standard: 기본값, 빠른 성능, 다중 저장, 높은 비용
  - S3 Infrequent Access (IA): 저장비용 감소, 호출비용 증가
    - S3 Standard-IA: IA 특징 보유 및 다중 저장
    - S3 One Zone-IA: IA 특징 보유 및 단일 저장 (안정성감소)
  - S3 Glacier: 데이터 보관용, 느린 성능, 낮은 비용
  - S3 Glacier Deep Archive: 성능 및 비용 최하 
  - S3 Intelligent-Tiering: 자동으로 스토리지 클래스 분석 및 설정

<img width="1273" height="1096" alt="image" src="https://github.com/user-attachments/assets/e854ec05-7fdc-4380-8099-14ea27a0558b" />

- https://jibinary.tistory.com/129

- 이러한 스토리지는 직접 지정할수도 있지만 규칙에 의해 자동화 가능
  - 특정 기간 이후 클래스 변경 또는 삭제


<img width="815" height="470" alt="image" src="https://github.com/user-attachments/assets/d0584a75-c9e4-4813-8598-a4ff7ddff332" />

- https://docs.aws.amazon.com/ko_kr/AmazonS3/latest/userguide/lifecycle-transition-general-considerations.html  
- 순차적 절감

---

## SNS/SQS 활용
**SNS와 SQS는 함께 사용**하여 시스템을 더욱 안정적이고 확장 가능하게 만듭니다. 
- **SNS:** 하나의 메시지를 여러 소비자에게 동시에 전달하는 **브로드캐스팅** 역할을 합니다.
- **SQS:** 메시지를 안전하게 보관하여, 소비자가 준비될 때까지 기다렸다가 처리하는 **버퍼** 역할을 합니다.

---

## 스토리지 비교: EBS, EFS, S3

| 항목                                                             | EBS                               | EFS                      | S3                    |
| -------------------------------------------------------------- | --------------------------------- | ------------------------ | --------------------- |
| 유형                                                             | 블록                                | 파일(NFSv4)                | 오브젝트                  |
| 공유                                                             | 기본 단일 인스턴스(특정 io1/io2는 멀티-어태치 지원) | 다수 인스턴스 동시 마운트           | HTTP(S) API로 전세계 접근   |
| 내구성/범위                                                         | AZ 내 복제, AZ 종속                    | 리전 내 다중 AZ 설계            | 리전 내 다중 AZ, 매우 높은 내구성 |
| 지연/성능                                                          | ms 단위, 디스크 성능                     | 파일 워크로드용, 처리량 모드 선택      | 대규모/비정형 데이터, 스루풋 중심   |
| 과금 기준                                                          | 용량+IOPS/스루풋(타입별)                  | 용량+처리량 모드                | 저장용량+요청+전송            |
| 대표 사례                                                          | DB, 트랜잭션 스토리지, 부팅 볼륨              | 컨텐츠 리포지토리, 홈디렉토리, 웹서버 공유 | 백업/아카이브, 데이터레이크, 정적웹  |

---

# 요약

<img width="2411" height="1072" alt="aws-saa drawio" src="https://github.com/user-attachments/assets/7d51962f-c717-4439-a477-c196f1b9eae5" />


