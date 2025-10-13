1. 한 회사가 회사의 AWS 계정에서 작업을 수행하기 위해 외부 공급업체를 고용했습니다. 공급업체는 공급업체가 소유한 AWS 계정에 호스팅된 자동화된 도구를 사용합니다. 공급업체는 회사의 AWS 계정에 대한 IAM 액세스 권한이 없습니다.
솔루션 아키텍트는 어떻게 공급업체에 이 액세스 권한을 부여해야 합니까?

A. 회사 계정에서 IAM 역할을 만들어 공급업체의 IAM 역할에 대한 액세스를 위임합니다. 공급업체가 요구하는 권한에 대한 적절한 IAM 정책을 역할에 첨부합니다.
B. 비밀번호 복잡성 요구 사항을 충족하는 비밀번호로 회사 계정에서 IAM 사용자를 만듭니다. 공급업체가 요구하는 권한에 대해 적절한 IAM 정책을 사용자에게 첨부합니다.
C. 회사 계정에서 IAM 그룹을 만듭니다. 공급업체 계정에서 도구의 IAM 사용자를 그룹에 추가합니다. 공급업체가 요구하는 권한에 대한 적절한 IAM 정책을 그룹에 연결합니다.
D. IAM 콘솔에서 공급자 유형으로 "AWS 계정"을 선택하여 새 ID 공급자를 만듭니다. 공급업체의 AWS 계정 ID와 사용자 이름을 제공합니다. 공급업체가 요구하는 권한에 대한 적절한 IAM 정책을 새 공급자에 연결합니다.

2. 한 회사에서 Amazon EC2 인스턴스를 사용하여 내부 시스템을 호스팅합니다.
배포 작업의 일부로 관리자가 AWS CLI를 사용하여 EC2 인스턴스를 종료하려고 합니다.
그러나 관리자는 403(액세스 거부) 오류 메시지를 받습니다.

관리자는 다음 IAM 정책이 첨부된 IAM 역할을 사용하고 있습니다:

{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": ["ec2:TerminateInstances"],
      "Resource": ["*"]
    },
    {
      "Effect": "Deny",
      "Action": ["ec2:TerminateInstances"],
      "Condition": {
        "NotIpAddress": {
          "aws:SourceIp": [
            "192.0.2.0/24",
            "203.0.113.0/24"
          ]
        }
      },
      "Resource": ["*"]
    }
  ]
}


실패한 요청의 원인은 무엇입니까? 

A. EC2 인스턴스에는 Deny 문이 있는 리소스 기반 정책이 있습니다.
B. 정책 생성시에 principal이 명시되지 않았습니다.
C. "Action" 필드에 EC2 인스턴스를 종료하는 데 필요한 작업을 허용하지 않았습니다.
D. EC2 인스턴스를 종료하려는 요청은 CIDR 블록 192.0.2.0/24 또는 203.0.113.0/24에서 시작되지 않았습니다.

3. 한 회사가 Amazon S3에 기밀 데이터를 저장할 준비를 하고 있습니다. 규정 준수를 위해 데이터는 휴면 상태에서 암호화되어야 합니다.
암호화 키 사용은 감사 목적으로 기록되어야 합니다. 키는 매년 순환되어야 합니다.

이러한 요구 사항을 충족하고 가장 운영 효율적인 솔루션은 무엇입니까? 

A. 고객 제공 키를 사용한 서버 측 암호화 (SSE-C)
B. Amazon S3 관리 키를 사용한 서버 측 암호화 (SSE-S3)
C. 수동 로테이션을 사용한 AWS KMS 키 (SSE-KMS)를 사용한 서버 측 암호화
D. 자동 순환을 포함한 AWS KMS 키 (SSE-KMS)를 사용한 서버 측 암호화

4. 한 회사에는 Amazon EC2 인스턴스에서 실행되고 Amazon Aurora 데이터베이스를 사용하는 애플리케이션이 있습니다.
EC2 인스턴스는 로컬 파일에 저장된 사용자 이름과 비밀번호를 사용하여 데이터베이스에 연결합니다.
이 회사는 자격 증명 관리의 운영 오버헤드를 최소화하려고 합니다.

솔루션 아키텍트는 이 목표를 달성하기 위해 무엇을 해야 할까요?

