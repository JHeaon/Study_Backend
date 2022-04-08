# OperatingSystem

## OperatingSystem 이란?
OperatingSystem 통칭 OS(운영체제)는 컴퓨터 하드웨어(CPU, I/O)를 관리해주면서 동시에 여러개의 Appliction들이 작동 할 수 있는 환경을 제공하는 Software 이다.

<br>

<p align = "center">
    <img src = "Pictures\OperatingSystem_1.png">
</p>

<br>

## Os가 하는 일
운영체제가 하는  일은 다음과 같다.

* Process management

> Process와 Thread의 Cpu위에서의 작업들을 Scheduling 한다.

> User와 System의 Process를 생성하거나 삭제한다.

* Memory management

> 명령어들이 순서에 맞게 실행되도록 관리한다.

> 모든 Data들이 실행되기 전에 Memory에 올라갈 수 있도록 관리한다.

> Meomory 공간을 할당하고 회수한다.

> 언제 어떤 것이 Memory에 올라갈지 결정한다.

* Storage management
* Protection and Security
  
<br>

본문에서 자주 언급되는 프로그램과 프로세스는 다른 개념이다.
Program은 현재 메모리에 올라온 Process들 중 실행 중인 Process들 말한다. Process는 CPU time, Memory, files, I/O 등 여러 자원을 필요로 한다.

<br>

## Os의 종류
운영체제의 종류는 여러가지 이며 window10, Mac os, dos, unix, linux 등등이 있습니다. 주로 window는 개인용으로 사용하고 unix, linux는 서버용 운영체제로 많이 사용합니다.

<br>

## Os의 목적
운영체제의 목적에는 처리능력 향상, 반환시간 단축, 사용 가능도 향상, 신뢰도 향상 등이 존재한다.

* 처리능력(Throughput) : 일정 시간 내에 시스템이 처리하는 일의 양
* 반환시간(Turn Around Time) : 시스템에 작업을 의뢰한 시간부터 처리가 완료될 때까지 걸린 시간
* 사용가능도(Availability) : 시스템을 사용할 필요가 있을 때 즉시 사용 가능한 정도
* 신뢰도(Reliabilty) : 시스템이 주어진 문제를 정확하게 해결하는 정도


<br>

## Os의 작동방식


<p align = "center">
    <img src = "Pictures\OperatingSystem_2.png">
</p>

컴퓨터의 전원이 켜지면, CPU는 ROM에 저장되어 있는 내용을 먼저 읽는다. ROM(Read Only Memory)은 컴퓨터에 전원이 나가도 사라지지 않는 비휘발성 메모리이며, 계속 보관되어야할 정보들을 저장한다. ROM안에는 POST(Power On Self-Test)와 Boot Loader 가 저장되어 있다.

* POST : 컴퓨터 전원이 켜지면 가장 먼저 실행되는 프로그램으로 컴퓨터에 이상이 있는지 체크하는 프로그램이다. 

* Boot Loader : 하드디스크에 저장되어 있는 Os 프로그램을 가져와서 RAM에 넘겨준다.

컴퓨터가 부팅이 되면 Os 프로그램을 실행한 후에 사용자의 입력 이벤트를 기다린다. 이 이벤트를 
Interrupt(인터럽트)라고 한다. 인터럽트가 발생되면 Os는 해당 명령어의 주소를 기억하고 그 후 인터럽트가 끝나면 해당 주소로 돌아가 다음 명령어를 수행하거나 대기 상태로 돌아간다.

* Interrupt : 인터럽트는 말그대로 방해의 의미를 가지고 있다. CPU가 프로그램을 실행하고 있을 때 입출력 하드웨어 등의 장치에 예외상황(에러라던지, 입력이라던지, 출력이라던지..) 다양한 상황에 대해서 CPU가 처리할 수 있도록 중간에 멈추게 한다. 인터럽트가 발생하면 CPU가 수행중이던 작업은 따로 저장하게 되고(CPU 내부 레지스터나 메인 메모리 등), 인터럽트가 발생한 작업을 먼저 수행하게된다.
  

