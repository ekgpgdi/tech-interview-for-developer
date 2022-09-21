> ## Collection Framework 란?
- 컬렉션 : 다수의 객체(데이터)를 모아 놓은 것
- 다수의 객체를 다루기 위해 표준화된 프로그래밍 방식
- Java.util 패키지에 포함
- Collection Framework의 구조
![](https://velog.velcdn.com/images/seonmikimm/post/2066bae4-808f-434c-afb4-a8d4b9079027/image.png)

> ## Collection 인터페이스란?
> - 인터페이스 List 와 Set 의 공통 부분을 모아 새로운 인터페이스인 Collection을 정의하였다.
> - 인터페이스 List 와 Set 은 Collection 을 상속하고 있다.

> ## List란? 
- 순서가 있는 데이터의 집합으로 중복을 허용한다.
- List 인터페이스를 구현하는 클래스
    - ArrayList 
    - LinkedList 
    - Vector : ArrayList와 거의 동일한 기능이며, 컬렉션 프레임워크가 도입되기 이전부터 지원하는 클래스
        - Stack : Vector 클래스를 상속

> ## ArrayList와 LinkedList를 언제 사용하는가?
### ArrayList
- 모든 객체의 최상위 타입인 Object 배열 기반, 객체 접근에 탁월함
- 배열 크기가 고정되어 있고 중간에 데이터 삽입/삭제 시 배열 전체의 크기 변경 연산이 필요함
- 무작위 접근이 가능하여 조회 속도가 높음
- 데이터 개수가 변하지 않는 경우, 검색/조회에 사용한다.
### LinkedList
- Node 객체 연결 기반
- Node 클래스는 자신의 데이터와 연결된 데이터의 주소로 이루어져 있음
- 연속적인 메모리 할당이 필요하지 않고 데이터를 특정 주소에 저장하여 주소를 연결
- 연결된 노드를 통해 순차적인 접근을 해야 하므로 접근 속도가 느림
- 데이터 삽입/삭제 시 노드 연결만 추가/삭제하면 됨
- 데이터 개수의 변경이 빈번한 경우, 삽입/삭제에 사용한다.

> ## Set 이란? 
- 순서를 유지하지 않는 데이터의 집합으로 중복을 허용하지 않는다.
- Set 인터페이스를 구현하는 클래스
    - HashSet : 가장 기본적인 Set 클래스로, hash에 의해 데이터의 위치를 특정시켜 해당 데이터를 빠르게 조회할 수 있다.
    - TreeSet : 특정 규칙에 의해 데이터를 정렬하는 자료 구조인 Tree와 중복을 허용하지 않는 Set 자료구조가 결합되었다.
    - LinkedHashSet : 중복을 허용하지 않는 Set 자료구조의 순서를 유지하고 싶을 때 사용한다.

> ## Map 이란? 
- 키와 값의 쌍으로 이루어진 데이터의 집합
- 순서를 유지하지 않으며, 키는 중복을 허용하지 않고, 값은 중복을 허용한다.
- Map 인터페이스를 구현하는 클래스
    - HashMap
    - TreeMap
    - LinkedHashMap
    - HashTable


> ## Stack 이란?
- Stack은 '쌓아 올리다' 라는 의미로, 가장 마지막에 쌓아 올린 짐이 가장 위에 있고, 가장 먼저 사용한다.
- LIFO(Last in First out) 또는 후입선출
- Vector 클래스를 상속하는 클래스로, 모두 Vector에 있는 메소드를 이용하여 구현되어 있다.
- Stack의 활용 예 
    - 웹 브라우저의 뒤로가기, 워드프로세서의 undo/redo, 수식계산

> ## Queue 란?
- Queue는 '대기열' 이라는 의미
- FIFO(First-in First-out) 또는 선입선출
- 시간 순으로 데이터를 처리할 때 사용한다.
- Queue의 활용 예
    - 최근 사용 문서, 인쇄 작업 대기목록, Buffer
