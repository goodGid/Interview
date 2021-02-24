

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
```

---

* **연관 관계**가 걸려있는 경우

  기본적으로 묶어서 insert/update가 되지 않는다.
  
``` java
public void doBatch() {
Session session = sessionFactory.openSession();
Transaction tx = session.beginTransaction();
for ( int i=0; i<100000; i++ ) {
    Customer customer = new Customer(.....);
    Cart cart = new Cart(...);
    customer.setCart(cart) // note we are adding the cart to the customer, so this object
     // needs to be persisted as well
    session.save(customer);
    if ( (i + 1) % 20 == 0 ) { //20, same as the JDBC batch size
        //flush a batch of inserts and release memory:
        session.flush();
        session.clear();
    }
}
tx.commit();
session.close();
}
```

* 이유는 Customer-Cart가 연관 관계가 있어서 

  하나의 Customer insert 후에 
  
  곧바로 Cart가 insert되고 
  
  그 다음에 다시 Customer가 insert가 되기 때문에 
  
  Customer는 Customer끼리 Cart는 Cart끼리 묶이지 않는다.
  
* 그래서 동일 객체끼리 묶기 위해선 

  다음과 같이 설정을 해줘야 한다.

> properties

```
spring.jpa.properties.hibernate.order_inserts=true
spring.jpa.properties.hibernate.order_updates=true
```

> 참고

* [관계에 대한 Batch Insert](https://kwonnam.pe.kr/wiki/java/hibernate/batch#%EA%B4%80%EA%B3%84%EC%97%90_%EB%8C%80%ED%95%9C_batch_insert)

* [JPA로 batch insert 하는 방법](https://ohgym.tistory.com/48)


---


* **@GeneratedValue(strategy = GenerationType.IDENTITY)** 설정이 되어있다면 insert가 되지 않는다.

> 참고

* [기억할 점](https://kwonnam.pe.kr/wiki/java/hibernate/batch#%EA%B8%B0%EC%96%B5%ED%95%A0_%EC%A0%90)

* [JPA로 batch insert 하는 방법](https://ohgym.tistory.com/48)


