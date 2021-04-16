---
title: "개발자가 알아야할 SOLID 원칙"
date: 2021-04-15T02:26:44+09:00
# weight: 1
# aliases: ["/first"]
tags: ["OOP", "SOLID"]
author: "halimess"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
draft: true
hidemeta: false
comments: false
description: "S.O.L.I.D principles"
disableHLJS: true # to disable highlightjs
disableShare: false
disableHLJS: false
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
cover:
    image: "<image path/url>" # image path/url
    alt: "<alt text>" # alt text
    caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
---

* 이 글은 [Chidume Nnamdi](https://kurtwanger40.medium.com/)님의 Medium 블로그 글, [SOLID Principles every Developer Should Know](https://blog.bitsrc.io/solid-principles-every-developer-should-know-b3bfa96bb688)을 번역하여 정리한 내용입니다.

OOP(Object-Oriented Programming)는 개발자가 하나의 기능을 담당하는 클래스에 데이터와 기능을 담을 수 있게 해준다.
하지만, OOP가 개발자에게 깔끔하고 관리하기 좋은 코드를 구현할 수 있게 해주진 않는다.

읽기 좋고, 관리하지 좋은 코드를 구현하기 위해, Robert C. Martin이 제안한 5가지 S.O.L.I.D 원칙을 소개한다.

* S: Single Responsibility Principle
* O: Open-Closed Principle
* L: Liskov Substitution Principle
* I: Interface Segregation Principle
* D: Dependency Inversion Principle



