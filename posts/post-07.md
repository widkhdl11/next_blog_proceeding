---
title: 이더넷 프레임이란
date: 2023-11-08
description: 이더넷 프레임이란
---

### 이더넷 프레임이란?

- 데이터 링크계층의 데이터 단위이다.

### 이더넷 프레임의 구조

1. Preamble[7바이트] : 이더넷 프레임이 시작임을 알려준다.
2. SFD[1바이트] : Start frame delimiter, 다음 필드부터 주소필드가 시작됨을 알려줍니다.
3. Destination Address[6바이트] : 목적지 주소입니다.
4. Source Address[6바이트] : 시작지 주소입니다.
5. EtherType[2바이트] : 데이터링크계층 위의 IP 프로토콜을 정의합니다. (IPv4, Ipv6)
6. Payload[가변바이트] : 데이터 또는 페이로드라고 합니다. 가변길이 필드입니다. 해당
   필드는 이진데이터(0과1 로 이루어진 데이터)로 구성됩니다. IEEE 표준은 최대
   페이로드를 1500 바이트로 지정하고 있습니다.
7. FCS[4바이트] : frame check sequence이며 수신측의 에러검출을 위해 삽입하는
   필드입니다. CRC 에러검출 기법에 의해 생성된 비트배열이 여기에 담깁니다.
   비트배열을 기반으로 수신된 데이터가 손상되었는지를 확인하고에러 확인시에는
   해당 프레임을 폐기하고 송신측에 재전송을 요구합니다. 이를 위한 필드입니다.

## 쉽게 설명하자면

- Preamable : 이더넷 프레임이 시작된다는 것을 나타냄
  &nbsp;
- SFD : 다음필드부터는 주소필드라는 것을 나타냄
  &nbsp;
- Destination Address, Source Address : 목적지와 시작지 주소
  &nbsp;
- EtherType : IPv4인지, IPv6인지 나타냄
  &nbsp;
- Payload : 데이터를 담음
  &nbsp;
- FCS : CRC 에러검출 기법으로 무결성을 확인하고 결점이 있을 시 재전송 요청함.
