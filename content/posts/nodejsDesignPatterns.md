---
title: "Node.js 디자인 패턴 바이블"
date: 2021-09-08T01:02:35+09:00
# weight: 1
# aliases: ["/first"]
tags: ["node.js", "design", "patterns"]
author: "halimess"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
draft: true
hidemeta: false
comments: false
description: "검증된 패턴과 기술을 이용한 수준 높은 Node.js 애플리케이션 설계 및 구현"
disableHLJS: true # to disable highlightjs
disableShare: false
disableHLJS: false
hideSummary: false
searchHidden: false
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
cover:
    # image: "<image path/url>" # image path/url
    # alt: "<alt text>" # alt text
    # caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
# editPost:
#     URL: "https://github.com/<path_to_repo>/content"
#     Text: "Suggest Changes" # edit text
#     appendFilePath: true # to append file path to Edit link
---

# 모듈 시스템과 패턴
## 노출식 모듈 패턴 - Revealing module pattern
``` javascript
const myModule = (() => {
    const privateFoo = () => { }
    const privateBar = []

    const exported = {
        publicFoo: () => { },
        publicBar: () => { }
    }

    return exported
})() 

console.log(myModule)
console.log(myModule )
```
