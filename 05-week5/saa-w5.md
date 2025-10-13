
1. 온라인 리테일 회사는 5,000만 명 이상의 활성 고객을 보유하고 있으며 매일 25,000건 이상의 주문을 받습니다. 이 회사는 고객의 구매 데이터를 수집하여 Amazon S3에 저장합니다. 추가 고객 데이터는 Amazon RDS에 저장됩니다.
이 회사는 모든 데이터를 다양한 팀에 제공하여 팀이 분석을 수행할 수 있도록 하려고 합니다. 솔루션은 데이터에 대한 세분화된 권한을 관리하는 기능을 제공해야 하며 운영 오버헤드를 최소화해야 합니다.

어떤 솔루션이 이러한 요구 사항을 충족할까요?

A. 구매 데이터를 마이그레이션하여 Amazon RDS에 직접 씁니다. RDS 액세스 제어를 사용하여 액세스를 제한합니다.
B. AWS Lambda 함수를 예약하여 Amazon RDS에서 Amazon S3로 데이터를 주기적으로 복사합니다. AWS Glue 크롤러를 만듭니다. Amazon Athena를 사용하여 데이터를 쿼리합니다. S3 정책을 사용하여 액세스를 제한합니다.
C. AWS Lake Formation을 사용하여 데이터 레이크를 만듭니다. Amazon RDS에 AWS Glue JDBC 연결을 만듭니다. Lake Formation에 S3 버킷을 등록합니다. Lake Formation 액세스 제어를 사용하여 액세스를 제한합니다.
D. Amazon Redshift 클러스터를 만듭니다. AWS Lambda 함수를 예약하여 Amazon S3 및 Amazon RDS에서 Amazon Redshift로 데이터를 주기적 으로 복사합니다. Amazon Redshift 액세스 제어를 사용하여 액세스를 제한합니다.

2. 미디어 회사가 온프레미스에서 사용자 활동 데이터를 수집하고 분석합니다. 이 회사는 이 기능을 AWS로 마이그레이션하려고 합니다. 사용자 활동 데이터 저장소는 계속 성장하고 페타바이트 크기가 될 것입니다. 이 회사는 SQL을 사용하여 기존 데이터와 새 데이터의 주문형 분석을 용이하게 하는 고가용성 데이터 수집 솔루션을 구축해야 합니다.

어떤 솔루션이 최소한의 운영 오버헤드로 이러한 요구 사항을 충족할까요?

A. 활동 데이터를 Amazon Kinesis 데이터 스트림으로 보냅니다. 스트림을 구성하여 데이터를 Amazon S3 버킷으로 전달합니다.
B. 활동 데이터를 Amazon Kinesis Data Firehose 전달 스트림으로 전송합니다. 스트림을 구성하여 데이터를 Amazon Redshift 클러스터로 전달합니다.
C. Amazon S3 버킷에 활동 데이터를 넣습니다. 데이터가 S3 버킷에 도착하면 데이터에 AWS Lambda 함수를 실행하도록 Amazon S3를 구성합니다.
D. 여러 가용성 영역에 걸쳐 분산된 Amazon EC2 인스턴스에서 수집 서비스를 만듭니다. Amazon RDS Multi-AZ 데이터베이스로 데이터를 전달하도록 서비스를 구성합니다

3. 한 회사가 AWS 계정의 모든 애플리케이션에서 Amazon EC2 Auto Scaling 이벤트를 보고하는 솔루션을 구축하고 있습니다. 이 회사는 서버리스 솔루션을 사용하여 Amazon S3에 EC2 Auto Scaling 상태 데이터를 저장해야 합니다. 그런 다음 이 회사는 Amazon S3의 데이터를 사용하여 대시보드에서 거의 실시간 업데이트를 제공합니다. 이 솔루션은 EC2 인스턴스 시작 속도에 영향을 미쳐서는 안 됩니다.

이 회사는 이러한 요구 사항을 충족하기 위해 어떻게 데이터를 Amazon S3로 옮겨야 할까요?

A. Amazon CloudWatch 메트릭 스트림을 사용하여 EC2 Auto Scaling  상태 데이터를 Amazon Kinesis Data Firehose로 전송합니다. Amazon S3에 데이터를 저장합니다.
B. Amazon EMR 클러스터를 시작하여 EC2 Auto Scaling 상태 데이터를 수집하고 Amazon Kinesis Data Firehose로 데이터를 전송합니다. AmazonS3에 데이터를 저장합니다.
C. Amazon EventBridge 규칙을 만들어 일정에 따라 AWS Lambda 함수를 호출합니다. Lambda 함수를 구성하여 EC2 Auto Scaling 상태 데이터를 Amazon S3로 직접 전송합니다.
D. EC2 인스턴스를 시작하는 동안 부트스트랩 스크립트를 사용하여 Amazon Kinesis Agent를 설치합니다. Kinesis Agent를 구성하여 EC2 Auto Scaling 상태 데이터를 수집하고 Amazon Kinesis Data Firehose로 데이터를 전송합니다. Amazon S3에 데이터를 저장합니다.

