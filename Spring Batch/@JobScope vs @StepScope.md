

## @JobScope과 @StepScope에 대해 설명해주세요

* 2개 Annotation 사용 이유는 Job Parameter를 사용하기 위해서이다.

* Spring Batch에서 Job Parameter를 사용하기 위해선 

  항상 Spring Batch 전용 Scope를 선언해야한다.

* 관련 예제는 [5-1. JobParameter와 Scope](https://jojoldu.tistory.com/330)글을 참고하자.

``` java
@JobScope
public Step xx() {
    ...
}

@StepScope
public TaskLet xxx() {
    ...
}
```

* 정리하자면 다음과 같다.

```
@JobScope  : Step 선언문에서 사용 가능
@StepScope : Tasklet이나 Chunk(ItemReader, ItemWriter, ItemProcessor)에서 사용 가능
```

---

> Singleton -> Lazy

* Spring Bean의 기본 Scope는 Singleton이다.

  그러나 Spring Batch 컴포넌트(Tasklet, ItemReader, ItemWriter, ItemProcessor 등)에 @StepScope를 사용하게 되면

  지정된 Step의 실행시점에 해당 컴포넌트를 Spring Bean으로 생성한다.

  즉 Bean의 생성 시점을 Scope이 실행되는 시점으로 지연시킨다.

---

> Lazy Loading 시 장점

1. JobParameter의 Late Binding 가능하다.

* 즉 Application이 실행되는 시점이 아니더라도 

  Controller / Service / Listener에서 Job Parameter를 할당 시키고 

  원하는 Step에서 사용이 가능하다.

2. 동일한 컴포넌트를 병렬 혹은 동시에 사용 시 유리하다.

* Step 안에 Tasklet이 있고 
  
  이 Tasklet은 멤버 변수를 변경하는 로직이 있다고 가정해보자.

  이 경우 @StepScope 없이 Step을 병렬로 실행시키게 되면 
  
  서로 다른 Step에서 하나의 Tasklet을 두고 마구잡이로 상태를 변경한다.

* 하지만 @StepScope가 있다면 
  
  각각의 Step에서 별도의 Tasklet을 생성하고 관리하므로 서로의 상태에 영향을 끼치지 않는다.


---

* [5-3. Job Parameter 오해](https://jojoldu.tistory.com/330) 부분을 보면서 제대로 개념을 이해했는지 체크해보자.

---



## Reference

* [5. Spring Batch 가이드 - Spring Batch Scope & Job Parameter](https://jojoldu.tistory.com/330)