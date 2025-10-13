---

1. 한 회사가 Amazon S3 Standard 스토리지를 사용하여 백업 파일을 저장하고 있습니다. 파일은 1개월 동안 자주 액세스됩니다. 그러나 1개월 후에는 파일에 액세스하지 않습니다. 회사는 파일을 무기한 보관해야 합니다. 

어떤 스토리지 솔루션이 이러한 요구 사항을 가장 비용 효율적으로 충족할까요?

A. S3 Intelligent-Tiering을 구성하여 객체를 자동으로 마이그레이션합니다.        
B. 1개월 후 S3 Standard에서 S3 Glacier Deep Archive로 객체를 전환하기 위한 S3 라이프사이클 구성을 생성합니다.       
C. 1개월 후 S3 Standard에서 S3 Standard-Infrequent Access(S3 Standard-IA)로 객체를 전환하기 위한 S3 수명 주기 구성을 생성합니다.        
D. 1개월 후 S3 Standard에서 S3 One Zone-Infrequent Access(S3 One Zone-IA)로 객체를 전환하기 위한 S3 라이프사이클 구성을 생성합니다.     

2. 한 회사가 Amazon API Gateway API에서 호출하는 AWS Lambda 함수에서 애플리케이션을 호스팅합니다. Lambda 함수는 고객 데이터를 Amazon Aurora MySQL 데이터베이스에 저장합니다. 회사가 데이터베이스를 업그레이드할 때마다 Lambda 함수는 업그레이드가 완료될 때까지 데이터베이스 연결을 설정하지 못합니다. 그 결과 일부 이벤트에 대한 고객 데이터가 기록되지 않습니다. 

솔루션 아키텍트는 데이터베이스 업그레이드 중에 생성된 고객 데이터를 저장하는 솔루션을 설계해야 합니다.

어떤 솔루션이 이러한 요구 사항을 충족할까요

A. Lambda 함수와 데이터베이스 사이에 Amazon RDS 프록시를 프로비저닝합니다. Lambda 함수를 구성하여 RDS 프록시에 연결합니다.      
B. Lambda 함수의 실행 시간을 최대로 늘립니다. 고객 데이터를 데이터베이스에 저장하는 코드에 재시도 메커니즘을 만듭니다.      
C. 고객 데이터를 Lambda 로컬 스토리지에 유지합니다. 로컬 스토리지를 스캔하여 고객 데이터를 데이터베이스에 저장하도록 새로운 Lambda 함수를 구성합니다.       
D. Amazon Simple Queue Service(Amazon SQS) FIFO 대기열에 고객 데이터를 저장합니다. 대기열을 폴링하고 고객 데이터를 데이터베이스에 저장하는 새로운 Lambda 함수를 만듭니다.       

3. 어떤 회사에는 다음 구성 요소가 포함된 데이터 수집 워크플로가 있습니다. 

- 새 데이터 전송에 대한 알림을 수신하는 Amazon Simple Notification Service(Amazon SNS) 토픽 
- 데이터를 처리하고 저장하는 AWS Lambda 함수 

수집 워크플로는 가끔 네트워크 연결 문제로 인해 실패합니다. 실패가 발생하면 회사에서 수동으로 작업을 다시 실행하지 않는 한 해당 데이터는 수집되지 않습니다. 

솔루션 아키텍트는 모든 알림이 결국 처리되도록 하기 위해 무엇을 해야 합니까

A. 여러 가용성 영역에 배포하기 위해 Lambda 함수를 구성합니다.       
B. Lambda 함수의 구성을 수정하여 함수에 대한 CPU 및 메모리 할당을 늘립니다.         
C. SNS 토픽의 재시도 전략을 구성하여 재시도 횟수와 재시도 간 대기 시간을 모두 늘립니다.         
D. Amazon Simple Queue Service(Amazon SQS) 대기열을 실패 시 목적지로 구성합니다. 대기열의 메시지를 처리하도록 Lambda 함수를 수정합니다      

4. 한 회사가 애플리케이션 로드 밸런서 뒤에 있는 Amazon EC2 온디맨드 인스턴스 그룹에서 프로덕션에서 상태 없는 웹 애플리케이션을 실행합니다. 이 애플리케이션은 각 영업일 8시간 동안 많은 사용량을 경험합니다. 애플리케이션 사용량은 밤새 적당하고 안정적입니다. 주말에는 애플리케이션 사용량 이 낮습니다.

이 회사는 애플리케이션의 가용성에 영향을 미치지 않으면서 EC2 비용을 최소화하려고 합니다.