4. 게임 회사가 여러 AWS 지역에서 새로운 인터넷 기반 애플리케이션을 출시하려고 합니다. 이 애플리케이션은 통신에 TCP 및 UDP 프로토콜을 사용합니다. 이 회사는 글로벌 사용자에게 높은 가용성과 최소 지연 시간을 제공해야 합니다.

솔루션 아키텍트는 이러한 요구 사항을 충족하기 위해 어떤 조치 조합을 취해야 합니까? (두 가지를 선택하세요.)

A. 각 지역의 애플리케이션 앞에 내부 네트워크 로드 밸런서를 생성합니다.
B. 각 지역의 애플리케이션 앞에 외부 애플리케이션 부하 분산 장치를 생성합니다.
C. 각 지역의 로드 밸런서로 트래픽을 라우팅하기 위해 AWS Global Accelerator 가속기를 생성합니다.
D. 트래픽을 분산하기 위해 지리적 위치 라우팅 정책을 사용하도록 Amazon Route 53을 구성합니다.
E. 각 지역의 애플리케이션에 대한 트래픽 및 경로 요청을 처리하도록 Amazon CloudFront를 구성합니다.

5. 한 회사에 두 가지 애플리케이션이 있습니다. 처리할 페이로드가 있는 메시지를 보내는 발신자 애플리케이션과 페이로드가 있는 메시지를 수신하도록 의도된 처리 애플리케이션입니다. 이 회사는 두 애플리케이션 간의 메시지를 처리하는 AWS 서비스를 구현하려고 합니다. 발신자 애플리케이션은 매시간 약 1,000개의 메시지를 보낼 수 있습니다. 메시지를 처리하는 데 최대 2일이 걸릴 수 있습니다. 메시지를 처리하지 못하면 나머지 메시지의 처리에 영향을 미치지 않도록 보관해야 합니다.

이러한 요구 사항을 충족하고 가장 운영 효율적인 솔루션은 무엇입니까?

A. Redis 데이터베이스를 실행하는 Amazon EC2 인스턴스를 설정합니다. 두 애플리케이션이 인스턴스를 사용하도록 구성합니다. 각각 메시지를 저장, 처리 및 삭제합니다.
B. Amazon Kinesis 데이터 스트림을 사용하여 발신자 애플리케이션에서 메시지를 수신합니다. 처리 애플리케이션을 Kinesis 클라이언트 라이브러리(KCL)와 통합합니다.
C. 발신자 및 처리자 애플리케이션을 Amazon Simple Queue Service(Amazon SQS) 대기열과 통합합니다. 처리에 실패한 메시지를 수집하기 위해 배달 못한 편지 대기열을 구성합니다.
D. Amazon Simple Notibcation Service(Amazon SNS) 토픽에 처리 애플리케이션을 구독하여 처리할 알림을 받습니다. 발신자 애플리케이션을 통합하여 SNS 토픽에 씁니다.

---



---

1. 금융 회사는 온프레미스 검색 애플리케이션을 사용하여 다양한 생산자료로부터 스트리밍 데이터를 수집합니다. 이 애플리케이션은 검색 및 시각화 기능에 대한 실시간 업데이트를 제공합니다.

이 회사는 AWS로 마이그레이션할 계획이며 AWS 네이티브 솔루션을 사용하려고 합니다.

어떤 솔루션이 이러한 요구 사항을 충족할까요?

A. Amazon EC2 인스턴스를 사용하여 데이터 스트림을 수집하고 처리하여 Amazon S3 버킷에 저장. Amazon Athena를 사용하여 데이터 검색. Amazon Managed Grafana를 사용하여 시각화 생성.
B. Amazon EMR을 사용하여 데이터 스트림을 수집하고 처리하여 Amazon Redshift에 저장. Amazon Redshift Spectrum을 사용하여 데이터 검색. Amazon QuickSight를 사용하여 시각화 생성.
C. Amazon Elastic Kubernetes Service(Amazon EKS)를 사용하여 데이터 스트림을 수집하고 처리하여 Amazon DynamoDB에 저장. Amazon CloudWatch를 사용하여 그래픽 대시보드를 만들어 데이터를 검색하고 시각화합니다.
D. Amazon Kinesis Data Streams를 사용하여 Amazon OpenSearch Service로 데이터 스트림을 수집하고 처리합니다. OpenSearch Service를 사용하여 데이터를 검색합니다. Amazon QuickSight를 사용하여 시각화를 만듭니다. (가장 많이 투표됨)

2. 한 회사에는 매일 1TB의 상태 알림을 생성하는 수천 개의 에지 디바이스가 있습니다. 각 알림의 크기는 약 2KB입니다. 솔루션 아키텍트는 향후 분석을 위해 알림을 수집하고 저장하는 솔루션을 구현해야 합니다. 

회사는 고가용성 솔루션을 원합니다. 그러나 회사는 비용을 최소화해야 하며 추가 인프라를 관리하고 싶지 않습니다. 또한 회사는 14일 분의 데이터를 즉시 분석할 수 있도록 보관하고 14일 이상 된 모든 데이터를 보관하려고 합니다.

