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

알고리즘이란 **어떤 문제를 해결하기 위한 일련의 규정된 절차**이다. 어떤 방법을 단계적 절차를 통해 논리적으로 기술해 놓은 명세서라고 생각하면 된다(어떤 작업을 수행하기 위한 명령어를 입력받아 결과를 출력해 내는 과정). 예를 들어 우리가 라면을 끓일 때 우리는 자동적으로 물을 먼저 넣고 그 다음에 면과 스프를 넣는다. 라면을 만든다는 문제를 해결하기 위해 우리는 논리적인 단계적 절차를 통해 이 문제를 해결한다. 라면 뒤에 나와있는 레시피 순서대로 실행하기만 하면 손쉽게 우리가 원하는 라면을 끓일 수 있다. 이것이 알고리즘이다. 그럼 자료 구조와 알고리즘은 어떤 연관이 있는 것일까? 다시 라면을 예로 들자면, 라면을 끓일 때 필요한 재료들은 면, 물, 스프, 계란, 파 등등이 있다. 이것이 바로 자료(Data)이다. 이러한 자료들을 어떠한 구조로 배치해야 라면을 끓이는데 최적의 환경이 될까? 아마 레시피 순서대로 재료들을 위에서부터 아래로 정렬해놓는게 가장 좋을 것이다. 이러한 자료 구조를 통해 라면 알고리즘을 최적의 상태에서 수행하게 된다. 즉, 알고리즘에 알맞은 순서대로 데이터들이 정리된 자료 구조가 알고리즘을 단순하고 효율적으로 작용하게 만든다. 그래서 자료 구조와 알고리즘은 뗄 수 없는 관계이다.

### 알고리즘의 분석 

알고리즘은 어떤 구조가 가장 효율적인지 분석해 설계해야 한다. 우리는 **복잡도**를 통해 해당 알고리즘이 특정 기준에 따라 얼마나 빠르고 느리게 실행되는지 알 수 있다.

### 시간 복잡도 

시간 복잡도란 알고리즘이 실행되고 종료될 때까지 어느 정도의 시간이 필요한지를 측정하는 방법이다. CPU의 실행 시간을 직접 측정하기는 어려우므로, 알고리즘 실행문이 실행된 횟수(=명령어 수행 횟수)를 파악해 측정한다. 시간 복잡도 간의 차이는 알고리즘의 형태에 따라 처리할 데이터의 양이 많을수록 더 확실하게 구분된다.

### Big O Notation 

알고리즘의 시간 복잡도를 표현하는 방법 중에 빅 오 표기법이 있다. 이것은 입력된 값의 크기에 따라 알고리즘 처리 횟수가 얼마나 증가하는지 나타낼 때 사용된다. 표기는 O(n)으로 하고 n은 n^2, log n 등등 다양하게 표현될 수 있다. 예를 들어 알고리즘의 수행 속도가 함수 4x^3 + 2x로 표현된다면, 이 알고리즘의 빅 오 표기법은 O(x^3)이다. 최고차항의 x 값만 남기고 나머지 상수와 계수는 없앤다.

ex) O(n): 알고리즘의 수행 횟수가 n만큼 커진다.  
    O(n^2): 알고리즘의 수행 횟수가 n^2만큼 커진다.
    
### Big O Notation의 여러가지 표현 방법들

#### Constant time

  A constant time algorithm is one that has the same running time regardless of the size of the input. As input data increases, the amount of time the algorithm takes does not change. The Big O notation for constant time is O(1).

#### Linear time

Linear time complexity is usually the easiest to understand. As the amount of data increases, the running time increases by the same amount. The Big O notation    for linear time is O(n).

#### Quadratic time

This time complexity refers to an algorithm that takes time proportional to the square of the input size. As the size of the input data increases, the amount of time it takes for the algorithm to run increases drastically. The Big O notation for quadratic time is O(n^2). (주로 for문 안의 for문, 선택 정렬, 버블 정렬)

#### Logarithmic time

데이터(정렬돼있는 데이터)의 양을 매번 절반으로 분할해서 처리하는 알고리즘은 통상적으로 이 그룹에 속한다. As input data increases, the time it takes to execute the algorithm increases at a slow rate. The Big O notation for this is O(log n).

#### Quasilinear time