어떤 솔루션이 이러한 요구 사항을 충족할까요?
A. 전체 작업 부하에 대해 스팟 인스턴스를 사용합니다.        
B. 기본 사용 수준에 예약 인스턴스를 사용합니다. 애플리케이션에 필요한 추가 용량에는 스팟 인스턴스를 사용합니다.         
C. 기본 사용 수준에는 온디맨드 인스턴스를 사용합니다. 애플리케이션에 필요한 추가 용량에는 스팟 인스턴스를 사용합니다.       
D. 기본 사용 수준에는 전용(dedicated) 인스턴스를 사용합니다. 애플리케이션에 필요한 추가 용량에는 온디맨드 인스턴스를 사용합니다.        

5. 개발팀은 다른 팀에서 액세스할 웹사이트를 호스팅해야 합니다. 웹사이트 콘텐츠는 HTML, CSS, 클라이언트 측 JavaScript 및 이미지로 구성됩니다. 웹사이트를 호스팅하는 데 가장 비용 효율적인 방법은 무엇입니까

A. 웹사이트를 컨테이너화하여 AWS Fargate에 호스팅합니다.        
B. Amazon S3 버킷을 생성하고 거기에 웹사이트를 호스팅합니다.        
C. Amazon EC2 인스턴스에 웹 서버를 배포하여 웹사이트를 호스팅합니다.        
D. Express.js 프레임워크를 사용하는 AWS Lambda 대상으로 애플리케이션 로드 밸런서를 구성합니다       

---
BDDBB

---

1. 한 회사가 월별로 통화 기록 파일을 저장합니다. 사용자는 통화 후 1년 이내에 무작위로 파일에 액세스하지만, 1년 후에는 드물게 파일에 액세스합니다. 이 회사는 사용자에게 1년 미만의 파일을 가능한 한 빨리 쿼리하고 검색할 수 있는 기능을 제공하여 솔루션을 최적화하고자 합니다. 이전 파일을 검색하는 데 지연이 있어도 괜찮습니다.

어떤 솔루션이 이러한 요구 사항을 가장 비용 효율적으로 충족할까요?

A. Amazon S3 Glacier Instant Retrieval에 태그가 있는 개별 파일을 저장합니다. 태그를 쿼리하여 S3 Glacier Instant Retrieval에서 파일을 검색합 니다.       
B. Amazon S3 Intelligent-Tiering에 개별 파일을 저장합니다. S3 Lifecycle 정책을 사용하여 1년 후 S3 Glacier Flexible Retrieval로 파일을 이동합니다. Amazon Athena를 사용하여 Amazon S3에 있는 파일을 쿼리하고 검색합니다. S3 Glacier Select를 사용하여 S3 Glacier에 있는 파일을 쿼리하 고 검색합니다.         
C. Amazon S3 Standard 스토리지에 태그가 있는 개별 파일을 저장합니다. 각 아카이브에 대한 검색 메타데이터를 Amazon S3 Standard 스토리지 에 저장합니다. S3 Lifecycle 정책을 사용하여 1년 후 파일을 S3 Glacier Instant Retrieval로 이동합니다. Amazon S3에서 메타데이터를 검색하여 파 일을 쿼리하고 검색합니다.         
D. 개별 파일을 Amazon S3 Standard 스토리지에 저장합니다. S3 Lifecycle 정책을 사용하여 1년 후 파일을 S3 Glacier Deep Archive로 이동합니다. 검색 메타데이터를 Amazon RDS에 저장합니다. Amazon RDS에서 파일을 쿼리합니다. S3 Glacier Deep Archive에서 파일을 검색합니다.           

2. 애플리케이션 개발팀은 큰 이미지를 더 작고 압축된 이미지로 변환하는 마이크로서비스를 설계하고 있습니다. 사용자가 웹 인터페이스를 통해 이미지를 업로드하면 마이크로서비스는 이미지를 Amazon S3 버킷에 저장하고, AWS Lambda 함수로 이미지를 처리하고 압축하고, 압축된 형태로 이미지를 다른 S3 버킷에 저장해야 합니다.

솔루션 아키텍트는 내구성이 뛰어나고 상태 없는 구성 요소를 사용하여 이미지를 자동으로 처리하는 솔루션을 설계해야 합니다.

이러한 요구 사항을 충족하는 작업의 조합은 무엇입니까? (두 가지를 선택하십시오.)

