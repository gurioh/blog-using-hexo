---
title: AWS 시험 정리
date: 2019-12-03 19:37:57
tags: [AWS]
categories:
 - [aws]
---

# IAM
 - IAM role can be attached to the Amazon EC2 instance.

# S3
 - S3에서는 특정 파일(Object)에 제한된 시간 동안 접근할 수 있도록 임시 permission을 부여하는 S3 pre-signed url 기능을 제공
 - ## S3 Glacier
    - 장기 백업을 위한 안전하고 내구성이 뛰어나고 매우 저렴한 Amazon S3 클라우드 스토리지 클래스
    - 고객은 월별 테라바이트당 1 USD의 저렴한 요금으로 데이터를 저장할 수 있으므로 온프레미스 솔루션과 비교하면 상당한 비용 절감을 기대할 수 있습니다
    - 비용을 낮게 유지하면서 동시에 다양한 검색 요구를 지원하기 위해 Amazon S3 Glacier에서는 아카이브에 액세스하는 3가지 옵션(몇 분에서 몇 시간까지 소요)을 제공하며 S3 Glacier Deep Archive는 2가지 액세스 옵션(12~48시간 소요)을 제공합니다.
 - ## S3 - S3 Standard-IA
    - 수명이 길지만 자주 액세스하지 않는 데이터
    - 자주 액세스하지 않지만 필요할 때 빠르게 액세스해야 하는 데이터에 적합
 - ## S3 - Athena
    - 표준 SQL을 사용해 Amazon S3에 저장된 데이터를 간편하게 분석할 수 있는 대화식 쿼리 서비스
    - Athena는 서버리스 서비스이므로 관리할 인프라가 없으며 실행한 쿼리에 대해서만 비용을 지불하면 됩니다.
 - ## S3 - encryption
   - 서버측암호화
      - Amazon S3에서는 데이터 센터의 디스크에 데이터를 쓸 때 객체 레벨에서 데이터를 암호화하고 해당 데이터에 액세스할 때 자동으로 암호 해독
      - Amazon S3 관리형 키를 사용한 서버 측 암호화(SSE-S3)
         - 각 객체는 고유한 키로 암호화
         - 또한 추가 보안 조치로 주기적으로 바뀌는 마스터 키를 사용하여 키 자체를 암호화
         - 가장 강력한 블록 암호 중 하나인 256비트 고급 암호화 표준(AES-256)을 사용하여 데이터를 암호화
      - 고객 제공 키를 사용한 서버 측 암호화(SSE-C)
         - 사용자는 암호화 키를 관리하고 Amazon S3는 암호화(디스크에 쓸 때) 및 해독(객체에 액세스할 때)을 관리
      - AWS Key Management Service에 저장된 고객 마스터 키(CMK)를 사용한 서버 측 암호화(SSE-KMS)
         - SSE-S3와 유사하지만 이 서비스 사용 시 몇 가지 추가적인 이점이 있고 비용이 발생
         - SSE-KMS도 CMK가 사용된 때와 사용 주체를 표시하는 감사 추적 기능을 제공
         - 고객 관리형 CMK를 생성하고 관리하거나 사용자, 서비스 및 리전에 고유한 AWS 관리형 CMK를 사용할 수 있습니다
   ## S3- pre-signed url
      - S3에서는 특정 파일(Object)에 제한된 시간 동안 접근할 수 있도록 임시 permission을 부여하는 S3 pre-signed url 기능

# Aurora
 - Amazon Aurora는 고성능 상용 데이터베이스의 성능과 가용성에 오픈 소스 데이터베이스의 간편성과 비용 효율성을 결합하였으며 클라우드를 위해 구축된 MySQL 및 PostgreSQL 호환 관계형 데이터베이스입니다
 - Amazon RDS에서 모든것을 관리한다.
 - 내결함성을 갖춘 자가 복구 분산 스토리지 시스템으로, __데이터베이스 인스턴스당 최대 64TB까지 자동으로 확장__
 - 지연 시간이 짧은 __읽기 전용 복제본 최대 15개__, 특정 시점으로 복구, Amazon S3로 지속적 백업, __3개의 가용 영역(AZ)에 걸친 복제__ 를 통해 뛰어난 성능과 가용성을 제공