A. AWS Secrets Manager를 사용합니다. 자동 회전을 켭니다.
B. AWS Systems Manager Parameter Store를 사용합니다. 자동 회전을 켭니다.
C. AWS Key Management Service(AWS KMS) 암호화 키로 암호화된 객체를 저장하기 위해 Amazon S3 버킷을 만듭니다. 자격 증명 파일을 S3 버킷으로 마이그레이션합니다. 애플리케이션을 S3 버킷으로 가리킵니다.
D. 각 EC2 인스턴스에 대해 암호화된 Amazon Elastic Block Store(Amazon EBS) 볼륨을 만듭니다. 각 EC2 인스턴스에 새 EBS 볼륨을 연결합니다. 자격 증명 파일을 새 EBS 볼륨으로 마이그레이션합니다. 애플리케이션을 새 EBS 볼륨으로 가리킵니다.

5.  한 회사가 단일 VPC의 여러 가용성 영역에 분산 된 여러 Amazon EC2 인스턴스에서 미디어 스토어를 실행하고 있습니다. 이 회사는 모든 EC2 인스턴스 간에 데이터를 공유하기 위한 고성능 솔루션을 원하며, VPC 내에서만 데이터를 보관하는 것을 선호합니다.

솔루션 아키텍트는 무엇을 추천해야 합니까?

A. Amazon S3 버킷을 생성하고 각 인스턴스의 애플리케이션에서 서비스 API를 호출합니다.
B. Amazon S3 버킷을 생성하고 모든 인스턴스가 마운트된 볼륨으로 액세스하도록 구성합니다.
C. Amazon Elastic Block Store(Amazon EBS) 볼륨을 구성하고 모든 인스턴스에 마운트합니다.
D. Amazon Elastic File System(Amazon EFS) 파일 시스템을 구성하고 모든 인스턴에 마운트합니다.

---

A/D/D/A/D

---
1. 한 회사가 Amazon Aurora 데이터베이스에 연결되는 Amazon EC2 인스턴스 그룹을 실행하려고 합니다. 이 회사는 EC2 인스턴스와 Aurora DB 클러스터를 배포하기 위해 AWS CloudFormation 템플릿을 빌드했습니다. 이 회사는 인스턴스가 안전한 방식으로 데이터베이스에 인증할 수 있도록 허용하려고 합니다. 이 회사는 정적 데이터베이스 자격 증명을 유지하고 싶어하지 않습니다.
어떤 솔루션이 최소한의 운영 노력으로 이러한 요구 사항을 충족합니까?

A. 사용자 이름과 비밀번호로 데이터베이스 사용자를 만듭니다. 데이터베이스 사용자 이름과 비밀번호에 대한 매개변수를 CloudFormation 템플릿에 추가합니다. 인스턴스가 시작될 때 EC2 인스턴스에 매개변수를 전달합니다.
B. 사용자 이름과 비밀번호로 데이터베이스 사용자를 만듭니다. 사용자 이름과 비밀번호를 AWS Systems Manager Parameter Store에 저장합니다. EC2 인스턴스를 구성하여 Parameter Store에서 데이터베이스 자격 증명을 검색합니다.
C. IAM 데이터베이스 인증을 사용하도록 DB 클러스터를 구성합니다. IAM 인증에 사용할 데이터베이스 사용자를 만듭니다. 인스턴스의 애플리케이션이 데이터베이스에 액세스할 수 있도록 EC2 인스턴스에 역할을 연결합니다.
D. IAM 사용자와 함께 IAM 데이터베이스 인증을 사용하도록 DB 클러스터를 구성합니다. IAM 사용자와 일치하는 이름을 가진 데이터베이스 사용자를 만듭니다. 인스턴스의 애플리케이션이 데이터베이스에 액세스할 수 있도록 IAM 사용자를 EC2 인스턴스와 연결합니다.

2. 솔루션 아키텍트는 애플리케이션이 Amazon RDS DB 인스턴스에 액세스하는 데 사용하는 데이터베이스 사용자 이름과 비밀번호를 안전하게 저장해야 합니다.
데이터베이스에 액세스하는 애플리케이션은 Amazon EC2 인스턴스에서 실행됩니다.
솔루션 아키텍트는 AWS Systems Manager Parameter Store에서 안전한 매개변수를 생성하려고 합니다.

솔루션 아키텍트는 이 요구 사항을 충족하기 위해 무엇을 해야 합니까?