A. Amazon Simple Queue Service(Amazon SQS) 대기열을 만듭니다. 이미지가 S3 버킷에 업로드되면 SQS 대기열에 알림을 보내도록 S3 버킷을 구성합니다.      
B. Lambda 함수를 구성하여 Amazon Simple Queue Service(Amazon SQS) 대기열을 호출 소스로 사용합니다. SQS 메시지가 성공적으로 처리되면 대기열에서 메시지를 삭제합니다.         
C. Lambda 함수를 구성하여 S3 버킷에서 새 업로드를 모니터링합니다. 업로드된 이미지가 감지되면 파일 이름을 메모리의 텍스트 파일에 쓰고 텍스트 파일을 사용하여 처리된 이미지를 추적합니다.         
D. Amazon Simple Queue Service(Amazon SQS) 대기열을 모니터링하기 위해 Amazon EC2 인스턴스를 시작합니다. 대기열에 항목이 추가되면 EC2 인스턴스의 텍스트 파일에 파일 이름을 기록하고 Lambda 함수를 호출합니다.        
E. Amazon EventBridge(Amazon CloudWatch Events) 이벤트를 구성하여 S3 버킷을 모니터링합니다. 이미지가 업로드되면 Amazon Ample Notibcation Service(Amazon SNS) 토픽에 알림을 보내 추가 처리를 위해 애플리케이션 소유자의 이메일 주소를 입력합니다.        

3. 어떤 회사에는 Amazon RDS의 데이터베이스에 목록을 저장하는 자동차 판매 웹사이트가 있습니다. 자동차가 판매되면 목록을 웹사이트에서 제거하고 데이터를 여러 대상 시스템으로 보내야 합니다.

솔루션 아키텍트는 어떤 디자인을 추천해야 할까요

A. Amazon RDS의 데이터베이스가 업데이트되면 Amazon Simple Queue Service(Amazon SQS) 대기열로 정보를 전송하여 대상이 사용할 수 있도 록 하는 AWS Lambda 함수를 생성합니다.         
B. Amazon RDS의 데이터베이스가 업데이트되면 Amazon Simple Queue Service(Amazon SQS) FIFO 대기열로 정보를 전송하여 대상이 사용할 수 있도록 하는 AWS Lambda 함수를 생성합니다.        
C. RDS 이벤트 알림을 구독하고 Amazon Simple Queue Service(Amazon SQS) 대기열을 여러 Amazon Simple Notibcation Service(Amazon SNS) 토픽으로 분산하여 보냅니다. AWS Lambda 함수를 사용하여 대상을 업데이트합니다.         
D. RDS 이벤트 알림을 구독하고 Amazon Simple Notibcation Service(Amazon SNS) 주제를 여러 Amazon Simple Queue Service(Amazon SQS) 대 기열로 분산하여 보냅니다. AWS Lambda 함수를 사용하여 대상을 업데이트합니다.      

4. 한 회사에서 기존 3계층 웹 아키텍처의 비용을 절감하고자 합니다. 웹, 애플리케이션 및 데이터베이스 서버는 개발, 테스트 및 프로덕션 환경을 위해 Amazon EC2 인스턴스에서 실행됩니다. EC2 인스턴스는 피크 시간에 평균 30%의 CPU 사용률을 보이고 비피크 시간에는 10%의 CPU 사용률을 보입니다.

프로덕션 EC2 인스턴스는 하루 24시간 실행됩니다. 개발 및 테스트 EC2 인스턴스는 매일 최소 8시간 실행됩니다. 이 회사는 개발 및 테스트 EC2 인스턴 스가 사용되지 않을 때 중단하기 위한 자동화를 구현할 계획입니다.

어떤 EC2 인스턴스 구매 솔루션이 회사의 요구 사항을 가장 비용 효율적으로 충족할까요?

A. 프로덕션 EC2 인스턴스에는 Spot Instances를 사용합니다. 개발 및 테스트 EC2 인스턴스에는 Reserved Instances를 사용합니다.      
B. 프로덕션 EC2 인스턴스에는 예약 인스턴스를 사용합니다. 개발 및 테스트 EC2 인스턴스에는 온디맨드 인스턴스를 사용합니다.        
C. 프로덕션 EC2 인스턴스에는 Spot 블록을 사용합니다. 개발 및 테스트 EC2 인스턴스에는 Reserved Instances를 사용합니다.       
D. 프로덕션 EC2 인스턴스에는 온디맨드 인스턴스를 사용합니다. 개발 및 테스트 EC2 인스턴스에는 스팟 블록을 사용합니다.        

5. 미디어 회사가 시스템을 AWS 클라우드로 이전할 가능성을 평가하고 있습니다. 이 회사는 비디오 처리를 위한 최대 I/O 성능을 갖춘 최소 10TB의 스토리지, 미디어 콘텐츠를 저장하기 위한 300TB의 매우 내구성 있는 스토리지, 더 이상 사용하지 않는 보관 미디어에 대한 요구 사항을 충족하기 위한 900TB의 스토리지가 필요합니다.

