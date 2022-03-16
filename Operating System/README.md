> 쉽게 배우는 운영체제 조성호 지음 / 컴퓨터 과학 개론 정기철 지음

# 운영체제

***

## 운영체제란?

하드웨어와 소프트웨어 자원을 효과적으로 관리하고 운영하기 위한 소프트웨어이다. 하드웨어와 사용자 사이를 연결하는 인터페이스 역할을 한다.
 
운영체제는 크게 커널과 사용자 인터페이스로 구성되어 있다. 커널은 운영체제의 가장 핵심적인 부분으로 일반 사용자가 관여하지 못하는 시스템 레벨 수준의 제어 작업을 수행한다. 메모리를 어떻게 관리할 것인지(메모리 관리), 어느 프로세스를 실행할 것인지(프로세스 관리), 입출력장치를 통해 어떻게 정보를 주고받을 것인지(입출력장치 관리) 등의 일을 처리한다. 사용자 인터페이스는 컴퓨터 사용자가 직접 프로그램을 제어하고 사용할 수 있는 환경을 뜻한다. 운영체제가 커널에 명령을 전달하고 실행 결과를 사용자와 응용 프로그램에 돌려주는 방식이다.

초창기 컴퓨터는 한번에 하나의 프로그램만 실행되는 단일 프로그래밍 방식이었다. 그러나 오늘날은 다중 프로그래밍 시스템(여러 개의 프로그램을 메모리 내에 두고 CPU가 작업을 오가며 동시에 실행하는 기법)이 주로 사용되면서 운영체제의 프로세스 및 메모리 관리 기능이 중요해졌다.

***

## 프로세스

프로그램은 보조기억장치에 있다가 실행 명령을 받으면 메인메모리로 이동해 CPU에 의해 실행된다. 프로세스란 실행 명령을 받아 메인메모리로 올라간 프로그램을 뜻한다. 즉, 컴퓨터상에서 실행 중인 프로그램이다.

다수 프로세스를 관리하는 프로세스 상태도에 관해 알아보자. 

* 준비(Ready) -  생성된 프로세스가 프로세서인 CPU 사용 시간을 할당받기 위해 기다리고 있는 상태. 우선순위가 높은 프로세스를 CPU에 할당하면 실행 상태로 넘어간다. 이는 CPU 스케쥴링에 의해 dispatch 된다.

* 실행(Running) -  CPU에 의해 프로세스가 실행되고 있는 상태. 이 단계에서 다음 단계로 넘가는 루트는 3가지이다.

  * 종료 - 프로세스의 모든 작업이 끝나면 종료된다.

  * 중단 / 방해(Interrupt) - 프로세스의 CPU 할당 시간이 끝났거나 인터럽트가 발생하면 실행 상태의 프로세스는 준비 상태로 넘어간다.

  * 입출력 또는 이벤트 기다림 - 실행 중인 프로세스가 입출력 명령을 마치면 CPU 사용을 반납하고 입출력 종료 신호가 올 때까지 대기 상태로 넘어간다.

* 대기(Blocked) - 입출력 등과 같이 임의의 자원을 요청한 후 할당받을 때까지 기다리는 상태. 대기 중인 프로세스가 필요한 자원을 할당받으면 다시 준비 상태로 넘어간다.

***

## 프로세스 제어 블록

프로세스 제어 블록(PCB)이란 운영체제가 관리하는 자료구조이다. 프로세스 관리에 필요한 거의 모든 정보가 저장되어 있다. 모든 프로세서는 별도의 PCB를 가지며 프로세스가 생성될 때 만들어졌다가 프로세스가 실행을 마치면 삭제된다.

