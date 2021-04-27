---
title: "책 내용 정리: Clean Architecture"
date: 2021-04-28T02:00:32+09:00
# weight: 1
# aliases: ["/first"]
tags: ["clean", "architecture", "book", "clean architecture"]
author: "halimess"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: false
description: "Clean Architecture 책에서 중요하다고 생각한 내용 정리"
disableHLJS: true # to disable highlightjs
disableShare: false
disableHLJS: false
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
cover:
    # image: "awsCloudPractitionerEssentials.png" # image path/url
    # alt: "AWS Cloud Practitoner Essentials" # alt text
    # caption: "aws" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
---

# 1장. 설계와 아키텍처란?

설계랑 아키텍처는 같은 말이다.
* 아키텍처는 고수준의 무언가, 설계는 저수준의 구조 혹은 결정사항을 의미할 때가 많지만, 이러한 구분은 무의미
* 저수준의 세부사항과 고수준의 구조는 소프트웨어 전체 설계의 구성 요소
* 고수준 -> 저수준으로 향하는 의사결정의 연속성만이 있을 뿐


## 소프트웨어 아키텍처의 목표
* 필요한 시스템을 만들고 유지보수하는 데 투입되는 인력을 최소화
* 즉, 설계 품질의 척도는 요구 사항을 만족시키는 데 드는 비용을 재는 척도


### 엉망진창이 되어가는 신호
1. 시스템을 급하게 만들거나
2. 결과물의 총량을 순전히 프로그래머 수만으로 결정하거나
3. 코드와 설계의 구조를 깔끔하게 만들려는 생각을 전혀하지 않으면
> 파국이다...

**빨리 가는 유일한 방법은 제대로 가는 것이다.**

---

# 2장. 두 가지 가치에 대한 이야기

### 소프트웨어 시스템의 두 가지 가치
1. 행위 (behavior)
    * 기계가 수익을 창출하거나 비용을 절약
    * 개발자는
        * 기능 명세서나 요구사항 문서를 구체화
        * 코드를 작성
        * 디버깅
2. 구조 (structure)
    * 기계의 행위를 쉽게 변경할 수 있도록
    * 변경사항을 적용하는 데 어려움은
        * 변경되는 범위(scope)에 비례
        * 변경사항의 형태(shape)와는 관련이 없어야 한다

### 중요성과 긴급성
아이젠하워 매트릭스의 4 가지 유형
1. 긴급하고 중요한
2. 긴급하지는 않지만 중요한
3. 긴급하지만 중요하지 않은
4. 긴급하지도 중요하지도 않은

* 아키텍처는 1, 2 번에 해당
* 행위는 1, 3번에 해당
> 3번에 해당하는 행위를 첫 번째로 격상시키지 마라.
> 아키텍처가 후순위가 되면, 개발하는 비용이 증가하고 변경사항을 적용하는 일이 현실적으로 불가능해진다.
>
> **기능의 긴급성이 아닌 아키텍처의 중요성을 설득하는 일은 개발자 책임이다.**

# 3장. 패러다임 개요
패러다임은 무엇을 해선 안되는지를 말한다.

* 구조적 프로그래밍 (structured programming)
    * goto문 ❌
* 객체 지향 프로그래밍 (object-oriented programming)
    * 함수 포인터 ❌
* 함수형 프로그래밍 (functional programming)
    * 할당문 ❌

*세 가지 패러다임과 아키텍처의 세 가지 큰 관심사(함수, 컴포넌트 분리, 데이터 관리)의 연관성에 주목하자*

**TBU**