이러한 요구 사항을 충족하기 위해 솔루션 아키텍트는 어떤 서비스 세트를 권장해야 합니까

A. 최대 성능을 위한 Amazon EBS, 내구성 있는 데이터 스토리지를 위한 Amazon S3, 보관 스토리지를 위한 Amazon S3 Glacier        
B. 최대 성능을 위한 Amazon EBS, 내구성 있는 데이터 스토리지를 위한 Amazon EFS, 보관 스토리지를 위한 Amazon S3 Glacier       
C. 최대 성능을 위한 Amazon EC2 인스턴스 스토어, 내구성 있는 데이터 스토리지를 위한 Amazon EFS, 보관 스토리지를 위한 Amazon S3       
D. 최대 성능을 위한 Amazon EC2 인스턴스 스토어, 내구성 있는 데이터 스토리지를 위한 Amazon S3, 보관 스토리지를 위한 Amazon S3 Glacier        

---

B/AB/B/B/D

---

1. 어떤 회사는 Amazon S3에 회계 기록을 저장해야 합니다. 기록은 1년 동안 즉시 액세스할 수 있어야 하며, 그 후 9년 동안 보관해야 합니다. 관리자와 루트 사용자를 포함하여 회사의 어느 누구도 10년 동안 기록을 삭제할 수 없습니다. 기록은 최대한의 복원력으로 저장해야 합니다.

어떤 솔루션이 이러한 요구 사항을 충족할까요?

A. S3 Glacier에 10년 전체 기간 동안 레코드를 저장합니다. 액세스 제어 정책을 사용하여 10년 동안 레코드 삭제를 거부합니다.        
B. S3 Intelligent-Tiering을 사용하여 레코드를 저장합니다. IAM 정책을 사용하여 레코드 삭제를 거부합니다. 10년 후 IAM 정책을 변경하여 삭제를 허용합니다.      
C. S3 Lifecycle 정책을 사용하여 1년 후 S3 Standard에서 S3 Glacier Deep Archive로 레코드를 전환합니다. 10년 동안 S3 Object Lock을 준수 모드 로 사용합니다.       
D. S3 Lifecycle 정책을 사용하여 1년 후 S3 Standard에서 S3 One Zone-Infrequent Access(S3 One Zone-IA)로 레코드를 전환합니다. 10년 동안 거버넌스 모드에서 S3 Object Lock을 사용합니다     

2. 한 회사가 온프레미스에서 AWS 클라우드로 다중 계층 애플리케이션을 이전하여 애플리케이션의 성능을 개선하고자 합니다. 애플리케이션은 RESTful 서비스를 통해 서로 통신하는 애플리케이션 계층으로 구성되어 있습니다. 한 계층이 과부하되면 트랜잭션이 삭제됩니다. 솔루션 아키텍트는 이러한 문제를 해결하고 애플리케이션을 현대화하는 솔루션을 설계해야 합니다.

이러한 요구 사항을 충족하고 가장 운영 효율적인 솔루션은 무엇입니까

A. Amazon API Gateway를 사용하고 AWS Lambda 함수에 대한 직접 거래를 애플리케이션 계층으로 사용합니다. Amazon Simple Queue Service(Amazon SQS)를 애플리케이션 서비스 간의 통신 계층으로 사용합니다.      
B. Amazon CloudWatch 메트릭을 사용하여 애플리케이션 성능 기록을 분석하여 성능 실패 중 서버의 최대 사용률을 확인합니다. 최대 요구 사항을 충족하도록 애플리케이션 서버의 Amazon EC2 인스턴스 크기를 늘립니다.         
C. Amazon Simple Notibcation Service(Amazon SNS)를 사용하여 Auto Scaling 그룹의 Amazon EC2에서 실행되는 애플리케이션 서버 간의 메시징을 처리합니다. Amazon CloudWatch를 사용하여 SNS 대기열 길이를 모니터링하고 필요에 따라 확장 및 축소합니다.         
D. Amazon Simple Queue Service(Amazon SQS)를 사용하여 Auto Scaling 그룹에서 Amazon EC2에서 실행되는 애플리케이션 서버 간의 메시징 을 처리합니다. Amazon CloudWatch를 사용하여 SQS 대기열 길이를 모니터링하고 통신 오류가 감지되면 확장합니다.       

3. 소셜 미디어 회사에서는 사용자가 이미지를 웹사이트에 업로드할 수 있도록 허용합니다. 이 웹사이트는 Amazon EC2 인스턴스에서 실행됩니다. 업로드 요청 중에 웹사이트는 이미지 크기를 표준 크기로 조정하고 크기가 조정된 이미지를 Amazon S3에 저장합니다. 사용자는 웹사이트에 대한 업로드 요청 이 느리다는 것을 경험하고 있습니다.

