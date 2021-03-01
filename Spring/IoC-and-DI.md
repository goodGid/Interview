

# IoC와 DI에 대해 설명해주세요



## IoC Container

* 기본적으로 IoC Container는 

  객체를 생성하고 객체 간의 의존성을 이어주는 역할을 한다.





### BeanFactory

* BeanFactory 인터페이스는 IOC 컨테이너의 기능을 정의하고 있는 인터페이스이다.

* Bean의 생성 및 의존성 주입, 생명주기(lifecycle) 관리 등의 기능을 제공한다. 

  여기서 Bean이란 IoC Container에 의해 생성되고 관리되는 객체를 의미한다.




### ApplicationContext

* BeanFactory 인터페이스를 상속받는 

  ApplicationContext는 BeanFactory가 제공하는 기능 외에 
  
  **AOP**, 메시지처리, 이벤트 처리 등의 기능을 제공한다.

* 모든 ApplicationContext 구현체는 BeanFactory의 기능을 모두 제공하므로 

  특별한 경우를 제외하고는 ApplicationContext를 사용하는 것이 바람직하다.

> ApplicationContext.class

``` java
public interface ApplicationContext extends EnvironmentCapable, ListableBeanFactory, HierarchicalBeanFactory,
		MessageSource, ApplicationEventPublisher, ResourcePatternResolver {
```


---

## DI

![](https://github.com/goodGid/Interview/blob/main/Spring/src/IoC-and-DI_1.png)

* 위의 그림처럼 IoC를 구현하는 방법으로 

  DL, DI 2가지 방법이 있다.

### DL(Dependency Lookup)

* Container에서 제공하는 API를 이용해 

  사용하고자 하는 Bean을 저장소에서 Lookup 하는 것을 말한다.


### DI(Dependency Injection)

* 각 객체 간의 의존성을 Container가 자동으로 연결해주는 것으로 

  개발자가 Bean 설정파일에 의존관계가 필요한 정보를 추가해주면 Container가 자동으로 연결해준다.

  Spring에서는 2가지 방식(Setter Injection, Constructor Injection)이 있다.



---


## Why use IoC ?

* 그렇다면 IoC를 왜 사용할까? 

  그 이유는 객체지향 프로그래밍과 아주 관련이 깊다.

* 객체지향 프로그래밍은 객체마다 자기의 역할과 책임을 온전히 다하며 

  서로 협력하며 변경에 유연한 프로그래밍을 할 수 있는 프로그래밍 기법이다. 
  
  즉 각 객체마다 올바른 캡슐화를 통해 높은 응집도와 낮은 결합도를 이루어나가는 것이 핵심이다.

* 이러한 관점에서 IoC에 의해

  제 3자 즉 다른 객체, 다른 Container에게 제어에 대한 역할과 책임을 위임하고 
  
  해당 객체는 다른 객체에 대해 신경 쓰지 않고 
  
  지금 내가 하고자 하는 역할과 책임에만 관심을 갖게 된다.
  
* 그렇다면 왜 이렇게 하는 것일까?

  그 이유는 변경에 유연한 코드 구조를 가져가기 위해서이다. 
  
  내가 작성하고자 하는 코드에서 
  
  객체의 Life Cycle을 관리하는 코드 + 비즈니스 코드 + @ 들어가게 된다면

  해당 객체에 들어가는 코드는 너무나도 방대해질 것이다.
  
> Example 1.

```
A라는 객체를 생성하고 있었는데 
A 객체는 삭제하고 B 객체를 추가해야 하는 상황이 왔다.

1개에서만 사용했다면 
1개만 수정해주면 된다.

n개에서 사용했다면
n개를 수정해줘야 한다.
```

> Exampe 2.

```
객체 생명 주기를 직접 관리하게 되면
절대 삭제하면 안 되는 객체를
개발자가 삭제해버릴 수도 있다.

즉 개발자에게 권한이 너무 많이 위임되면서
객체에 대한 핸들링을 직접 하게 되면
객체지향이 지향하는 캡슐화에 대해 위반하게 된다.
```

---


## Reference

* [[Spring] Spring IoC와 DI](https://gangnam-americano.tistory.com/60)


* [IoC, DI란 무엇일까](https://biggwang.github.io/2019/08/31/Spring/IoC,%20DI%EB%9E%80%20%EB%AC%B4%EC%97%87%EC%9D%BC%EA%B9%8C/)
