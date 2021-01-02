

## What is QueryDSL

* SQL, JPQL을 코드로 작성할 수 있도록 도와주는 Builder API이다.

* SQL 및 JPQL은 Type Safe하지 않다. 

  하지만 QueryDSL은 Compile 시점에 Check가 가능하다. 
  
  즉 Type Safe하다.





## Benefit

* Query는 Code로 작성할 수 있다.

* Compile 시점에 Check가 가능하다.

* Dynamic Query 작성이 가능하다.

``` java
private final JPAQueryFactory jpaQueryFactory;

BooleanBuilder builder = getBooleanBuilder(...);

List<XXX> xxxList = jpaQueryFactory.selectFrom(Qxxx)
                                    .where(builder)
                                    .limit(limitSize)
                                    .fetch();


private BooleanBuilder getBooleanBuilder(...) {
    BooleanBuilder builder = new BooleanBuilder();
    builder.and(xxx.yyy.eq(zzz));  
    return builder;
}
```




---

## Reference

* [[JPA] Spring Data JPA와 QueryDSL 이해, 실무 경험 공유](https://ict-nroo.tistory.com/117)