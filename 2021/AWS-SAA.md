# AWS-SAA 집중 준비기간 (1월 20일 ~ 2월 27일)

- 모의고사 응시 예정일 : 2월 첫째주
- 시험 응시 예정일 : 2월 27일

## 참고 사이트 정리
- [AWS Aurora 도입전에 알아야 할 몇가지 사실](https://link.medium.com/uH6SmWivLdb)

## 개인적인 의문사항 정리

## 부족한 개념 범위
- Redshift 및 데이터베이스의 구체적인 부분
- RDS 성능에 영향을 미치는 요소
- Lambda함수와 보안
- 단어 / 개념 공부 목록
    - 프록시
    - 네트워크 용량
    - Amzon의 페일오버 테크놀로지
    - Amazon API Gateway
    - ALB의 패스 베이스 루팅 기능(경로 기반 라우팅)
    - Amazon EMR
    - Amazon EFS
    - Amazon Kinesis Data Firehose/Data Streams
    - RAID 5종류
    - Amazon Simple Workflow Service
    - IAM
    - Amazon Directory Service
    - Amazon WorkSpaces
    - URI와 URL의 정확한 차이
    - 스루풋이란
    - Amazon CloudFormation
    - Egress-Only 인터넷 게이트웨이

## 봤는데 모르겠음
- CloudWatch/Trail과 ELB의 액세스 로그의 차이

## 완료 리스트
- SQS와 DB간의 유연한 결합이 의미하는 것
- 미리 서명된 URL로 S3에 객체를 업로드 한다는게 무슨뜻인지? 웹서버에 어떻게 부하가 가지않는 방식인건지
- Amazon ElastiCache
- Amazon Elastic Beanstalk
- Amazon EBS의 종류 4가지
- Route 53의 정확한 역할
- 인바운드 아웃바운드 (반대로 알고 있었음...)
- Amazon Aurora : 멀티 AZ 지원 불가
- 도커, 쿠버네티스, Amazon ECS/Fargate/EKS/ECR
- 서버리스, Lambda 함수, 트리거
- Amazon EBS, EFS, S3의 차이점과 블록 스토리지, 객체 스토리지, 파일 스토리지의 차이점
- S3 버켓 폴리시와 IAM폴리시의 차이, 우선도
- S3 암호화 보존법/KMS/서버사이드 암호화/클라이언트 암호화

## 시험 직전 복습 리스트
- S3 버켓 폴리시와 IAM폴리시의 차이, 우선도



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