이 회사는 애플리케이션 내에서 결합을 줄이고 웹사이트 성능을 개선해야 합니다. 솔루션 아키텍트는 이미지 업로드를 위한 가장 운영 효율적인 프로세 스를 설계해야 합니다.

솔루션 아키텍트는 이러한 요구 사항을 충족하기 위해 어떤 조치 조합을 취해야 합니까? (두 가지를 선택하세요.)  

A. S3 Glacier에 이미지를 업로드하도록 애플리케이션을 구성합니다.         
B. 웹 서버를 구성하여 원본 이미지를 Amazon S3에 업로드합니다.       
C. 미리 서명된 URL을 사용하여 각 사용자의 브라우저에서 Amazon S3로 직접 이미지를 업로드하도록 애플리케이션을 구성합니다.        
D. 이미지가 업로드될 때 AWS Lambda 함수를 호출하도록 S3 이벤트 알림을 구성합니다. 함수를 사용하여 이미지 크기를 조정합니다.         
E. 업로드된 이미지의 크기를 조정하기 위해 일정에 따라 AWS Lambda 함수를 호출하는 Amazon EventBridge(Amazon CloudWatch Events) 규칙 을 만듭니다      

4. 한 회사에서는 많은 Amazon EC2 인스턴스를 사용하여 완료하는 매우 동적인 일괄 처리 작업을 합니다. 이 작업은 본질적으로 상태 비저장이며, 부정적인 영향 없이 언제든지 시작 및 중지할 수 있으며, 일반적으로 완료하는 데 총 60분 이상 걸립니다. 이 회사는 솔루션 아키텍트에게 작업 요구 사항을 충 족하는 확장 가능하고 비용 효율적인 솔루션을 설계해 달라고 요청했습니다.

솔루션 아키텍트는 무엇을 추천해야 합니까?

A. EC2 스팟 인스턴스를 구현합니다.      
B. EC2 예약 인스턴스를 구매합니다.      
C. EC2 온디맨드 인스턴스를 구현합니다.      
D. AWS Lambda에서 처리를 구현합니다.                

5. 어떤 회사는 확장성과 가용성에 대한 요구 사항을 충족하기 위해 컨테이너에서 중요한 애플리케이션을 실행하고자 합니다. 이 회사는 중요한 애플리케이션의 유지 관리에 집중하는 것을 선호합니다. 이 회사는 컨테이너화된 워크로드를 실행하는 기본 인프라를 프로비저닝하고 관리하는 책임을 맡고 싶어하지 않습니다.

솔루션 아키텍트는 이러한 요구 사항을 충족하기 위해 무엇을 해야 할까요

A. Amazon EC2 인스턴스를 사용하고 인스턴스에 Docker를 설치합니다.       
B. Amazon EC2 워커 노드에서 Amazon Elastic Container Service(Amazon ECS)를 사용합니다.      
C. AWS Fargate에서 Amazon Elastic Container Service(Amazon ECS)를 사용합니다.       
D. Amazon Elastic Container Service(Amazon ECS)에 최적화된 Amazon Machine Image(AMI)에서 Amazon EC2 인스턴스를 사용합니다       

---

C/A/BD/A/C

---

1. 한 회사에는 각각 약 5MB 크기의 많은 파일을 생성하는 애플리케이션이 있습니다. 이 파일은 Amazon S3에 저장됩니다. 회사 정책에 따라 이 파일은 삭제하기 전에 4년 동안 보관해야 합니다. 파일에는 쉽게 재생산할 수 없는 중요한 비즈니스 데이터가 포함되어 있으므로 항상 즉각적인 접근성이 필요합니다. 이 파일은 객체 생성 후 처음 30일 동안 자주 액세스되지만 처음 30일 이후에는 거의 액세스되지 않습니다.

어떤 스토리지 솔루션이 가장 비용 효율적일까요?

A. 객체 생성 후 30일 후에 S3 Standard에서 S3 Glacier로 파일을 이동하는 S3 버킷 수명 주기 정책을 만듭니다. 객체 생성 후 4년 후에 파일을 삭제 합니다.     
B. 객체 생성 후 30일 후에 S3 Standard에서 S3 One Zone-Infrequent Access(S3 One Zone-IA)로 파일을 이동하는 S3 버킷 수명 주기 정책을 만듭니다. 객체 생성 후 4년 후에 파일을 삭제합니다.        
C. 객체 생성 후 30일 후에 S3 Standard에서 S3 Standard-Infrequent Access(S3 Standard-IA)로 파일을 이동하는 S3 버킷 수명 주기 정책을 만듭니다. 객체 생성 후 4년 후에 파일을 삭제합니다.           
D. 객체 생성 후 30일 후에 S3 Standard에서 S3 Standard-Infrequent Access(S3 Standard-IA)로 파일을 이동하는 S3 버킷 수명 주기 정책을 만듭니다. 객체 생성 후 4년 후에 파일을 S3 Glacier로 이동합니다        

