---
title: "리눅스 기초 명령어 top 10"
date: 2021-09-28T19:35:09Z
# weight: 1
# aliases: ["/first"]
tags: ["linux", "command", "devops"]
author: "halimess"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
draft: true
hidemeta: false
comments: false
description: "유튜브 영상, '신입 or Jr. 엔지니어를 위한 리눅스 명령어 Top 10'를 보고 공부하여 정리한 내용"
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

> 레퍼런스
>
> [신입 or Jr 엔지니어 면접을 위한 리눅스 명령어 top 10](https://www.youtube.com/watch?v=u9RukvKZJZM)

1. Server를 어떻게 접속하나요?  
    특별히 사용하는 도구나 방법이 있을까요?

    * ssh와 그 원리를 알고 있는지  
    * password가 아닌 key 방식을 사용해봤는지?
    * 특정 도구(?)나 대체도구는 무엇이 있나?
    * 접근 제어 하는 방식은?

2. IP를 확인하는 리눅스 명령어는 무엇인가요?  
    자신의 Public IP는 어떻게 확인하나요?

    * IP를 조회하는 명령어인 ifconfig 그리고 자신의 Public IP 조회를 어떻게 하는지?
    * 대표적인 방법으로는 curl ifconfig.com, curl ifconfig.me
    * NAT
    * Public, Private subnet

3. 웹사이트가 잘 동작하는지 체크할 때 사용하는 명령어는?  
    curl을 사용해본적은 있는지?  
    사용해보았다면 주로 어떨 때 사용하는지?

    * 주로 curl을 사용해보았는지와 그 사용을 얼마만큼 했는지에 대한 질문입니다.
    * 단순 사용을 넘어 GET, POST 지정을 해보았는지와
    * -v 옵션에 대한 결과 내용 이해를 묻는 연계 질문

## 위 3개 공부하고 넘어가자
## 나머지 명령어들은 이렇게 따라 적지말고 공부하면서 내용을 정리하자