# Amazon Redshift
 - Amazon Redshift는 클라우드에서 완벽하게 관리되는 페타바이트급 데이터 웨어하우스 서비스
 - 작게는 수백 기가바이트부터 시작하여 페타바이트 이상까지 데이터를 확장

# Read Replica
 - Amazon RDS 읽기 전용 복제본은 데이터베이스(DB) 인스턴스의 성능과 내구성을 높여줍니다
 - 특정 소스 DB 인스턴스의 복제본을 여러 개 만들어 여러 데이터 사본이 요청하는 높은 애플리케이션 읽기 트래픽도 처리할 수 있습니다. 덕분에 전체 읽기 처리량이 향상됩니다.
 - 읽기 전용 복제본은 Amazon RDS for MySQL, MariaDB, PostgreSQL 및 Oracle뿐만 아니라 Amazon Aurora에서도 사용할 수 있습니다.

<hr/>

# SES ( Simple Email Service)
 - 디지털 마케터 및 애플리케이션 개발자가 마케팅, 알림 및 트랜잭션 이메일을 발송하는 데 도움이 되도록 설계된 클라우드 기반 이메일 발송 서비스

# Beanstalk
 - Elastic Beanstalk를 사용하면, 애플리케이션을 실행하는 인프라에 대한 염려 없이 AWS 클라우드에서 애플리케이션을 신속하게 배포 및 관리할 수 있다.   
 - workflow
 ![](../../../image/2020-01-27-15-52-00.png)

# VPC 구성요소
![](../../../image/2020-02-21-14-36-34.png)

# VPC Endpoint
 -  VPC 네트워크 내에서 VPC 외부에 위치한 Public한 서비스를 IGW를 거치지 않고 VPC내부에서 직접 접근하도록 지원
 -  VPC 엔드포인트를 통해 인터넷 게이트웨이, NAT 디바이스, VPN 연결 또는 AWS Direct Connect 연결을 필요로 하지 않고 __AWS PrivateLink 구동 지원 AWS 서비스 및 VPC 엔드포인트 서비스에 비공개로 연결할 수 있습니다.__ VPC의 인스턴스는 서비스의 리소스와 통신하는 데 __퍼블릭 IP 주소를 필요로 하지 않습니다__. VPC와 기타 서비스 간의 트래픽은 Amazon 네트워크를 벗어나지 않습니다.
    - 인터페이스 엔드포인트
        - 인터페이스 엔드포인트는 __프라이빗 IP 주소__ 를 가진 탄력적 네트워크 인터페이스이며, 지원되는 서비스로 전달되는 트래픽에 대한 __진입점 역할을 하는 서브넷의 IP 주소 범위__
    - 게이트웨이 엔드포인트
        - 게이트웨이 엔드포인트는 __지원되는 AWS 서비스로 전달되는 트래픽에 대한 라우팅 테이블에서 경로의 대상으로 지정하는 게이트웨이__ 
# Gateway Endpoint 
- Endpoint가 Gateway 타입으로 지원하여 AWS 서비스 접근 시, 라우팅으로 접근
  라우팅 테이블에서 S3나 DynamoDB의 목적지 네트워크에 대한 Target(Next Hop)으로 Gateway Endpoint를 지정 S3와 DynamoDB 접근을 지원
# Interface Endpoint
-  생성 시에는 어느 VPC의 어떤 AZ의 어떤 Subnet을 사용할지 선택,  생성 시에 지정한  각 서브넷의 IP를 각각 할당 받음
- Interface Endpoint 를 이용해서 서비스를 호출하는 경우에는, AWS에서 기본으로 사용하는 도메인을 사용하거나, 
    별도의 서비스 도메인을 지정하여 VPC 내에서 서비스 도메인 Lookup 시에  Interface Endpoint 의  IP로 응답하여
    접근하도록 할 수 있음.
# VPC Peering 
- VPC 간의 인터넷을 통하지 않고 직접 통신 할 수 있도록 연결하는 기술
- VPC Peering으로 연결 시에 VPC 간의 네트워크 대역이 겹치지 않도록 설계해야 함.
- VPC Peering은 단일 계정으로도 가능하며, 서로 다른 계정 간의 VPC Peering 구성도 가능

