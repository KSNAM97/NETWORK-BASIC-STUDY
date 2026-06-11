# 04. 주소 체계 (MAC / IP / Port)

## MAC vs IP

| 구분 | MAC 주소 (L2) | IP 주소 (L3) |
| --- | --- | --- |
| 특징 | 장비에 고정된 물리적 주소 (48bit) | 네트워크에 따라 변경되는 논리적 주소 (32bit) |
| 프로토콜 | Ethernet (Frame) | IPv4/IPv6 (Packet) |
| 역할 | 동일 LAN 내부(다음 홉)까지의 물리적 전달 | 출발지 ~ 최종 목적지까지의 경로 탐색(라우팅) |

> ※ 외부 네트워크 통신 시, IP 패킷의 **목적지 IP**는 최종 목적지이지만,
> Ethernet 프레임의 **목적지 MAC**은 외부로 나가는 관문인
> **게이트웨이(라우터)의 MAC 주소**로 설정됩니다.

---

## Port Number (L4)

데이터가 목적지 IP 장비에 도착한 후, **어떤 응용 프로그램(서비스)**에게
전달할지 결정하는 16bit(0 ~ 65535) 식별 번호입니다.

| Port | 서비스 | 설명 |
| --- | --- | --- |
| 20/21 | FTP | 파일 전송 |
| 22 | SSH | 보안 원격 접속 |
| 23 | Telnet | 평문 원격 접속 |
| 53 | DNS | 이름 해석 (도메인 → IP) |
| 67/68 | DHCP | IP 자동 할당 |
| 69 | TFTP | 간이 파일 전송 |
| 80 | HTTP | 웹 통신 |
| 443 | HTTPS | 암호화 웹 통신 |

---

## DNS (Domain Name System)

사용자가 외우기 힘든 IP 주소 대신 이해하기 쉬운 도메인 이름(예: `www.example.com`)을
사용할 수 있게 해주는 이름 해석 서비스입니다.

---

[![Prev](https://img.shields.io/badge/⬅_Prev-03_OSI_7계층-lightgrey)](../03_osi-7layer/osi-7layer.md)
[![Next](https://img.shields.io/badge/Next_➡-05_TCP_Flags-blue)](../05_tcp-flags/tcp-flags.md)