2. 한 회사에는 다음으로 구성된 데이터 수집 워크플로가 있습니다. 
• 새 데이터 전송에 대한 알림을 위한 Amazon Simple Notibcation Service(Amazon SNS) 주제 
• 데이터를 처리하고 메타데이터를 기록하는 AWS Lambda 함수 
이 회사는 네트워크 연결 문제로 인해 수집 워크플로가 가끔 실패하는 것을 관찰합니다. 이러한 실패가 발생하면 Lambda 함수는 회사에서 수동으로 작업을 다시 실행하지 않는 한 해당 데이터를 수집하지 않습니다. 

솔루션 아키텍트는 Lambda 함수가 앞으로 모든 데이터를 수집하도록 하기 위해 어떤 작업 조합을 취해야 합니까? (두 가지를 선택하세요.)

A. 여러 가용성 영역에 Lambda 함수를 배포합니다.         
B. Amazon Simple Queue Service(Amazon SQS) 대기열을 생성하고 이를 SNS 주제에 구독합니다.            
C. Lambda 함수에 할당된 CPU와 메모리를 늘립니다.        
D. Lambda 함수에 대한 프로비저닝된 처리량을 늘립니다.       
E. Amazon Simple Queue Service(Amazon SQS) 대기열에서 읽도록 Lambda 함수를 수정합니다.      

3. 한 회사에서 사용자가 사진을 업로드하고 이미지에 사진 프레임을 추가할 수 있는 이미지 분석 애플리케이션을 만들었습니다. 사용자는 이미지와 메타 데이터를 업로드하여 이미지에 추가할 사진 프레임을 나타냅니다. 이 애플리케이션은 단일 Amazon EC2 인스턴스와 Amazon DynamoDB를 사용하여 메타데이터를 저장합니다.

이 애플리케이션은 점점 더 인기를 얻고 있으며 사용자 수도 증가하고 있습니다. 이 회사는 동시 사용자 수가 시간대와 요일에 따라 크게 달라질 것으로 예상합니다. 이 회사는 애플리케이션이 증가하는 사용자 기반의 요구 사항을 충족하도록 확장할 수 있도록 해야 합니다. 어떤 솔루션이 이러한 요구 사항을 충족합니까?

A. AWS Lambda를 사용하여 사진을 처리합니다. DynamoDB에 사진과 메타데이터를 저장합니다.      
B. Amazon Kinesis Data Firehose를 사용하여 사진을 처리하고 사진과 메타데이터를 저장합니다.      
C. AWS Lambda를 사용하여 사진을 처리합니다. Amazon S3에 사진을 저장합니다. DynamoDB를 유지하여 메타데이터를 저장합니다.     
D. EC2 인스턴스 수를 3개로 늘립니다. Provisioned IOPS SSD(io2) Amazon Elastic Block Store(Amazon EBS) 볼륨을 사용하여 사진과 메타데이터를 저장합니다.       

4. 솔루션 아키텍트는 회사가 AWS에서 애플리케이션을 실행하는데 드는 비용을 최적화하도록 도와야 합니다. 이 애플리케이션은 아키텍처 내에서 컴퓨팅을 위해 Amazon EC2 인스턴스, AWS Fargate, AWS Lambda를 사용합니다.

EC2 인스턴스는 애플리케이션의 데이터 수집 계층을 실행합니다. EC2 사용은 산발적이고 예측할 수 없습니다. EC2 인스턴스에서 실행되는 워크로드는 언제든지 중단될 수 있습니다. 애플리케이션 프런트 엔드는 Fargate에서 실행되고 Lambda는 API 계층을 제공합니다. 프런트 엔드 사용률과 API 계층 사용률은 내년 내내 예측 가능합니다.

이 애플리케이션을 호스팅하는 데 가장 비용 효율적인 솔루션을 제공하는 구매 옵션의 조합은 무엇입니까? (두 가지를 선택하십시오.)

A. 데이터 수집 계층에 Spot Instances 사용       
B. 데이터 수집 계층에 온디맨드 인스턴스 사용        
C. 프런트엔드 및 API 계층에 대한 1년 컴퓨팅 절감 플랜을 구매하세요.         
D. 데이터 수집 계층에 대해 1년 선불 예약 인스턴스를 구매합니다.         
E. 프런트엔드 및 API 계층에 대한 1년 EC2 인스턴스 절감 플랜을 구매하세요        