# VPC Peering 제한
- 멀티 Region 간의 VPC Peering 시에는 security group 참조 지원 안 함.
- 멀티 Region 간의 VPC Peering 시에는 DNS resolution 지원 안 함.
- IPv6와 Jumbo 프레임 지원 안 함.
- VPC Peering을 통해서 외부 혹은 다른 VPC에서 VPC를 통해서 또 다른 VPC로 접근하는 Transit 기능은 지원하지 않음.

# Transit Gateway
- VPC 간의 Transit이 가능하도록 해주는 게이트웨이 서비스
- 
# AWS Direct Connect
-  온프레미스에서 AWS로 전용 네트워크 연결을 쉽게 설정할 수 있는 클라우드 서비스 솔루션
- AWS Direct Connect를 사용하면 AWS와 사용자의 데이터 센터, 사무실, 또는 코로케이션 환경 사이에 프라이빗 연결을 설정할 수 있습니다. 따라서 많은 경우 네트워크 비용을 줄이고, 대역폭 처리량을 늘리며, 인터넷 기반 연결보다 일관된 네트워크 경험을 제공할 수 있습니다.

# CloudFront
 - CloudFront는 개발자 친화적 환경에서 짧은 지연 시간과 빠른 전송 속도로 데이터, 동영상, 애플리케이션 및 API를 전 세계 고객에게 안전하게 전송하는 고속 콘텐츠 전송 네트워크(CDN) 서비스
 - CloudFront는 AWS Shield와 연동되어 DDoS 완화를 수행하고, 애플리케이션 오리진으로서 Amazon S3, Elastic Load Balancing 또는 Amazon EC2를 사용하고, Lambda@Edge와 연동되어 사용자지정 코드를 고객의 사용자에서 가까운 위치에서 실행하고 맞춤화된 사용자 경험을 제공
 - Amazon S3, Amazon EC2 또는 Elastic Load Balancing과 같은 AWS 오리진을 사용하는 경우, 이러한 서비스와 CloudFront 간에 전송된 데이터에 대해서는 비용을 지불하지 않습니다.
 - Q1 : A Solutions Architect has been asked to deliver video content stored on Amazon S3 to specific users from Amazon CloudFront while restricting access by unauthorized users.
How can the Architect implement a solution to meet these requirements?
Answer :CloudFront 배포를 통해서만 Amazon S3 버킷에 대한 액세스를 허용하려면 먼저 배포에 OAI(오리진 액세스 ID)를 추가합니다. 그런 다음, 버킷 정책 및 Amazon S3 ACL(액세스 제어 목록)을 검토

# Multi-AZ 
 - 다중 AZ DB 인스턴스를 프로비저닝하면 Amazon RDS는 기본 DB 인스턴스를 자동 생성하고 다른 가용 영역(AZ)에 있는 예비 인스턴스에 데이터를 동기적으로 복제
 - 각 AZ는 물리적으로 분리된 자체 독립 인프라에서 실행되며 높은 안정성을 제공하도록 설계



 # ELB(Elastic Load Balancer)
  - Application Load Balancer
    - Application Load Balancer는 HTTP 및 HTTPS 트래픽의 로드 밸런싱에 가장 적합
    - 마이크로서비스와 컨테이너 등 최신 애플리케이션 아키텍처 전달을 위한 고급 요청 라우팅 기능을 제공합니다
    - 개별 요청 수준(계층 7)에서 작동하는 Application Load Balancer는 요청의 콘텐츠를 기반으로 Amazon VPC(Amazon Virtual Private Cloud) 내의 대상으로 트래픽을 라우팅합니다.
  - Network Load Balancer
    - Network Load Balancer는 극한의 성능이 요구되는 TCP(Transmission Control Protocol), UDP(User Datagram Protocol) 및 TLS(전송 계층 보안) 트래픽의 로드 밸런싱에 가장 적합
    - 연결 수준(계층 4)에서 작동하는 Network Load Balancer는 Amazon VPC(Amazon Virtual Private Cloud) 내의 대상으로 트래픽을 라우팅하며, 초당 수백만 개의 요청을 처리하면서 지연 시간을 매우 낮게 유지
    - Network Load Balancer는 갑작스러운 일시적 트래픽 패턴 처리에도 최적화
  - Classic Load Balancer
    - 여러 Amazon EC2 인스턴스에서 기본적인 로드 밸런싱을 제공
    - Classic Load Balancer는 EC2-Classic 네트워크 내에 구축된 애플리케이션을 대상으로 합니다.