문맥 전환(Context Switching) - 프로세스가 실행 상태를 벗어나면(준비 상태나 대기 상태로 넘어갈 때) 어떻게 될까? 실행 상태인 프로세스가 사용하는 레지스터 값 등은 해당 프로세스의 PCB에 저장되고 새롭게 실행 상태로 넘어온 프로세스의 레지스터 값 등은 CPU에 적재된다. 문맥 전환이 이루어질 때마다 PCB 내 레지스터 값들과 CPU 내 실제 레지스터 값들이 서로 교환된다. 이때 PCB 안에 있는 레지스터 값은 백업본이다. 이 과정을 문맥 전환이라고 한다.

***

## 프로세스 스케줄링(CPU 스케줄링)

프로세스 스케줄링이란 다중 프로그래밍 환경에서 현재 실행 중인 프로세스 다음에 어떤 프로세스를 실행하면 좋을지 결정하는 과정이다. 준비 상태에 있는 여러 프로세스 중 CPU가 실제로 수행할 프로세스를 정하는 것이다. 몇가지 기법들이 있다.

* 순환 순서 기법(Round Robin) - 한 프로세스가 CPU를 계속 차지하고 있는 것이 아니라 여러 프로세스가 돌아가면서 조금씩 차지하는 방법이다. 준비 상태 있는 모든 프로세스에게 CPU 실행 시간을 골고루 나누어 준다. 사용자와의 인터랙션이 빈번한 개인용 컴퓨터에 적합하다.

***

## Concurrency(병행) VS Parallelism(병렬)

**병행**이란 소프트웨어적인 의미를 가지고 있다. 2개 이상의 프로세스가 동시에 실행되는 것을 말한다. 모든 소프트웨어 프로그램은 컴퓨터에서 동작하면서 작업을 수행할 때 결국은 CPU 연산 과정을 거치게 되는데, 만약 CPU를 하나의 프로세스가 점유하고 있다면 다른 프로세스들은 작업을 수행할 수 없다. 따라서 이런 물리적인 상황을 극복하기 위해서 소프트웨어적으로 작업을 번갈아가며 수행하게 함으로서 여러 프로세스를 교차 수행한다. 교차 과정이 매우 짧은 시간에 여러번 수행되므로 마치 여러 작업들이 동시에 실행되는 것 처럼 보인다. 이런 병행 과정에서는 소프트웨어가 교차적으로 실행될 때 각 작업의 상태를 관리하는 것, 적절한 타이밍에 적절한 작업으로 교차되는 것 등이 중요한 포인트가 될 것이다. 병행 프로세스는 다른 프로세스와 협력하면서 실행되므로 서로 영향을 주고받는다. 그래서 수행 과정상 예측할 수 없는 상황이 발생하기도 하는데 이런 오류를 막기 위해 사용하는 개념이 동기화, 임계 영역, 상호 배제이다.

  * Synchronization - 하나의 데이터에 2개 이상의 프로세스가 동시에 접근하면 데이터가 불일치 상태에 놓일 수 있다. 이때, 데이터의 일관성을 유지하려면 병행 프로세스의 처리 순서를 잘 정해야 한다. 이를 프로세스 동기화라고 한다.
  
  * Critical Section - 병행 프로세스의 코드 영역 중 데이터를 읽고 수정하는 등의 작업이 이루어지는 부분을 임계 영역이라고 한다. 하나의 프로세스가 임계 영역 내에 존재하면 다른 프로세스들은 임계 영역에 진입하지 못하도록 제거해야 한다.

  * Mutual Exclusion - 하나의 프로세스가 공유 자원을 사용하는 동안 다른 프로세스가 자원을 사용하지 못하게 막는 것이다.

**병렬**은 기계적인 의미를 가지고 있다. 반도체 기술이 진화하면서 우리는 멀티 코어 CPU가 당연한 수준의 시대에 살고있다. 이런 상황에서 병렬(Parallel)이란 멀티 코어 환경에서 여러개의 코어에 작업을 각 코어로 분산시켜서 동시에 작업하는 것을 의미하며 실제 물리적으로 여러 작업이 동시에 실행되는 것이다. 당연히 멀티 코어 환경의 병렬 작업은 작업을 어떻게 분산시키느냐가 매우 중요한 포인트이다.