<br>


## 운영체제의 구조

운영체제는 DOS 시절부터 꾸준히 발전해왔습니다. 기본적으로 하나의 CPU는 하나의 작업만을 처리할 수 있습니다. 따라서 하나의 작업이 끝날 때 까지, 다른 작업은 대김나 하고 있어서 효율이 낮았습니다.

<p align = "center">
    <img src = "Pictures\OperatingSystem_3.png">
</p>

이러한 문제를 해결하기 위해서 생긴 방법론이 멀티 프로그래밍 입니다. 입출력을 수행하고 있는경우, 다른 작업에 CPU를 할당해서 처리하도록 한다. 반대로 CPU가 작업하고 있을 경우, 입출력 장치들을 대기 상태로 만들어서 입출력이 필요한 작업에게 입출력 리소스를 할당한다.

<p align = "center">
    <img src = "Pictures\OperatingSystem_4.png">
</p>

기술이 발전하면서, 프로세서의 처리 속도가 빨라졌는데 반대로 C프로세서의 낭비가 더욱 커졌습니다. 그 이유는 프로세서의 처리 속도의 발전 속도를 입출력 장치가 따라가지 못해서 였습니다. 

<p align = "center">
    <img src = "Pictures\OperatingSystem_5.png">
</p>

이러한 문제를 해결하기 위해서 나온 개념이 멀티 태스킹 입니다. 멀티 태스킹은 각각의 작업들에게 자원 할당 시간을 줘서 그 시간이 지나면 다른 작업들에게 자원을 넘겨주는 형식입니다. 이때 각 자원들에게 시간을 할당하는것이 스케쥴링 이고 Job 스케쥴링과 CPU 스케쥴링이 있습니다. 

<br>

## Os의 원리

운영체제는 interrupt_driven 방식으로 사용자의 요청이 발생하면 운영체제는 적절하게 자원(CPU, I/O, Memory)을 분배하여 그 요청을 처리하는 구조이다.

Interrupt에는 2가지가 존재한다. I/O, 메모리, CPU와 관련된 H/W interrupt 와 프로그램이 실행되다가 발생되는 Errors, 운영체제 Service들의 요청인 System Call과 관련된 S/W interrupt가 있다. S/W interrupt은 잘못 처리하면 한 작업이 자원을 계속 점유하거나, 컴퓨터의 동작을 크게 저해할 수 있기 때문에, 여러 방법을 써서 이를 예방하여야 한다.

그 첫 번째로는 Dual-Mode Exection이다. 운영체제는 기본적으로 사용자에게 인터페이스를 제공하는 User Mode 와 Kernel Mode가 있다. Kenel 에서의 작업은 컴퓨터의 중요한 부분과 해당하는 작업이기에 사용자가 접근하지 못하도록 한다.

일반적으로 사용자가 User Mode 에서 작업을 명령하면 Kernel Mode 에서 이를 처리해야 하는데 그 연결다리 역활이 "Mode-bit" 이다.

운영체제는 User mode에 들어온 명령어와 일치하는 Mode-bit을 가진 Kernel Mode의 명령어를 찾아 Kernel에서 실행한 후, 그 결과를 User-Mode에 넘겨주는데 이러한 행위를 System Call 이라고 한다.

<p align = "center">
    <img src = "Pictures\OperatingSystem_6.png">
</p>

두 번째로는 Timer가있는데 프로세스들에게 유효 시간을 부여하여 그 시간이 지나면 프로세스를 종료 시켜 Error가 발생하여 작업이 멈추더라도 CPU를 계속 점유하는 것을 방지한다.

참고 사이트 :
* https://velog.io/@brian_kim/OS-%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C-%EA%B5%AC%EC%A1%B0%EC%99%80-%EC%9B%90%EB%A6%AC
* https://velog.io/@qkrqudcks7/OS%EC%9D%98-%EC%9E%91%EB%8F%99%EC%9B%90%EB%A6%AC%EB%9E%80