이러한 요구 사항을 충족하는 가장 운영 효율적인 솔루션은 무엇입니까?

A. 알림을 수집하기 위해 Amazon Kinesis Data Firehose 전송 스트림을 만듭니다. 알림을 Amazon S3 버킷으로 전송하도록 Kinesis Data Firehose 스트림을 구성합니다. 14일 후 Amazon S3 Glacier로 데이터를 전환하도록 S3 Lifecycle 구성을 설정합니다.
B. 두 개의 가용성 영역에 걸쳐 Amazon EC2 인스턴스를 시작하고 이를 Elastic Load Balancer 뒤에 배치하여 알림을 수집합니다. EC2 인스턴스에서 Amazon S3 버킷에 알림을 저장하는 스크립트를 만듭니다. 14일 후 Amazon S3 Glacier로 데이터를 전환하도록 S3 Lifecycle 구성을 설정합니다.
C. 알림을 수집하기 위한 Amazon Kinesis Data Firehose 전달 스트림을 만듭니다. 알림을 Amazon OpenSearch Service(Amazon Elasticsearch Service) 클러스터로 전달하도록 Kinesis Data Firehose 스트림을 구성합니다. Amazon OpenSearch Service(Amazon Elasticsearch Service) 클러스터를 설정하여 매일 수동 스냅샷을 찍고 14일 이상 된 클러스터의 데이터를 삭제합니다.
D. 알림을 수집하기 위한 Amazon Simple Queue Service(Amazon SQS) 표준 대기열을 만들고 메시지 보관 기간을 14일로 설정합니다. 소비자가 SQS 대기열을 폴링하고, 메시지의 나이를 확인하고, 필요에 따라 메시지 데이터를 분석하도록 구성합니다. 메시지가 14일 된 경우 소비자는 메시지를 Amazon S3 버킷에 복사하고 SQS 대기열에서 메시지를 삭제해야 합니다.

3. 한 회사가 고객 결제 데이터를 Amazon S3의 회사 데이터 레이크로 수집하려고 합니다. 회사는 평균적으로 1분마다 결제 데이터를 수신합니다. 회사는 실시간으로 결제 데이터를 분석하려고 합니다. 그런 다음 회사는 데이터를 데이터 레이크로 수집하려고 합니다.

어떤 솔루션이 가장 높은 운영 효율성으로 이러한 요구 사항을 충족할까요?

A. Amazon Kinesis Data Streams를 사용하여 데이터를 수집합니다. AWS Lambda를 사용하여 실시간으로 데이터를 분석합니다.
B. AWS Glue를 사용하여 데이터를 수집합니다. Amazon Kinesis Data Analytics를 사용하여 실시간으로 데이터를 분석합니다.
C. Amazon Kinesis Data Firehose를 사용하여 데이터를 수집합니다. Amazon Kinesis Data Analytics를 사용하여 실시간으로 데이터를 분석합니다.
D. Amazon API Gateway를 사용하여 데이터를 수집합니다. AWS Lambda를 사용하여 실시간으로 데이터를 분석합니다.

4. 한 회사가 Amazon S3에 정적 웹사이트를 호스팅하고 있으며 DNS에 Amazon Route 53을 사용하고 있습니다. 이 웹사이트는 전 세계에서 수요가 증가하고 있습니다. 이 회사는 웹사이트에 액세스하는 사용자의 대기 시간을 줄여야 합니다.

어떤 솔루션이 이러한 요구 사항을 가장 비용 효율적으로 충족합니까?

A. 웹사이트가 포함된 S3 버킷을 모든 AWS 리전에 복제합니다. Route 53 지리적 위치 라우팅 항목을 추가합니다.
B. AWS Global Accelerator에서 가속기를 프로비저닝합니다. 제공된 IP 주소를 S3 버킷과 연결합니다. Route 53 항목을 편집하여 가속기의 IP 주소를 가리킵니다.
C. S3 버킷 앞에 Amazon CloudFront 배포를 추가합니다. Route 53 항목을 편집하여 CloudFront 배포를 가리킵니다.
D. 버킷에서 S3 Transfer Acceleration을 활성화합니다. Route 53 항목을 편집하여 새 엔드포인트를 가리킵니다.

5. 글로벌 전자상거래 회사가 AWS에서 중요한 워크로드를 실행합니다. 워크로드는 Multi-AZ 배포를 위해 구성된 Amazon RDS for PostgreSQL DB 인스턴스를 사용합니다.

고객은 회사에서 데이터베이스 장애 조치를 겪을 때 애플리케이션 시간 초과가 발생한다고 보고했습니다. 이 회사는 장애 조치 시간을 줄이기 위한 복원력 있는 솔루션이 필요합니다.

어떤 솔루션이 이러한 요구 사항을 충족할까요?

