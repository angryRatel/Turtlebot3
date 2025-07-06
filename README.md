## 디지털 트윈 기반 서비스 로봇 시스템 구성

### detect_lane에 중점을 두고 aruco_detect로 Manipulation을 작동하는 것을 서브로 프로젝트를 진행함
---
### 시나리오 구성보다 코드 분석에 중점을 둔 프로젝트

### 시현 영상 : https://youtube.com/shorts/JMnDxCcO9bU?feature=share
---
### 실제 사용시 관련 사이트에서 파일을 다운 후 사용
### Turtlebot3 홈페이지 : https://emanual.robotis.com/docs/en/platform/turtlebot3/quick-start/

---

### 설명 순서

#### 1. Camera calibration
카메라 시점을 calibration과 image_raw 값을 받도록해 라인을 잘볼 수 있도록 수정후

![제목 없음](https://github.com/user-attachments/assets/6becd47b-97c9-4232-ba3e-52231181b117)

![1](https://github.com/user-attachments/assets/bf3f3783-5f5d-4dcf-a7fa-a29712724e83)


##### 2. ArUco Macker

직접 아르코 마커를 위한  calibration을 추가 진행

![2](https://github.com/user-attachments/assets/e0323ad8-20b0-4071-be4a-b4a4f49276ae)

![3](https://github.com/user-attachments/assets/3b6d4c11-e446-4fc8-adda-8b32225c55b3)



#### 3. controll lane.py
로봇이 라인을 이탈하면 스스로 돌아오게 코너를 돌때 속도를 줄이게 코드 작성


#### 4. Detect_lane.py

라인을 트레이싱 할때 조향의 영향을 받지 않게 조건 부여

##### 1. 프레임 스킵
##### 2. 밝기 측정
##### 3. 차선 마스킹
##### 4. 곡률 기반 필터링
##### 5. 곡선 추정 실패 시 대처
##### 6. 시각화 및 퍼블리싱
##### 7. 밝기 보정 및 반사 처리
##### 8. 신뢰도 기반 로직 적용

#### 5. Turtlebot_arm_controller.cpp
간단한 코드 분석을 진행

#### 5. Pick_n_place.py
##### 초기자세 설정
##### 아르코를 인식하는 토픽을 구독
##### 아르코를 인식시 물체를 집도록 코드 시나리오 작성
![4](https://github.com/user-attachments/assets/a908ae5a-6856-4fdf-8776-f9ac8c2921f7)


##### 추가 설명은 ppt 참고