# EC2 price model type
 - T-series instances
 - scheduled Reserved Instances.
 - Spot instances.
   - 스팟 인스턴스는 Auto Scaling, EMR, ECS, CloudFormation, Data Pipeline 및 AWS Batch와 같은 AWS 서비스와 긴밀하게 통합
   -  AWS 클라우드에서 미사용 EC2 용량을 활용할 수 있습니다. 


# EBS 볼륨
* Instance Store Volume are somethimes called Ephemeral Storage
* Instance store volume cannot be stopped If the underlying host fails, you will lose your data.
* EBS backed instances can be stopped. You will not lose the data on this instance if it is stopped.
* You can reboot both, you will not lose your data.
* By default, both ROOT volumes will be deleted on termination. However, with EBS volumes, you can tell aws to keep the root device volume
 - ## EBS 데이터를 잃는 경우
    - Failure of an underlying drive
    - Stopping an Amazon EBS-backed instance
    - Terminating an instance

 - ## EBS 볼륨 유형
    - SSD 지원 볼륨
        : 작은 I/O 크기의 읽기/쓰기 작업을 자주 처리하는 트랜잭션 워크로드에 최적화되어 있으며, 기준 성능 속성은 IOPS
        - 범용 SSD (gp2)
        : 다양한 워크로드에 사용할 수 있으며 가격 대비 성능이 우수한 범용 SSD 볼륨
        - 프로비저닝된 IOPS SSD (io1)
        : 지연 시간이 짧거나 처리량이 많은 미션 크리티컬 워크로드에 적합한 고성능 SSD 볼륨

    - HDD 지원 볼륨
        : __대용량 스트리밍 워크로드__ 에 최적화되어 있으며, IOPS보다는 처리량(MiB/s로 측정)이 더 정확한 성능 측정 기준
        - 처리량에 최적화된 HDD (st1)
        : - __자주 액세스하는 처리량 집약적 워크로드에 적합한 저비용__ 
          - 빅 데이터, 저비용으로 일관되고 높은 처리량을 요구하는 스트리밍 
        
        - Cold HDD (sc1) 
        :  - 자주 액세스하지 않는 워크로드에 적합한 최저 비용 HDD 볼륨
           - __자주 액세스하지 않는 대용량 데이터를 위한 처리량 중심의 스토리지__

 - # EBS Snapshots
   - Snapshots with AWS Marketplace product codes can't be made public.


# S3 vs EBS vs EFS
 - https://sarc.io/index.php/aws/1789-s3-vs-ebs-vs-efs

# EBS 지연 발생시 확인 사항
 - If your I/O latency is higher than you require, check your average queue length to make sure that your application is not trying to drive more IOPS than you have provisioned. You can maintain high IOPS while keeping latency down by maintaining a low average queue length (which is achieved by provisioning more IOPS for your volume).
# Route 53
-  Route 53는 높은 가용성과 확장성이 뛰어난 클라우드 Domain Name System (DNS) 웹 서비스
- 사용자를 AWS 외부의 인프라로 라우팅하는 데도 Route 53를 사용할 수 있습니다.
   - ## 라우팅 정책
      - 단순 라우팅 정책
      - 장애 조치 라우팅 정책
      - 지리 위치 라우팅 정책
      - 지리 근접 라우팅 정책 
      - 지연 시간 라우팅 정책
      - 다중 응답 라우팅 정책 
      - 가중치 기반 라우팅 정책
-  Route 53 health check
   - Route 53 natively supports ELB with an internal health check. Turn "Evaluate target health" on and "Associate with Health Check" off and R53 will use the ELB's internal health check.
- 액티브-액티브 및 액티브-패시브 장애 조치
   - 액티브 - 액티브 장애조치
      모든 리소스를 대부분의 시간 동안 사용 가능하도록 하려면 이 장애 조치 구성을 사용
   - 액티브-패시브 장애 조치
      기본 리소스 또는 리소스 그룹이 대부분의 시간 동안 사용 가능하도록 하고 보조 리소스 또는 리소스 그룹은 기본 리소스가 사용 불가능할 경우를 대비해 대기 중에 있도록 하고 싶다면 이 장애 조치 구성