A. Amazon RDS 프록시를 만듭니다. 프록시는 DB 인스턴스에 할당됩니다.
B. DB 인스턴스에 대한 읽기 복제본을 만듭니다. 읽기 트래픽을 읽기 복제본으로 이동합니다.
C. Performance Insight를 활성화합니다. CPU 부하를 모니터링하여 시간 초과를 식별합니다.
D. 정기적으로 자동 스냅샷을 찍습니다. 자동 스냅샷을 여러 AWS 리전에 복사합니다.

---



---
1. 한 회사에서 레거시 애플리케이션을 사용하여 CSV 형식으로 데이터를 생성합니다. 레거시 애플리케이션은 출력 데이터를 Amazon S3에 저장합니다.
이 회사는 Amazon Redshift와 Amazon S3에만 저장된 데이터를 분석하기 위해 복잡한 SQL 쿼리를 수행할 수 있는 새로운 상용 기성품(COTS) 애플리케이션을 배포하고 있습니다. 그러나 COTS 애플리케이션은 레거시 애플리케이션이 생성하는 .csv 파일을 처리할 수 없습니다.
이 회사는 레거시 애플리케이션을 업데이트하여 다른 형식으로 데이터를 생성할 수 없습니다. 이 회사는 COTS 애플리케이션이 레거시 애플리케이션이 생성하는 데이터를 사용할 수 있도록 솔루션을 구현해야 합니다.

어떤 솔루션이 이러한 요구 사항을 가장 적은 운영 오버헤드로 충족할까요?

A. 일정에 따라 실행되는 AWS Glue 추출, 변환 및 로드(ETL) 작업을 만듭니다. ETL 작업을 구성하여 .csv 파일을 처리하고 처리된 데이터를 Amazon Redshift에 저장합니다.
B. Amazon EC2 인스턴스에서 실행되는 Python 스크립트를 개발하여 .csv 파일을 .sql 파일로 변환합니다. Cron 일정에 따라 Python 스크립트를 호출하여 Amazon S3에 출력 파일을 저장합니다.
C. AWS Lambda 함수와 Amazon DynamoDB 테이블을 만듭니다. S3 이벤트를 사용하여 Lambda 함수를 호출합니다. Lambda 함수를 구성하여 .csv 파일을 처리하고 처리된 데이터를 DynamoDB 테이블에 저장하기 위해 ETL(추출, 변환 및 로드) 작업을 수행합니다.
D. Amazon EventBridge를 사용하여 주간 일정으로 Amazon EMR 클러스터를 시작합니다. EMR 클러스터를 구성하여 .csv 파일을 처리하고 처리된 데이터를 Amazon Redshift 테이블에 저장하기 위해 추출, 변환 및 로드(ETL) 작업을 수행합니다.

2. 한 회사가 온프레미스 데이터 소스에서 데이터를 수집하기 위해 Amazon EC2 인스턴스 플릿을 사용하고 있습니다. 데이터는 JSON 형식이며 수집 속도는 최대 1MB/초입니다. EC2 인스턴스가 재부팅되면 이동 중인 데이터가 손실됩니다. 회사의 데이터 과학 팀은 수집된 데이터를 거의 실시간으로 쿼리하려고 합니다.
어떤 솔루션이 최소한의 데이터 손실로 확장 가능한 거의 실시간 데이터 쿼리를 제공합니까?

A. Amazon Kinesis Data Streams에 데이터를 게시하고 Kinesis Data Analytics를 사용하여 데이터를 쿼리합니다.
B. Amazon Redshift를 대상으로 Amazon Kinesis Data Firehose에 데이터를 게시합니다. Amazon Redshift를 사용하여 데이터를 쿼리합니다.
C. 수집된 데이터를 EC2 인스턴스 스토어에 저장합니다. Amazon S3를 대상으로 Amazon Kinesis Data Firehose에 데이터를 게시합니다. Amazon Athena를 사용하여 데이터를 쿼리합니다.
D. 수집된 데이터를 Amazon Elastic Block Store(Amazon EBS) 볼륨에 저장합니다. Amazon ElastiCache for Redis에 데이터를 게시합니다. Redis 채널을 구독하여 데이터를 쿼리합니다.

3. 한 회사가 고객 결제 데이터를 Amazon S3의 회사 데이터 레이크로 수집하려고 합니다. 회사는 평균적으로 1분마다 결제 데이터를 수신합니다. 회사는 실시간으로 결제 데이터를 분석하려고 합니다. 그런 다음 회사는 데이터를 데이터 레이크로 수집하려고 합니다.

어떤 솔루션이 가장 높은 운영 효율성으로 이러한 요구 사항을 충족할까요?

A. Amazon Kinesis Data Streams를 사용하여 데이터를 수집합니다. AWS Lambda를 사용하여 실시간으로 데이터를 분석합니다.
B. AWS Glue를 사용하여 데이터를 수집합니다. Amazon Kinesis Data Analytics를 사용하여 실시간으로 데이터를 분석합니다.
C. Amazon Kinesis Data Firehose를 사용하여 데이터를 수집합니다. Amazon Kinesis Data Analytics를 사용하여 실시간으로 데이터를 분석합니다.
D. Amazon API Gateway를 사용하여 데이터를 수집합니다. AWS Lambda를 사용하여 실시간으로 데이터를 분석합니다.

