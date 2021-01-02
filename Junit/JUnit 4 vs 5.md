




## JUnit 4 vs JUnit 5

* JUnit 5는 17년 10월에 공개되었고

  Java 8 이상을 필요로 한다.

* JUnit 5 = JUnit Flatform + JUnit Jupiter(for ver5) + JUnit Vintage(for ver3,4)

  관련 내용은 [JUnit 5 구조](https://goodgid.github.io/Junit5-Intro-Structure/#junit-5-%EA%B5%AC%EC%A1%B0) 를 참고하자.




### [Required JDK Version](https://howtodoinjava.com/junit5/junit-5-vs-junit-4/)

```
Junit 4 requires Java 5 or higher.
Junit 5 requires Java 8 or higher.
```





### [JUnit 5 Advantages](https://www.baeldung.com/junit-5-migration#junit-5-advantages)

```
The entire framework was contained in a single jar library. 
The whole library needs to be imported even when only a particular feature is required. 
In JUnit 5, we get more granularity and can import only what is necessary

One test runner can only execute tests in JUnit 4 at a time 
(e.g. SpringJUnit4ClassRunner or Parameterized ). 
JUnit 5 allows multiple runners to work simultaneously

JUnit 4 never advanced beyond Java 7, missing out on a lot of features from Java 8. 
JUnit 5 makes good use of Java 8 features

The idea behind JUnit 5 was to completely rewrite JUnit 4 to solve most of these drawbacks.
```





### [Difference](https://www.baeldung.com/junit-5-migration#differences)

* JUnit 5 comes with important changes within its annotations. 

  The most important one is that 
  
  we can no longer use @Test annotation for specifying expectations.

``` java
// JUnit 4
@Test(expected = Exception.class)
public void shouldRaiseAnException() throws Exception {
    // ...
}

// JUnit 5
public void shouldRaiseAnException() throws Exception {
    Assertions.assertThrows(Exception.class, () -> {
        //...
    });
}
```


``` java
// JUnit 4
@Test(timeout = 1)
public void shouldFailBecauseTimeout() throws InterruptedException {
    Thread.sleep(10);
}

// JUnit 5
@Test
public void shouldFailBecauseTimeout() throws InterruptedException {
    Assertions.assertTimeout(Duration.ofMillis(1), () -> Thread.sleep(10));
}
```


---


## Reference

* [Junit5 : 소개 및 구조](https://goodgid.github.io/Junit5-Intro-Structure/)

* [JUnit 5 vs JUnit 4](https://howtodoinjava.com/junit5/junit-5-vs-junit-4/)

* [Migrating from JUnit 4 to JUnit 5](https://www.baeldung.com/junit-5-migration)