# Cognito
- 웹 및 모바일 앱에 대한 인증, 권한 부여 및 사용자 관리
   - 사용자 풀
      - 사용자 풀은 Amazon Cognito의 사용자 디렉터리
      - Amazon Cognito를 통해, 또는 타사 자격 증명 공급자(IdP)를 통해 연동하여 웹 또는 모바일 앱에 로그인
   - 자격 증명 풀
      - 임시 AWS 자격 증명을 얻어 Amazon S3 및 DynamoDB 등과 같은 다른 AWS 서비스에 액세스
# DynamoDB
-  DynamoDB는 어떤 규모에서도 10밀리초 미만의 성능을 제공하는 키-값 및 문서 데이터베이스
- 내구성이 뛰어난 다중 리전, 다중 마스터 데이터베이스로서, 인터넷 규모 애플리케이션을 위한 보안, 백업 및 복원, 인 메모리 캐싱 기능을 기본적으로 제공
- Amazon DynamoDB supports increment and decrement atomic operations.
- DynamoDB supports in-place atomic updates
- DynamoDB allows for the storage of large text and binary objects, but there is a limit of 400 KB.

# Data Pipeline
- 데이터의 이동과 변환을 자동화하는 데 사용할 수 있는 웹 서비스


# Kinesis Data Firehouse
- 스트리밍 데이터를 데이터 레이크, 데이터 스토어 및 분석 도구에 쉽고 안정적으로 로드하는 방법.
- 스트리밍 데이터를 캡처하고 변환한 후 Amazon S3, Amazon Redshift, Amazon Elasticsearch Service 및 Splunk로 로드하여 이미 사용하고 있는 기존 비즈니스 인텔리전스 도구 및 대시보드를 통해 거의 실시간으로 분석
- 데이터를 로드하기 전에 배치 처리, 압축, 변환 및 암호화하여 대상 스토리지의 사용량을 최소화하고 보안을 강화할 수 있습니다.



# AWS Import/Export
- AWS Import/Export does not currently support export from Amazon EBS or Amazon Glacier.


# SNS
-  애플리케이션, 최종 사용자 및 디바이스에서 즉시 알림을 전송하고 클라우드의 알림을 수신하도록 하는 웹 서비스입니다.


# Gateway-cached
 - AWS Storage Gateway는 __온프레미스 소프트웨어 어플라이언스를 클라우드 기반 스토리지에 연결하여 데이터 보안 기능으로 온프레미스 IT 환경과 AWS 스토리지 인프라 사이에 원활한 통합이 이루어지도록 지원__
 

# AWS CloudFormation
 - 클라우드 환경에서 AWS 및 타사 애플리케이션 리소스를 모델링하고 프로비저닝할 수 있도록 공용 언어를 제공합니다
 - CloudFormation을 사용하면 프로그래밍 언어 또는 간단한 텍스트 파일을 사용하여 자동화되고 안전한 방식으로 모든 지역과 계정에 걸쳐 애플리케이션에 필요한 모든 리소스를 모델링 및 프로비저닝할 수 있습니다.


# EIP (Elastic IP)
 -  탄력적 IP 주소는 동적 클라우드 컴퓨팅을 위해 고안된 정적 IPv4 주소입니다
 - 탄력적 IP 주소는 AWS 계정과 연결됩니다.
 - 탄력적 IP 주소를 사용하면 주소를 계정의 다른 인스턴스에 신속하게 다시 매핑하여 인스턴스나 소프트웨어의 오류를 마스킹할 수 있습니다.
 - 탄력적 IP 주소는 인터넷에서 연결 가능한 퍼블릭 IPv4 주소입니다
 - 인스턴스에 퍼블릭 IPv4 주소가 없는 경우 탄력적 IP 주소를 인스턴스와 연결하여 인터넷과 통신을 활성화하고 예를 들어 로컬 컴퓨터에서 인스턴스에 연결할 수 있습니다.
 - 현재는 IPv6에 대한 탄력적 IP 주소를 지원하지 않습니다.
 - __모든 AWS 계정은 리전당 5개의 탄력적 IP 주소__ 로 제한됩니다.

