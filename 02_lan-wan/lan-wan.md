# 02. LAN / WAN

네트워크는 용도와 크기에 따라 LAN, WAN 으로 나누어 구분합니다.

## LAN (Local Area Network)

자신이 속한 가까운(근거리) 네트워크를 의미하며, 보통 좁은 영역에 구성됩니다.

| 항목 | 내용 |
| --- | --- |
| 구성 장비 | NIC(랜카드), Switch, T/P Cable |
| 특징 | 네트워크 운영/관리 책임이 개인(조직)에게 있어 부담이 적음 |
| 대표 Protocol | **Ethernet** (IEEE에서 제정한 LAN 표준 Protocol) |

### Ethernet 속도

- Ethernet : 10 Mbps
- FastEthernet : 100 Mbps
- GigabitEthernet : 1,000 Mbps

### MAC-address (사용 주소)

16진수 48bit, `HH-HH-HH-HH-HH-HH` 형태입니다.

```
예) 00-E0-4C-B0-C4-81   (일반 표기)
    00E0.4CB0.C481       (CISCO 표기)

  00-E0-4C : OUI — NIC 제조 업체가 IEEE로부터 할당받은 주소
  B0-C4-81 : 해당 회사에서 부여한 제품 일련번호
```

---

## WAN (Wide Area Network)

자신이 속하지 않은 외부(원거리) 네트워크를 의미하며, 넓은 영역에 구성됩니다.
(분리된 LAN과 LAN을 연결하는 네트워크)

| 항목 | 내용 |
| --- | --- |
| 구성 장비 | Router |
| 특징 | 일반적으로 ISP로부터 임대회선을 사용하므로 운영/관리 부담이 큼 |
| 대표 Protocol | **IP** (Internet Protocol : IANA에서 관리) |
| 사용 주소 | IP address (10진수 32bit, `A.B.C.D`) 예) `192.168.1.100` |

### ICMP

> IP 네트워크 환경에서 통신 시 통신 상태(연결 성공/실패)를 확인하는 프로토콜입니다.

---

[![Prev](https://img.shields.io/badge/⬅_Prev-01_네트워크기초-lightgrey)](../01_network-basics/network-basics.md)
[![Next](https://img.shields.io/badge/Next_➡-03_OSI_7계층-blue)](../03_osi-7layer/osi-7layer.md)