4. 한 회사가 us-west-2 지역의 네트워크 로드 밸런서(NLB) 뒤에 있는 세 개의 Amazon EC2 인스턴스에 자체 관리형 DNS 솔루션을 구현했습니다. 이 회사의 사용자 대부분은 미국과 유럽에 있습니다. 이 회사는 솔루션의 성능과 가용성을 개선하고자 합니다. 이 회사는 eu-west-1 지역에서 세 개의 EC2 인스턴스를 시작하고 구성한 후 EC2 인스턴스를 새 NLB의 대상으로 추가합니다.

이 회사는 모든 EC2 인스턴스로 트래픽을 라우팅하는 데 어떤 솔루션을 사용할 수 있습니까?

A. Amazon Route 53 지리적 위치 라우팅 정책을 만들어 두 NLB 중 하나로 요청을 라우팅합니다. Amazon CloudFront 배포를 만듭니다. Route 53 레코드를 배포의 원점으로 사용합니다.
B. AWS Global Accelerator에서 표준 가속기를 만듭니다. us-west-2와 eu-west-1에서 엔드포인트 그룹을 만듭니다. 두 개의 NLB를 엔드포인트 그룹의 엔드포인트로 추가합니다.
C. 6개의 EC2 인스턴스에 Elastic IP 주소를 연결합니다. Amazon Route 53 지리적 위치 라우팅 정책을 만들어 요청을 6개의 EC2 인스턴스 중 하나로 라우팅합니다. Amazon CloudFront 배포를 만듭니다. Route 53 레코드를 배포의 원점으로 사용합니다.
D. 두 개의 NLB를 두 개의 Application Load Balancer(ALB)로 교체합니다. 두 개의 ALB 중 하나로 요청을 라우팅하기 위한 Amazon Route 53 지연 라우팅 정책을 만듭니다. Amazon CloudFront 배포를 만듭니다. Route 53 레코드를 배포의 원점으로 사용합니다.

5. 한 회사에 자동차의 IoT 센서에서 데이터를 수집하는 애플리케이션이 있습니다. 이 데이터는 Amazon Kinesis Data Firehose를 통해 Amazon S3에 스트리밍되어 저장됩니다. 이 데이터는 매년 수조 개의 S3 객체를 생성합니다. 매일 아침 이 회사는 이전 30일의 데이터를 사용하여 일련의 머신 러닝(ML)모델을 재교육합니다.
이 회사는 매년 4회 이전 12개월의 데이터를 사용하여 분석을 수행하고 다른 ML 모델을 교육합니다. 이 데이터는 최대 1년 동안 최소한의 지연으로 사용할 수 있어야 합니다. 1년 후에는 보관 목적으로 데이터를 보관해야 합니다.

이러한 요구 사항을 가장 비용 효율적으로 충족하는 스토리지 솔루션은 무엇입니까?

A. S3 Intelligent-Tiering 스토리지 클래스를 사용합니다. 1년 후 객체를 S3 Glacier Deep Archive로 전환하기 위한 S3 Lifecycle 정책을 만듭니다.
B. S3 Intelligent-Tiering 스토리지 클래스를 사용합니다. 1년 후에 S3 Glacier Deep Archive로 객체를 자동으로 이동하도록 S3 Intelligent-Tiering을 구성합니다.
C. S3 Standard-Infrequent Access(S3 Standard-IA) 스토리지 클래스를 사용합니다. 1년 후 객체를 S3 Glacier Deep Archive로 전환하기 위한 S3 Lifecycle 정책을 만듭니다.
D. S3 Standard 스토리지 클래스를 사용합니다. 30일 후에 S3 Standard-Infrequent Access(S3 Standard-IA)로, 1년 후에 S3 Glacier Deep Archive로 객체를 전환하는 S3 Lifecycle 정책을 만듭니다.

---



---
1. 한 회사에 Amazon S3 데이터 레이크가 있습니다. 이 회사에는 데이터 레이크의 데이터를 변환하여 매일 데이터 웨어하우스에 로드하는 솔루션이 필요합니다. 데이터 웨어하우스에는 대량 병렬 처리(MPP) 기능이 있어야 합니다.
그런 다음 데이터 분석가는 데이터에 SQL 명령을 사용하여 머신 러닝(ML) 모델을 만들고 학습해야 합니다. 이 솔루션은 가능한 한 서버리스 AWS 서비스를 사용해야 합니다.

어떤 솔루션이 이러한 요구 사항을 충족할까요?