A. Parameter Store 매개변수에 대한 읽기 액세스 권한이 있는 IAM 역할을 만듭니다. 매개변수를 암호화하는 데 사용되는 AWS Key Management Service(AWS KMS) 키에 대한 Decrypt 액세스를 허용합니다. 이 IAM 역할을 EC2 인스턴스에 할당합니다.
B. Parameter Store 매개변수에 대한 읽기 액세스를 허용하는 IAM 정책을 만듭니다. 매개변수를 암호화하는 데 사용되는 AWS Key Management Service(AWS KMS) 키에 대한 Decrypt 액세스를 허용합니다. 이 IAM 정책을 EC2 인스턴스에 할당합니다.
C. Parameter Store 매개변수와 EC2 인스턴스 간에 IAM 신뢰 관계를 만듭니다. 신뢰 정책에서 Amazon RDS를 주체로 지정합니다.
D. DB 인스턴스와 EC2 인스턴스 간에 IAM 신뢰 관계를 만듭니다. 신뢰 정책에서 Systems Manager를 주체로 지정합니다.

3. 한 회사의 보안 팀이 클라우드에 저장된 모든 데이터를 온프레미스에 저장된 암호화 키를 사용하여 항상
암호화된 상태로 저장할 것을 요구합니다.

이러한 요구 사항을 충족하는 암호화 옵션은 무엇입니까? (2 개 선택)

A. Amazon S3 관리형 암호화 키를 이용하는 서버 측 암호화(SSE-S3)를 사용합니다.
B. AWS KMS 관리형 암호화 키를 이용하는 서버 측 암호화(SSE-KMS)를 사용합니다.
C. 고객 제공 암호화 키를 이용하는 서버 측 암호화(SSE-C)를 사용합니다.
D. 미사용 데이터 암호화를 제공하기 위해 클라이언트 측 암호화를 사용합니다.
E. 고객의 키를 사용하여 데이터를 암호화하기 위해 Amazon S3 이벤트에 의해 호출된 AWS Lambda함수를 사용합니다


4. 회사가 AWS 클라우드에서 새로운 내부 웹 애플리케이션을 설계하고 있습니다.
이 새로운 애플리케이션은 여러 직원의 사용자 이름과 비밀번호를 AWS 관리형 서비스에서 안전하게 검색하고 저장해야 합니다.

다음 중 운영 오버헤드가 가장 적은 솔루션은 무엇입니까?

A. 직원 자격 증명을 AWS Systems Manager Parameter Store에 저장합니다. AWS CloudFormation과 BatchGetSecretValue API를 사용하여 Parameter Store에서 사용자 이름과 비밀번호를 검색합니다.
B. 직원 자격 증명을 AWS Secrets Manager에 저장합니다. AWS CloudFormation과 AWS Batch 및 BatchGetSecretValue API를 사용하여 Secrets Manager에서 사용자 이름과 비밀번호를 검색합니다.
C. 직원 자격 증명을 AWS Systems Manager Parameter Store에 저장합니다. AWS CloudFormation과 AWS Batch 및 BatchGetSecretValue API를 사용하여 Parameter Store에서 사용자 이름과 비밀번호를 검색합니다.
D. 직원 자격 증명을 AWS Secrets Manager에 저장합니다. AWS CloudFormation과 BatchGetSecretValue API를 사용하여 Secrets Manager에서 사용자 이름과 비밀번호를 검색합니다.

5. 한 회사가 단일 Amazon EC2 On-Demand 인스턴스에서 웹사이트 분석 애플리케이션을 호스팅합니다. 분석 애플리케이션은 매우 복원성이 뛰어나고 상태 비저장 모드로 실행되도록 설계되었습니다.

이 회사는 바쁜 시간에 애플리케이션이 성능 저하를 보이고 5xx 오류가 표시된다는 것을 알았습니다. 이 회사는 애플리케이션을 원활하게 확장해야 합니다.

어떤 솔루션이 이러한 요구 사항을 가장 비용 효율적으로 충족할까요?

A. 웹 애플리케이션의 Amazon Machine Image(AMI)를 만듭니다. AMI를 사용하여 두 번째 EC2 On-Demand 인스턴스를 시작합니다. Application Load Balancer를 사용하여 두 EC2 인스턴스에 부하를 분산합니다.
B. 웹 애플리케이션의 Amazon Machine Image(AMI)를 만듭니다. AMI를 사용하여 두 번째 EC2 On-Demand 인스턴스를 시작합니다. Amazon Route 53 가장 가까운 위치를 사용하여 두 EC2 인스턴스에 부하를 분산합니다.
C. EC2 인스턴스를 중지하고 인스턴스 유형을 변경하기 위한 AWS Lambda 함수를 만듭니다. CPU 사용률이 75%를 넘을 때 Lambda 함수를 호출하기 위한 Amazon CloudWatch 알람을 만듭니다.
D. 웹 애플리케이션의 Amazon Machine Image(AMI)를 만듭니다. AMI를 실행 템플릿에 적용합니다. 실행 템플릿을 포함하는 Auto Scaling 그룹을 만듭니다. Spot Fleet을 사용하도록 실행 템플릿을 구성합니다. Auto Scaling 그룹에 Application Load Balancer를 연결합니다.

