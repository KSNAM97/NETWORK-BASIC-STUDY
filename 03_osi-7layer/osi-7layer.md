# 03. OSI 7계층 (데이터 주소 / 계층화)

OSI 7계층은 통신 과정을 7개의 계층으로 나누어 표준화한 모델입니다.

```
7계층  응용(Application)    ── 사용자 서비스 영역 · DNS, 웹, 응용 서비스
        ▼
6계층  표현(Presentation)  ── 데이터 형식 표현 · 인코딩, 포맷, 변환
        ▼
5계층  세션(Session)       ── 통신 연결 유지 · 세션 생성/유지/종료
        ▼
4계층  전송(Transport)     ── 데이터 전달 방식 · TCP/UDP, Port 번호
        ▼
3계층  네트워크(Network)   ── 목적지까지 경로 선택 · IP, 라우팅, ICMP
        ▼
2계층  데이터링크(DataLink)── 같은 네트워크 내 전달 · Ethernet, MAC, ARP
        ▼
1계층  물리(Physical)      ── 실제 연결 매체 · 케이블, 신호, 포트
```

---

## Layer 4 (전송 계층)

| 항목 | 내용 |
| --- | --- |
| 주소 | Port number (16bit : Source/Destination Port = 0 ~ 65535) |
| 역할 | 해당 시스템의 서비스를 사용하는 Port number를 이용하여 확인 |
| 대표 Protocol | TCP, UDP |
| 데이터 단위 | **Segment** |

- **TCP** : 신뢰성 기반의 연결 지향 통신
  - HTTP(80), FTP(20/21), Telnet(23) (평문), SSH(22) (암호화), HTTPS(443)
- **UDP** : 신속성 기반의 비연결 지향 통신
  - RTP(실시간/인터넷전화/스트리밍), DNS(53), TFTP(69), DHCP(67/68)

## Layer 3 (네트워크 계층)

| 항목 | 내용 |
| --- | --- |
| 주소 | IP Header에 포함된 IP address |
| 역할 | Local 네트워크에서 Remote 네트워크까지 경로 탐색 시 사용 |
| 대표 장비 | Router |
| 데이터 단위 | **Packet** |

## Layer 2 (데이터링크 계층)

| 항목 | 내용 |
| --- | --- |
| 주소 | Ethernet Header에 포함된 MAC-address (16진수 48bit) |
| 역할 | 자신이 속한 같은 네트워크 환경에서 경로 탐색 시 사용 |
| 대표 장비 | Switch |
| 데이터 단위 | **Frame** |

> 💡 핵심: 특히 **L3 IP**와 **L2 Ethernet/MAC**의 연결 관계가 중요합니다.

---

[![Prev](https://img.shields.io/badge/⬅_Prev-02_LAN/WAN-lightgrey)](../02_lan-wan/lan-wan.md)
[![Next](https://img.shields.io/badge/Next_➡-04_주소체계-blue)](../04_address-system/address-system.md)
