# KIAPI_dataset
## Korea Intelligent Automotive Parts Promotion Institute(KIAPI) <img src="https://user-images.githubusercontent.com/85465084/206626658-6b1c7aee-bce9-48f9-86bd-207140e3bd0d.jpg" width="300" height ="100">
## Infra Dataset

### Download#1 PVD Data : [Download](http://gofile.me/5HZpx/Ah4coBH2c)

### 1. 개요  
### infra envrionment  
  * 인프라 데이터는 도심로 2.4km, 자동차전용도로 12.9km 총 15.3km에 구축되어있는 대구 실증지역(대구 달성군 테크노폴리스로 일대)에서 계측을 진행하였음  
  * 신호등, 합류/분기로, 지·정체 구간 등의 데이터 계측이 가능
  * RSU, 돌발상황 검지기, 보행자검지기, 측위보정기준국 등의 인프라가 구축되어 있음  
  * 차량간 무선 통신을 통하여 돌발상황 정보를 전송하고 지능형 교통체계와 연동하여 실시간 교통 정보 제공이 가능
  #### 인프라 구성
   |  인프라 | 수량  |  설명  |  
   |:---------:|:--------:|--------------------------|  
   | RSU | 18식 | 차량과 차량, 차량과 인프라 간 통신이 가능한 WAVE 통신 기지국 </br> - (상행) 일부 터널을 제외한 모든 구간 WAVE 통신 가능 </br> - (하행) 터널을 제외한 모든 구간 WAVE 통신 가능 |  
   | 돌발상황검지기 | 3식 | 도로에서 발생하는 돌발상황(역주행, 정지차, 보행자, 지·정체 등) 검지(SAE J2735 - RSA) </br> - 합류로 분기로, 교통 정체 구간에 설치(김흥, 기세, 본리) </br> - C-ITS 서비스 중 3가지(합류로, 분기로, 교통 정체 구간) 제공 가능
   | 보행자검지기 | 2식 | 횡단보도 주변에서 발생하는 돌발상황(보행자 무단횡단 및 정상횡단 등) 검지 </br> - 유가사입구사거리, 휴양림입구사거리에 설치 |
   | 신호제어기 | 4식 | 신호등 주기 및 현시 정보를 차량에 제공(J2735 - SPaT) </br> - 유가입구사거리, 휴양림입구사거리, 수목원 3주차장, 수목원 2주차장에 설치 |
   | CCTV | 8식 | 시험차량 거동 정보 추적 및 녹화를 통한 영상 데이터 제공 </br> - 유가사입구사거리, 휴양림입구사거리에 설치 |
   | 측위보정기준국 | 1식 | DGPS 원리를 이용하여 실증도로 구간에서 정밀한 차량 위치 정보 제공 </br> - 테크노폴리스로 중간지점에 설치 |
   | RFID | 2식 | 시험 차량 식별 및 테스트 시작/종료 시점 정보 제공 </br> - 유가사입구사거리 및 휴양림입구사거리에 설치 |
<img src="https://user-images.githubusercontent.com/85465084/206636026-c0faf0ff-6fd6-44a3-ad7e-f188941b2c34.PNG" width="850" height="330">  

### 2. 데이터셋  
* 인프라 데이터는 국제 표준 SAE J2735 데이터 규격을 따름  
  * SAE J2735는 V2V/V2I 통신을 위한 메시지, 데이터 프레임, 요소 형식 및 구조 등 신호 규격에 대한 정의를 포함하고 있음  
  * 2017년 기준으로 메시지 17개, 데이터 프레임 156개, 데이터 요소 230개, 외부 정의 참조 데이터 요소 58개로 구성되어 있고, 개체들은 ASN(Abstract Syntax Notation 1) 방식으로 정의되어 있음
* 본 데이터셋은 도로 내 구축된 RSU 장비별 C-ITS 메시지 수집 데이터(PVD(Probe Vehicle Data), SPaT(Signal Phase and Timing), RSA(Road Side Alert), TIM(Traveler Information Message))를 공유함
#### 1) PVD data(obu_state.csv)
* 차량 운행 행테에 관한 정보를 포함하고 있음
* 노변장치(RSU)를 통해 차량의 상태(브레이크 작동 여부 등), 위치(경도, 위도, 고도), 운행정보(방향, 감가속도 등)를 포함하고 있으며, 이벤트 발생 시 위치 및 시간정보를 송신함  
  ##### obu_state 구조 정의
  |  Name | Type  |  Unit  |   Value   |   Description    | 
  |:-----:|:-----:|:------:|:---------:|------------------|  
  |lod_id         |bigint  |-            |-                              |데이터 log id|
  |obu_id        |integer  |-            |-                              |obu id|
  |Latitude      |integer  |$10^{-7}$ deg|INTEGER (-900000000..900000001)|차량의 위도 정보|
  |Longitude     |integer  |$10^{-7}$ deg|INTEGER (-179999999..180000001)|차량의 경도 정보|
  |Elevation     |integer  |0.1 m        |INTEGER (-4096..61439)         |차량의	고도 정보|
  |Velocity	     |integer  |0.02 m/s	    |INTEGER (0..8191)              |차량의	속도 정보|
  |Accel_lon     |integer  |0.01 $m/s^2$ |	INTEGER (-2000..2001)         |종방향 가속도 정보|
  |Accel_lat     |integer  |0.01 $m/s^2$ |	INTEGER (-2000..2001)         |횡방향 가속도 정보|
  |Accel_yaw     |integer  |0.01 deg/sec |	INTEGER (-32767..32767)       |	yaw 가속도 정보|
  |Heading	      |integer  |0.0125 deg  	|INTEGER (0..28800)             |차량의	방향 정보|
  |Steering_angle|integer  |1.5 deg      |INTEGER (-126..127)            |차량의 조향각 정보|
  |Brake	        |character|-	           |-	                             |브레이크 동작 여부|
  |Brake_pressure|integer	 |-	           |-	                             |브레이크 압력 정보|
  |Transmission_state|integer|-          | 0x00 : Neutral </br> 0x01 : Parking </br> 0x02 : Drive </br> 0x03 : Rear | 차량 기어 변속 정보|
  |Exterior_light|integer  |-            | 0 : Low-beam </br> 1 : High-beam </br> 2 : Left turn </br> 3 : Right turn </br> 4 : Hazard signal | 차량 외부등 상태 정보|
  |rsu_id        |integer  |-            |-                              |rsu id|
  |created_time  |date     |-            |-                              |메시지 생성 시간|
  |rssi          |integer  |dm           |-                              |수신 신호 세기(강도) 정보|

#### 2) SPaT data(rsu_signal.csv)
* 교차로의 상세 정보를 포함하고 있음
* 인프라에서 차량으로 제공되는 I2V(Intra to Vehicle) 메시지로써, 교차로의 현재 및 다음 제어 상태를 의미함
  ##### rsu_signal 구조 정의
  |  Name | Type  |  Unit  |   Value   |   Description    | 
  |:-----:|:-----:|:------:|:---------:|------------------|  




  
  