출처: https://jungseob86.tistory.com/13 [Random Access Memories]

***

## 교착 상태(Deadlock)

교착 상태란 프로세스가 자원을 얻지 못해 다음 처리를 하지 못하는 상태로 시스템적으로 한정된 자원을 여러 곳에서 사용하려 할 때 발생한다.

## 임계 영역

프로세스 간에 공유자원을 접근하는 데 있어서 문제가 발생하지 않도록 한 번에 하나의 프로세스만 이용하게끔 보장해줘야 하는 영역.

***

## 메모리 관리

다중 프로그래밍 환경의 메인메모리 관리 기법으로는 고정 분할 메모리 관리와 가변 분할 메모리 관리가 있다. 고정 분할 메모리 관리는 메인메모리를 고정된 크기로 미리 나눠 두었다가 실행 중인 프로세스에 할당하는 기법이다. 그러나 가변 분할 메모리 관리는 고정된 분할 공간의 경계를 없애고 작업량이 맞는 공간을 할당한다. 작업이 완료되면 빈 공간은 다시 모아 관리한다. 사용자 프로그램이 실행되면 그때그때 알맞은 크기로 공간을 분할해 할당한다고 보면 된다.

### Virtual Memory

Virtual memory is a memory management technique where secondary memory can be used as if it were a part of the main memory. Virtual memory is a common technique used in a computer's operating system (OS).

Virtual memory uses both hardware and software to enable a computer to compensate for physical memory shortages, temporarily transferring data from random access memory (RAM) to disk storage. Mapping chunks of memory to disk files enables a computer to treat secondary memory as though it were main memory.

Today, most personal computers (PCs) come with at least 8 GB (gigabytes) of RAM. But, sometimes, this is not enough to run several programs at one time. This is where virtual memory comes in. Virtual memory frees up RAM by swapping data that has not been used recently over to a storage device, such as a hard drive or solid-state drive (SSD).

Virtual memory is important for improving system performance, multitasking and using large programs. However, users should not overly rely on virtual memory, since it is considerably slower than RAM. If the OS has to swap data between virtual memory and RAM too often, the computer will begin to slow down -- this is called thrashing.

Virtual memory was developed at a time when physical memory -- also referenced as RAM -- was expensive. Computers have a finite amount of RAM, so memory will eventually run out when multiple programs run at the same time. A system using virtual memory uses a section of the hard drive to emulate RAM. With virtual memory, a system can load larger or multiple programs running at the same time, enabling each one to operate as if it has more space, without having to purchase more RAM.

쉽게 말하면 램이 부족할 때 디스크의 일부 용량을 램처럼 사용하는 것이다.

***

> Seogeurim/CS Study

# 질문 정리

<details><summary>프로그램과 프로세스의 차이는 무엇인가?</summary>
프로그램은 작업을 위해 실행할 수 있는 파일의 단위를 말하고 프로세스는 프로그램이 메모리에 적재되어 실행되고있는 상태를 말한다.
</details>
 
<details><summary>프로세스와 스레드의 차이는?</summary>
스레드는 프로세스를 구성하는 실행 단위이다. 하나의 프로세스 안에서도 여러가지 일을 동시에 할 수 있다. 예를 들어 워드에서 글자를 치는 동시에 자동 저장을 하고 맞춤법 검사를 한다. 이 모든 작업들은 각각의 스레드에 의해 이루어진다. 프로세스와 달리 스레드는 코드, 데이터, 힙 영역을 통해 프로세스 자원을 공유할 수 있다. 또한 스레드는 자원을 공유하기 때문에 한 스레드에서 오류가 발생하면 같은 프로세스 내의 스레드 모두가 종료된다.
</details>

<details><summary>프로세스가 도중에 중지되는 경우, 그 원인과 다시 실행할 수 있는 방법은?</summary>
원인: 인터럽트 혹은 시스템 콜 등에 의해 프로세스가 중지될 수 있다.
 
