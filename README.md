# Busy Bee

---

<img width="1896" height="1051" alt="KakaoTalk_20241125_093325900" src="https://github.com/user-attachments/assets/3a5c0824-7d33-4220-930c-323bbeedf739" />

- 삼성 SDS 기업연계 프로젝트
- 개발기간: 2024.10.14 ~ 2024.11.19
- 성과: 전국 프로젝트상우수상(삼성전자)

## 프로젝트 소개

---

<img width="400" alt="image" src="https://github.com/user-attachments/assets/62f8f8ab-4ea2-49cf-b0bf-30ac4c16a882" />

**매일매일 반복되는 메일업무! 이젠 Busy 하지 말고 BusyBee 하세요 !**

- Busy Bee는 AI 기반 물류 업무메일 의도분류 및 업무 자동화 서비스 입니다.
- 인텔리전스 자동화로 이메일의 내용과 첨부파일, zip파일을 분석하여 업무메일의 의도를 분류하고 업무까지 자동화 합니다.
- 이메일로 이루어지는 물류 포워딩 업무에 필요한 견적요청검토, 견적 산출, 물류 계약, 컨테이너 모니터링 일체를 제공합니다.

## **👨‍👩‍👧‍👦 Developer**

| 김도이 | 노영호 | 정현조 |
| --- | --- | --- |
| <img width="160px" src="https://avatars.githubusercontent.com/u/153525545?v=4" /> | <img width="160px" src="https://avatars.githubusercontent.com/u/161284817?v=4" /> | <img width="160px" src="https://avatars.githubusercontent.com/u/109647275?v=4" /> |
| [@kimdobbang](https://github.com/kimdobbang) | [@youngho98](https://github.com/youngho98) | [@HyunjoJung](https://github.com/HyunjoJung) |
| 팀장/BE/IoT | BE/IoT | AI/Infra |

| 박민호 | 고승희 | 임종혁 |
| --- | --- | --- |
| <img width="160px" src="https://avatars.githubusercontent.com/u/97956971?v=4" /> |<img width="160px" src="https://avatars.githubusercontent.com/u/86093028?v=4" /> | <img width="160px" src="https://avatars.githubusercontent.com/u/42922673?v=4" /> |
| [@parkminho-zz](https://github.com/parkminho-zz) | [@alex-koko](https://github.com/alex-koko) | [@limjongheok](https://github.com/limjongheok) |
| FE | FE | Infra |

# 주요기능

---

🐝 **이메일 서비스 및 이메일 의도 분류**

- 받은 이메일에서 필요한 정보와 첨부파일을 추출한 후, 이메일의 내용을 분석하여 의도에 맞게 분류합니다.

🐝 **자동 견적 산출 및 이메일 발송**

- 이메일에서 추출한 데이터를 기반으로 자동으로 견적을 산출하고, 이를 바탕으로 견적 메일을 고객에게 자동으로 발송합니다.

🐝 **인텔리전스 업무 자동화**

- 화물 및 물류 견적을 요청한 고객이 제공한 정보에 누락이나 오류가 있을 경우 이를 자동으로 식별하고, 해당 정보를 다시 요청하는 LLM(대형 언어 모델) 기반 챗봇을 통해 고객에게 회신합니다.

🐝 **챗봇**

- 챗봇은 고객이 필요한 정보를 모두 입력하면 자동으로 견적을 산출하여 회신합니다.
- 또한, 챗봇은 물류 관련 다양한 질문을 처리할 수 있으며, 다국어 지원과 음성 인식 기능도 제공합니다.

🐝 **IoT 물류 컨테이너 모니터링**

- 물류 계약이 완료되면, 고객은 실행사의 컨테이너 내부 상황을 실시간으로 모니터링할 수 있는 대시보드를 통해 화물의 상태를 확인할 수 있습니다.

# 프로젝트 기술 스택 및 개발환경

---

- **프로그래밍 언어**: Python, JavaScript, Arduino C, Java, TypeScript
- **클라우드 환경**: AWS Lambda, API Gateway, S3, SES, Route 53, CloudFront, EC2, Cognito, Amazon Translate
- **AI/ML**: LangChain, GPT-4o Mini, Distilkobert, PyTorch
- **IoT 및 센서**: Arduino Uno, 온습도 센서(DHT11), GPS 모듈(GY-GPS6MV2), 카메라(ESP32-CAM)
- **데이터베이스**: DynamoDB
- **메시지 큐**: AWS SQS, SNS
- **Frontend** : React
- **IAC** : Terraform

# 화면 구성

---

## 로그인

<img width="492" height="428" alt="image" src="https://github.com/user-attachments/assets/895ba1fd-d630-43c7-8128-c950d363101f" />

- 코그니토를 사용하여 유저 로그인, 로그아웃, 회원가입 기능을 구현했습니다.
- 유저 데이터와 비밀번호는 개인 데이터베이스에 저장하지 않고, AWS에서 관리하므로 보안 관리에 유리합니다.
- 유저 그룹에 따라 서로 다른 권한을 부여할 수 있습니다.

## 메일함

<img width="817" alt="image" src="https://github.com/user-attachments/assets/7210cebc-08a8-4696-aae1-92db7d50e846" />

<img width="817" height="512" alt="image" src="https://github.com/user-attachments/assets/2f4eeed5-77d9-43bf-b3e3-b2c98a60d336" />

- 관리자 계정은 도착한 이메일의 본문과 첨부파일을 조회할 수 있습니다.
- 메일함에서는 메일 내용을 분석하고, 이를 바탕으로 이메일을 **견적**, **주문**, **스팸**, **기타**로 4가지로 분류하고 태그를 자동으로 붙입니다.

## 대시보드

<img width="1895" height="895" alt="image" src="https://github.com/user-attachments/assets/2b1c56b8-bee4-4f7e-84c7-fd00810a3451" />

![대시보드녹화5](https://github.com/user-attachments/assets/95fa71c9-76ec-424c-98e5-c0613ab5a251)

- 대시보드에서는 현재 배송 중인 건의 단계와, 배송 중일 경우 실시간 위치를 지도에서 조회할 수 있습니다.
- 카메라를 통해 컨테이너 내부 상황을 실시간으로 볼 수 있으며, 열림 감지, 온도, 습도 정보 등을 제공하여 물류가 정상적으로 배송되고 있는지 확인할 수 있습니다.
- 운송지에 도착한 후 **RFID 태그**를 찍어 운송 완료 처리를 할 수 있습니다.

## 채팅

<img width="942" height="424" alt="10-2 채팅링크메일(구글)" src="https://github.com/user-attachments/assets/46576363-d0f8-4a1a-b8a9-abbff6d9b501" />

- 견적 요청 메일을 보낼 때, 누락된 정보가 있다면 채팅 링크를 통해 추가 정보를 받을 수 있습니다.

<img width="1920" height="919" alt="image" src="https://github.com/user-attachments/assets/047512f4-d719-46b2-b88b-a73995d9c694" />

- 자연어를 이용해 유연하게 추가 정보를 입력받을 수 있습니다. 요청된 순서나 보기 내에서만 요청하는 것이 아니라, 필요할 때 돌발적인 정보도 요청할 수 있습니다. 특히, 사용자의 요청에 따라 Tavily(AI 기반 검색 엔진)를 이용해 최신 물류 뉴스와 운송 가능 지역을 제공할 수 있습니다.

<img width="602" height="232" alt="image (1)" src="https://github.com/user-attachments/assets/dfe9ae95-6839-45de-8aeb-111b73d6bc13" />

<img width="602" height="401" alt="image" src="https://github.com/user-attachments/assets/447c5cef-91ec-4479-b7bd-d4e050c5d395" />

<img width="602" height="263" alt="image (3)" src="https://github.com/user-attachments/assets/4277d8a1-9194-4269-97a1-282f4a3ad8ba" />

<img width="602" height="225" alt="image (4)" src="https://github.com/user-attachments/assets/8e08cce4-f01b-4930-a56e-860c713ca3be" />

- 영어, 일본어, 태국어 등 다른 언어로 요청할 시 해당 언어로 답변을 제공합니다.

# 워크플로우

---

<img width="2408" height="1685" alt="image" src="https://github.com/user-attachments/assets/eee69bda-1c72-4282-b39e-f126136223c0" />

# 개선사항

---

## 1. Lambda 사용을 통한 비용 절감

<img width="3542" height="1904" alt="image (5)" src="https://github.com/user-attachments/assets/1b0a5e16-dbc0-4bb0-9aaf-3f24c2f52798" />

## 2. AI

### 2-1. DistilKoBert 모델 학습 파이프라인 구축

<img width="3392" height="1600" alt="image" src="https://github.com/user-attachments/assets/d0032e08-d7d6-418d-89bb-cfcfe09c23d2" />

- 사람이 이메일 데이터의 분류를 확인하게 되면 SQS에 들어가게 되고, 특정 사이즈 이상이 될 경우 훈련 데이터로 사용되게 했습니다.

<img width="3125" height="1418" alt="image" src="https://github.com/user-attachments/assets/c7011048-2790-4149-b706-d726ab2ba14c" />

- 학습을 통해 85% 수치까지 개선되는 것을 확인하였습니다.

### 2-2. 이메일에서 견적에 필요한 정보 추출 모델 개발

<img width="500" alt="image" src="https://github.com/user-attachments/assets/758eabaf-914f-4ce3-bbdd-dc8fca6a70a1" />

- LM 스튜디오를 통해 여러 모델을 실행해보고 비교해보고, 가장 빠른 GPT-4o-mini 모델을 채택했습니다.

### 2-3. LangGraph + RAG 활용

<img width="3857" height="1910" alt="image" src="https://github.com/user-attachments/assets/c729b3dd-f5bc-44fd-9be0-68f2a60f0f85" />

- LangGraph를 활용하여, 디버깅을 유용하게 하고 Tavily라는 AI 에이전트(특히 LLMs)를 위해 최적화된 선도적인 검색 엔진을 활용하게 했습니다.