---

C/A/CD/D/D

---
1. 개발자는 AWS Lambda 함수를 사용하여 Amazon S3에 파일을 업로드하는 애플리케이션을 가지고 있으며 작업을 수행하는 데 필요한 권한이 필요합니다.
개발자는 이미 Amazon S3에 필요한 유효한 IAM 자격 증명이 있는 IAM 사용자를 가지고 있습니다.

솔루션 아키텍트는 권한을 부여하기 위해 무엇을 해야 합니까?

A. Lambda 함수의 리소스 정책에 필요한 IAM 권한을 추가합니다.
B. Lambda 함수에서 기존 IAM 자격 증명을 사용하여 서명된 요청을 만듭니다.
C. 새로운 IAM 사용자를 생성하고 Lambda 함수에서 기존 IAM 자격 증명을 사용합니다.
D. 필요한 권한이 있는 IAM 실행 역할을 생성하고 해당 IAM 역할을 Lambda 함수에 연결합니다. 

2. 
솔루션 아키텍트가 두 개의 IAM 정책인 Policy1과 Policy2를 만들었습니다. 두 정책 모두 IAM 그룹에 연결되었습니다.

Policy 1

{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "iam:Get*",
        "iam:List*",
        "kms:List*",
        "ec2:*",
        "ds:*",
        "logs:Get*",
        "logs:Describe*"
      ],
      "Resource": "*"
    }
  ]
}


Policy 2

{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Deny",
      "Action": "ds:Delete*",
      "Resource": "*"
    }
  ]
}


클라우드 엔지니어가 IAM 그룹에 IAM 사용자로 추가되었습니다.
클라우드 엔지니어가 수행할 수 있는 작업은 무엇입니까?

A. IAM 사용자 삭제
B. 디렉토리 삭제
C. Amazon EC2 인스턴스 삭제
D. Amazon CloudWatch Logs에서 로그 삭제

3. 회사가 Amazon S3 버킷에 데이터가 저장된 환경을 운영합니다. 객체는 하루 종일 자주 액세스됩니다.
이 회사는 S3 버킷에 저장된 데이터에 대해 엄격한 데이터 암호화 요구 사항을 가지고 있습니다.
이 회사는 현재 암호화를 위해 AWS Key Management Service(AWS KMS)를 사용합니다.

이 회사는 AWS KMS에 대한 추가 호출 없이 S3 객체를 암호화하는 데 드는 비용을 최적화하려고 합니다.

어떤 솔루션이 이러한 요구 사항을 충족할까요?

A. Amazon S3 관리 키(SSE-S3)를 사용하여 서버 측 암호화를 사용합니다.
B. AWS KMS 키(SSE-KMS)를 사용하여 객체의 서버 측 암호화를 위한 S3 버킷 키를 사용합니다.
C. AWS KMS 고객 관리 키로 클라이언트 측 암호화를 사용합니다.
D. AWS KMS에 저장된 고객 제공 키(SSE-C)를 사용하여 서버 측 암호화를 사용합니다.

4. 어떤 회사에는 Amazon RDS MySQL DB 인스턴스에서 정보를 검색하는 임베디드 자격 증명이 있는 사용자 지정 애플리케이션이 있습니다.
경영진은 최소한의 프로그래밍 노력으로 애플리케이션을 더 안전하게 만들어야 한다고 말합니다.

솔루션 아키텍트는 이러한 요구 사항을 충족하기 위해 무엇을 해야 합니까?
 
A.
AWS Key Management Service(AWS KMS)를 사용하여 키를 생성합니다.
AWS KMS에서 데이터베이스 자격 증명을 로드하도록 애플리케이션을 구성합니다.
자동 키 로테이션을 활성화합니다.

B.
RDS for MySQL 데이터베이스에서 애플리케이션 사용자에 대한 자격 증명을 만들고 AWS Secrets Manager에 자격 증명을 저장합니다.
Secrets Manager에서 데이터베이스 자격 증명을 로드하도록 애플리케이션을 구성합니다.
Secrets Manager에서 자격 증명을 순환하는 AWS Lambda 함수를 만듭니다.

C.
RDS for MySQL 데이터베이스에서 애플리케이션 사용자에 대한 자격 증명을 만들고 AWS Secrets Manager에 자격 증명을 저장합니다.
Secrets Manager에서 데이터베이스 자격 증명을 로드하도록 애플리케이션을 구성합니다.
Secrets Manager를 사용하여 RDS for MySQL 데이터베이스에서 애플리케이션 사용자에 대한 자격 증명 로테이션 일정을 설정합니다.

