### MVVM

Model-View-ViewModel (MVVM) is a software design pattern that is structured to separate program logic and user interface controls. MVVM is also known as model-view-binder and was created by Microsoft architects Ken Cooper and John Gossman.

Like many other design patterns, MVVM helps organize code and break programs into modules to make development, updating and reuse of code simpler and faster. The pattern is often used in Windows and web graphics presentation software.

The MVVM pattern is used in Windows Presentation Foundation (WPF), which runs on Microsoft’s .NET. Silverlight, a Microsoft WPF internet equivalent multimedia plug-in, also uses MVVM.
 
The separation of the code in MVVM is divided into View, ViewModel and Model:

View is the collection of visible elements, which also receives user input. This includes user interfaces (UI), animations and text. The content of View is not interacted with directly to change what is presented. -> UI

ViewModel is located between the View and Model layers. This is where the controls for interacting with View are housed, while binding is used to connect the UI elements in View to the controls in ViewModel. -> Manages Model for View

Model houses the logic for the program, which is retrieved by the ViewModel upon its own receipt of input from the user through View. -> Data Point

<p align = "center"><img src = "https://user-images.githubusercontent.com/96713521/155720849-e72e7245-4bcd-4361-8bde-91f163b67c66.png" width = "800" height = "500"></p>

***
 
### JSON parsing

***

### 프레임워크 VS 라이브러리

프레임워크는 뼈대라고 생각하면 된다. 코딩할때 필수적인 코드와 알고리즘 등과 같이 어느 정도의 구조를 ㅈㅔ공해주기 때문에 프로그래머는 이 뼈대 위에서 코드를 작성하여 프로그램을 개발하면 된다.

라이브러리는 특정 기능에 대한 도구나 함수들의 집합이다. 프로그램 기능 수행을 따로 정립해놓은 것을 말한다.

프레임워크가 집이라면 라이브러리는 그 안에 있는 가구들이다. 프레임워크는 특정 공간에 들어간다는 느낌이 강하고 라이브러리는 라이브러리 자체를 프레임워크에 가져가 직접 사용하고 호출하는 용도의 개념이다.

***

### API

***

### 컴파일 과정

소스코드 -> 컴파일러 -> 어셈블리어 -> 어셈블러 -> 기계어

링커 - 기계어로 변환된 여러 소스 코드들을 하나로 연결해줌.

로더 - 실행파일을 메모리에 올림. 

***

### 컴퓨터 부팅 과정

1. ROM에 있는 바이오스 프로그램(바이오스(BIOS; Basic Input/Output System)는 운영 체제 중 가장 기본적인 소프트웨어이자 컴퓨터의 입출력을 처리하는 펌웨어다. 사용자가 컴퓨터를 켜면 시작되는 프로그램으로 주변 장치(하드웨어)와 컴퓨터 운영 체제(소프트웨어) 사이의 데이터의 흐름을 관리한다.)이 실행된다.
2. 부팅 프로그램을 주기억 장치에 로딩한다.
3. 운영체제를 주기억 장치에 로딩한다.
4. 운영체제에 의해 프로그램이 로드된다.
5. 운영체제 명령에 의해 CPU가 프로그램을 실행한다.

***




