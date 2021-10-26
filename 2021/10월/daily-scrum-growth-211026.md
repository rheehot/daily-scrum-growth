21.10.26

# 1. Scrum

### 어제 한 일

- 수신, 송신 메시지 구조 정의
- 메시지 빌더 구조 정의
- JSON 문자열 to Java Obect 기술 학습

### 오늘 할 일

`중요 / 급하지 않음`

- 프로젝트의 문제점 공유하기

---

`중요 / 급함`

- F/E - B/E JSON 문자열 구조 설계
- F/E - B/E JSON 문자열 처리 구조 설계
- 설계 질문
    - JSON 으로부터 생성하는 VO와, Builder에 의해 생성하는 VO를 하나로 쓰는 것이 맞는가?
    - JSON 문자열로 전달되는 다양한 메시지를 각각의 VO로 전환해야 하는데, 문자열에서 메시지 ID를 먼저 알아야 ObjectMapper.readValue()를 호출할 때 적절한 클래스를 지정해 줄 수 있다.
- NextMoveAcuLegacyEncoder 구현 및 단위 시험 (JSON to DTO)
- NextMoveAcuMessageEncoder 구현 및 단위 시험 (DTO to 통신 메시지)
- DatagramEncoder 구현 및 단위 시험

### 문제점

- 시흥 지상국 `시험 일정 지연`. (원인을 분석해야 합니다) ⭐
    
    → ObjectMapper, JSON, Netty 등 첫 러닝커브가 존재한다. 
    
    → 일을 원활히 하기 위해 `학습이 필요한 일`이 있어서 시간이 꽤 든다. 박미정님 처럼 미리 학습을 해야하는걸까?
    
- LCAM과 ContecOne 고객용 화면과 관리자용 `화면 설계`에 투자가 너무 적다.
- `빡빡한 개발 일정`
    
    → 우선 돌아가도록, 그리고 핵심 기능에 집중하여 개발해야 한다. 
    

### 감사

- 

# 2. Study

### Hard Skills

- [ObjectMapper.readTree()](https://www.baeldung.com/jackson-object-mapper-tutorial), [JsonNode](https://fasterxml.github.io/jackson-databind/javadoc/2.7/com/fasterxml/jackson/databind/JsonNode.html)
- [Map Interface](https://www.geeksforgeeks.org/map-interface-java-examples/)
    - get() : It returns NULL when the map contains no such mapping for the key.
- [Java assert](https://www.baeldung.com/java-assert) vs [Spring Assert](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/util/Assert.html)
- Json 중첩 구조
    - 배열 : [ value1, value2, ..., value3 ]
    - 구조체 : { key1 : value1, key2 : value2, ..., keyN : valueN }

### Soft Skills

- 어이 없고, 불편한 사람의 말에 신경을 두지 않고! 스쳐 흘려 보낸다!
- Java 프로그램이에도 .NET이나 MFC 에서 하던 것 같이, 절대 실행되어서는 안되는 개발 오류를 잡기위한 Assert 문을 생활화 하자.