# KIAPI_dataset
## Korea Intelligent Automotive Parts Promotion Institute(KIAPI) 
## <img src="https://github.com/Yunhyeongseok-kiapi/KIAPI_dataset/assets/85465084/9304bae8-7878-4b71-853f-08cff6392d4e" width="300" height ="100">
## Autonomous Driving Data

### Download Autonomous Driving(with V2X)        

#### Data #1   : [Download](https://gofile.me/7eXA5/zflXSoUeo)     

#### Data #2   : [Download](https://gofile.me/7eXA5/Gc8NbNusp)         

#### Data #3   : [Download](https://gofile.me/7eXA5/hBCu2ySd6)      

#### Data #4   : [Download](https://gofile.me/7eXA5/5VMLTsti0)         

#### Data #5   : [Download](https://gofile.me/7eXA5/0spcqUr01)               


※ **자율주행차량의 주행 데이터는 2023년 9월 19일에 실제 차량을 통해 계측한 데이터임**  
※ 차량에 장착된 센서 데이터와 실증도로 기반의 V2X 데이터를 포함하고 있음

### 1. 개요  
### Autonomous vehicle  
  * 차종(차명) : 승용(현대 IONIQ electric)  
  * Radar, Lidar 2대, GPS, Camera, OBU 장치가 장착되어 있음
<img src="https://github.com/Yunhyeongseok-kiapi/KIAPI_dataset/assets/85465084/98408c85-9d99-46f7-8550-357abb3a0c7e" width="650" height="350"> 

#### 데이터 수집 리스트
  * 주행 데이터는 Ubuntu(Linux)의 ROS 환경 기반의 bag 포맷으로 계측을 진행하였음
  * 센서 데이터 및 차량에서 계측된 주행 데이터의 목록은 다음과 같음
  * 수집 데이터의 구조는 ROS에서 제공되는 구조와 자체 정의한 custom_msgs로 구성되어 있음
    (custom_msgs의 상세 구조는 과제 관련 2차년도 KIAPI 기술문서(엣지 인프라 및 자율주행차량 데이터 융복합 InterFace 구성 방안 설계서)에 정의되어 있음)
<img src="https://github.com/Yunhyeongseok-kiapi/KIAPI_dataset/assets/85465084/88d2a6f0-d19c-4efd-972b-025f06e6bcb1" width="612" height="682">  

### 2. 데이터 환경  
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