다시 실행할 수 있는 방법: PCB 안에 해당 프로세스의 정보(프로그램카운터와 같은 실행 정보 등)가 저장되어 있기 때문에 추후에 실행 가능한 상태가 되면 PCB를 통해 다시 실행할 수 있다.
</details>

<details><summary>프로세스의 힙, 스택 영역에는 어떤 정보가 있는가?</summary>
힙 영역: 동적 할당되는 모든 요소들
 
스택 영역: 매개변수, 로컬변수, 리턴값, 복귀주소 등
</details>

<details><summary>스택을 스레드마다 독립적으로 할당하는 이유는?</summary>
각 스레드가 독립적인 실행 흐름을 갖기 위해서는 독립적인 함수 호출이 보장되어야 하기 때문이다.
</details>

<details><summary>스레드와 멀티 스레드의 차이에 대하여 설명하고, 멀티 스레드의 장단점을 설명하시오</summary>
스레드: 할당 받은 자원을 이용한 프로세스의 실행 흐름의 단위이다.
 
멀티 스레드: 한 프로세스 내에서 이러한 스레드가 여러 개 동작하는 방식을 의미한다.
 
멀티스레드의 장점: 프로세스를 여러개 두는 방식에 비해 컨텍스트 스위칭 비용이 적게 들며 응답 시간이 빠르다는 장점이 있다.
 
멀티스레드의 단점: 같은 프로세스 내의 자원을 다른 스레드들과 공유하므로 동기화 문제를 고려해야 한다. 또한 프로세스가 종료되면 내부 스레드들 역시 모두 종료되므로 한 스레드가 프로세스를 의도치 않게 종료했을 경우 나머지 스레드들도 모두 종료될 수 있다는 단점이 있다.
</details>

<details><summary>멀티 스레드와 멀티 프로세스의 차이는?</summary>
멀티 스레드: 적은 메모리 공간 차지, context switch 빠름. 하지만 동기화 문제가 있고 하나의 스레드가 종료되면 전체 스레드가 종료될 수 있음.
 
멀티 프로세스: 하나의 프로세스가 죽더라도 다른 프로세스에는 영향을 끼치지 않음. 하지만 많은 메모리 공간을 차지하고 CPU 점유 시간을 많이 차지함.
</details>

<details><summary>Context Switching에 대하여 설명하시오</summary>
프로세스는 CPU를 할당받은 상태의 실행 중인 프로그램이다. 현재 CPU를 할당받아 실행중인 프로세스 A와 대기중인 프로세스 B가 있다고 가정했을 때, A 프로세스에서 B 프로세스로 CPU 사용/제어권이 이전되는 것을 Context Switching 이라고한다.
</details>

***

<details><summary>스케쥴링이 왜 필요한가?</summary>
한정적인 메모리(자원)를 효율적으로 관리하기 위해, 공정성을 주기 위해 필요하다.
</details>

<details><summary>스케줄러와 CPU 스케줄러의 차이에 대하여 설명하시오.</summary>
스케줄러(=Job Scehduler, 장기 스케줄러)는 디스크와 메모리 간 스케줄링을 담당한다.

CPU 스케쥴러(= 단기 스케줄러)는 메모리와 CPU 간 스케줄링을 담당한다.
</details>

<details><summary>중기 스케쥴러에서 suspended 상태와 blocked 상태의 다른점은 무엇인가?</summary>
blocked 상태는 다른 I/O 작업을 기다리는 상태이기 때문에 스스로 ready queue(CPU 할당을 대기 중인 프로세스)로 돌아갈수 있지만, suspended는 외부적인 이유로 유예됐기 때문에 스스로 돌아갈 수 없다.
</details>

