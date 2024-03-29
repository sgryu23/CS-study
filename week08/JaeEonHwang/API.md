# API
* Application Programming Interface
* 둘 이상의 컴퓨터 프로그램이 서로 통신하는 방법
* 컴퓨터 사이에 있는 중계 계층
    * 프로토콜, 메서드, 데이터타입 등이 정의되어 있음
## 인터페이스
* 서로 다른 두 새의 시스템, 장치 사이에서 정보나 신호를 주고받는 경우의 접점이나 경계면
## API의 장점
1. 제공자는 서비스의 중요한 부분을 드러내지 않아도 됨
2. 사용자는 해당 서비스가 어떻게 구현되는지 알 필요없이 피룡한 정보만을 받을 수 있음.
3. OPEN API의 경우 앱 개발 프로세스를 단순화시키고 시간과 비용을 절약할 수 있음
4. 내부 프로세스가 수정되었을 때 API가 수정이 안 되게 만들 수 있음. 이를 통해 내부 DB, 서버의 로직이 변경되어도 매번 사용자가 앱을 업데이트하는 일을 줄일 수 있음
5. 제공자는 데이터를 한곳에 모을 수 있음
## API의 종류
* private
    * 내부적으로 사용
    * 주로 해시키를 하드코딩하고 이를 기반으로 서버와 서버간에 통신을 함
    * 비지니스 파트너와도 해시키를 공유해 통신 가능
* public
    * 모든 사람이 사용가능
    * 많은 트래픽을 방지하기 위해 하루 요청 수, 계정당 요청 수 등을 제한함