# Amazon ElastiCache
 - AWS 클라우드상의 분산 인 메모리 캐시 환경을 손쉽게 설정 및 관리하고 및 확장
 - 환경의 배포 및 관리와 관련된 복잡성을 제거하면서 고성능, 크기 조정 가능 및 비용 효율적인 인 메모리 캐시를 제공
 - Redis 및 Memcached 엔진과 호환


# AWS Key Management Service(KMS)
 -  손쉽게 암호화 키를 생성 및 관리하고 다양한 AWS 서비스와 애플리케이션에서의 사용을 제어
 - AWS KMS는 AWS CloudTrail과도 통합되어 모든 키 사용에 관한 로그를 제공함으로써 각종 규제 및 규정 준수 요구 사항을 충족할 수 있게 지원



# AWS PrivateLink
- AWS 네트워크 내에 네트워크 트래픽을 유지하여 AWS에 호스팅된 서비스에 쉽고 안전하게 액세스
- __퍼블릭 인터넷에 데이터가 노출되지 않도록 하여 클라우드 기반 애플리케이션과 공유된 데이터 보안을 간소화합니다__
- __AWS PrivateLink는 Amazon 네트워크를 통해 VPC, AWS 서비스 및 온프레미스 애플리케이션 간에 안전하게 비공개 연결을 제공__
- PrivateLink를 사용하면 여러 계정과 VPC에 걸쳐 손쉽게 서비스에 연결하여 네트워크 아키텍처를 상당히 간소화


# Application load balancers support dynamic host port mapping
- 동적 포트 매핑을 사용하면 Amazon ECS 클러스터의 동일한 Amazon EC2 서비스에서 여러 작업을 더욱 쉽게 실행할 수 있습니다.
- Classic Load Balancer에서는 컨테이너 인스턴스의 포트 번호를 정적으로 매핑해야 합니다.
- Classic Load Balancer에서는 포트가 충돌하게 되므로 동일한 인스턴스에서 여러 개의 작업 사본을 실행할 수 없습니다 
- Application Load Balancer는 동적 포트 매핑을 사용하므로 동일한 컨테이너 인스턴스의 단일 서비스에서 여러 작업을 실행할 수 있습니다.


# Amazon EC2 Auto Scaling
   - 대상 추적 조정 정책
      - CloudWatch 경보를 생성 및 관리하면서 지표와 목표 값을 기준으로 조정 조절값을 계산합니다
      - 조정 정책은 필요에 따라 용량을 Spot Instances 추가하거나 제거하여 측정치를 지정한 목표 값으로, 혹은 목표 값에 가깝게 유지
   - 단순 단계 조정 정책
      -  일련의 조정 조절을 기반으로 Auto Scaling 그룹의 용량을 늘리거나 줄입니다.
      - 단순 및 단계 조정 정책을 사용할 경우, 조정 프로세스를 트리거하는 CloudWatch 경보에 대한 조정 지표와 임계값을 선택하고, 지정된 평가 기간 동안 임계값을 위반했을 때 Auto Scaling 그룹을 어떻게 조정할지 정의해야 합니다.

# AWS WAF(웹 애플리케이션 방화벽)
   - 가용성에 영향을 주거나, 보안을 위협하거나, 리소스를 과도하게 사용하는 일반적인 웹 공격으로부터 웹 애플리케이션이나 API를 보호하는 데 도움이 되는 웹 애플리케이션 방화벽입니다. 
   - AWS WAF에서는 SQL 주입 또는 사이트 간 스크립팅과 같은 일반적인 공격 패턴을 차단하는 보안 규칙 및 사용자가 정의한 특정 트래픽 패턴을 필터링하는 규칙을 생성하도록 지원하여 애플리케이션에 트래픽이 도달하는 방법을 제어할 수 있습니다


