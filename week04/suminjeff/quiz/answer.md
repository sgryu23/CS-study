## 1. 운영체제의 역할은 무엇인가?
1. CPU 스케줄링과 프로세스 상태관리
1. 메모리관리
1. 디스크 파일 관리
1. I/O 디바이스 관리

## 2. PCB는 무엇인가?
PCB(Process Control Block)는 운영체제에서 관리하는 프로세스에 대한 메타데이터를 저장한 데이터블록. 커널 스택에 저장되며 각 프로세스가 생성될 때마다 고유의 PCB가 생성이 되고 프로세스가 종료되면 PCB는 제거됨

## 3. 인터럽트란?
인터럽트(interrupt)는 어떤 신호가 들어왔을 때 CPU를 잠깐 정지시키는 것

## 4. 메모리 계층엔 어떤 것이 있죠?
메모리 계층(memory hierarchy)은 레지스터, 캐시, 주기억장치, 보조기억장치로 구성되어 있음

## 5. 프로세스와 스레드의 차이는?
1. 프로세스는 코드, 데이터, 스택, 힙 메모리 영역을 기반으로 작업하는 반면 스레드는 프로세스 내의 스택 메모리를 제외한 다른 메모리 영역을 프로세스 내의 다른 스레드들과 공유하기 때문에 메모리적 이점이 있음
1. 프로세스는 다른 프로세스와 격리되어있기 때문에 서로 통신을 하기 위해서는 IPC를 사용해야 하지만 스레드는 다른 스레드와 서로 격리되어있지 않으므로 그냥 통신할 수 있으므로 프로세스보다 더 빠름
1. 프로세스는 한 프로세스에 문제가 생겨도 다른 프로세스에 영향을 끼치지 않지만 스레드는 격리가 되어있지 않아 한 스레드에 문제가 생기면 다른 스레드에도 영향을 끼쳐 스레드로 이루어져 있는 프로세스에 영향을 줄 수 있음.
1. 프로세스는 생성과 종료에 더 많은 시간이 들며 스레드는 더 적은 시간이 듬

## 6. 프로그램 컴파일 과정을 설명해보세요
1. 전처리 - 소스코드의 주석제거, #include 등 헤더파일을 병합하고 매크로를 치환
2. 컴파일러 - 오류처리, 코드최적화 작업을 하여 어셈블리어로 변환

3. 어셈블러 - 어셈블리어는 목적코드(object code)로 변환됨. 이때 확장자는 운영체제마다 다름 (리눅스: .o)

4. 링커 - 프로그램 내 있는 라이브러리 함수 등과 결합해 실행파일이 만들어짐 .exe, .out이라는 확장자를 갖게 됨

## 7. 메모리 계층에 대해 설명해보세요
메모리 계층(memory hierarchy)은 레지스터, 캐시, 주기억장치, 보조기억장치로 구성되어 있음.
1. 레지스터: CPU 내의 작은 메모리, 휘발성, 속도 가장 빠름, 기억 용량이 가장 적음
1. 캐시: CPU내의 L1, L2 캐시를 지칭합니다. 휘발성, 속도 빠름, 기억 용량이 적음
1. 주기억장치: RAM. 휘발성, 속도 보통, 기억 용량이 보통
1. 보조기억장치: HDD, SSD를 일컬으며 비휘발성, 속도 낮음, 기억 용량이 많음

## 8. 메모리 계층이 존재하는 이유는?
1. 더 빠른 접근과 처리속도가 증가
1. 비용의 효율성
1. 자원의 효율적 사용

## 9. 가상 메모리는 무엇이고 왜 필요하죠?
가상 메모리(virtual memory)는 OS에서 사용되는 메모리 관리 기법의 하나로 컴퓨터가 실제로 이용가능한 메모리 자원(실제주소, physical address)을 추상화하여 이를 사용하는 사용자들에게 매우 큰 메모리로 보이게 만드는 것

필요한 이유
1. 주기억장치의 효율적 관리(스와핑)
1. 메모리 관리의 단순화
1. 메모리 용량 및 안정성 보장

## 10. 스와핑은 무엇인가?
메모리의 당장 사용하지 않는 영역을 하드디스크로 옮기고 하드디스크의 일부분을 “마치 메모리처럼” 불러와 쓰는 것을 스와핑이라고 함