# 데굴이: 자율주행 휠체어 로봇 (Deguli: Autonomous Wheelchair Robot)

## Project Introducion
**병원 내 휠체어 이용 환자의 이동성 및 인력 효율 개선**을 목표로, **TurtleBot3**를 기반으로 자율주행 휠체어 로봇을 구현한 팀 프로젝트

- **진행 기간** 2023.04.01 ~ 2023.11.22
- **역할**
  **TurtleBot3 환경을 설정하고 ROS1 기반 인프라를 관리**하여 프로젝트의 안정적 실행을 지원.  
  로봇 주행 및 UI 동작에 필요한 **파라미터 조정**을 수행하고, 코드 전반에 대한 **테스트 및 유지보수**를 담당.  
  개발 과정 전반에서 시스템 안정성과 신뢰성을 확보하며 프로젝트 완성도 향상에 기여.
- **영상** [Project Presentation Video](https://youtu.be/672hE6_kYBc)
 <img width="400" alt="introduce_1" src="https://github.com/user-attachments/assets/2f0f399c-a721-4449-aeb9-3a877dbbe740" />
 <img width="400" alt="introduce_3" src="https://github.com/user-attachments/assets/9c0644e5-5825-4012-9fa9-1e4fef79548e" />

</br>

## Tech stack
ROS1, Python2, Python3, YAML <br>
UI: PyQt5 <br>
IDE: VSCode

</br>
  
## Fuction
<img width="600" alt="introduce_2" src="https://github.com/user-attachments/assets/1c80e79a-208d-4c09-bccc-af69538a0d94" /> 
### 자율주행
- 목적지 선택 및 주행 시작 클릭 시 tts로 음성안내 및 서버로 목적지 publishing
- 서버에서 최적 경로를 연산하여 모터 제어 명령을 subscribe

> 목적지 설정 클릭 -> 목적지 선택 -> 주행 시작 클릭

### 수동주행
- ui에서 버튼 클릭 시 해당 방향으로 주행하도록 모터에 명령

### 긴급호출
- 환자 위급상황 발생 시 해당 버튼을 클릭 -> 관제 측에 알림 전송 및 tts 음성안내


## main src code
### runOnLaptop
- remote PC에서 원격제어를 목적으로 서버 관리
### runOnTurtlebot3
- emrCall.py: 긴급호출 관련 메서드 관리 - tts, 관제 알림
- emrCall_ui.py: 긴급호출 페이지 ui
- loading.py: 관제 측에서 모터 제어 시 화면 비활성화를 위한 메서드 관리
- main.py: 어플리케이션의 동작 및 실행 관리
- mainPage_ui.py: 메인화면 페이지 ui
- manualDriving.py: 수동주행 관련 메서드 관리 - 모터 제어
- manualDriving_ui.py: 수동주행 페이지 ui
- selDestination.py: 자율주행 관련 메서드 관리 - 목적지, 서버 publishing
- selDestination_ui.py: 자율주행 페이지 ui
### etc
- sudong.py: 서버에서 수동주행 버튼값 subscribe 및 주행명령
- tf_publishing: 3초마다 관제 측에 현재 위치 값 전송(python2)

