# HTTP Request

HTTP 응답과 구조는 비슷하다.

## Reques Line

요청에서의 중요한 내용이 담긴다.

### Method

HTTP 요청의 첫 줄에는 어떤 메서드를 사용할지에 대한 내용이 나와있다.

GET, POST, DELETE 등의 메서드가 전달된다.

### Path

URL에서 호스트 네임과 포트를 제외한 나머지 경로 부분이 나와있다.

Endpoint와 Query String에 대한 값이 전달된다.

### HTTP Version

HTTP의 버전 정보가 담긴다.

## Headers

여러가지 정보가 담긴다. 헤더에 들어있는 정보에 따라 요청을 처리하는 방식이 달라지거나 응답을 생성할 때 타입 등이 바뀌기도 한다.

## Message Body

POST나 PUT 같은 메서드는 보통 메세지 바디가 동반되며, 그 정보가 담긴다.  