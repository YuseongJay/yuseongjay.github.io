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
draft: false
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

> 레퍼런스: DevOpsArt [신입 or Jr 엔지니어 면접을 위한 리눅스 명령어 top 10](https://www.youtube.com/watch?v=u9RukvKZJZM)

1. Server를 어떻게 접속하나요?  
    특별히 사용하는 도구나 방법이 있을까요?

    * 다양한 방법이 있겠지만, 여기선 ssh만 설명
    * ssh란 secure shell의 약자로 클라이언트와 서버 간의 보안 상 안전한 연결을 위한 암호화 프로토콜
    * ![ssh protocol flow](/ssh-protocol-2021-09-30-063637.png)
    * 예시: aws ec2 생성 시 private key를 설정하여 서버 접근 시 활용
    ``` bash
        ssh -i "/pwd/private-key.pem" user@server.host # private key 활용
    ```
    * 기본 ssh 포트는 22
    * ssh 포트 변경 시 `/etc/ssh/sshd_config`의 설정을 변경해주자
    * ssh-agent, ssh-add 명령어로 ssh-agent에 private key를 저장하여 활용 가능
        * private key를 직접 입력하지 않고 서버 접속을 가능케 함
    * ![ssh-agent ssh-add](/ssh-agent-2021-09-30-072947.png)
    <!-- * ssh와 그 원리를 알고 있는지  
    * password가 아닌 key 방식을 사용해봤는지?
    * 특정 도구(?)나 대체도구는 무엇이 있나?
    * 접근 제어 하는 방식은? -->

> [ssh academy](https://www.ssh.com/academy/ssh/command)

2. IP를 확인하는 리눅스 명령어는 무엇인가요?  
    자신의 Public IP는 어떻게 확인하나요?

    * `ifconfig` Private IP가 조회될 수 있음
    * `curl icanhazip.com`
    * `curl ifconfig.co`
    * `curl ifconfig.me`
    <!-- * IP를 조회하는 명령어인 ifconfig 그리고 자신의 Public IP 조회를 어떻게 하는지?
    * 대표적인 방법으로는 curl ifconfig.com, curl ifconfig.me
    * NAT
    * Public, Private subnet -->

3. 웹사이트가 잘 동작하는지 체크할 때 사용하는 명령어는?  
    curl을 사용해본적은 있는지?  
    사용해보았다면 주로 어떨 때 사용하는지?

    * `curl google.com`
        * ![curl google.com](/curl-1-2021-09-30-074141.png)
        * google.com 도메인에 연결된 서버에서 301 Moved 응답을 내려준 것을 확인할 수 있음
        * 브라우저는 301 Moved 응답에서 지정된 링크로 이동할 것임
    * `curl -v google.com`
        * ![curl -v google.com](/curl-2-2021-09-30-074141.png)
        * 어떻게 request했는 지, 어떤 response header를 받았는 지 확인할 수 있음
    * `curl -v https://google.com`
        * ![curl -v https://google.com](/curl-3-2021-09-30-074837.png)
        * https 프로토콜에 대한 ssl 인증서 확인 가능

    <!-- * 주로 curl을 사용해보았는지와 그 사용을 얼마만큼 했는지에 대한 질문입니다.
    * 단순 사용을 넘어 GET, POST 지정을 해보았는지와
    * -v 옵션에 대한 결과 내용 이해를 묻는 연계 질문 -->

4. Domain의 IP를 조회하는 명령어는?

    * `nslookup`
        * 더 이상 maintain되진 않는다고 함
    * `dig`
        * DNS 진단에 활용
    * `host`
        * 간단히 DNS 확인 시 유용

> [nslookup](https://docs.microsoft.com/ko-kr/windows-server/administration/windows-commands/nslookup)  
> [nslookup vs dig and host](https://www.linuxquestions.org/questions/linux-networking-3/nslookup-vs-dig-and-host-238612/)  
> [why nslookup is deprecated](https://www.linuxquestions.org/questions/linux-networking-3/why-nslookup-is-deprecated-122337/)

5. 웹서버 혹은 DB 같은 서버들을 확인하는 방법은?

    * `telnet host port`
        * ![telnet google.com 80](/telnet-2021-09-30-082912.png)
    * `nc`
    * `ping`
        * ICMP 프로토콜로 특정 IP와의 연결을 테스트
        * 특정 TCP 포트를 통한 연결을 테스트하긴 어렵다

6. 내 서버의 서버(웹 어플리케이션 or DB)가 잘 떠있는지,  
    현재 DB 커넥션 등을 확인하는 명령어는?

    * `netstat -lntp`
    * ![netstat -lntp](/netstat-2021-09-30-083729.png)
    * ec2 인스턴스에 tomcat을 띄우고 8080 포트로 tomcat이 뜬 것을 확인할 수 있음

    <!-- * netstat 명령어와 그 옵션 등을 사용해보았는 지에 대한 것을 묻는 질문
    * netstat -lntpu
    * netstat -an | grep "port"
    등의 예시를 정확히 이해하고 있는지에 대한 질문 -->

7. Linux에서 특정 프로세스를 확인하는 명령어는?  
    process id, option 등을 확인하고 싶다면?

    * `ps -ef | grep ssh`
    * ![ps -ef | grep ssh](/ps-ef-2021-09-30-084427.png)
    * TODO: ps 자주 사용하는 옵션 내용 정리

    <!-- * 주로 ps 명령어를 사용해보았는 지에 대한 질문
    * ps -ef | grep ""
    * ps aux | grep ""
    * 등 위와 같은 명령어를 실제 사용했고, 어떤 상황에서 사용하는지에 대해서 확인하는 질문 -->

8. Linux에서 CPU, Memory, Disk 등 시스템 정보 등을 확인하는 명령어들은?

    * `top`
        * 현재 프로세스, cpu/memory 사용량 확인
    * `sar 1`
        * 1초마다 cpu 상태 출력
    * `free -m`
        * 메모리 사용량
        * /proc/meminfo
    * df
        * 디스크 확인
    * iostat
    <!-- * 모니터링에 사용될 수 있는 명령어들을 알고 있는지 사용해보았는지에 대해서 확인 -->

9. Linux에서 서비스들은 어떻게 관리되고, 그와 연관된 명려어는?

    * yum, apt 등으로 설치하면 자동으로 system 파일을 생성해주기 때문에 모르고 넘어가는 경우가 많음
    * /etc/systemd/system 참고
    * `service tomcat status`
    * ![service tomcat status](/service-2021-09-30-085808.png)

    <!-- * service
    * systemctl
    * 위 명령어들을 사용해보았는지에 대한 질문
    * 결국 위 명령어들은 systemd에 관련된 질문, systemd를 이해하고 있는지와
    * 직접 작성해봤는지와 어던 기능과 사용사례에 대해서 확인하는 질문.
    * init.d, upstart까지 설명할 수 있다면 참고로 더 이상 물을게 없음. -->

10. Linux 파일 권한 체계를 이해하고 있는지?

    * chmod
        * read = 4
        * write = 2
        * execute = 1
        * `chmod 400` : owner-r, group-, other-
        * `chmod 755` : owner-rwx, group-rx, other-rx
    * chown
        * `chown owner[:group]`
    * ![ls -al /](/ls-al-2021-09-30-090047.png)

    <!-- * 등을 이해하고 있는지를 묻는 질문. -->

11. 그 밖에도 많은 명령어가 있습니다.

    * cd, cp, mv, ls 같은 명령어는 당연히 알아야하는 명령어입니다.
    * 리눅스의 부팅 프로세스를 알고 있는지에 대한 질문도 하는 경우가 있습니다.(/etc/profile. /etc/rc*, cloud-init 등 그 이후 cron 등)
    * fdisk, lvm, mkfs 등 파일 시스템 관련
    * yum, apt 등 repo 관련한
