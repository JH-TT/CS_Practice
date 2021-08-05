# 면접 질문들
## Contents
* ### [Network](https://github.com/JH-TT/CS_Practice/blob/main/Contents/Interview.md#network-1)
  * [HTTPS란?](https://github.com/JH-TT/CS_Practice/blob/main/Contents/Interview.md#https%EB%9E%80)
  * [TCP/IP란 무엇인가?](https://github.com/JH-TT/CS_Practice/blob/main/Contents/Interview.md#tcpip%EB%9E%80)
  * TCP와 UDP의 차이점
# Network
## HTTPS란?
* HyperText Transfer Protocol over Secure socket layer의 약자로 HTTP의 보안이 강화된 버전이다.
* HTTPS는 소켓 통신에서 일반 텍스트를 이용하는 대신에, SSL이나 TLS 프로토콜을 통해 세션 데이터를 암호화 한다.
* HTTPS를 사용하는 경우, URL에서 (HTTPS://)를 사용한다.
* HTTPS의 기본 TCP/IP 포트는 443이다.
* TLS는 컴퓨터 네트워크에 통신 보안을 제공하기 위해 설계된 암호 규약이다.
SSL은 표준화되기 전의 이름이고, 표준화된 정식 명칭이 TLS이다.
* HTTPS와 TLS는 유사하지만 다른 개념이다.
  * TLS는 다양한 종류의 보안 통신을 하기 위한 프로토콜이고, HTTPS는 TLS위에 HTTP프로토콜을 얹어 보안된 HTTP통신을 하는 프로토콜이다.
  * TLS는 HTTP뿐만 아니라 FTP, SMTP와 같은 여타 프로토콜에도 적용할 수 있으며, HTTPS는 TLS와 HTTP가 조합된 프로토콜만을 가리킨다.
> [Top](https://github.com/JH-TT/CS_Practice/blob/main/Contents/Interview.md#contents)
## TCP/IP란?
* 인터넷 표준 프로토콜로서 컴퓨터 간의 주고받는 데이터를 전송할 때 에러가 발생하지 않도록 알맞게 나누어 전송하고 이를 수신하여 다시 기존의 정보로 변환하는 것을 약속해 놓은 것을 말한다.
* 데이터의 흐름관리, 정확성 확인, 패킷의 목적지 보장을 담당한다.(데이터의 정확성 확인은 TCP, 패킷을 목적지까지의 전송은 IP가 담당)
* TCP/IP계층은 응용계층, 전송계층, 인터넷 계층, 네트워크 인터페이스 계층 총 4계층으로 구성된다.
> [Top](https://github.com/JH-TT/CS_Practice/blob/main/Contents/Interview.md#contents)
## TCP와 UDP의 차이점
