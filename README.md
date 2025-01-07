# KIAPI_dataset
## Korea Intelligent Automotive Parts Promotion Institute(KIAPI) 
## <img src="https://github.com/Yunhyeongseok-kiapi/KIAPI_dataset/assets/85465084/9304bae8-7878-4b71-853f-08cff6392d4e" width="300" height ="100">
## Development of multi-agent simulation & test scenario generation SW for edge connected autonomous driving service verification
## Autonomous Driving Data

### Download Autonomous Driving(with V2X)        

#### Data #1   : [Download](https://gofile.me/7eXA5/zflXSoUeo)     

#### Data #2   : [Download](https://gofile.me/7eXA5/Gc8NbNusp)         

#### Data #3   : [Download](https://gofile.me/7eXA5/hBCu2ySd6)      

#### Data #4   : [Download](https://gofile.me/7eXA5/5VMLTsti0)         

#### Data #5   : [Download](https://gofile.me/7eXA5/0spcqUr01)               


※ **자율주행차량의 주행 데이터는 2023년 9월 19일에 실제 차량을 통해 계측한 데이터임**  
※ 차량에 장착된 센서 데이터와 실증도로 기반의 V2X 데이터를 포함하고 있음

### Download Simulation Driving data

#### Link :  [Download](https://gofile.me/7omT6/RKaMyMWgo)

※ 오픈 시뮬레이션인 'CARLA' 시뮬레이션을 활용하여 데이터 계측을 수행  
※ 교통류 환경을 기반으로 랜덤 객체들을 생성하고 자율주행을 수행  
※ 차량 정보, 센서 및 인프라 데이터를 포함하고 있으며, 전체 약 1,100km 정도의 주행거리를 포함하고 있음

### 1. 개요  
### Autonomous vehicle  
  * 차종(차명) : 승용(현대 IONIQ electric)  
  * Radar, Lidar 2대, GPS, Camera, OBU 장치가 장착되어 있음
<img src="https://github.com/Yunhyeongseok-kiapi/KIAPI_dataset/assets/85465084/98408c85-9d99-46f7-8550-357abb3a0c7e" width="650" height="350"> 

### Simulation  
  * CARLA는 자율 주행 시스템의 개발, 교육 및 검증을 지원하기 위해 처음부터 개발되었으며, 오픈 소스 코드 및 프로토콜 외에도 자유롭게 사용할 수 있는 오픈 디지털 자산(도시 레이아웃, 건물, 차량)을 제공  
  * 시뮬레이션 플랫폼은 센서 제품군, 환경 조건, 모든 정적 및 동적 액터의 전체 제어, 맵 생성 등을 유연하게 지정할 수 있음
<img src="https://github.com/user-attachments/assets/c98e2a31-a6c7-406f-8345-a67aa9bbc450" width="650" height="350"> 


#### 데이터 수집 리스트
##### 1) Autonomous vehicle  
  * 주행 데이터는 Ubuntu(Linux)의 ROS 환경 기반의 bag 포맷으로 계측을 진행하였음
  * 센서 데이터 및 차량에서 계측된 주행 데이터의 목록은 다음과 같음
  * 수집 데이터의 구조는 ROS에서 제공되는 구조와 자체 정의한 custom_msgs로 구성되어 있음
    (custom_msgs의 상세 구조는 과제 관련 2차년도 KIAPI 기술문서(엣지 인프라 및 자율주행차량 데이터 융복합 InterFace 구성 방안 설계서)에 정의되어 있음)
<img src="https://github.com/Yunhyeongseok-kiapi/KIAPI_dataset/assets/85465084/88d2a6f0-d19c-4efd-972b-025f06e6bcb1" width="612" height="682">

##### 2) Simulation  
   * 주행 데이터는 Ubuntu(Linux)의 ROS 환경 기반의 bag 포맷으로 계측을 진행하였음
   * 센서 데이터 및 차량에서 계측된 데이터의 목록은 다음과 같음  
     * /carla/ego_vehicle/gnss                               // 자차량의 gnss 정보  
     * /carla/ego_vehicle/imu                                // 자차량의 imu 정보  
     * /carla/ego_vehicle/lidar                              // Simulation의 Lidar 센서 정보  
     * /carla/ego_vehicle/odometry                           // 자차량의 odometry 정보  
     * /carla/ego_vehicle/rgb_front/image/compressed         // Simulation의 Camera 센서 정보  
     * /carla/ego_vehicle/target_speed                       // 자차량의 목표 속도 정보  
     * /carla/ego_vehicle/vehicle_info                       // 자차량의 차량 내부 정보  
     * /carla/ego_vehicle/vehicle_status                     // 자차량의 차량 상태 정보  
     * /carla/objects                                        // 주변 객체들의 상태 정보  
     * /carla/traffic_lights/info                            // 교차로 내 신호등 정보  
     * /carla/traffic_lights/status                          // 교차로 내 신호등 현시정보  
※ CARLA 관련 내용은 CARAL 시뮬레이션 Git(https://github.com/carla-simulator/carla.git)을 참고

### 2. 데이터 환경  
##### 1) Autonomous vehicle  
* 2023년 9월 19일에 실제 자율주행차량을 통해 계측한 데이터  
  * 약 140km 주행에 관한 데이터로 약 350GB
  * Linux(Ubuntu) ROS환경에서 제공되는 bag 포맷으로 저장
  * 대구 실증도로를 비롯한 주변 도로를 주행하면서 계측을 진행
    
* <주행 경로>
<img src="https://github.com/Yunhyeongseok-kiapi/KIAPI_dataset/assets/85465084/d4812db0-5712-483b-9be5-05802c870d5f" width="800" height="300">

* <주행 거리>
<img src="https://github.com/Yunhyeongseok-kiapi/KIAPI_dataset/assets/85465084/8bc505fc-fb99-4b23-adfa-cdc4a4549b16" width="800" height="300">

* <운행 정보 예시>
<img src="https://github.com/Yunhyeongseok-kiapi/KIAPI_dataset/assets/85465084/ed1465a1-063c-424c-93ba-598626b87935" width="800" height="500">  
