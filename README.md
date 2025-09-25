# 데굴이: 자율주행 휠체어 로봇 (Deguli: Autonomous Wheelchair Robot)

## Prjoect Introducion
**병원 내 휠체어 이용 환자의 이동성 및 인력 효율 개선**을 목표로, **TurtleBot3**를 기반으로 자율주행 휠체어 로봇을 구현한 팀 프로젝트

- **역할** turtlebot3 환경설정, 인프라 관리, 파라미터 조정, 코드 테스트 및 보수, 발표자료 제작
- **진행 기간** 2023.04.01 ~ 2023.11.22  
>
> [Project Presentation Video](https://youtu.be/672hE6_kYBc)

</br>

## Tech stack
python2, python3, ROS1

ui: pyqt5
IDE: vscode

</br>
  
## Fuction
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

