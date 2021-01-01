

## Save( ) vs SaveAll( )

* [Spring data save vs saveAll performance](https://stackoverflow.com/questions/49869277/spring-data-save-vs-saveall-performance)

```
if you are calling save in a loop that 
means a new transaction is being created each time you call save,

but in the case of saveAll 
there is one call and 
therefor one transaction created regardless of the number of entities being saved.
```

* [Performance Difference Between save() and saveAll() in Spring Data](https://www.baeldung.com/spring-data-save-saveall)

```
each time we call the save() method, 
a new transaction is created

whereas when we call saveAll(),
only one transaction is created, 
and it's reused later by save().
```






## Bulk Insert/Update로 성능 최적화

* [JPA로 batch insert 하는 방법](https://ohgym.tistory.com/48)

  [Hibernate Batch/Bulk Insert/Update](https://kwonnam.pe.kr/wiki/java/hibernate/batch) 
  
  

* **batch_size** 는 한꺼번에 insert/update를 실행할 크기만큼 설정해 주면 된다.

> yml

``` java
spring:
  jpa:
    properties:
      hibernate:
        jdbc:
          batch_size: 100
```


> properties

```
spring.jpa.properties.hibernate.jdbc.batch_size=4
spring.jpa.properties.hibernate.order_inserts=true
```