D.RDS for MySQL 데이터베이스에서 애플리케이션 사용자에 대한 자격 증명을 만들고 AWS Systems Manager Parameter Store에 자격 증명을 저장합니다.
Parameter Store에서 데이터베이스 자격 증명을 로드하도록 애플리케이션을 구성합니다.
Parameter Store를 사용하여 RDS for MySQL 데이터베이스에서 애플리케이션 사용자에 대한 자격 증명 로테이션 일정을 설정합니다.

5. 전자상거래 회사가 고객에게 지속적인 서비스를 제공하기 위해 AWS에 웹 애플리케이션을 배포할 준비를 하고 있습니다. 아키텍처에는 회사가 Amazon EC2 인스턴스에서 호스팅하는 웹 애플리케이션, Amazon RDS의 관계형 데이터베이스, 회사가 Amazon S3에 저장하는 정적 자산이 포함됩니다.

회사는 애플리케이션에 대한 견고하고 회복성 있는 아키텍처를 설계하고자 합니다.

어떤 솔루션이 이러한 요구 사항을 충족할까요?

A. 단일 가용 영역에 Amazon EC2 인스턴스를 배포합니다. 동일한 가용 영역에 RDS DB 인스턴스를 배포합니다. 정적 자산을 저장하기 위해 버전 관리를 활성화한 Amazon S3를 사용합니다.

B. 여러 가용성 영역에 걸쳐 Auto Scaling 그룹에서 Amazon EC2 인스턴스를 배포합니다. Multi-AZ RDS DB 인스턴스를 배포합니다. Amazon CloudFront를 사용하여 정적 자산을 배포합니다.

C. 단일 가용성 영역에 Amazon EC2 인스턴스를 배포합니다. 교차 AZ 중복성을 위해 두 번째 가용성 영역에 RDS DB 인스턴스를 배포합니다. EC2 인스턴스에서 직접 정적 자산을 제공합니다.

D. AWS Lambda 함수를 사용하여 웹 애플리케이션을 제공합니다. 데이터베이스에 Amazon Aurora Serverless v2를 사용합니다. 정적 자산을 Amazon Elastic File System(Amazon EFS) One Zone-Infrequent Access(One Zone-IA)에 저장합니다.

---

D/C/A/C/B

---
1. 한 회사가 새로운 비즈니스 애플리케이션을 구현하고 있습니다. 이 애플리케이션은 두 개의 Amazon EC2 인스턴스에서 실행되고 문서 저장을 위해 Amazon S3 버킷을 사용합니다. 솔루션 아키텍트는 EC2 인스턴스가 S3 버킷에 액세스할 수 있는지 확인해야 합니다.

솔루션 아키텍트는 이 요구 사항을 충족하기 위해 무엇을 해야 합니까?

A. S3 버킷에 대한 액세스를 허용하는 IAM 역할을 만듭니다. 역할을 EC2 인스턴스에 연결합니다.
B. S3 버킷에 대한 액세스를 허용하는 IAM 정책을 만듭니다. 정책을 EC2 인스턴스에 연결합니다.
C. S3 버킷에 대한 액세스를 허용하는 IAM 그룹을 만듭니다. 그룹을 EC2 인스턴스에 연결합니다.
D. S3 버킷에 대한 액세스를 허용하는 IAM 사용자를 만듭니다. 사용자 계정을 EC2 인스턴스에 연결합니다.

2. 다음 IAM 정책은 IAM 그룹에 첨부되었습니다. 이것은 그룹에 적용되는 유일한 정책입니다.

{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "1",
      "Effect": "Allow",
      "Action": "ec2:*",
      "Resource": "*",
      "Condition": {
        "StringEquals": {
          "ec2:Region": "us-east-1"
        }
      }
    },
    {
      "Sid": "2",
      "Effect": "Deny",
      "Action": [
        "ec2:StopInstances",
        "ec2:TerminateInstances"
      ],
      "Resource": "*",
      "Condition": {
        "BoolIfExists": {
          "aws:MultiFactorAuthPresent": false
        }
      }
    }
  ]
}


그룹 구성원에 대한 이 정책의 효과적인 IAM 권한은 무엇입니까? D

