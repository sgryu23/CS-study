## 1. 데이터 처리량의 의미와 처리량에 영향을 주는 요소
* 링크 내에서 성공적으로 전달된 데이터의 양(트래픽)
* 트래픽, 네트워크 장치 간의 대역폭, 네트워크 중간에 발생하는 에러, 장치의 하드웨어 스펙에 영향을 받는다.
## 2. 트리 토폴로지의 특징, 장점, 단점
* 특징
	1. 버스 토폴로지와 스타토폴로지의 하이브리드 형태를 가진다.
* 장점
  1. 리프노드 기반의 확장/삭제가 용이하다.
  2. 리프노드의 에러는 나머지 부분에 영향을 미치지 않는다.
* 단점
  1. 특정 노드 트래픽 집중시 하위노드에 영향을 준다.
  2. 루트노드에 문제가 생기면 전체네트워크에 큰 문제가 생긴다.
## 3. 네트워크 토폴로지가 중요한 이유
* 데이터의 전달 방식/경로를 이해할 수 있으며, 병목현상이 생겼을 경우 올바르게 해결할 수 있다.
## 4. 데이터 전송 과정에서의 캡슐화와 비캡슐화란?
* 캡슐화: 데이터 송신 과정에서 각 계층마다 헤더를 붙이는 과정
* 비캡슐과: 데이터 수신 과정에서 각 계층의 헤더를 제거하면서 데이터를 전달받는 과정
## 5. TCP/IP 4계층과 각각의 역할
* 애플리케이션 계층: 서비스가 이용자에게 제공되는 계층
* 전송 계층: 송신자와 수신자 사이에서 데이터가 전달될 때 중계 역할을 하는 계층
* 인터넷 계층: 네트워크 패킷을 지정된 목적지로 전송하기 위한 계층
* 링크 계층: 실질적으로 데이터를 전달하는 계층
## 6. PDU의 뜻과 TCP/IP 4계층에서의 PDU
* PDU(protocol data unit): 각 계층의 데이터 단위
* 애플리케이션 계층: 메시지
* 전송 계층: 세그먼트(TCP), 데이터그램(UDP)
* 인터넷 계층: 패킷
* 링크 계층: 프레임(데이터 링크 계층), 비트(물리 계층)
## 7. OSI 7계층이 TCP/IP 4계층과 어떻게 다른지
1. 애플리케이션 계층이 애플리케이션/프레젠테이션/세션 계층으로 세분화됨
2. 링크 계층이 데이터 링크/물리 계층으로 세분화됨
## 8. HTTP 프로토콜의 특징
1. 헤더를 통한 확장이 쉽고
2. 여러 요청 사이에 연속적인 상태값이 없다. = 무상태성
## 9. TCP와 UDP의 차이점
1. TCP는 패킷의 순서가 보장된다.
2. TCP는 클라이언트와 서버의 연결을 보장한다.
3. TCP가 조금 더 느리다
## 10. TCP의 연결해제과정인 4-way 핸드셰이크에서 TIME_WAIT가 필요한 이유
1. 지연패킷을 받기 위함
2. 다시 연결될 때 올바르게 연결되려면 클라이언트와 서버 모두 CLOSED 상태여야함