# Amazon API Gateway
   - 모든 규모의 API를 생성, 유지 관리 및 보호
   -  API는 애플리케이션이 백엔드 서비스의 데이터, 비즈니스 로직 또는 기능에 액세스할 수 있는 "정문" 역할을 합니다. API Gateway를 사용하면 실시간 양방향 통신 애플리케이션이 가능하도록 하는 RESTful API 및 WebSocket API를 작성할 수 있습니다. API Gateway는 컨테이너식 서버리스 워크로드 및 웹 애플리케이션을 지원합니다.



   # storage type 정리
      - 자주 액세스하는 객체를 위한 스토리지 클래스
         - 성능에 민감한 사용 사례(밀리초 액세스 시간을 필요로 하는 사례)와 자주 액세스되는 데이터를 위해 Amazon S3는 다음과 같은 스토리지 클래스를 제공
            - STANDARD —기본 스토리지 클래스. 객체를 업로드할 때 스토리지 클래스를 지정하지 않으면 Amazon S3가 STANDARD 스토리지 클래스를 할당합니다.
            - REDUCED_REDUNDANCY—Reduced Redundancy Storage(RRS) 스토리지 클래스는 STANDARD 스토리지 클래스보다 더 적은 중복성으로 저장될 수 있는 중요하지 않고 재현 가능한 데이터용으로 설계되었습니다.
      - 자주 액세스하는 객체와 자주 액세스하지 않는 객체를 자동으로 최적화하는 스토리지 클래스
         - INTELLIGENT_TIERING 스토리지 클래스는 성능 영향 또는 운영 오버헤드 없이 가장 비용 효율적인 스토리지 액세스 계층으로 데이터를 자동으로 이동하여 스토리지 비용을 최적화하도록 설계
         - 세스 패턴이 바뀔 때 자주 액세스하는 티어와 저렴한 요금의 자주 액세스하지 않는 티어 사이에 세분화된 객체 수준에서 데이터를 이동함으로써 자동 비용 절감 효과
      - 자주 액세스하지 않는 객체를 위한 스토리지 클래스
         - STANDARD_IA 및 ONEZONE_IA 스토리지 클래스는 수명이 길고 자주 액세스하지 않는 데이터용으로 설계되었습니다.
         - STANDARD_IA 및 ONEZONE_IA 객체는 밀리초 액세스에 사용 가능합니다(STANDARD 스토리지 클래스와 유사함)
         - Amazon S3는 이들 객체에 대해 검색 요금을 부과하므로 이들 객체는 자주 액세스되지 않는 데이터에 가장 적합합니다
            - 다음의 경우에 STANDARD_IA 및 ONEZONE_IA 스토리지 클래스를 선택할 수 있을 것입니다.
               - 백업
               - 밀리초 액세스가 필요한 오래된 데이터의 경우
            - STANDARD_IA—Amazon S3가 객체 데이터를 지리적으로 분리된 여러 개의 가용 영역에 중복되게 저장합니다
            - ONEZONE_IA–Amazon S3가 객체 데이터를 하나의 가용 영역에만 저장하므로 STANDARD_IA보다 더 저렴합니다
            ![](../../../image/2020-02-03-21-55-15.png)

   - 객체 아카이빙을 위한 스토리지 클래스
      - GLACIER 및 DEEP_ARCHIVE 스토리지 클래스는 저비용 데이터 아카이빙용으로 설계
         - GLACIER—분 단위로 데이터의 일부를 검색해야 하는 아카이브에 사용합니다
         - LACIER 스토리지 클래스에 저장된 데이터는 최소 스토리지 기간이 90일이며 신속 검색을 사용하여 최소 1~5분 이내에 액세스할 수 있습니다. 90일 최소 기간 이전에 삭제했거나 덮어썼거나 다른 스토리지 클래스로 이전한 경우, 90일 요금이 부과됩니다
         - DEEP_ARCHIVE—거의 액세스할 필요가 없는 데이터를 아카이빙할 때 사용합니다.
         - 최소 스토리지 기간은 180일이고 기본 검색 시간은 12시간입니다. 


# VPC Flow Logs
- VPC의 네트워크 인터페이스에서 전송되고 수신되는 IP 트래픽에 대한 정보를 수집할 수 있는 기능
- 플로우 로그 데이터를 Amazon CloudWatch Logs 및 Amazon S3로 게시할 수 있습니다.



# Amazon S3 multipart upload
- 



# AWS CloudTrail
![](../../../image/2020-02-06-16-49-53.png)

