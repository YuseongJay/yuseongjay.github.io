---
title: "AWS VPC 이론 공부"
date: 2021-09-14T14:56:08Z
# weight: 1
# aliases: ["/first"]
tags: ["aws", "vpc", "이론"]
author: "halimess"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: false
description: "Desc Text."
disableHLJS: true # to disable highlightjs
disableShare: false
disableHLJS: false
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
# cover:
#     image: "<image path/url>" # image path/url
#     alt: "<alt text>" # alt text
#     caption: "<text>" # display caption under cover
#     relative: false # when using page bundles set this to true
#     hidden: true # only hide on current single page
# editPost:
#     URL: "https://github.com/<path_to_repo>/content"
#     Text: "Suggest Changes" # edit text
#     appendFilePath: true # to append file path to Edit link
---

이 문서는 유튜브 강의 [AWS VPC 상세히 알아보기](https://www.youtube.com/watch?v=ZISUSL431bY)를 공부하며 작성한 내용을 포함합니다.


AWS VPC는 사용자가 정의한 가상 네트워크
> Region에 종속적임

AWS VPC 구성 요소
* subnet : VPC를 특정 범위로 나눔
* RouteTable : 네트워크 트래픽 라우팅 테이블
* Internet GW : VPC의 리소스에서 인터넷 통신을 활성하기 위한 게이트웨이
* NAT GW : 네트워크 주소 변환을 통해 private subnet 에서 인터넷 통신을 연결하는 게이트웨이
* VPC Endpoint : NAT, IGW 등을 통하지 않고 AWS 서비스를 비공개로 연결 가능케하는 서비스

subnet
> AZ에 종속적
> AZ는 3개 이상 사용하는 것을 권장

subnet을 설정하는 best practices
* AZ마다 public subnet, private subnet 생성
* public subnet에는 bastion 위치
* 그 외 대부분 서비스는 private subnet에 위치
* 요즘엔 서비스 구별에 따라 private subnet을 여러 개 만들지 않는 추세라고 함
* subnet 내 서비스들의 IP 를 설정하지 않도록 설계
    * autoscaling 등을 위함
