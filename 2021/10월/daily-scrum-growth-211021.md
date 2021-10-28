# 01. Scrum

### 어제 한 일

- LastStatusUpdater 구현 및 단위테스트
- UdpChannel의 전체 InboundPipeline 단위테스트
- 기존 LCAM 코드 구조 분석 (Command, Initialize 전체 흐름)

### 오늘 할 일

- B/E 동료와 Command, Initialize 인터페이스 설계 논의 (Json String 대신 VO 변경)
- ACU, X-DC 초기화, 제어, 모니터링 항목 결정 → F/E 동료와 공유
- 수신 파이프라인
    - CRC 체크 코드 추가하기
    - LastStatus로 업데이트하지 않는 수신 메시지는 우선 로그를 찍도록 변경하기 → 추후 메시지 송신의 응답으로 연계되도록 리팩토링하기
- 송신 파이프라인
    - CRC 생성 코드 추가하기
- Cam 개발하기
    - postConstruct
    - preDestroy
    - getAlarmList
    - command
    - initialEvent
- Self Server-Client 기반으로 Cam을 테스트할 수 있도록 개발하기
- Web과 독립적으로 장비 연동(ACU, X-DC)을 테스트할 수 있는 테스트 케이스 개발하기
    - CRC 알고리즘 적합함을 테스트하기 위한 테스트 케이스 개발하기


### 어려운 일

- F/E 동료 업무 할당과 협업
    
    → Figma로 화면에 대한 의견 공유
    
- 데드라인 대비 전체 일정 관리가 한 눈에 들어오지 않는다.
- 해야할 일이 산더미인데 오늘 해야할 일을 명확히 구분할 수 없다. 

# 02. Study

### Hard Skills

- [웹 기반 CRC 알고리즘 별 코드 생성](https://www.lammertbies.nl/comm/info/crc-calculation?crc=8005&method=hex) ⭐
- REST API를 통해 파라미터를 전달하는 방법
    - Request Body / Path Parameter / Query Parameter

### Soft Skills

- Scrum
    - 오늘은 어제가 아니다. 내일과도 구분된다. 오늘은 오늘이다.
    - 문제를 인식하는 것과 원인을 찾고 해결하는 것을 분리해도 좋다.
