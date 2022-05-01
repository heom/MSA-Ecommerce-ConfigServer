# MSA Ecommerce
- [MSA Ecommerce] Config Server
![configserver](https://user-images.githubusercontent.com/42602972/165476498-5bc9b445-cdc4-4c6c-8ed4-c95c9a2735d8.png)

## 프로젝트 개발 구성
- Java 8
- Spring Boot(+Maven) 2.6.4
- Spring Cloud 2021.0.1
  - Config-server 3.1.1
  - Bus-amqp(RabbitMq) 3.1.1
- Spring Actuator 2.6.4

## 프로젝트 서버 구성
- IP : localhost
- PORT : 8888
- RabbitMq : localhost:5672

## URL
- **[Config API]**
  - [POST Refresh All config]
    - http://localhost:8888/actuator/busrefresh
  - [POST encrypt]
    - http://localhost:8888/encrypt
      - Request Body(raw)
        - 암호화 하려는 데이터 

## 추가 정리
- **구동방법**
  - Config 파일 다운로드
    - [GitHub - Config Repository](https://github.com/heom/MSA-Ecommerce-Config)
      - apiGateway-local.yml
      - catalogService-local.yml
      - discoveryService-local.yml
      - orderService-local.yml
      - userService-local.yml
  - 다운로드 파일 폴더, 로컬 저장소 생성
  - yml 파일 수정
    - [application.yml](src/main/resources/application.yml)
      - spring.cloud.config.server.git.uri : file://${로컬 저장소}