A. 그룹 구성원은 us-east-1 지역 내에서 모든 Amazon EC2 작업을 허용받습니다. 허용 권한 이후의 명령문은 적용되지 않습니다.
B. 그룹 구성원은 다중 인증(MFA)을 사용하여 로그인하지 않는 한 us-east-1 지역에서 Amazon EC2 권한이 거부됩니다.
C. 그룹 멤버는 다중 요소 인증(MFA)으로 로그인한 경우 모든 리전에 대해 ec2:StopInstances 및 ec2:TerminateInstances 권한이 허용됩니다. 그럴 때만 다른 모든 Amazon EC2 작업이 허용됩니다.
D. 그룹 멤버는 멀티팩터 인증(MFA)으로 로그인한 경우에만 us-east-1 지역에 대한 ec2:StopInstances 및 ec2:TerminateInstances 권한이 허용됩니다. 그룹 멤버는 us-east-1 지역 내에서 다른 모든 Amazon EC2 작업이 허용됩니다.


3. 한 회사가 Amazon S3 버킷으로 데이터를 마이그레이션하려고 계획하고 있습니다.
요구 사항:
- 데이터는 S3 버킷 내에서 휴면 상태로 암호화되어야 함
- 암호화 키는 매년 자동으로 순환되어야 함

어떤 솔루션이 가장 적은 운영 오버헤드로 이러한 요구 사항을 충족할까요?

A. S3 버킷으로 데이터를 마이그레이션합니다. Amazon S3 관리 키(SSE-S3)로 서버 측 암호화를 사용합니다.

B. AWS Key Management Service(AWS KMS) 고객 관리 키를 만듭니다. 자동 키 로테이션을 활성화합니다. S3 버킷의 기본 암호화 동작을 고객 관리 KMS 키를 사용하도록 설정합니다. 데이터를 S3 버킷으로 마이그레이션합니다.

C. AWS Key Management Service(AWS KMS) 고객 관리 키를 만듭니다. S3 버킷의 기본 암호화 동작을 고객 관리 KMS 키를 사용하도록 설정합니다. 데이터를 S3 버킷으로 마이그레이션합니다. 매년 KMS 키를 수동으로 순환합니다.

D. 고객 키 자료를 사용하여 데이터를 암호화합니다. 데이터를 S3 버킷으로 마이그레이션합니다. 키 자료 없이 AWS Key Management Service(AWS KMS) 키를 만듭니다. 고객 키 자료를 KMS 키로 가져옵니다. 자동 키 로테이션을 활성화합니다.

4. 한 회사에는 Amazon RDS for MySQL DB 클러스터의 데이터베이스에서 정보를 검색하는 임베디드 자격 증명이 있는 사용자 지정 애플리케이션이 있습니다. 이 회사는 최소한의 프로그래밍 노력으로 애플리케이션을 더 안전하게 만들어야 합니다. 이 회사는 애플리케이션 사용자를 위해 RDS for MySQL 데이터베이스에 자격 증명을 만들었습니다.

어떤 솔루션이 이러한 요구 사항을 충족할까요?

A. AWS Key Management Service(AWS KMS)에 자격 증명을 저장합니다. AWS KMS에 키를 만듭니다. AWS KMS에서 데이터베이스 자격 증명을 로드하도록 애플리케이션을 구성합니다. 자동 키 로테이션을 활성화합니다.

B. 암호화된 로컬 저장소에 자격 증명을 저장합니다. 로컬 저장소에서 데이터베이스 자격 증명을 로드하도록 애플리케이션을 구성합니다. Cron 작업을 생성하여 자격 증명 로테이션 일정을 설정합니다.

C. AWS Secrets Manager에 자격 증명을 저장합니다. Secrets Manager에서 데이터베이스 자격 증명을 로드하도록 애플리케이션을 구성합니다. Secrets Manager에 대한 AWS Lambda 함수를 생성하여 자격 증명 로테이션 일정을 설정합니다.

D. AWS Systems Manager Parameter Store에 자격 증명을 저장합니다. Parameter Store에서 데이터베이스 자격 증명을 로드하도록 애플리케이션을 구성합니다. Parameter Store를 사용하여 RDS for MySQL 데이터베이스에 자격 증명 로테이션 일정을 설정합니다.

5. 한 회사가 Amazon Aurora MySQL DB 클러스터를 스토리지로 사용하는 다중 계층 웹 애플리케이션을 호스팅합니다.
애플리케이션 계층은 Amazon EC2 인스턴스에서 호스팅됩니다.

회사의 IT 보안 지침:

- 데이터베이스 자격 증명은 암호화되어야 함
- 14일마다 순환되어야 함

솔루션 아키텍트는 최소한의 운영 노력으로 이 요구 사항을 충족하기 위해 무엇을 해야 합니까?

