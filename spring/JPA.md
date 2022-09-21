# Spring Data JPA
## ORM이란 무엇인가요?
**Object Relational Mapping**의 줄임말로, 객체와 관계형 데이터베이스간에 데이터를 자동으로 매핑해주는 기술입니다.

## JPA, Hibernate, Spring Data JPA는 각각 무엇인가요?
- JPA는 자바 진영의 ORM을 위한 명세를 의미합니다.
- Hibernate란 자바 진영의 ORM 명세인 JPA를 구현한 여러 구현체 중 하나를 의미합니다.
- Spring Data JPA는 Spring 환경에서 편리하게 사용할 수 있도록 Repository 기반으로 추상화 시킨 스프링 서브 프로젝트입니다.

## 프로젝트에 JPA를 사용하신 이유가 뭔가요? 
프로젝트가 진행되면서 발생하는 반복 쿼리문을 없애고, 좀 더 객체지향적으로 코드를 작성하고 싶어서 JPA를 사용했습니다.

## JPA의 장/단점은 무엇이 있나요?
장점으로는 개발자가 반복되는 쿼리를 직접 작성하지 않아도 되면서 개발 생산성이 올라가 효율이 증가하는 점이 있습니다. 단점으로는 Pesistent Context에서 Cache, Write Behind, Dirty Checking, Lazy Loading 등 다양한 기능을 지원해주는데 개념을 잘 모르고 JPA를 사용했을 경우 수많은 예외와 성능 감소가 발생할 수 있다는 점이 있습니다.

## JPA Entity의 상태 변화에 대해서 설명해주시겠어요?
JPA Entity 상태에는 Transient, Persistent, Detached, Removed 상태가 존재합니다.
- Transient 상태는 객체가 새롭게 생성된 상태를 의미하며 Persistent Context에서 관리하지 않는 상태입니다.
- Persistent는 Persistent Context에 의해 관리되며 해당 엔티티는 1차 Cache, Write Behind, Dirty Checking 등의 다양한 기능을 제공받을 수 있습니다.
- Detached는 해당 엔티티를 더이상 Persistent Context에서 관리하지 않는 상태를 의미합니다.
- Removed는 데이터베이스로부터 해당 엔티티를 제거한 상태를 의미합니다.

## 영속성은 어떻게 유지되고 DB에 저장되는 건가요?
1. Transaction이 시작합니다.
2. 새로운 Entity 객체를 생성합니다.
3. Persistent Context에 Entity 객체를 올립니다.
4. Persistent Context는 해당 Entity를 관리하면서 Dirty Checking이나 1차 Cache 등의 다향한 기능을 제공해줍니다.
5. 트랜잭션이 커밋되기 전에 flush가 발생하며 Persistent Context의 변경 내용들이 데이터베이스에 반영됩니다.
6. 트랜잭션 커밋됩니다.

### 용어 정리 갑니다~
#### 1차 Caching 이란 ?
flush가 발생하기 전까지 Persistent Context 내부에서 엔티티를 캐싱하는 것을 1차 캐싱이라고 합니다.

#### Dirty Checking 이란?
Persistent Context 에서 flush가 일어날 때 **저장된 엔티티와 스냅샷의 상태를 비교해서 서로 다르면 알맞는 쿼리문을 데이터베이스에 반영하는 것**입니다.

#### Lazy Loading 이란?
Lazy Loading 이란 DB로부터 엔티티를 가져올 때 참조된 엔티티와 관련된 select 쿼리가 발생하는 것이 아닌, **프록시를 통해서 직접 참조된 엔티티를 사용될 경우에 select 쿼리가 발생하는 것**을 의미합니다.

#### 어떤 경우에 즉시 Loading을 쓰는 것이 좋은가?
DB로부터 직접 가져오는 엔티티와 이에 참조된 엔티티가 자주 같이 사용된다면 즉시 로딩을 사용하면 좋습니다.

#### Querydsl 이란?
Type-safe한 방식으로 쿼리를 작성할 수 있도록 도와주는 프레임워크를 의미합니다. 컴파일 타임에 쿼리의 문법 오류를 검증할 수 있고, IDE 자동 완성 기능을 사용해서 보다 Type-safe한 쿼리를 작성할 수 있습니다.
