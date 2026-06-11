# 🌐 NETWORK-BASIC-STUDY

![Network](https://img.shields.io/badge/Network-Basic-blue)
![OSI](https://img.shields.io/badge/OSI-7_Layer-green)
![Protocol](https://img.shields.io/badge/Protocol-TCP/IP-orange)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

**네트워크 기초 개요 (LAN/WAN · OSI · TCP/IP · 주소체계 · Subnetting/VLSM · ARP/ICMP)**

---

부트캠프 네트워크 기초 과정을 정리한 학습 노트입니다.
통신의 기본 개념(캡슐화, 프로토콜)에서 출발하여 LAN/WAN, OSI 계층별 주소 체계,
IPv4 주소 / 서브넷팅 / VLSM / IP 집약 / Wildcard Mask, TCP 3-Way Handshake,
ARP/ICMP 동작, 그리고 PC에서 외부 웹 서버까지의 실제 통신 흐름을 단계별로 다룹니다.
**네트워크 입문 / CCNA 기초**용 자료입니다.

| 항목 | 내용 |
| --- | --- |
| 대상 | 네트워크 입문자, 클라우드/DevOps 학습자 |
| 범위 | 통신 개념, LAN/WAN, OSI 7계층, MAC/IP/Port, IPv4/Subnet/VLSM/Summary/Wildcard, ARP, ICMP, TCP Handshake, 통신 흐름 |
| 키워드 | Encapsulation, Ethernet, Protocol, IP Class, Subnet, VLSM, CIDR, Wildcard, ARP, ICMP, SYN/ACK, NAT |

---

## 📁 디렉터리 구조

```
network-basic-study/
├── 01_network-basics/        # 네트워크/통신 개념, 캡슐화, 프로토콜
├── 02_lan-wan/               # LAN vs WAN, NIC/Switch/Router
├── 03_osi-7layer/            # OSI 7계층 개요와 계층별 주소
├── 04_address-system/        # MAC / IP / Port 주소 체계
├── 05_tcp-flags/             # TCP Flag 비트와 의미
├── 06_arp-icmp/              # ARP / ICMP 동작 원리
├── 07_tcp-handshake/         # TCP 3-Way Handshake
├── 08_communication-flow/    # PC → 외부 웹 서버 통신 흐름
├── 09_ipv4-address/          # IPv4 주소, IP Class, 사설/공인 IP, Network-ID/Broadcast
├── 10_subnetting-vlsm/       # Subnetting, VLSM 계산
├── 11_ip-summary/            # IP 주소 집약(Summary), Classful 집약
├── 12_wildcard-mask/         # Wildcard Mask
│
├── LICENSE
└── README.md
```

---

## 📚 학습 챕터

| # | 챕터 | 내용 |
| --- | --- | --- |
| 01 | [네트워크 기초](./01_network-basics/network-basics.md) | 통신 개념, 사회/IT 네트워크, Protocol, Encapsulation |
| 02 | [LAN / WAN](./02_lan-wan/lan-wan.md) | LAN vs WAN, NIC/Switch/Router, Ethernet, MAC 주소 |
| 03 | [OSI 7계층](./03_osi-7layer/osi-7layer.md) | OSI 7계층 개요, 계층별 역할, L2/L3/L4 주소와 데이터 단위 |
| 04 | [주소 체계](./04_address-system/address-system.md) | MAC(L2) / IP(L3) / Port(L4), 주요 포트 번호 |
| 05 | [TCP Flags](./05_tcp-flags/tcp-flags.md) | TCP Flag 비트(CWR/ECE/URG/ACK/PSH/RST/SYN/FIN) |
| 06 | [ARP / ICMP](./06_arp-icmp/arp-icmp.md) | ARP Request/Reply, ICMP Echo, ping 동작 흐름 |
| 07 | [TCP 3-Way Handshake](./07_tcp-handshake/tcp-handshake.md) | SYN → SYN/ACK → ACK, Seq/Ack, 패킷 헤더 분석 |
| 08 | [통신 흐름](./08_communication-flow/communication-flow.md) | PC → Switch → Router → ISP → Web Server, NAT |
| 09 | [IPv4 주소](./09_ipv4-address/ipv4-address.md) | 진법 변환, IP Class(A~E), SubnetMask, Network-ID/Broadcast, 사설/공인 IP |
| 10 | [Subnetting / VLSM](./10_subnetting-vlsm/subnetting-vlsm.md) | 서브넷팅, VLSM, 비트 분할 계산 예제 |
| 11 | [IP Summary](./11_ip-summary/ip-summary.md) | IP 주소 집약(Summary), Classful 집약, 라우팅 테이블 최적화 |
| 12 | [Wildcard Mask](./12_wildcard-mask/wildcard-mask.md) | Wildcard Mask, SubnetMask와 비교, ACL/Routing 적용 |

---

## 🧷 핵심 요약

- **Encapsulation(캡슐화)** : 원본 데이터에 헤더(Source/Destination Address)를 덧붙여 전송
- **LAN/WAN** : LAN은 Switch 중심 근거리망, WAN은 Router 중심 원거리망
- **주소 체계** : MAC(L2, 물리), IP(L3, 논리), Port(L4, 서비스 식별)
- **IP Class** : A(0~127), B(128~191), C(192~223), D(멀티캐스트), E(예비)
- **가용 호스트** : `2^(호스트 비트) - 2` (Network-ID, Broadcast 제외)
- **Subnetting/VLSM** : 하나의 네트워크를 효율적으로 분할하여 사용
- **IP Summary** : 여러 네트워크를 하나로 집약 → 라우팅 테이블 최소화
- **Wildcard Mask** : SubnetMask의 비트를 반대로(0=체크, 1=무시), ACL/OSPF/EIGRP에서 사용
- **통신 흐름** : IP는 종단 간 유지, MAC은 홉(Hop)마다 변경

---

## 🛠 학습 환경

| 도구 | 용도 |
| --- | --- |
| GNS3 / Packet Tracer | 토폴로지 시뮬레이션 |
| Wireshark | 패킷 캡처 및 헤더 분석 |
| Git / GitHub | 학습 노트 관리 |

---

## License

[MIT License](./LICENSE)

<div align="center">

**작성자**: [KSNAM97](https://github.com/KSNAM97)
**작성일**: 2026.06  

</div>
