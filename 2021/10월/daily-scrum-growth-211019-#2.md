# 01. Scrum

### 어제 한 일

- NextMoveAcuMessageDecoder 구현 및 단위 테스트

### 오늘 할 일

- ~~LastStatusUpdater 구현 및 단위 테스트~~
- ~~Inbound Pipeline 단위 테스트~~



# 02. Study

### Hard Skills

- SerializationUtils.clone() supports deep clone but it is slower than manual copy!
- @SpringBootTest(classes = {xxx.class}) 동작의 의미 이해하기.
- [@ActiveProfiles / @Profile](http://wonwoo.ml/index.php/post/1933)
- [@ExtendWith(SpringExtension.class)](https://www.baeldung.com/junit-5-extensions)
- Netty ChannelPipeline을 MessageToMessageDecoder로 연결 시, 연결되는 Handler 간의 입출력 타입이 맞지 않으면, 예외 발생이나 오류 메시지 출력 없이, 현 Handler를 건너뛰고 다음 Handler로 전달된다.
  
```java
package io.netty.handler.codec;

public abstract class MessageToMessageDecoder<I> extends ChannelInboundHandlerAdapter {
		... 

		// 입출력 간의 타입 체크 
    public boolean acceptInboundMessage(Object msg) throws Exception {
        return matcher.match(msg);
    }

    @Override
    public void channelRead(ChannelHandlerContext ctx, Object msg) throws Exception {
        CodecOutputList out = CodecOutputList.newInstance();
        try {
            if (acceptInboundMessage(msg)) {
                @SuppressWarnings("unchecked")
                I cast = (I) msg;
                try {
                    decode(ctx, cast, out);
                } finally {
                    ReferenceCountUtil.release(cast);
                }
            } else {
                out.add(msg);
            }
        } catch (DecoderException e) {
            ... 
        }
    }
    ...
}
```

- [ObjectMapper](https://www.baeldung.com/jackson-object-mapper-tutorial)
    - Json to Object (Class or List or Map)
- CRC16
    - [파이썬 모듈 구현](https://github.com/gtrafimenkov/pycrc16/blob/master/python3x/crc16/crc16pure.py)
    - CRC-CCITT (XModem)
        - [구현 타입-1](https://stackoverflow.com/questions/17196743/crc-ccitt-implementation) (Stack Overflow)
        - [구현 타입-2](https://www.codeproject.com/Questions/1208413/How-to-calculate-CRC-ccitt-xmodem-with-polynomial) (Code Proejct / C#)
       
        
        - [구현 타입-3](https://www.notion.so/68072c44c02879a2abf94ef350d1c7c6)
        