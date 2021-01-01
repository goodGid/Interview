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
