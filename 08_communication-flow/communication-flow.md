# 08. 통신 흐름 (PC → 외부 Web Server)

사용자가 PC에서 외부 웹 서버로 접속할 때, 내부 LAN의 MAC 기반 전달과
외부 네트워크의 IP 기반 라우팅이 함께 이어집니다.

## 전체 토폴로지

```
[ 로컬 네트워크 1 ]                  [ 인터넷 ]            [ 로컬 네트워크 2 ]
 PC1 192.168.1.101                                          Server1 203.0.113.10
 PC2 192.168.1.102                                          Server2 203.0.113.20
 PC3 192.168.1.103                                          Server3 203.0.113.30
   │                                                              ▲
   ▼                                                              │
 Switch1 (MAC 테이블)                                       Switch2 (MAC 테이블)
   │                                                              ▲
   ▼                                                              │
 Router1 (G/W 192.168.1.1) ──▶  ISP Server  ──▶  Router2 (서버측 게이트웨이)
```

---

## PC1 → Server2 단계별 흐름

```
1) PC1: 목적지 IP가 외부 대역 → ARP로 게이트웨이(Router1) MAC 확인
        ▼
2) Switch1: 목적지 MAC을 Router1로 설정한 프레임을 해당 포트로 전달
        ▼
3) Router1: IP 헤더 분석 → ISP 방향 결정, SA/DA MAC을 외부망 기준으로 재캡슐화
        ▼
4) ISP: 라우팅 테이블을 거쳐 Router2 방향으로 패킷 라우팅
        ▼
5) Router2: 목적지 IP가 직접 연결된 네트워크 확인 → Server2 MAC으로 재캡슐화
        ▼
6) Switch2: MAC 테이블 참조 → Server2 포트로 스위칭
        ▼
7) Server2: 자신의 MAC/IP/Port(80) 확인 후 역캡슐화 → HTTP 요청 처리
```

---

## MAC vs IP (홉 간 변화)

| 구분 | MAC 주소 | IP 주소 |
| --- | --- | --- |
| 계층 | L2 (데이터링크) | L3 (네트워크) |
| 범위 | 로컬 구간(다음 홉)의 물리 주소 | 종단 간 논리 주소 |
| 변화 | 라우터를 지날 때마다(홉마다) **변경됨** | 출발지~목적지까지 **유지됨** |

> **NAT (Network Address Translation)**
> Router1에서 NAT가 적용되어, 여러 내부 PC(사설 IP)가 인터넷으로 나갈 때
> **하나의 공인 IP + Port 조합**을 공유합니다.

> 💡 **핵심: IP 주소는 통신 내내 유지되고, MAC 주소는 각 홉을 지날 때마다 변경된다!**

---

[![Prev](https://img.shields.io/badge/⬅_Prev-07_TCP_Handshake-lightgrey)](../07_tcp-handshake/tcp-handshake.md)
[![Next](https://img.shields.io/badge/Next_➡-09_IPv4주소-blue)](../09_ipv4-address/ipv4-address.md)