<details><summary>FCFS(first come first serve) 스케줄링을 개선한 스케줄링 방식에 대하여 설명하시오.</summary>
FCFS는 먼저 도착한 프로세스에게 CPU를 할당하는 기법이다. 하지만 먼저 도착한 프로세스가 실행 시간이 긴 경우 나중에 도착한 프로세스들의 대기 시간이 길어지는 Convoy Effect(Convoy Effect is phenomenon associated with the First Come First Serve (FCFS) algorithm, in which the whole Operating System slows down due to few slow processes)라는 문제점을 가지고 있다.
이를 개선한 SJF(Shortest Job First) 기법이 있다.
</details>
 
<details><summary>Round Robin 스케줄링 방식에서 time quantum 설정에 따른 결과를 설명하시오.</summary>
타임 퀀텀이란: 프로세스마다 얼만큼의 시간 배분을 해줄건지 정하는 것.
타임퀀텀이 긴 경우: 타임퀀텀이 프로세스의 실행시간과 비슷해진다면 FCFS랑 다를 바 없어진다.

타임퀀텀이 짧은 경우: 타임퀀텀이 짧아 Context Switching이 자주 일어나게 되어 오버헤드가 발생한다.
</details>

<details><summary>오버 헤드란?</summary>
프로그램의 실행 흐름 도중에 동떨어진 위치의 코드를 실행시켜야 할 때, 추가적으로 시간, 메모리, 자원이 사용되는 현상을 오버헤드라 한다.
</details>

***

<details><summary>동기와 비동기의 차이는?</summary>
동기는 요청이 들어온 순서에 맞게 하나씩 처리하는 것.
 
비동기는 하나의 요청이 끝나기도 전에 다른 요청을 동시에 처리할 수 있는 것.
</details>

<details><summary>Blocking과 Non Blocking의 차이</summary>
Blocking은 자신의 작업을 진행하다가 다른 주체의 작업이 시작되면 다른 작업이 끝날 때까지 기다렸다가 자신의 작업을 시작하는 것.
 
Non Blocking은 다른 주체의 작업에 관련 없이 자신의 작업을 하는 것.
</details>

***

<details><summary>Race Condition(경쟁 상태)이란?</summary>
Race Condition이란 두 개 이상의 concurrent한 프로세스 혹은 스레드가 공유 자원에 접근하려고 할 때 동기화 메커니즘 없이 접근하여 그 순서에 따라 결과가 달라지는 문제를 말합니다. 간단한 예시로는 계좌 잔고 관리를 설명해보겠습니다. 계좌의 잔고라는 공유 자원 데이터를 확인하고 출금하는 연산을 수행할 때, 동기화가 이루어지지 않으면 잔고에서 이중으로 출금되는 오류가 발생할 수 있습니다.
</details>

<details><summary>여러 프로세스가 데이터를 공유하며 수행될 때, 각 프로세스에서 공유 데이터를 접근하는 프로그램 코드는? 그리고 그에 대한 간단한 설명은?</summary>
임계 영역입니다. 임계 영역은 공유 자원을 동시에 접근하는 작업을 실행하는 코드 영역을 칭합니다. 공유 자원을 여러 프로세스가 동시에 접근할 때 잘못된 결과를 만들 수 있기 때문에 한 프로세스가 임계 구역을 수행할 때는 다른 프로세스가 접근하지 못하도록 해야 합니다.
</details>

<details><summary>임계 영역을 프로세스들이 같이 쓸 수 있는 전제 조건을 설명하시오.</summary>
 
임계 영역을 프로세스들이 같이 쓸 수 있는 전제 조건으로는 Mutual Exclusion, Progress, Bounded Waiting 3가지가 있습니다.
 
상호 배제 (Mutual Exclusion) : 어떤 task가 임계 영역을 사용 중이면 다른 task는 사용이 불가능합니다. 
 
진행 (Progress) : 현재 임계 영역을 사용 중인 task가 없고, 들어가길 원하는 task가 있다면 바로 들여보냅니다.
 