5. 한 회사가 온프레미스 애플리케이션을 AWS로 마이그레이션하려고 합니다. 이 애플리케이션은 수십 기가바이트에서 수백 테라바이트에 이르는 다양한 크기의 출력 파일을 생성합니다. 애플리케이션 데이터는 표준 파일 시스템 구조에 저장해야 합니다. 이 회사는 자동으로 확장되는 솔루션을 원합니다. 가용성이 높고 최소한의 운영 오버헤드만 필요합니다. 어떤 솔루션이 이러한 요구 사항을 충족할까요

A. Amazon Elastic Container Service(Amazon ECS)에서 컨테이너로 실행되도록 애플리케이션을 마이그레이션합니다. 스토리지로 Amazon S3를 사용합니다.             
B. Amazon Elastic Kubernetes Service(Amazon EKS)에서 컨테이너로 실행되도록 애플리케이션을 마이그레이션합니다. 스토리지로 Amazon Elastic Block Store(Amazon EBS)를 사용합니다.               
C. 애플리케이션을 Multi-AZ Auto Scaling 그룹의 Amazon EC2 인스턴스로 마이그레이션합니다. 스토리지에 Amazon Elastic File System(Amazon EFS)을 사용합니다.            
D. 애플리케이션을 Multi-AZ Auto Scaling 그룹의 Amazon EC2 인스턴스로 마이그레이션합니다. 스토리지에 Amazon Elastic Block Store(Amazon EBS)를 사용합니다.        

---

C/BE/C/AC/C

---

1. 솔루션 아키텍트는 회사의 스토리지 비용을 줄이기 위한 솔루션을 구현해야 합니다. 회사의 모든 데이터는 Amazon S3 Standard 스토리지 클래스에 있습니다. 회사는 모든 데이터를 최소 25년 동안 보관해야 합니다. 가장 최근 2년 동안의 데이터는 가용성이 높고 즉시 검색할 수 있어야 합니다.

어떤 솔루션이 이러한 요구 사항을 충족할까요

A. 객체를 S3 Glacier Deep Archive로 즉시 전환하기 위한 S3 수명 주기 정책을 설정합니다.      
B. 2년 후 객체를 S3 Glacier Deep Archive로 전환하기 위한 S3 수명 주기 정책을 설정합니다.        
C. S3 Intelligent-Tiering을 사용합니다. 데이터가 S3 Glacier Deep Archive에 보관되도록 보관 옵션을 활성화합니다.                 
D. 객체를 즉시 S3 One Zone-Infrequent Access(S3 One Zone-IA)로 전환하고 2년 후에는 S3 Glacier Deep Archive로 전환하는 S3 수명 주기 정책 을 설정합니다.

2. 한 회사가 사용자가 작은 파일을 Amazon S3에 업로드하는 애플리케이션을 설계하고 있습니다. 사용자가 파일을 업로드한 후, 해당 파일은 데이터를 변환하고 JSON 형식으로 저장하여 나중에 분석하기 위해 한 번의 간단한 처리가 필요합니다.

각 파일은 업로드 후 가능한 한 빨리 처리해야 합니다. 수요는 다양합니다. 어떤 날에는 사용자가 많은 수의 파일을 업로드합니다. 다른 날에는 사용자가 몇 개의 파일을 업로드하거나 전혀 업로드하지 않습니다.

어떤 솔루션이 운영 오버헤드를 최소화하면서 이러한 요구 사항을 충족할까요

A. Amazon S3에서 텍스트 파일을 읽도록 Amazon EMR을 구성합니다. 처리 스크립트를 실행하여 데이터를 변환합니다. 결과 JSON 파일을 Amazon Aurora DB 클러스터에 저장합니다        
B. Amazon S3를 구성하여 Amazon Simple Queue Service(Amazon SQS) 대기열에 이벤트 알림을 보냅니다. Amazon EC2 인스턴스를 사용하여 대 기열에서 읽고 데이터를 처리합니다. 결과 JSON 파일을 Amazon DynamoDB에 저장합니다.        
C. Amazon S3를 구성하여 Amazon Simple Queue Service(Amazon SQS) 대기열에 이벤트 알림을 보냅니다. AWS Lambda 함수를 사용하여 대기 열에서 읽고 데이터를 처리합니다. 결과 JSON 파일을 Amazon DynamoDB에 저장합니다.        
D. 새 파일이 업로드되면 Amazon Kinesis Data Streams에 이벤트를 보내도록 Amazon EventBridge(Amazon CloudWatch Events)를 구성합니다. AWS Lambda 함수를 사용하여 스트림에서 이벤트를 소비하고 데이터를 처리합니다. 결과 JSON 파일을 Amazon Aurora DB 클러스터에 저장합니 다.       