A. 매일 Amazon EMR 작업을 실행하여 데이터를 변환하고 Amazon Redshift에 데이터를 로드합니다. Amazon Redshift ML을 사용하여 ML 모델을 만들고 학습합니다.
B. 매일 Amazon EMR 작업을 실행하여 데이터를 변환하고 Amazon Aurora Serverless에 데이터를 로드합니다. Amazon Aurora ML을 사용하여 ML 모델을 만들고 학습합니다.
C. 매일 AWS Glue 작업을 실행하여 데이터를 변환하고 Amazon Redshift Serverless에 데이터를 로드합니다. Amazon Redshift ML을 사용하여 ML 모델을 만들고 학습합니다.
D. 매일 AWS Glue 작업을 실행하여 데이터를 변환하고 Amazon Athena 테이블에 데이터를 로드합니다. Amazon Athena ML을 사용하여 ML 모델을 만들고 학습합니다.

2. 한 회사가 여러 위치에 데이터 수집 센서를 두고 있습니다. 데이터 수집 센서는 회사에 대량의 데이터를 스트리밍합니다. 이 회사는 AWS에서 대량 스트리밍 데이터를 수집하고 처리하는 플랫폼을 설계하고자 합니다. 이 솔루션은 확장 가능해야 하며 거의 실시간으로 데이터 수집을 지원해야 합니다. 이회사는 향후 보고를 위해 Amazon S3에 데이터를 저장해야 합니다.

어떤 솔루션이 이러한 요구 사항을 가장 적은 운영 오버헤드로 충족할까요?

A. Amazon Kinesis Data Firehose를 사용하여 스트리밍 데이터를 Amazon S3로 전송합니다.
B. AWS Glue를 사용하여 스트리밍 데이터를 Amazon S3에 전송합니다.
C. AWS Lambda를 사용하여 스트리밍 데이터를 전달하고 해당 데이터를 Amazon S3에 저장합니다.
D. AWS Database Migration Service(AWS DMS)를 사용하여 스트리밍 데이터를 Amazon S3로 전송합니다.

3. 한 회사가 백엔드 프로세서에 점수 업데이트를 스트리밍한 다음 리더보드에 결과를 게시하는 모바일 게임을 개발하고 있습니다. 솔루션 아키텍트는 대규모 트래픽 급증을 처리하고, 수신 순서대로 모바일 게임 업데이트를 처리하고, 처리된 업데이트를 고가용성 데이터베이스에 저장할 수 있는 솔루션을 설계해야 합니다. 또한 이 회사는 솔루션을 유지 관리하는 데 필요한 관리 오버헤드를 최소화하려고 합니다.

솔루션 아키텍트는 이러한 요구 사항을 충족하기 위해 무엇을 해야 할까요?

A. Amazon Kinesis Data Streams에 점수 업데이트를 푸시합니다. AWS Lambda로 Kinesis Data Streams에서 업데이트를 처리합니다. 처리된 업데이트를 Amazon DynamoDB에 저장합니다.
B. Amazon Kinesis Data Streams에 점수 업데이트를 푸시합니다. Auto Scaling을 위해 설정된 Amazon EC2 인스턴스 플릿으로 업데이트를 처리합니다. 처리된 업데이트를 Amazon Redshift에 저장합니다.
C. Amazon Simple Notibcation Service(Amazon SNS) 토픽에 점수 업데이트를 푸시합니다. AWS Lambda 함수를 SNS 토픽에 구독하여 업데이트를 처리합니다. 처리된 업데이트를 Amazon EC2에서 실행되는 SQL 데이터베이스에 저장합니다.
D. Amazon Simple Queue Service(Amazon SQS) 대기열에 점수 업데이트를 푸시합니다. Auto Scaling이 있는 Amazon EC2 인스턴스 플릿을 사용하여 SQS 대기열의 업데이트를 처리합니다. 처리된 업데이트를 Amazon RDS Multi-AZ DB 인스턴스에 저장합니다.

4. 한 회사에서 UDP를 사용하는 수천 개의 지리적으로 분산된 원격 장치에서 데이터를 수신하는 애플리케이션을 실행합니다. 이 애플리케이션은 데이터를 즉시 처리하고 필요한 경우 장치로 메시지를 다시 보냅니다. 데이터는 저장되지 않습니다.
이 회사는 장치에서 데이터 전송에 대한 지연 시간을 최소화하는 솔루션이 필요합니다. 이 솔루션은 또한 다른 AWS 지역으로의 빠른 장애 조치를 제공해야 합니다.

어떤 솔루션이 이러한 요구 사항을 충족할까요?