한정된 대기 (Bounded Waiting) : 프로세스가 진입 가능한 횟수에는 제한이 있어서 특정한 한 프로세스만 계속 진입하는 것을 방지합니다.
</details>

<details><summary>Thread-safe란?</summary>
멀티 스레드 환경에서 여러 스레드가 동시에 공유 자원에 접근할 때 의도한대로 동작한걸 말한다. Thread-safe하기 위해서는 공유 자원에 접근하는 임계 영역을 Mutex, Semaphore 등의 동기화 기법으로 제어해야한다.
</details>

<details><summary>Reentrancy와 Thread-safe와의 차이점</summary>
Reentrant는 재진입성이라는 의미로, Reentrant 함수는 여러 스레드가 동시에 접근해도 언제나 같은 실행 결과를 반환합니다. 이를 만족하기 위해서 함수 내에서는 공유 자원을 사용하지 않고, 호출 시 제공된 매개변수 만으로 동작하면 됩니다. 따라서 Reentrant하다면 Thread-safe하지만 그 역은 성립하지 않습니다.
</details>

<details><summary>Mutex Lock과 Semaphore의 차이</summary>
참고: https://www.youtube.com/watch?v=oazGbhBCOfU
</details>

<details><summary>CPU와 가까운 순으로 메모리 구조의 순서를 말하시오</summary> 
레지스터 → 캐시 메모리 → 메인 메모리 → 보조기억장치 → 외부기억장치의 구조를 가집니다. CPU로부터 멀어질수록 사이즈는 커지고, 가격은 저렴해지며, 접근 속도는 느려집니다.
</details>

<details><summary>메모리 관리는 무엇이고 왜 하는 것인가</summary>
시스템이 실행될 때 여러 프로세스가 실행이 되는데, 각 프로세스가 실행되기 위해서는 메모리를 필요로 한다. 그러나 메모리는 한정되어 있다. 실행되어야 하는 모든 프로세스가 필요한 시기에 적절하게 메모리의 할당을 받을 수 있도록 메모리 관리가 필요하다.
</details>

<details><summary>RAM을 늘리면 어떻게 되는가</summary>
RAM을 늘린다는 것은 메인 메모리의 공간을 늘린다는 것이다. 그만큼 한 번에 메모리에 적재시킨 후 처리할 수 있는 프로세스의 양이 많아진다. 따라서 컴퓨터의 속도가 빨라진다.
</details>

<details><summary>만약 16GB의 메인메모리를 가지고 있고, 운영체제의 용량이 16GB라고 해보자. 그럼 이 컴퓨터는 운영체제 외에 다른 프로그램은 실행할 수 없는 것인가?</summary>
운영체제의 용량이 16GB라고해서 16GB 전체를 메모리에 적재하지 않는다. 지금 당장 필요한 부분만 메모리에 적재후 실행한다. 프로그램의 용량이 16GB라고해서 꼭 그 용량만큼의 공간이 필요한 것은 아니다.
</details>

<details><summary>내부 단편화와 외부 단편화에 대한 설명</summary>
 
내부 단편화 - 메모리를 할당할 때 프로세스가 필요한 양보다 더 큰 메모리가 할당되어서 프로세스에서 사용하는 메모리 공간이 낭비 되는 현상.
 
외부 단편화 - 메모리의 할당 및 해제 작업 반복으로 잉여 메모리가 중간중간에 생겨 사용하지 않는 메모리가 존재하여 총 메모리 공간은 충분하지만 실제로 할당할 수 없는 상황. 즉, 여유 공간이 여러 조각으로 나뉘는 현상. (프로세스 바깥쪽에 조각이 발생하여 외부 단편화라고 불림). 이러한 문제는 압축 기술(시간이 오래 걸림)과 페이징 기법 등을 통하여 해결한다. 페이징 기법이란 메모리를 일정한 크기인 페이지로 분배한 후 프로세스가 요구하는 용량만큼 메모리 조각을 할당하는걸 말한다.
</details>

***




 
 
 
 