Another common time complexity you’ll encounter is quasilinear time. Quasilinear time algorithms perform worse than linear time but dramatically better than quadratic time. They are among the most common algorithms you’ll deal with. An example of a quasilinear time algorithm is Swift’s sort method. The Big-O notation for quasilinear time complexity is O(n log n) which is a multiplication of linear and logarithmic time. So quasilinear fits between logarithmic and linear time; it is worse than linear time but still better than many of the other complexities that you’ll see next. The quasilinear time complexity shares a similar curve with quadratic time but doesn’t go up quite as fast so is more resilient to large data sets.

![Time-Complexity](https://user-images.githubusercontent.com/96713521/148945963-ff8a10f8-e5ae-4d5f-87e7-269471f14713.png)

***

# 여러가지 자료 구조들

## Array

An array is an ordered collection of values of the same type. The elements in the array are zero-indexed, which means the index of the first element is 0, the index of the second element is 1, and so on. Knowing this, you can determine that the last element’s index is the number of values in the array minus one.

```swift
let array = [1, 2, 3, 4]
```

```swift
let array: [String] = [] 
```

### Running time for array operations 

Arrays are stored as a contiguous block in memory. That means if you have ten elements in an array, the ten values are all stored one next to the other. With that in mind, here’s the performance cost of various array operations

* Accessing elements: The cost of fetching an element is cheap, meaning it happens in a fixed or constant time. Sometimes this is written O(1). And it's random access.

* Inserting elements: The complexity of adding an element depends on the position in which you add the new element.

  * If you add to the beginning of the array, Swift requires time proportional to the size of the array because it has to shift all of the elements over by one to make room. This is called linear time and sometimes written O(n).

  * Likewise, if you add to the middle of the array, all values from that index on need to be shifted over. Doing so will require n/2 operations; therefore, the running time is still linear with the size of the array or O(n).

  * If you add to the end of the array using append and there’s room, it will take O(1). If there isn’t room, Swift will need to make space somewhere else and copy the entire array over before adding the new element, which will take O(n). The average case is O(1) because arrays are not full most of the time.

* Deleting elements: Deleting an element leaves a gap where the removed element was. All elements in the array must be sequential, so this gap needs to be closed by shifting elements forward. The complexity is similar to inserting elements: If you’re removing an element from the end, it’s an O(1) operation. Otherwise, the complexity is O(n).

* Searching for an element: If the element you’re searching for is the first element in the array, then the search will end after a single operation. If the element doesn’t exist, you need to perform N operations until you realize that the element is not found. On average, searching for an element will take n/2(평균적으로 중간값이라는 뜻) operations; therefore, searching has a complexity of O(n). (그러나 검색은 지금처럼 선형검색도 있지만 이진검색도 있다. 이진검색은 반드시 배열이 정렬되어있을때만 사용가능하다. 이때 이진검색의 시간복잡도는 O(log n)이다.)

There are also two other Swift standard libraries. The dictionary and set.

***

## Dictionary 

A dictionary is an **unordered** collection of pairs, where each pair comprises a key and a value. As shown in the code below, keys are unique. The same key can’t appear twice in a dictionary, but different keys may point to the same value. All keys must be of the same type, and all values must be of the same type.

```swift
var scores = ["Eric": 9, "Andy": 10]
var pairs: [String: Int] = [:]
var pairs2 = [:]
```

### Running time for dictionary operations

* Accessing elements: Getting the value for a key is a constant time operation, or O(1).

* Inserting elements: To insert an element, the dictionary needs to calculate the hash value of the key then store data based on that hash. These are all O(1) operations.

* Deleting elements: Again, the dictionary needs to calculate the hash value to know exactly where to find the element and then remove it. This is also an O(1) operation.

* Searching for an element: As mentioned above, accessing an element has constant running time, so the complexity for searching is also O(1).

***
 
## Set

A set is a container that holds unique values. Imagine it being a bag that allows you to insert items into it, but rejects items that have already been inserted. And a set is also an unordered data set.

```swift
var set: Set<Int> = [1,2,3] // 같은 자료형만 담을 수 있다.
var seet = Set([1,2,3])
```

### Running time for set operations

Sets have a very similar implementation to dictionaries, and they also require the elements to be hashable. The running time of all the operations is identical to those of dictionaries.

***

## 연결 리스트

배열은 논리적인 순서와 물리적인 순서가 같아서 데이터 위치를 찾기는 쉽지만, 추가나 삭제시 나머지 데이터들을 추가로 옮겨야 해 비효율적이다. 이러한 문제를 개선한 데이터 표현 방법이 연결 리스트이다. 연결 리스트는 연속된 물리적 순서에 따라 데이터 순서를 표현하는 것이 아니라, 각 데이터에 저장된 다음 데이터의 주소에 따라 순서가 연결되는 방식이다. 그래서 배열과 달리 데이터의 논리적인 순서와 물리적인 순서가 일치하지 않아도 된다. 연결 리스트는 데이터(데이터 필드)와 다음에 이어질 데이터에 대한 주소(링크 필드)가 합쳐진 노드로 구성되어있다. 

* 연결 리스트는 단순 연결 리스트, 원형 연결 리스트, 이중 연결 리스트로 분류된다.

  * 단순 연결 리스트는 아래 사진과 같이 노드의 링크 필드가 하나이며, 링크 필드는 다음 노드와 연결되는 가장 기본 구조이다.
  * 원형 연결 리스트는 단순 연결 리스트의 마지막 노드가 리스트의 첫 번째 노드를 가리키게 하여 리스트 구조를 원형으로 만든 구조이다.
  * 이중 연결 리스트는 선행 노드로 접근하기 어려운 단순 연결 리스트와 원형 연결 리스트의 단점을 보완한 구조이다. 양쪽 모두 순회할 수 있도록 링크가 데이터 양쪽에 있어서 이중 연결 리스트이다.

<p align = "center"><img src = "https://user-images.githubusercontent.com/96713521/150917662-5420e93f-7099-4b68-a5a3-0059b813ea04.png" width = "800" height = "500"></p>

**<데이터 구조의 항목 A가 다른 항목 B의 어드레스를 보유하고 있을 때 A를 B의 포인터라고 한다.>**

### 연결 리스트에서의 데이터 추가 및 삭제

단순 연결 리스트에서 새로운 항목을 추가할때는 새로운 데이터를 추가하고 기존 노드에서 링크 필드에 연결된 화살표가 가리키는 위치만 적절히 수정해주면 된다. 삭제할때도 마찬가지로 링크 필드가 삭제하고자 하는 데이터를 가리키지 않으면 된다.

### 배열과 연결 리스트 비교

연결 리스트는 검색 기능이 약하다. 배열은 인덱스를 알면 위치와 상관없이 데이터를 금방 찾지만 연결 리스트는 첫 노드부터 순서대로 찾아가야 되기 때문이다. 하지만 연결 리스트는 정적인 메모리(방을 미리 만들어놓고 사용)를 사용하는 배열과 달리 노드 단위로 메모리를 할당받을 수 있어 공간을 보다 효율적으로 사용할 수 있다. 무엇보다, 연결 리스트는 배열보다 데이터를 추가하고 삭제하는 방법이 빠르고 쉽다.

### Running time for linked list

Most operations on a linked list have O(n) time, so linked lists are generally slower than arrays. However, they are also much more flexible -- rather than having to copy large chunks of memory around as with an array, many operations on a linked list just require you to change a few pointers. The reason for the O(n) time is that you can't simply write list[2] to access node 2 from the list. If you don't have a reference to that node already, you have to start at the head and work your way down to that node by following the next pointers (or start at the tail and work your way back using the previous pointers). But once you have a reference to a node, operations like insertion and deletion are really quick. It's just that finding the node is slow. This means that when you're dealing with a linked list, you should insert new items at the front whenever possible. That is an O(1) operation. Likewise for inserting at the back if you're keeping track of the tail pointer.

***

## 스택

스택은 박스를 수직으로 쌓아올린 형태로 생각하면 된다. 스택 자료 구조는 맨 위에서만 데이터의 추가, 삭제 작업이 가능하다. 구조의 중간에서는 데이터를 추가하거나 삭제하지 못한다. 같은 크기의 데이터를 정해진 방향으로만 쌓을 수 있고 톱을 통해서만 접근할 수 있다. 톱을 통해 들어온 데이터는 아래에서 위로 차곡차곡 쌓인다. 삭제할 때도 마찬가지이다. 정리하면 스택은 가장 마지막에 삽입된 데이터가 가장 먼저 삭제된다는 Last In First Out 구조로 운영된다.

<p align = "center"><img src = "https://user-images.githubusercontent.com/96713521/151124589-a1517169-6c5d-44d4-bbb9-05df2660b533.jpeg"></p>

### Running time for stack

삭제나 삽입시 맨 위에 데이터를 삽입하거나 삭제하기 때문에 시간복잡도는 늘 O(1) 의 시간복잡도를 가진다. 하지만 특정 데이터를 찾을 때는 특정 데이터를 찾을 때까지 수행을 해야하므로 O(n)의 시간 복잡도를 가지게 된다.

*** 

## 큐
 
큐는 스택의 반대 개념이다. 매표소에 줄 서 있는 사람들의 모습을 생각해보자. 먼저 삽입된 데이터가 먼저 삭제되는 First In First Out 구조로 운영된다.

<p align = "center"><img src = "https://user-images.githubusercontent.com/96713521/151283217-7c6db0b7-0847-40c4-b931-0a661b45875c.png" width = "800" height = "500"></p>

### Running time for queue

Enqueue is an O(1) append operation. But dequeue is O(n) operation because removing an item from the front of the queue can be inefficient, as removal causes all elements to shift up by one.

***

## 덱

덱(Deque)이란 Double-Ended Queue의 줄임말이다.
즉, 앞쪽 front와 뒤쪽 rear에서 모두 삽입과 삭제가 가능한 큐를 의미한다.

***

## Non-linear data structure

앞서 배운 배열, 연결 리스트, 스택, 큐는 선형 자료구조이고 이번 섹션에서 배울 트리와 그래프는 비선형 자료 구조이다.

### 트리(그래프 안에 트리가 포함됨)

트리는 나무를 뒤집어 놓은 모습의 자료구조이다. 1:n 관계인 비선형 구조로 놓여 있다. 또한 계층 관계로 만들어져 계층형 자료구조이기도 하다. 트리의 각 원들은 노드라 하고, 노드와 노드를 연결한 선은 간선이라고 한다. 가장 위에 있는 정보부터 레벨 정보가 시작되고 한 층 내려갈수록 레벨이 올라간다. 트리 맨 위에 위치한 노드는 루트 노드라 부르며 가장 아래에 위치한 노드들(더 이상 자식이 없는 노드)은 단말 노드 또는 잎 노드라 부른다. 트리의 구조를 제한해 정의하면 연산은 더욱 단순하고 명확해진다. 이진 트리는 노드의 자식 노드를 2개 이하로 정해 놓은 것이다.

<p align = "center"><img src = "https://user-images.githubusercontent.com/96713521/151296463-5cb9045c-1991-436f-8a62-40ddc318fa27.png" width = "800" height = "500"></p>
 
### 그래프

그래프는 연결된 데이터들의 n:n 관계를 표현한 자료구조이다. 

<p align = "center"><img src = "https://user-images.githubusercontent.com/96713521/151311203-103bca3e-457e-4410-bc5e-56ce3c40c60d.jpg" width = "800" height = "500"></p>

https://www.youtube.com/watch?v=fVcKN42YXXI

***

# 여러가지 알고리즘들

## 정렬(Sort) 알고리즘

정렬이란 데이터를 일정한 규칙에 따라 재배열하는 것이다. 작은 것에서 큰 것 순서대로 정리하는 것, 오늘 할 일을 순서대로 정리하는 것, 도서관에서 책을 번호대로 정리하는 것 등이 정렬 알고리즘의 예라고 할 수 있다. **<키(key): 데이터를 정렬하는 데 기준이 되는 특정 값. 컴퓨터 아이콘을 정렬할 때 '크기'를 기준으로 정렬하면 크기가 키가 된다.>**

### 선택 정렬

선택 정렬은 아무렇게나 놓인 데이터 중 가장 작은 데이터의 위치를 가장 앞에 있는 데이터 위치와 바꾸는 알고리즘이다.(오름차순 기준)

### 버블 정렬

버블 정렬은 나란히 놓인 데이터 두 개 중 숫자가 큰 데이터를 뒤로 보내며 정렬하는 방식이다. 왼쪽에 놓인 데이터에서부터 시작하며, 크기순으로 자리를 서로 바꾼다.(오름차순 기준)

### 삽입 정렬

삽입 정렬은 아직 정렬되지 않은 데이터를 이미 정렬된 부분 중 한 곳에 삽입해 정렬하는 방식이다.

### 병합 정렬

병합 정렬은 정렬된 여러 개의 집합을 병합하여 하나의 정렬된 집합으로 만드는 정렬 방법이다. 
병합 정렬은 과정을 아래 3가지로 나눌 수 있다.

* 분할: 자료들을 부분집합으로 분할한다.(전체 자료의 집합이 최소 원소의 부분집합이 될 때까지 분할 작업을 반복한다.)
 
* 정복: 부분집합에 있는 원소를 정렬한다.
 
* 결합: 정렬된 부분집합들을 하나의 집합으로 정렬하여 결합한다.

병합 정렬의 시간복잡도는 분할 단계에선 1/2씩 데이터의 개수가 줄어들기 때문에 O(log n)단계로 이루어지지만 정복 및 결합 단계에서는 데이터의 개수 총합 n개와 log n개의 병합 단계가 실행되어 평균적인 시간 복잡도는 O(n log n)이 된다.

***

## 검색 알고리즘

검색이란 특정 데이터 집합에서 어떤 조건이나 성질을 만족하는 데이터를 찾는 것이다. 

### 순차 검색

순차 검색은 일렬로 나열된 데이터를 처음부터 끝까지 순서대로 검색하는 방법이다. 배열이나 연결 리스트로 구현된 선형 자료구조에서 자주 쓰인다. 순서대로 데이터를 비교하며 원하는 항목을 찾는다. 정렬되어 있지 않은 데이터를 순차 검색할때는 첫 번째 데이터부터 마지막 데이터까지 순서대로 비교하며 찾아야 한다. 만약 마지막 데이터까지 비교해도 검색 값과 일치하는 데이터가 없으면 검색에 실패한 것이다. 반면 정렬되어 있는 데이터를 순차 검색할 때는 중간의 데이터 값이 검색 값보다 크면(오름차순) 찾는 데이터가 없다는 뜻이므로 검색 실패 여부를 좀 더 빨리 알 수 있다.

### 이진 검색(Binary search)

이진 검색은 데이터 가운데에 위치한 항목을 검색 값과 비교하여, 검색 값이 더 크면 오른쪽 부분을 검색하고 검색 값이 더 작으면 왼쪽 부분을 검색하는 방법이다. 정렬된 데이터에서만 사용할 수 있지만 속도가 빠르다.

### 해싱(Hash)

해시는 잘게 자른 조각을 뜻하며, 전산 처리에서 해싱(hashing)은 검색하고자하는 Key 값을 해시함수에 넣어 반환받은 해쉬코드를 배열의 인덱스로 환산해서 데이터에 접근하는 것을 말한다. 즉 데이터들이 해시함수에 의해 분류가 되어 예쁘게 정렬된 상태로 해쉬테이블(Key(Index): Value)에 저장이 된다. ex) 피자 -> 해시 함수 -> 0: 3$
짧은 해시 키를 사용해 항목을 찾으면 원래의 값을 이용하여 찾는 것보다 더 빠르다. 배열과 마찬가지로 인덱스를 이용해 O(1)의 시간 안에 원하는 항목에 접근할 수 있다. 컴퓨터의 메인메모리를 RAM이라고 부르는 이유도 주소를 통해 모든 위치를 동일한 시간 안에 접속할 수 있기 때문이다.

***

## 기타 알고리즘

### 완전 탐색

완전탐색의 종류

브루트 포스 : for문을 이용하여 처음부터 끝까지 탐색하는 방법

비트 마스크 : 이진수 표현을 자료구조로 쓰는 기법 (AND, OR, XOR, SHIFT, NOT)

백트래킹 : 분할정복을 이용한 기법, 재귀함수를 이용, 해를 찾아가는 도중에 해가 될 것 같지 않은 경로가 있다면 더 이상 가지 않고 되돌아간다. DFS + 가지치기

재귀함수 : 함수 내에서 함수 자기 자신을 계속해서 호출하는 것

순열 : 서로 다른 n개의 원소에서 r개의 중복을 허용하지 않고 순서대로 늘어 놓은 수

BFS(너비 우선 탐색) - 큐 사용

DFS(깊이 우선 탐색) - 스택, 재귀 사용

### Dynamic Programming

https://galid1.tistory.com/507

https://semaph.tistory.com/16

중복, 규칙, 누적을 통해서 점화식을 구해야 한다.
### 분할정복

https://www.youtube.com/watch?v=qDEKiNzAH1U



