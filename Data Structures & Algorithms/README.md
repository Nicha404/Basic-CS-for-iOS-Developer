> Data structures & Algorithms in Swift By raywenderlich, Matthijs Hollemans / 인공지능 시대를 위한 컴퓨터 과학 개론 By 정기철 / Swift algorithm club

# 자료 구조 & 알고리즘

## 도대체 자료 구조는 뭐고 알고리즘은 뭘까? 그리고 둘은 왜 항상 같이 다닐까?

## 자료 구조

자료 구조는 영어로 Data Structure, 즉 **데이터들의 구조적 체계**를 말한다. 현대에 들어서 폭발적으로 증가하는 데이터들을 좀 더 효율적으로 그리고 구조적으로 다루기 위해 이러한 방법론이 생겨났다.

예를 들어 우리가 만약 대형마트에 갔다고 생각해보자. 그런데 만약 마트에 물건들이 일정한 체계 없이 아무렇게 진열되어있다고 생각해보자. 식료품과 생활품이 같은 곳에 섞여있거나 장난감과 의류들이 같은 곳에 뒤죽박죽 있다고 해보자. 이러면 우리가 원하는 물건을 제때 찾을 수 있을까? 아마 하루종일 걸려서 겨우 찾을 것이다. 그런데 다행히 우리가 이용하는 마트들은 아주 체계적으로 물품이 정렬되어있다. 마트는 물품(Data)들을 구조적 체계(Structure)를 통해 우리 소비자에게 효율적이고 최적화된 소비 방식을 제공한다. 이것이 우리가 배우는 자료구조의 기본 골자이다. 마트와 마찬가지로 우리가 데이터들을 어떤 구조로 표현하느냐에 따라 프로그램의 성능이 결정된다. 따라서 자료구조란 데이터의 구조적 특성이 잘 살도록 체계적으로 데이터를 저장하고 사용하는 방법을 의미한다.

* 자료구조는 크게 단순 구조, 선형 구조, 비선형 구조로 분류된다.

  * 단순 구조는 정수, 실수, 문자, 문자열 등의 자료형을 말한다.
  * 선형 구조는 데이터들이 한 줄로 늘어선 자료구조이다. 배열, 연결 리스트, 스택, 큐 등이 있다.
  * 비선형 구조는 일렬로 나열할 수 없는 비순차적인 성질을 지닌 데이터들을 표현한 구조이다. 트리와 그래프 등이 있다.

## 알고리즘

알고리즘이란 **어떤 문제를 해결하기 위한 일련의 규정된 절차**이다. 어떤 방법을 단계적 절차를 통해 논리적으로 기술해 놓은 명세서라고 생각하면 된다. 예를 들어 우리가 라면을 끓일 때 우리는 자동적으로 물을 먼저 넣고 그 다음에 면과 스프를 넣는다. 라면을 만든다는 문제를 해결하기 위해 우리는 논리적인 단계적 절차를 통해 이 문제를 해결한다. 라면 뒤에 나와있는 레시피 순서대로 실행하기만 하면 손쉽게 우리가 원하는 라면을 끓일 수 있다. 이것이 알고리즘이다. 그럼 자료 구조와 알고리즘은 어떤 연관이 있는 것일까? 다시 라면을 예로 들자면, 라면을 끓일 때 필요한 재료들은 면, 물, 스프, 계란, 파 등등이 있다. 이것이 바로 자료(Data)이다. 이러한 자료들을 어떠한 구조로 배치해야 라면을 끓이는데 최적의 환경이 될까? 아마 레시피 순서대로 재료들을 위에서부터 아래로 정렬해놓는게 가장 좋을 것이다. 이러한 자료 구조를 통해 라면 알고리즘을 최적의 상태에서 수행하게 된다. 즉, 알고리즘에 알맞은 순서대로 데이터들이 정리된 자료 구조가 알고리즘을 단순하고 효율적으로 작용하게 만든다. 그래서 자료 구조와 알고리즘은 뗄 수 없는 관계이다.

