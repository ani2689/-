### 트랜잭션을 보장하는 코드

서버 내부에서 순수 자바 코드로 트랜잭션을 보장하고 싶을때는 try-catch 문을 사용할 수 있다.

```java

public void CustomService(){

    Connection connection = dataSource.getConnection();
    connection.setAutoCommit(false);

    try {
    // 한번에 처리되어야 하는 로직
            connection.commit();	
    } catch(SQLException e) {
            connection.rollback();
            throw new RemittanceException();
    }

}

```

한번에 처리되어야 하는 로직이 굴러가는 도중에 에러가 발생하면 catch문을 실행시켜 롤백해 트랜잭션의 원자성을 보장한다.

그러나 위의 방법으로 하면 문제가 몇가지 있다.

1. 원자성을 보장해야 하는 모든 비지니스 코드에 try-catch 문을 모두 반복적으로 작성해야한다. 
2. 트랜잭션의 원자성을 보장해주기 위한 코드가 비지니스 로직과 함께 있다. 따라서 개발자는 비지니스 로직에 집중할 수 없다.

여기서 생각할 수 있는 개념이 관점지향 프로그래밍 (AOP) 이다.

### 트랜잭션과 AOP

AOP란 횡단 관심사에 집중하는 것이다. 예를 들어 프로그램에 계좌 이체, 입출금, 이자 계산이라는 서비스가 존재할 때 이 셋 모두 로깅과 트랜잭션, 보안 처리를 해주어야 한다.

비지니스 로직을 제외한 공통적 부가 기능을 따로 분리하여 관리하는 것이 바로 AOP라고 할 수 있다.

스프링에서 사용하는 @Transactional 어노테이션이 바로 AOP의 개념이 적용된 예이다.


---

#### 참고 :: [Spring Transaction에 대한 기본 개념](https://velog.io/@byeongju/Spring-Transaction%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B8%B0%EB%B3%B8-%EA%B0%9C%EB%85%90#%EC%B0%B8%EA%B3%A0-%EC%9E%90%EB%A3%8C)