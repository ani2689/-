# Spring AOP 에서 사용되는 Annotation

스프링 AOP에서 사용되는 Annotation을 정리해보자.

## @Aspect

해당 클래스를 Aspect로 사용하겠다며 명시하는 어노테이션.

## @Before

대상 메서드가 실행되기 전에 Advice를 실행합니다.

## @AfterReturning

대상 메서드가 정상적으로 실행된 후 Advice를 실행합니다.

## @AfterThrowing

대상 메서드에서 예외가 발생했을 때 Advice를 실행합니다.

## @After

대상 메서드가 실행된 후 Advice를 실행합니다.

## @Around

대상 메서드의 실행 전, 실행 후 또는 예외 발생 시에 Advice를 실행합니다.