A. Amazon Route 53 장애 조치 라우팅 정책을 구성합니다. 두 리전 각각에 네트워크 로드 밸런서(NLB)를 만듭니다. NLB를 구성하여 AWS Lambda 함수를 호출하여 데이터를 처리합니다.
B. AWS Global Accelerator를 사용합니다. 두 리전 각각에 엔드포인트로 Network Load Balancer(NLB)를 만듭니다. Fargate 시작 유형으로 Amazon Elastic Container Service(Amazon ECS) 클러스터를 만듭니다. 클러스터에서 ECS 서비스를 만듭니다. NLProcess의 대상으로 ECS 서비스를 설정합니다. Amazon ECS에서 데이터를 처리합니다.
C. AWS Global Accelerator를 사용합니다. 두 리전 각각에 엔드포인트로 Application Load Balancer(ALB)를 만듭니다. Fargate 시작 유형으로 Amazon Elastic Container Service(Amazon ECS) 클러스터를 만듭니다. 클러스터에서 ECS 서비스를 만듭니다. ECS 서비스를 ALB의 대상으로 설정합니다. Amazon ECS에서 데이터를 처리합니다.
D. Amazon Route 53 장애 조치 라우팅 정책을 구성합니다. 두 리전 각각에 Application Load Balancer(ALB)를 만듭니다. Fargate 시작 유형으로 Amazon Elastic Container Service(Amazon ECS) 클러스터를 만듭니다. 클러스터에서 ECS 서비스를 만듭니다. ECS 서비스를 ALB의 대상으로 설정합니다. Amazon ECS에서 데이터를 처리합니다.

5. 한 회사에는 타사 공급업체에서 거의 실시간으로 데이터를 수신할 수 있는 REST 기반 인터페이스가 있는 애플리케이션이 있습니다. 수신되면 애플리케이션은 데이터를 처리하고 추가 분석을 위해 저장합니다. 애플리케이션은 Amazon EC2 인스턴스에서 실행 중입니다. 타사 공급업체는 애플리케이션에 데이터를 보낼 때 많은 503 서비스 사용 불가 오류를 수신했습니다. 데이터 볼륨이 급증하면 컴퓨팅 용량이 최대 한도에 도달하고 애플리케이션은 모든 요청을 처리할 수 없습니다.

솔루션 아키텍트는 확장성이 더 뛰어난 솔루션을 제공하기 위해 어떤 설계를 권장해야 합니까?

A. Amazon Kinesis Data Streams를 사용하여 데이터를 수집합니다. AWS Lambda 함수를 사용하여 데이터를 처리합니다.
B. 기존 애플리케이션 위에 Amazon API Gateway를 사용합니다. 타사 공급업체에 대한 할당량 제한이 있는 사용 계획을 만듭니다.
C. Amazon Simple Notibcation Service(Amazon SNS)를 사용하여 데이터를 수집합니다. EC2 인스턴스를 Application Load Balancer 뒤의 Auto Scaling 그룹에 넣습니다.
D. 애플리케이션을 컨테이너로 다시 패키징합니다. Auto Scaling 그룹이 있는 EC2 시작 유형을 사용하여 Amazon Elastic Container Service(Amazon ECS)를 사용하여 애플리케이션을 배포합니다.

---



---
1. 한 회사가 300개가 넘는 글로벌 웹사이트와 애플리케이션을 호스팅합니다. 이 회사는 매일 30TB가 넘는 클릭스트림 데이터를 분석할 플랫폼이 필요합니다.

솔루션 아키텍트는 클릭스트림 데이터를 전송하고 처리하기 위해 무엇을 해야 합니까?

A. AWS 데이터 파이프라인을 설계하여 데이터를 Amazon S3 버킷에 보관하고 해당 데이터로 Amazon EMR 클러스터를 실행하여 분석을 생성합니다.
B. Amazon EC2 인스턴스의 자동 확장 그룹을 생성하여 데이터를 처리하고 이를 Amazon Redshift에서 분석에 사용할 수 있도록 Amazon S3 데이터 레이크로 전송합니다.
C. Amazon CloudFront에 데이터를 캐시합니다. Amazon S3 버킷에 데이터를 저장합니다. S3 버킷에 객체가 추가되면 AWS Lambda 함수를 실행하여 분석을 위해 데이터를 처리합니다.
D. Amazon Kinesis Data Streams에서 데이터를 수집합니다. Amazon Kinesis Data Firehose를 사용하여 데이터를 Amazon S3 데이터 레이크로 전송합니다. 분석을 위해 Amazon Redshift에 데이터를 로드합니다.

2. 한 회사가 AWS에서 온라인 마켓플레이스 웹 애플리케이션을 실행합니다. 이 애플리케이션은 최대 시간대에 수십만 명의 사용자에게 서비스를 제공합니다. 이 회사는 수백만 건의 금융 거래에 대한 세부 정보를 여러 다른 내부 애플리케이션과 공유할 수 있는 확장 가능하고 거의 실시간에 가까운 솔루션이 필요합니다. 또한 트랜잭션은 저지연 검색을 위해 문서 데이터베이스에 저장되기 전에 민감한 데이터를 제거하기 위해 처리되어야 합니다.

솔루션 아키텍트는 이러한 요구 사항을 충족하기 위해 무엇을 권장해야 합니까?

