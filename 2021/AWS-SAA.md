# AWS-SAA 집중 준비기간 (1월 20일 ~ 2월 27일)

- 모의고사 응시 예정일 : 2월 첫째주
- 시험 응시 예정일 : 2월 28일

## 참고 사이트 정리
- [AWS Aurora 도입전에 알아야 할 몇가지 사실](https://link.medium.com/uH6SmWivLdb)

## 부족한 개념 범위
- Redshift 및 데이터베이스의 구체적인 부분
- RDS 성능에 영향을 미치는 요소
- Lambda함수와 보안
- 단어 / 개념 공부 목록
    - RAID 5종류
    - Amazon Simple Workflow Service
    - Amazon Directory Service
    - Amazon WorkSpaces
    - URI와 URL의 정확한 차이
    - AWS Secrets Manager
    - AWS DataSync/StrogeGateway/Direct Connect Gateway 차이
    - AWS TransitGateway
    - AWS step
    - Amazon VPC 게이트웨이형/인터페이스형 + ENI
    - ALB Connection Draining
- AWS Directory Service

## 봤는데 모르겠음
- CloudWatch/Trail과 ELB의 액세스 로그의 차이


## 완료 리스트 및 요약 정리
### 기초 개념
- SQS와 DB간의 유연한 결합이 의미하는 것
- 인바운드 아웃바운드 (반대로 알고 있었음...)
- 프록시
- 워크로드
- CORS 크로스 오리진 리소스 쉐어링
- 네트워크 용량
- NAT 게이트웨이의 구성
- 피어링 접속
- FQDN
- CNAME
- 스루풋이란

### AWS 서비스
#### 미분류
- EMR
- Amazon API Gateway
- Amazon Kinesis Data Streams vs Firehose vs analytics 차이
- Amzon의 페일오버 테크놀로지
- AWS Glue
- Amazon Athena
- AWS App mesh    
- AWS Snowball

#### 업무자동화 / 유저 툴
- Amazon CloudFormation
- Amazon Elastic Beanstalk
- CloudFormation vs Elatic Beanstalk vs Code Deploy
- Code deploy vs code pipline vs code build 차이

#### 루팅/네트워크 
- ENI
- Route 53의 정확한 역할
- Egress-Only 인터넷 게이트웨이
- ALB의 패스 베이스 루팅 기능(경로 기반 라우팅)

#### 서버리스
- 도커, 쿠버네티스, Amazon ECS/Fargate/EKS/ECR
    - ECS : 컨테이너를 태스크, EC2를 Cluster라고 부름 / Cluster용 EC2 인스턴스가 필요
    - Fargate : EC2없이 콘테이너 동작가능 / 액티브 상태가 아닐 때 과금되지 않음
    - Amazon Aurora Serverrless : 자동으로 스케일링 해줌
    - EKS : EC2 관리 안해도 됨
    - ECR : 컨테이너 + "레지스트리" 어쩌구 나오면 이거 
- 서버리스, Lambda 함수, 트리거

#### 스토리지 관련
- Amazon EBS, EFS, S3의 차이점과 블록 스토리지, 객체 스토리지, 파일 스토리지의 차이점
- S3 관련
    - S3 Transfer Acceleration
    - S3 버켓 폴리시와 IAM폴리시의 차이, 우선도
        - S3 버켓에 제한을 거는 3가지 방법 1. 버켓단위로 제한하는 버켓 폴리시 2. IAM 유저단위로 제한하는 유저 폴리시 3. IAM 유저 단위로 제한하는 ACL
        - S3의 리소스는 기본으로 프라이빗 설정이 되어있음. 오브젝트의 소유자만이 오브젝트에 액세스 가능.
        - 버켓 ACL보다 버켓 폴리시가 우선시 됨
        - IAM 롤을 사용해서 버켓을 퍼블릭으로 설정할 수 없음. IAM 폴리시는 버켓에 어태치할 수 없음.
        - 버켓에 대한 액세스 허가와 오브젝트에 대한 액세스 허가는 완전히 독립되어있으며 액세스 허가는 버켓에서 오브젝트로 계승되지않음.
        - 세큐리티 그룹은 S3로의 액세스를 제어하지 않음.
    - 미리 서명된 URL로 S3에 객체를 업로드 
    

    - S3 암호화 보존법/KMS/서버사이드 암호화/클라이언트 암호화

            |암호화|담당|암호화 키 관리|
            |---|---|---|
            |SSE-S3|서버 측|S3|
            |SSE-KMS|서버 측|KMS|
            |SSE-C|서버 측|클라이언트|
            |CSE-KMS|클라이언트 측|KMS|
            |CSE-C|클라이언트 측|클라이언트|

- EC2
    - T2 인스턴스에서 사용할 수 있는 스토리지는 EBS뿐
    - T2 인스턴스의 Linux Amazon 머신이미지는 하드웨어 가상머신(HVM)만 사용할 수 있음

- Amazon EBS의 종류 4가지
- EBS 관련
    - EBS 볼륨은 서로 다른 AZ에서 미러링할 수 없음

- ELB 관련
    - 인스턴스가 정상 상태 코드를 반환하는지 체크하는 건 ELB의 헬스체크의 역할
    - 만약 인스턴스에 이상이 발생했을 시, ELB 헬스체크의 역할은 ELB에서 해당 인스턴스를 분리하는 것
    - 항상 설정한 갯수만큼의 인스턴스가 돌아가게 하는 것은 Auto Scailing의 역할
    - Auto Scailing이 인스턴스를 재기동 혹은 생성시켜놓으면 ELB가 다시 와서 연결
    - 만약 Auto Scailing 그룹의 헬스체크 설정이 EC2로 되어있다면 ELB의 헬스체크 결과는 참고하지않음.

- RDS 관련
    - RDS의 Auto Scailing은 "용량"을 실시간으로 스케일링 해주는 것 / 퍼포먼스 향상에는 상관X
- Amazon ElastiCache

- RedShift 관련
    - RedShift의 크로스 리젼 스냅샷

- Amazon FSx for Lustre
    - HPC 어쩌구 or 아무튼 고성능이 필요하다~ 나오면 무조건 이거

- AWS DataSync/StrogeGateway/Direct Connect Gateway 차이
- Amazon Aurora : 멀티 AZ 지원 불가 (구조 자체가 이미 멀티 AZ)

#### 디렉토리 기반
- AWS Managed Microsoft AD
    - 하나의 디렉토리를 여러 사용 사례에 공유 가능. 
    - 디렉토리를 공유하여 .NET애플리케이션, Windows 인증 RDS가 활성화된 SQL Server용 등
    - 사용자에게 외부 클라우드 애플리케이션에 액세스할 수 있게 허용하고 온프레미스 AD 사용자가 AWS 클라우드의 리소스를 관리하고, 액세스 할 수 있도록 허용하는 기능이 포함됨.
    - AD 디렉토리에서 AWS 애플리케이션 또는 서비스를 활성화하면 사용자는 AD 자격 증명을 사용하여 애플리케이션 또는 서비스에 액세스 할 수 있음.

- Active Directory Connector (AD Connector)
    - AD Connector는 클라우드에서 정보를 캐시 저장하지 않고도 온프레미스 Microsoft Active Diretory로 디렉토리 요청을 리다이렉션하수 있는 디렉토리 게이트 웨이
    - AWS Management 콘솔에 대한 IAM 역할 기반 액세스를 통해 Amazon EC2 인스턴스나 Amazon S3 버킷 같은 AWS 리소스를 관리할 수 있음

#### 세큐리티/인증 영역 정리
- IAM
    - IAM 유저 : 나는 사람이다
    - IAM 롤 : 나는 프로그램(서비스)이다
    - IAM 그룹 : 우리가 유저다
    - IAM 폴리시 : 내가 법이다

- AWS의 인증정보를 안전하게 설정하고 사용하는 법
    - 인스턴스에 롤을 부여
    - MFA는 인증정보를 안전하게 보관하는 것과는 상관없음

- Lambda함수가 프라이빗 서브넷 내의 RDS 데이터 베이스에 액세스 하는 방법 
    - RDS가 있는 VPC에 Lambda함수를 작성함
    - RDS의 세큐리티 그룹에서, Lambda의 세큐리티 그룹으로부터의 인바운드 액세스를 허가함

    - AWS Certifcate manager
    - AWS 서비스 및 연결된 내부 리소스에 사용할 공인 및 사설 SSL/TLS(Secure Sockets Layer/전송 계층 보안) 인증서를 손쉽게 프로비저닝, 관리 및 배포할 수 있도록 지원하는 서비스
    - 아무튼 인증서 관련

- Amazon Cognito
    - 모든 인증/허가의 서비스만 외부유저의 이용에게 적합한 것은 Cognito뿐
    - 모바일과 웹 앱에서 인증 및 보안관리, 별도 사용자 계정 서비스를 활용하여 다양한 AWS 서비스를 손쉽게 연동하고 권한 및 접근 관리를 할 수 있음.
    - Amzon Cognito 유저 풀
        - 완전 관리형 사용자 디렉토리
        - 몇 분 안에 모바일 앱 혹은 웹앱에 회원 가입 데이터 베이스를 만들 수 있음.
    - 사용자 풀 : 사용자의 가입과 로그인을 제공하는 사용자 저장소
    - 자격 증명 풀 : 사용자 풀에 저장된 정보를 바탕으로 로그인 또는 회원가입에 성공한 사용자에게 AWS 인프라의 여러 서비스에 대한 권한을 부여
        

- 모니터링 정리
    - EC2 인스턴스의 상세모니터링 = 데이터를 더 많은 항목으로 알고 싶다 X 데이터를 더 자주 취득하고 싶다 O
        - 기본 모니터링 : 5분에 한번씩 데이터 취득
        - 상세 모니터링 : 1분에 한번씩 데이터 취득

- CloudWatch의 기본 메트릭스 vs 커스텀 메트릭스
    - 만약 메트릭스에서 이상을 검지했다고 하더라도, CloudWatch만으로는 문제가 발생한 어플리케이션만 재기동할 수 없음.(인스턴스 전체 재기동은 가능)
    - 따라서 AWS Systems Manager나 AWS Lambda와 같은 서비스와의 연계가 필수
    - S3는 메트릭스가 없음! 액세스 로그를 유효설정하는 것으로 취득 가능.
    - CloudWatch의 데이터는 2주간 보존.

            |서비스|커스텀 항목|기본 항목|
            |------|---|---|
            |EC2|디스크/메모리/swap사용률, ping/프로세스/포트/web감시|CPU사용률, CPU크레짓 소비수, 디스크r/w의 I/O수, 네트워크 인아웃사용 바이트 수, 시스템 체크, 로그 감시|
    - 클라이언트의 접속정보를 알고 싶다면 ELB의 액세스 로그 활성화

### #100
```
- 스케쥴에 기반한 Auto Scailing
- Load Balancer란
- Provisioning
- 3 Tier Architecture
- ACL, NACL
- 네이티브 암호화 : Amazon S3, Storage Gateway, Dyanamo DB
- IAM의 엑세스 키 사용(비추천)
- SSH의 포트번호는 22, TCP의 포트번호는 43
```
- Auto Scailing이 정확하게 무엇을 스케일링 하는 것인가? EC2와 어떤 관계인가? 로드밸런서와 무엇이 다른가?
- 포트가 무엇인지는 알겠는데, SSH와 TCP의 레이어와 포트가 다른 것은 무엇을 의미하는지?

### #99
```
- 미리 서명된 URL로 S3에 업로드 하기
- Microsoft RDP(Remote Desktop Protocol)를 사용하여 Windows 인스턴스에 원격 접속, 로그인
- EC2 인스턴스에 IMA롤을 어태치하는 것으로 인증 정보를 안전하게 넘길 수 있음.
```

- S3는 데이터 베이스인가? 다른 데이터 베이스와 무엇이 다른가? File Storage와 Database의 차이점은?
    - S3를 데이터베이스로 사용할 수도 있다. DyanamoDB나 다른 DB, 저장소마다 특장점이 있기 때문에 필요한 요건에 맞춰 선택해야한다 

### #98
```
- Amazon EC2의 인스턴스 타입 : T2인스턴스에서 사용할 수 있는 스토리지는 EBS뿐
- T2 인스턴스에서의 Linux Amazon머신 이미지는 하드웨어 가상머신(HVM)만 사용할 수 있음.
- Amazon SQS에 기반한 스케일링
    - SQS는 명령을 큐에 넣어서 분실을 예방하는 것이 가능함.
    - 또한, 보류 중의 큐에 기반해서 처리 노드르르 스케일링 하는 것으로 수요에 대처 가능.
- 느슨한 결합과 강한 결합
    - 느슨한 결합은 컴포넨트 간의 의존성을 줄이고 강한 결합은 그 반대
    - 일반적으로 강한 결합은 좋지 않다. 유연성과 코드의 재사용성을 줄이고 변경을 더 어렵게 하고 시험 가능성을 지연시킴
- Amazon DynamoDB Accelerator (DAX)
    - DB에 영향을 주고 싶지 않다 = DAX
    - Auto Scailing은 DB의 부하 경감시키지 않음
- Amazon EBS 스냅샷
    - EBS 볼륨은 서로 다른 AZ에서 미러링할 수 없음
    - 인스턴스 스토어는 영속적으로 스토리지를 제공하지 않음
    - EBS 암호화는 백업이 아니고 세큐리티 영역
```

### #97
```
- IOPS : Input/Output Operations Per Second
    - HDD,SDD,SAN 같은 컴퓨터 저장장치를 벤치마크 하는데 사용되는 성능 측정 단위
- 완전한 스냅샷을 작성하기 위해서는 EC2 인스턴스를 정지시켜야함
- Amazon RDS 리드레플리카는 프라이머리 데이터베이스의 부하를 경감시켜 퍼포먼스를 향상시킴.
```
### #96
```
- VPC 엔드포인트와 NAT 엔드포인트의 다른점
- 오브젝트의 라이프 사이클 관리
- AWS Trusted Advisor의 5가지 카테고리
    - 코스트의 최적화
    - 세큐리티
    - 내구성
    - 퍼포먼스
    - 서비스의 제한
```

### #94
```
- 데이터베이스는 SQL을 사용해서 조작할 수 있는 테이블 형태의 데이터의 모음이다. 극단적으로 말해서 엑셀과 비슷한 것. 사진이나 동영상등을 저장하기 어렵다. S3는 단순히 쌓아두기만 하기 때문에 저렴한 것, 반면 RDS의 경우는 응답이 빨라야하므로 (저레이턴시) 용량제한이나 객체의 개당 용량제한이 있는 것
- 세큐리티그룹(보안그룹) : 일단 차단하고 나중에 허용 / 인스턴스 단위(EC2 등)
- 네트워크 ACL : 일단 허용하고 나중에 차단 / 서브넷 단위 / 1서브넷 1ACL
- 세큐리티그룹과 ACL이 충돌하면 세큐리티 그룹이 우선함
- 리드 레플리카 = DB의 비동기 백업
- 멀티 AZ배치 = 동기 백업
- 비동기 레플리케이션 = 그런거없음
- 수동백업 = 비추
```

### #92