A. 새로운 AWS Key Management Service(AWS KMS) 암호화 키를 만듭니다. AWS Secrets Manager를 사용하여 적절한 자격 증명과 함께 KMS 키를 사용하는 새로운 비밀을 만듭니다. 비밀을 Aurora DB 클러스터와 연결합니다. 14일의 사용자 지정 로테이션 기간을 구성합니다.
B. AWS Systems Manager Parameter Store에 두 개의 매개변수를 만듭니다. 하나는 문자열 매개변수로 사용자 이름을 위한 매개변수이고 다른 하나는 암호에 SecureString 유형을 사용합니다. 암호 매개변수에 AWS Key Management Service(AWS KMS) 암호화를 선택하고 애플리케이션 계층에 이러한 매개변수를 로드합니다. 14일마다 암호를 순환하는 AWS Lambda 함수를 구현합니다.
C. 자격 증명이 포함된 파일을 AWS Key Management Service(AWS KMS) 암호화된 Amazon Elastic File System(Amazon EFS) 파일 시스템에 저장합니다. 애플리케이션 계층의 모든 EC2 인스턴스에 EFS 파일 시스템을 마운트합니다. 파일 시스템에서 파일에 대한 액세스를 제한하여 애플리케이션이 파일을 읽을 수 있고 슈퍼 사용자만 파일을 수정할 수 있도록 합니다. 14일마다 Aurora에서 키를 순환하고 새 자격 증명을 파일에 쓰는 AWS Lambda 함수를 구현합니다.
D. 애플리케이션이 자격 증명을 로드하는 데 사용하는 AWS Key Management Service(AWS KMS) 암호화된 Amazon S3 버킷에 자격 증명이 포함된 파일을 저장합니다. 올바른 자격 증명이 사용되도록 정기적으로 애플리케이션에 파일을 다운로드합니다. 14일마다 Aurora 자격 증명을 순환하고 이러한 자격 증명을 S3 버킷의 파일에 업로드하는 AWS Lambda 함수를 구현합니다.

---

A/D/A/A/A

---
1. 새로운 직원이 배포 엔지니어로 회사에 합류했습니다. 배포 엔지니어는 AWS CloudFormation 템플릿을 사용하여 여러 AWS 리소스를 만듭니다. 솔루션 아키텍트는 배포 엔지니어가 최소 권한 원칙을 따르면서 작업 활동을 수행하기를 원합니다.

솔루션 아키텍트는 이 목표를 달성하기 위해 어떤 작업 조합을 취해야 합니까? (두 가지를 선택하세요.)

*CloudFormation > AWS 여러 서비스 생성변경삭제를 자동화하는 스크립트성 서비스

A. 배포 엔지니어가 AWS 계정 루트 사용자 자격 증명을 사용하여 AWS CloudFormation 스택 작업을 수행하도록 합니다.
B. 배포 엔지니어를 위한 새로운 IAM 사용자를 생성하고 PowerUsers IAM 정책이 연결된 그룹에 IAM 사용자를 추가합니다.
C. 배포 엔지니어를 위한 새로운 IAM 사용자를 만들고 AdministratorAccess IAM 정책이 연결된 그룹에 IAM 사용자를 추가합니다.
D. 배포 엔지니어를 위한 새로운 IAM 사용자를 생성하고 AWS CloudFormation 작업만 허용하는 IAM 정책이 있는 그룹에 IAM 사용자를 추가합니다.
E. 배포 엔지니어가 AWS CloudFormation 스택에 대한 권한을 명시적으로 정의하고 해당 IAM 역할을 사용하여 스택을 시작할 수 있도록 IAM 역할을 생성합니다.

2. Amazon EC2 관리자가 여러 사용자가 포함된 IAM 그룹과 관련된 다음 정책을 생성했습니다.

{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "ec2:TerminateInstances",
      "Resource": "*",
      "Condition": {
        "IpAddress": {
          "aws:SourceIp": "10.100.100.0/24"
        }
      }
    },
    {
      "Effect": "Deny",
      "Action": "ec2:*",
      "Resource": "*",
      "Condition": {
        "StringNotEquals": {
          "ec2:Region": "us-east-1"
        }
      }
    }
  ]
}


이 정책의 효과는 무엇입니까?

