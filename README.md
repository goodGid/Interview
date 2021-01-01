## Java

- GC에 대해 설명해주세요

  - [가비지 컬렉션(Garbage Collection) 1편](https://goodgid.github.io/Java-Garbage-Collection-(1))
  
  - [가비지 컬렉션(Garbage Collection) 2편](https://goodgid.github.io/Java-Garbage-Collection-(2))
  
- Java 8과 Java 11에서 Default GC 전략은 무엇인가요?

  - [Best practice for JVM Tuning with G1 GC](https://backstage.forgerock.com/knowledge/kb/article/a75965340)
  
    ```
    Java 8 : the default GC is Parallel GC 
    Java 11 : the default GC is G1 GC
    ```

- JVM에 대해 설명해주세요

  - [JVM 구조](https://goodgid.github.io/Java-JVM/)

- Map 관련해서 설명해주세요
  
  - [Map 컬렉션 - HashMap, LinkedHashMap, Hashtable, TreeMap](https://velog.io/@gillog/Map-%EC%BB%AC%EB%A0%89%EC%85%98-HashMap)
  
    ```
    HashMap : No Thread Safe
    HashTable : Thread Safe
    LinkedHashMap : the linked list preserves the insertion-order.
    TreeMap : Sorted by keys
    ```

- Stream에 대해 설명해주세요

- Java 8에서의 특징에 대해 설명해주세요

  - Coding
  
    - Lambda 표현으로 Coding이 가능 --> 가독성 좋아짐
    
  - Default Method
  
    - [Java 8 디폴트 메서드(Default Method) : 다이아몬드 문제(=다중 상속) 해결하기](https://goodgid.github.io/Java-8-Default-Method/)
    
  - JVM의 변화
  
    - [Java 8에서 JVM의 변화 : PermGen이 사라지고 Metaspace가 등장하다.](https://goodgid.github.io/Java-8-JVM-Metaspace/)
    
- String.equals( ) vs Object.equals( )에 대해 설명해주세요

  - [String.class의 equals() 메소드 알아보기](https://goodgid.github.io/Java-Object-String-Equlas)
  
- Servlet Life Cycle에 대해 설명해주세요

  - [Servlet Life Cycle 알아보기](https://goodgid.github.io/Java-Servlet-Life-Cycle/)
  
- Java에서 String을 다루는 다양한 클래스들(String, StringBuffer, StringBuilder)에 대해서 비교 설명해주세요 

  - [String, StringBuffer, StringBuilder의 특징 및 비교](https://goodgid.github.io/Java-String-Set/)





## JPA

- JPA에서 말하는 Dialect(방언)에 대해 설명해주세요

  - [JPA에서 말하는 Dialect(방언)이란?](https://goodgid.github.io/What-is-Dialect/)
  
- 생명 주기에 대해 설명해주세요

  - [Entity 생명 주기](https://github.com/goodGid/Lecture/blob/master/inflearn/%EC%9E%90%EB%B0%94%20ORM%20%ED%91%9C%EC%A4%80%20JPA%20%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D%20-%20%EA%B8%B0%EB%B3%B8%ED%8E%B8/Chapter_3.md)

- 성능을 고려해서 작업한 부분이 있나요?

  - [Data Save시 Bulk Insert 혹은 Bulk Update로 처리하기](https://github.com/goodGid/Interview/blob/main/JPA/Data%20Save%EC%8B%9C%20Bulk%20Insert%20%ED%98%B9%EC%9D%80%20Bulk%20Update%EB%A1%9C%20%EC%B2%98%EB%A6%AC%ED%95%98%EA%B8%B0.md)

- N+1 문제와 해결책에 대해 설명해주세요  

  - [즉시 로딩과 지연 로딩](https://github.com/goodGid/Lecture/blob/master/inflearn/%EC%9E%90%EB%B0%94%20ORM%20%ED%91%9C%EC%A4%80%20JPA%20%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D%20-%20%EA%B8%B0%EB%B3%B8%ED%8E%B8/Chapter_8.md#82-%EC%A6%89%EC%8B%9C-%EB%A1%9C%EB%94%A9%EA%B3%BC-%EC%A7%80%EC%97%B0-%EB%A1%9C%EB%94%A9)




## Spring

- Spring AOP에 대해 설명해주세요

- IoC에 대해 설명해주세요

- MVC vs Boot 차이에 대해 설명해주세요






## ORM

- Hibernate에 대해 설명해주세요






