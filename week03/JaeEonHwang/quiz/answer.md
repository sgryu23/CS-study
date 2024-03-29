# 1. ARP는 무엇이며 어떤 과정으로 이루어지는지
* ARP: IP 주소로부터 MAC 주소를 구하는 프로토콜
* 과정
	1. 해당 IP 주소에 맞는 MAC 주소를 찾기 위해, 해당 데이터를 '브로드캐스팅'을 통해 연결된 네트워크에 있는 장치에게 모두 보낸다.
	2. 맞는 장치가 있다면, 해당 장치는 보낸 장치에게 유니캐스트로 데이터를 전달해 IP 주소에 맞는 MAC 주소를 찾는다.
# 2. 홉바이홉 통신이란
* 시작 IP 주소부터 시작하여, 다음 IP로 계속해서 이동하는 '라우팅' 과정을 거쳐 패킷이 최종 목적지까지 도달하는 통신
# 3. IPv4와 IPv6의 차이점
1. IPv4
	* 수가 부족하기 때문에 NAT, 서브네팅 등 부수적인 기술이 필요
    * 체크섬 있음
    * 헤더가 가변길이
2. IPv6
	* NAT, 서브네팅이 필요하지 않음
	* IPv4 헤더의 불필요한 필드를 제거하여 보다 빠른 처리 가능
    * 일반적으로는 IPv6가 빠르지만, IPv6가 사용하는 패킷의 크기가 더 크기 때문에, 일부 사용 사례에서는 속도가 느려질 수 있다.
    * 체크섬 없음
    * 헤더가 고정길이
# 4. 클래스 기반 할당 방식이란
* 네트워크 주소를 매기고 그에 따라 네트워크의 크기를 다르게 구분하여 클래스를 할당하는 주소체계
# 5. RTT란
* 왕복 지연 시간, 신호를 전송하고 해당 신호의 수신확인에 걸린 시간
# 6. HTTP 1.0과 비교한 1.1의 차이
1. keep-alive default: 한 번 TCP 연결을 한 후에 계속해서 데이터를 받을 수 있음
2. 하나의 IP에 여러 호스트를 가질 수 있음
3. 파일 다운로드가 중간에 끊겨도 다운로드 재개 요청을 할 수 있게 바뀜
# 7. HTTP 2와 비교한 HTTP 3의 장점
* 초기연결 설정시 지연시간 감소한다.
# 8. HTTPS란
* HTTP와 TLS를 활용해서 암호화된 통신을 가능하게 함
# 9. 각 HTTP 상태코드에 대한 설명
1. 1XX(정보 제공)
2. 2XX(성공)
3. 3XX(리디렉션)
4. 4XX(클라이언트 오류)
5. 5XX(서버 오류)
# 10. CORS란
* HTTP 헤더를 기반으로 브라우저가 다른 오리진에 대한 리소스로드를 허용해주는 매커니즘