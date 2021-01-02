



## What is Feign Client?

```
Feign aims at simplifying HTTP API clients. 
Simply put, the developer needs only to declare 
and annotate an interface 
while the actual implementation is provisioned at runtime.
```

* HTTP API Client를 편리하게 사용하는게 목표이다.

  그리고 runtime 시점에 구현체가 제공되므로 

  선언적으로 사용하면 된다.


```
The actual implementation of making a REST call is handled at runtime by Feign. 
This means that the implementation can be configured without changing your business logic code.

By just changing the Feign configuration in a Java 
or using properties you can add encoding/decoding, logging, and change the REST call implementation library. 

All this is done through configuration only, 
while the business logic that calls the service remains unchanged. 

Since Feign uses standard Java interfaces, 
it's also easy to mock them during unit tests.
```

* Business Logic Code 수정없이 구현체 구성이 가능하다.



---


## Reference

* [Intro to Feign](https://www.baeldung.com/intro-to-feign)

* [What are the advantages and disadvantages of using feign over RestTemplate](https://stackoverflow.com/questions/46884362/what-are-the-advantages-and-disadvantages-of-using-feign-over-resttemplate)

