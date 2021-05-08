---
title: "AWS 자격증, AWS Cloud Practitioner Essentials"
date: 2021-04-17T02:19:32+09:00
# weight: 1
# aliases: ["/first"]
tags: ["aws", "cloud", "자격증"]
author: "halimess"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
draft: true
hidemeta: false
comments: false
description: "AWS 클라우드 개념, AWS 서비스, 보안, 아키텍처, 요금 및 지원에 대해 학습하여 AWS 클라우드 지식 습득"
disableHLJS: true # to disable highlightjs
disableShare: false
disableHLJS: false
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
cover:
    image: "awsCloudPractitionerEssentials.png" # image path/url
    alt: "AWS Cloud Practitoner Essentials" # alt text
    caption: "aws" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
---

여기에는 AWS Cloud Practitioner Essentials 무료 교육에서 배운 내용을 정리한다.

### 모듈 1
* AWS의 이점을 요약할 수 있습니다.
* 온디맨드식 제공과 클라우드 배포의 차이점을 설명할 수 있습니다.
* 종량 과금제 모델을 요약 설명할 수 있습니다.

AWS 클라우드는 IT 인프라를 제공하며 사용한 확장, 축소가 용이하며 초기 비용없이 사용한 만큼 비용을 지불하면 됩니다. 크지 않은 조직이나 개인이 운용하기 힘든 인프라를 관리해주고, 개발자는 서비스 개발에 좀더 집중할 수 있도록 제공합니다.

#### 클라우드 컴퓨팅 배포 모델
클라우드 기반, 온프레미스, 하이브리드 세 가지
* 클라우드 기반
    * 애플리케이션의 모든 부분을 클라우드에서 실행
    * 기본 애플리케이션을 클라우드로 마이그레이션
    * 새 애플리케이션을 클라우드에 설계 및 빌드
* 온프레미스
    * 가상화 및 리소르 관리 도구를 사용하여 리소스를 배포
    * 애플리케이션 관리 및 가상화 기술을 사용하여 리소스 활용도를 높임
    * 프라이빗 클라우드 배포라고도 함
    * 레거시 IT 인프라와 유사하나, 애플리케이션 관리 및 가상화 기술이 통합되어 리소스 사용률을 높임
* 하이브리드
    * 클라우드 기반 리소스를 온프레미스 인프라에 연결
    * 클라우드 기반 리소스를 레거시 IT 애플리케이션과 통합

### 모듈 2
* 기본적인 Amazon EC2의 이점을 설명할 수 있습니다.
* 서로 다른 Amazon EC2 인스턴스 유형을 파악할 수 있습니다.
* Amazon EC2의 다양한 결제 옵션을 구분할 수 있습니다.
* Amazon EC2 Auto Scaling의 이점을 요약할 수 있습니다.
* Elastic Load Balancing의 이점을 요약할 수 있습니다.
* Elastic Load Balancing 사용 사례를 제시할 수 있습니다.
* Amazon Simple Notification Service(Amazon SNS)와 Amazon Simple Queue Service(Amazon SQS)의 차이점을 요약할 수 있습니다.
* 그 외 AWS 컴퓨팅 옵션을 요약할 수 있습니다.

AWS에서 제공하는 EC2는 필요한 컴퓨팅 파워의 가상 서버는 몇 분안에 사용할 수 있다. 더 이상 서버는 사용하지 않아도 될 때는 언제든 끌 수 있다. 반면 온프레미스는 서비스나 개발에 필요한 서버 스펙을 확립하고 서버 장비를 구매, 데이터 센터를 대여 혹은 구축하여 설치하고, 인터넷, 전원 등을 모두 준비해야 서버를 사용할 수 있다. 서버를 사용하기 전에 많은 비용이 청구된다. EC2는 필요한 서버를 간편하게 필요한 경우에만 사용할 수 있는 이점이 있다.

### 모듈 3
- 기본적인 Amazon EC2의 이점을 설명할 수 있습니다.
- 서로 다른 Amazon EC2 인스턴스 유형을 파악할 수 있습니다.
- Amazon EC2의 다양한 결제 옵션을 구분할 수 있습니다.
- Amazon EC2 Auto Scaling의 이점을 요약할 수 있습니다.
- Elastic Load Balancing의 이점을 요약할 수 있습니다.
- Elastic Load Balancing 사용 사례를 제시할 수 있습니다.
- Amazon Simple Notification Service(Amazon SNS)와 Amazon Simple Queue Service(Amazon SQS)의 차이점을 요약할 수 있습니다.
- 그 외 AWS 컴퓨팅 옵션을 요약할 수 있습니다.

— 이점 설명 —

EC2는 `가상화` 기술로 AWS의 물리적 호스트 시스템에서 `가상 머신`을 제공. 호스트 시스템에는 `하이퍼바이저`가 가상 머신 간 물리적 리소스 공유를 책임지며, 이렇게 하드웨어를 공유하는 걸 `멀티 테넌시`라고 부른다. 하이퍼바이저는 호스트의 리소스를 공유하는 가상 머신을 분리하여 각 EC2 인스턴스는 안전하게 분리

EC2 인스턴스는 프로비저닝할 때, OS로 Windows, Linux를 선택할 수 있으며 수천 개를 생성할 수도 있다.

운영 체제 외에 인스턴스에서 실행할 소프트웨어도 구성 가능. 자체 사내 애플리케이션, 웹 앱, 데이터베이스, 엔터프라이즈 소프트웨어 패키지 등 모든 소프트웨어는 인스턴스 관련 설정을 제어할 수 있다.

EC2 인스턴스의 크기 조정 가능, 작은 인스턴스에서 시작하여 서버 한도를 초과하면 더 많은 메모리와 CPU를 제공 → 인스턴스의 `수직 확장`

인스턴스는 필요에 따라 언제든 크기를 조정할 수 있고, 네트워크도 제어 가능

애플리케이션의 요구 조건에 따라 EC2 인스턴스 유형을 선택할 수 있다.

- 범용
    - 컴퓨팅, 메모리, 네트워크 리소스의 균형
    - 웹 서비스, 코드 리포지토리
- 컴퓨팅 최적화
    - 게임 서비스, 고성능 컴퓨팅
    - HPC, 과학 모델링
- 메모리 최적화
    - 메모리 집약 작업
- 액셀러레이티드 컴퓨팅
    - 하드웨어 액셀러레이터 → 부동 소수점 계산, 그래픽 처리
    - 데이터 패턴 매칭