### 알고리즘의 분석 - Big O Notation

알고리즘은 어떤 구조가 가장 효율적인지 분석해 설계해야 한다. 우리는 **복잡도**를 통해 해당 알고리즘이 특정 기준에 따라 얼마나 빠르고 느리게 실행되는지 알 수 있다.

#### 시간 복잡도

시간 복잡도란 알고리즘이 실행되고 종료될 때까지 어느 정도의 시간이 필요한지를 측정하는 방법이다. CPU의 실행 시간을 직접 측정하기는 어려우므로, 알고리즘 실행문이 실행된 횟수(=명령어 수행 횟수)를 파악해 측정한다. 시간 복잡도 간의 차이는 알고리즘의 형태에 따라 처리할 데이터의 양이 많을수록 더 확실하게 구분된다.

#### Big O Notation 

알고리즘의 시간 복잡도를 표현하는 방법 중에 빅 오 표기법이 있다. 이것은 입력된 값의 크기에 따라 알고리즘 처리 횟수가 얼마나 증가하는지 나타낼 때 사용된다. 표기는 O(n)으로 하고 n은 n^2, log n 등등 다양하게 표현될 수 있다. 예를 들어 알고리즘의 수행 속도가 함수 4x^3 + 2x로 표현된다면, 이 알고리즘의 빅 오 표기법은 O(x^3)이다. 최고차항의 x 값만 남기고 나머지 상수와 계수는 없앤다.

O(n): 알고리즘의 수행 횟수가 n만큼 커진다.  
O(n^2): 알고리즘의 수행 횟수가 n^2만큼 커진다.

***

## 배열

배열이란 자료형이 같은 데이터를 순서대로 나열한 뒤 메모리에 연속으로 저장해 만든 자료이다. 배열을 통해 여러 변수들을 따로따로 선언할 필요 없이 한번에 선언할 수 있는 장점이 있다. 변수 한 개의 이름으로 메모리 방을 여러 개 사용하는 구조이다.

And An Array is also a Random Access Collection. Random-access is a trait that data structures can claim if they can handle element retrieval in a constant amount of time. For example, getting "A Specific Data" from the "Array" takes constant time. Again, this performance should not be taken for granted. Other data structures such as linked lists and trees do not have constant time access. 이 방식은 접근 방식에서만 유효하다. 검색, 추가, 삭제에서는 다른 방식 적용된다. 자세한건 알고리즘에서 시간, 공간 복잡도 편에서 알아보자!( 이 글 삭제하고 알고리즘편에 옮기기), 배열 딕셔너리 셋 swfit appretice 참고해서 알고리즘편에 자세하게 서술하기.

배열에서의 데이터 추가나 삭제를 알아보자. 정해진 배열의 중간에 다른 데이터를 추가하고 싶다면 추가하려는 자리 다음의 데이터를 모두 한 칸씩 뒤로 옮겨야 한다. 반대도 삭제할 때도 데이터를 삭제한 뒤 삭제한 데이터 뒤에 있는 데이터들을 앞으로 한 칸씩 옮겨야 한다. 사람들이 줄을 서는데 새치기 하는 사람을 생각해보자! 그래서 추가와 삭제를 자주하면 시간이 오래걸린다. 

```swift
let fruits = ["Apple", "Banana", "Peach"]
```

There are also two other Swift standard library. The dictionary and set.

## Dictionary 

A dictionary is an unordered generic collection that holds key-value pairs. 

```swift
var scores = ["Eric": 9, "Andy": 10]
```

## Set

A set is a container that holds unique values. Imagine it being a bag that allows you to insert items into it, but rejects items that have already been inserted. And a set is also an unordered data set.

```swift
var set: Set<Int> = [1,2,3] // 같은 자료형만 담을 수 있다.
var seet = Set([1,2,3])
```

***

## 연결 리스트

