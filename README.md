Cisco-routing-setting
===
### Date: 2017-06~
#### university programming assignments.
-------------
#### 	라우터 스위치 연동 테스트
- 라우터와 스위치에서 각각 running configuration
- 스위치에서 스위치 까지 ping test 결과

#### 라우터 스위치 연동 rip 프로토콜 설정
- 라우터와 스위치의 running configuration
- 가장 끝단 스위치에서 ping, telnet 테스트

#### 라우터 스위치 연동 -igrp
- 라우터와 스위치의 running configuration
- 스위치 A에서 스위치 C 까지 ping 테스트
- sh ip route
- sh ip protocol

#### 라우터 스위치 연동 ospf
- 라우터와 스위치의 running configuration
- sh ip protocol, sh ip route, sh ip ospf interface, hs ip ospf neighbor
- 가장 끝단 스위치에서 ping 테스트

#### 라우터와 스위치 연동 rip, igrp, ospf
- ip addr : class C /25
- as no  300, process-id 300, area 0
- ospf 설정 후  sh ip route로 설정확인할 것 
- 라우터와 스위치의 running configuration
-  sh ip protocol, sh ip route,  sh ip ospf interface
- 가장 끝단 스위치에서 ping 테스트

#### standard access list 설정
- eigrp 설정 as no 200
- 스위치 A->라우터 C로의 트리픽 deny
- 스위치 A->라우터 B로의 트래픽 deny
- ping 동작결과
  - 스위치 A -> 라우터 B
  - 스위치 A -> 라우터 C
  - 라우터 C -> 스위치 A
  - 라우터 B -> 스위치 A
  - 스위치 C -> 스위치 B
  - 스위치 B -> 스위치 C
- 각 라우터의 running configuration

#### extended access list
- ospf,  process-id 200, area 0
- enable secret password : kpu
- vty password : computer
- extended access list 설정
  - B sw-> A sw telnet deny
  - B sw-> C sw telnet deny
- 동작결과
  - B sw-> A sw telnet, ping 
  - B sw-> C sw telnet, ping
  - A sw-> B sw telnet, ping 
  - C sw-> B sw telnet, ping
  - C sw-> A sw telnet, ping
  - A sw-> C sw telnet, ping
  
#### nat 설정
- 스위치 A,C의 주소 : 10.1.1.1
- 라우터 A,B,C  serial addr : class B addr
- rip 설정
- nat 설정 : pool name (computer)
- 동작결과
  - Sw A -> Router C serial Interface ping
  - Sw C -> Router A serial Interface  ping
  - 동작 후 라우터 A,C 에서 sh ip nat translations
  
#### ppp chap 설정
- host name 설정
- IP addr : class C/24
- PPP CHAP 설정 (password computer)
- ping test left<->center, center<->right
