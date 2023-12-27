# Spring AOP 용어 정리

Spring AOP에서 사용되는 용어를 정리해보자.

## Aspect

공통적인 기능을 모듈화 한 것

## Target

Aspect가 적용될 대상. 메서드나 클래스 등이 이에 해당 될 수 있다.

## Join Point

Aspect가 적용될 수 있는 시점. 메소드 실행 전, 실행 후가 주로 해당된다.

## Advice

Aspect의 기능을 정의한 것. 메서드 실행 전, 실행 후, 예외 발생 시 실행 될 코드가 이에 해당된다.

## Point Cut

Advice가 적용될 메서드의 범위를 지정하는 것.