3. 한 회사에서 사용자가 사진을 업로드하고 이미지에 사진 프레임을 추가할 수 있는 이미지 분석 애플리케이션을 만들었습니다. 사용자는 이미지와 메타 데이터를 업로드하여 이미지에 추가할 사진 프레임을 나타냅니다. 이 애플리케이션은 단일 Amazon EC2 인스턴스와 Amazon DynamoDB를 사용하여 메타데이터를 저장합니다.

이 애플리케이션은 점점 더 인기를 얻고 있으며 사용자 수도 증가하고 있습니다. 이 회사는 동시 사용자 수가 시간대와 요일에 따라 크게 달라질 것으로 예상합니다. 이 회사는 애플리케이션이 증가하는 사용자 기반의 요구 사항을 충족하도록 확장할 수 있도록 해야 합니다.

어떤 솔루션이 이러한 요구 사항을 충족합니까?

A. AWS Lambda를 사용하여 사진을 처리합니다. DynamoDB에 사진과 메타데이터를 저장합니다.      
B. Amazon Kinesis Data Firehose를 사용하여 사진을 처리하고 사진과 메타데이터를 저장합니다.      
C. AWS Lambda를 사용하여 사진을 처리합니다. Amazon S3에 사진을 저장합니다. DynamoDB에 메타데이터를 저장합니다.      
D. EC2 인스턴스 수를 3개로 늘립니다. Provisioned IOPS SSD(io2) Amazon Elastic Block Store(Amazon EBS) 볼륨을 사용하여 사진과 메타 데이터를 저장합니다.      

4. 솔루션 아키텍트는 클라이언트 사례 파일을 저장하는 시스템을 설계해야 합니다. 파일은 핵심 회사 자산이며 중요합니다. 파일 수는 시간이 지남에 따라 증가합니다.

파일은 Amazon EC2 인스턴스에서 실행되는 여러 애플리케이션 서버에서 동시에 액세스할 수 있어야 합니다. 솔루션에는 기본 제공 중복성이 있어야 합니다.

어떤 솔루션이 이러한 요구 사항을 충족합니까?

A. Amazon Elastic File System(Amazon EFS)       
B. Amazon Elastic Block Store(Amazon EBS)       
C. Amazon S3 Glacier Deep Archive       
D. AWS 백업     

5. 어떤 회사가 새로운 동적 주문 웹사이트를 구축하고 있습니다. 이 회사는 서버 유지 관리 및 패치를 최소화하고자 합니다. 웹사이트는 고가용성이어야 하며 사용자 수요의 변화에 대응하기 위해 가능한 한 빨리 읽기 및 쓰기 용량을 확장해야 합니다.

어떤 솔루션이 이러한 요구 사항을 충족할까요

A. Amazon S3에 정적 콘텐츠를 호스팅합니다. Amazon API Gateway와 AWS Lambda를 사용하여 동적 콘텐츠를 호스팅합니다. 데이터베이스에 대한 주문형 용량으로 Amazon DynamoDB를 사용합니다. Amazon CloudFront를 구성하여 웹사이트 콘텐츠를 제공합니다.      
B. Amazon S3에 정적 콘텐츠를 호스팅합니다. Amazon API Gateway와 AWS Lambda를 사용하여 동적 콘텐츠를 호스팅합니다. 데이터베이스에 Aurora Auto Scaling과 함께 Amazon Aurora를 사용합니다. Amazon CloudFront를 구성하여 웹사이트 콘텐츠를 제공합니다.      
C. Amazon EC2 인스턴스에서 모든 웹사이트 콘텐츠를 호스팅합니다. EC2 인스턴스를 확장하기 위해 Auto Scaling 그룹을 만듭니다. 트래픽을 분 산하기 위해 Application Load Balancer를 사용합니다. 데이터베이스에 대한 프로비저닝된 쓰기 용량이 있는 Amazon DynamoDB를 사용합니다.      
D. 모든 웹사이트 콘텐츠를 Amazon EC2 인스턴스에 호스팅합니다. EC2 인스턴스를 확장하기 위해 Auto Scaling 그룹을 만듭니다. 트래픽을 분산 하기 위해 Application Load Balancer를 사용합니다. 데이터베이스에 Aurora Auto Scaling과 함께 Amazon Aurora를 사용합니다.      



---

BCCAA
