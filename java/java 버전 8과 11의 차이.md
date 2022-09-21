## Java 8

- Heap Permanent Generation 제거
- 인터페이스에 디폴트 메소드와 정적 메소드 추가
- 함수형 인터페이스, 람다 표현식, 메소드 참조 기능 추가
    - 주로 함수형 인터페이스의 익명 객체를 대체하기 위해 람다식을 사용하며, 간결하고 부수 효과가 없는 코드를 만들어 낼 수 있게 된다.
- 스트림 API 도입
- 새로운 날짜 관련 라이브러리 추가
    - LocalDate, LocalTime, LocalDateTime 등의 라이브러리
    - 기존에 사용하던 날짜 관련 클래스인 Date, Calendar 등은 가변 객체이므로 Thread-Safe하지 않다.
- Optional 지원
    - Optional을 통해 null에 대한 참조를 안전하게 할 수 있다.
- 병렬 처리 지원

## Java 11 

- 람다에서 로컬 변수 Var 사용 가능
- Files 클래스에 새로운 메소드 추가
    - writeString()
    - readString()
    - isSameFile()
    - 등과 같은 다양한 메소드가 있어 파일에 대해 여러 작업을 수행 할 수 있음.
- String 에 새로운 메소드 추가
    - `strip()`: 문자열 앞, 뒤의 공백 제거.
    - `stripLeading()`: 문자열 앞의 공백 제거.
    - `stripTrailing()`: 문자열 뒤의 공백 제거.
    - `isBlank()`: 문자열이 비어있거나, 공백만 포함되어 있을 경우 true를 반환한다.
        - `String.trim().isEmpty()` 와 결과가 동일함.
    - `repeat(n)`: n개만큼 문자열을 반복하여 붙여서 반환함.
- 자바 파일 실행 방식 단순화
    - javac를 통해 컴파일 하지 않고도, 바로 java 파일을 실행할 수 있게 되었다.