A. 거래 데이터를 Amazon DynamoDB에 저장합니다. DynamoDB에 규칙을 설정하여 쓰기 시 모든 거래에서 민감한 데이터를 제거합니다. DynamoDB Streams를 사용하여 거래 데이터를 다른 애플리케이션과 공유합니다.
B. 거래 데이터를 Amazon Kinesis Data Firehose로 스트리밍하여 Amazon DynamoDB 및 Amazon S3에 데이터를 저장합니다. Kinesis Data Firehose와 AWS Lambda 통합을 사용하여 민감한 데이터를 제거합니다. 다른 애플리케이션은 Amazon S3에 저장된 데이터를 사용할 수 있습니다.
C. 거래 데이터를 Amazon Kinesis Data Streams로 스트리밍합니다. AWS Lambda 통합을 사용하여 모든 거래에서 민감한 데이터를 제거한 다음 거래 데이터를 Amazon DynamoDB에 저장합니다. 다른 애플리케이션은 Kinesis 데이터 스트림에서 거래 데이터를 사용할 수 있습니다.
D. 일괄 처리된 거래 데이터를 Amazon S3에 파일로 저장합니다. AWS Lambda를 사용하여 모든 파일을 처리하고 민감한 데이터를 제거한 후 Amazon S3에 있는 파일을 업데이트합니다. 그런 다음 Lambda 함수는 데이터를 Amazon DynamoDB에 저장합니다. 다른 애플리케이션은 Amazon S3에 저장된 거래 파일을 사용할 수 있습니다.

3. 한 회사는 Amazon EC2 인스턴스에서 실행되는 RESTful 웹 서비스 애플리케이션을 사용하여 수천 개의 원격 장치에서 데이터를 수집합니다. EC2 인스턴스는 원시 데이터를 수신하고, 원시 데이터를 변환하고, 모든 데이터를 Amazon S3 버킷에 저장합니다. 원격 장치의 수는 곧 수백만 개로 늘어날 것입니다. 이 회사는 운영 오버헤드를 최소화하는 확장성이 뛰어난 솔루션이 필요합니다.

솔루션 아키텍트는 이러한 요구 사항을 충족하기 위해 어떤 단계 조합을 취해야 합니까? (두 가지를 선택하세요.)

A. AWS Glue를 사용하여 Amazon S3의 원시 데이터를 처리합니다.
B. Amazon Route 53을 사용하여 다른 EC2 인스턴스로 트래픽을 라우팅합니다.
C. 점점 늘어나는 수신 데이터 양을 수용하기 위해 EC2 인스턴스를 더 추가합니다.
D. 원시 데이터를 Amazon Simple Queue Service(Amazon SQS)로 보냅니다. EC2 인스턴스를 사용하여 데이터를 처리합니다.
E. Amazon API Gateway를 사용하여 원시 데이터를 Amazon Kinesis 데이터 스트림으로 전송합니다. Amazon Kinesis Data Firehose를 구성하여 데이터 스트림을 소스로 사용하여 데이터를 Amazon S3로 전달합니다.

4. 한 회사에 TCP 및 UDP 멀티플레이어 게임 기능이 있는 온라인 게임 애플리케이션이 있습니다. 이 회사는 Amazon Route 53을 사용하여 애플리케이션 트래픽을 여러 AWS 지역의 여러 네트워크 로드 밸런서(NLB)로 연결합니다. 이 회사는 사용자 증가에 대비하여 온라인 게임의 애플리케이션 성능을 개선하고 지연 시간을 줄여야 합니다.

어떤 솔루션이 이러한 요구 사항을 충족할까요?

A. NLB 앞에 Amazon CloudFront 배포를 추가합니다. Cache-Control max-age 매개변수를 늘립니다.
B. NLB를 애플리케이션 로드 밸런서(ALB)로 교체합니다. Route 53을 구성하여 대기 시간 기반 라우팅을 사용합니다.
C. NLB 앞에 AWS Global Accelerator를 추가합니다. 올바른 리스너 포트를 사용하도록 Global Accelerator 엔드포인트를 구성합니다.
D. NLB 뒤에 Amazon API Gateway 엔드포인트를 추가합니다. API 캐싱을 활성화합니다. 다른 단계에 대한 메서드 캐싱을 재정의합니다.

5. 한 회사가 대량의 데이터를 저장하는 새로운 애플리케이션을 만들고 있습니다. 데이터는 매시간 분석되고 여러 가용성 영역에 배포된 여러 Amazon EC2 Linux 인스턴스에 의해 수정됩니다. 필요한 저장 공간의 양은 향후 6개월 동안 계속 증가할 것입니다.
솔루션 아키텍트는 이러한 요구 사항을 충족하기 위해 어떤 저장 솔루션을 권장해야 합니까?
A. Amazon S3 Glacier에 데이터를 저장합니다. S3 Glacier 볼트 정책을 업데이트하여 애플리케이션 인스턴스에 대한 액세스를 허용합니다.
B. Amazon Elastic Block Store(Amazon EBS) 볼륨에 데이터를 저장합니다. 애플리케이션 인스턴스에 EBS 볼륨을 마운트합니다.
C. Amazon Elastic File System(Amazon EFS) 파일 시스템에 데이터를 저장합니다. 애플리케이션 인스턴스에 파일 시스템을 마운트합니다.
D. 애플리케이션 인스턴스 간에 공유되는 Amazon Elastic Block Store(Amazon EBS) 프로비저닝된 IOPS 볼륨에 데이터를 저장합니다.
---


---