A. 사용자는 us-east-1을 제외한 모든 AWS 지역에서 EC2 인스턴스를 종료할 수 있습니다.
B. 사용자는 us-east-1 지역에서 IP 주소 10.100.100.1을 사용하여 EC2 인스턴스를 종료할 수 있습니다.
C. 사용자의 소스 IP가 10.100.100.254인 경우 사용자는 us-east-1 지역의 EC2 인스턴스를 종료할 수 있습니다.
D. 사용자의 소스 IP가 10.100.100.254인 경우 사용자는 us-east-1 지역의 EC2 인스턴스를 종료할 수 없습니다.

3. 회사가 온프레미스 환경에서 AWS로 애플리케이션을 마이그레이션하고 있습니다.
애플리케이션은 Amazon S3에 민감한 데이터를 저장합니다.
회사는 Amazon S3에 데이터를 저장하기 전에 데이터를 암호화해야 합니다.

어떤 솔루션이 이러한 요구 사항을 충족할까요?

A. 고객 관리 키를 사용하여 클라이언트 측 암호화를 사용하여 데이터를 암호화합니다. 
B. AWS KMS 키(SSE-KMS)를 사용하여 서버 측 암호화를 사용하여 데이터를 암호화합니다.
C. 고객이 제공한 키(SSE-C)를 사용하여 서버 측 암호화를 사용하여 데이터를 암호화합니다.
D. Amazon S3 관리 키를 사용하여 클라이언트 측 암호화를 사용하여 데이터를 암호화합니다.

4. 한 회사가 AWS에서 2계층 웹 애플리케이션을 개발하고 있습니다. 이 회사의 개발자는 백엔드 Amazon RDS 데이터베이스에 직접 연결되는 Amazon EC2 인스턴스에 애플리케이션을 배포했습니다. 이 회사는 애플리케이션에 데이터베이스 자격 증명을 하드코딩해서는 안 됩니다. 또한 이 회사는 정기적으로 데이터베이스 자격 증명을 자동으로 순환하는 솔루션을 구현해야 합니다.

어떤 솔루션이 이러한 요구 사항을 가장 적은 운영 오버헤드로 충족할까요?

A. 인스턴스 메타데이터에 데이터베이스 자격 증명을 저장합니다. Amazon EventBridge(Amazon CloudWatch Events) 규칙을 사용하여 RDS 자격 증명과 인스턴스 메타데이터를 동시에 업데이트하는 예약된 AWS Lambda 함수를 실행합니다.

B. 암호화된 Amazon S3 버킷의 구성 파일에 데이터베이스 자격 증명을 저장합니다. Amazon EventBridge(Amazon CloudWatch Events) 규칙을 사용하여 RDS 자격 증명과 구성 파일의 자격 증명을 동시에 업데이트하는 예약된 AWS Lambda 함수를 실행합니다. S3 버전 관리를 사용하여 이전 값으로 폴백할 수 있는 기능을 보장합니다.

C. AWS Secrets Manager에서 데이터베이스 자격 증명을 비밀로 저장합니다. 비밀에 대한 자동 로테이션을 켭니다. EC2 역할에 필요한 권한을 연결하여 비밀에 대한 액세스를 부여합니다.

D. AWS Systems Manager Parameter Store에 암호화된 매개변수로 데이터베이스 자격 증명을 저장합니다. 암호화된 매개변수에 대한 자동 로테이션을 켭니다. 암호화된 매개변수에 대한 액세스 권한을 부여하기 위해 EC2 역할에 필요한 권한을 연결합니다

5. 한 회사가 Amazon RDS for PostgreSQL을 사용하여 us-east-1 지역에서 애플리케이션을 실행합니다. 이 회사는 또한 기계 학습(ML) 모델을 사용하여 거의 실시간 보고서를 기반으로 연간 수익을 예측합니다. 보고서는 동일한 RDS for PostgreSQL 데이터베이스를 사용하여 생성됩니다. 데이터베이스 성능은 영업 시간 동안 느려집니다. 이 회사는 데이터베이스 성능을 개선해야 합니다.

어떤 솔루션이 이러한 요구 사항을 가장 비용 효율적으로 충족할까요?

A. 지역 간 읽기 복제본을 만듭니다. 읽기 복제본에서 생성될 보고서를 구성합니다.

B. RDS for PostgreSQL에 대한 Multi-AZ DB 인스턴스 배포를 활성화합니다. 스탠바이 데이터베이스에서 생성될 보고서를 구성합니다.

C. AWS Data Migration Service(AWS DMS)를 사용하여 데이터를 새 데이터베이스로 논리적으로 복제합니다. 새 데이터베이스에서 생성될 보고서를 구성합니다.

D. us-east-1에 읽기 복제본을 만듭니다. 읽기 복제본에서 생성될 보고서를 구성합니다.

---

D/C/A/C/D

---

