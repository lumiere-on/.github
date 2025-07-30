# 🤖터틀봇을 이용한 미로 학습
------
포스터자리
<img width="425" height="598" alt="Image" src="https://github.com/user-attachments/assets/c8b9db78-a48b-4a66-ad15-30cb73c1cd1e" />
------
### 프로젝트 소개
- 대학생 인공지능연합 동아리 프로메테우스 7기에서 진행한 프로젝트입니다.
- 시뮬레이션 환경인 Webot에서 터틀봇을 학습시킨 다음 실물 맵에서 터틀봇을 동작시켰습니다.
- 실제 구현한 맵 이외에도 다양한 맵에서 터틀봇을 동작시킬 수 있습니다.

-----
### 팀원 구성
|김용빈|문재원|전지윤|홍지연|
||||
||@lumiere-on||

### 1. 개발 환경
- 시뮬레이터: webot
- 로봇: 터틀봇
- 버전 및 이슈 관리: Github
- 터틀봇 환경: Docker
  
------
### 2. 데이터셋
- (터틀봇이 벽을 따라가는 데이터)
### 3. 프로젝트 구조
#### 3.1 Webot simulation
<pre>
```text
📁 webot_simulation  
├── 📁 controllers  
│   ├── 📁 wall_follower  
│   │   ├── data.csv  
│   │   └── wall_follower.py  
│   └── 📁 wall_follower_PID  
│       ├── data.csv  
│       └── wall_follower.py   
└── 📁 worlds  
    └── final_world.wbt
</pre>

#### 3.2 Turtlebot #### 

<pre>
```text
📁 turtlebot  
├── 📁 webots_ros2_turtlebot  
│   ├── 📁 webots_ros2_turtlebot  # turtlebot activation by rule-based controll
│   └── 📁 resource  # implement algorithm  
│   └── 📁 launch   # launch turtlebot on hardware and robot 
│   ├── setup.cfg
│   └── setup.py
└── 📁 .github/workflows  
    └── docker-build.yml 
├── Dockerfile
└── raspberry-pi-setup.sh  
<\pre>
----
### 4. 환경 구현 및 로봇 동작 단계

#### ✅ Step 1. 라즈베리파이 Wi-Fi 설정

1. 노트북과 라즈베리파이 보드를 **이더넷 케이블로 연결**합니다.
2. 터미널에서 다음 명령어로 라즈베리파이에 SSH 접속합니다:

   ```bash
   ssh simulsimul@192.168.0.49
   ```
3. 아래 두 파일을 열어 Wi-Fi ID 및 비밀번호를 수정합니다:

   * `wfa_supplicant.conf`
   * `50-cloud-init.yaml`
4. 설정 후 라즈베리파이를 재부팅합니다:

   ```bash
   sudo reboot
   ```
5. 재접속한 뒤, 다음 명령어로 Wi-Fi 설정을 적용합니다:

   ```bash
   sudo netplan apply
   ```
6. `ip a` 명령어로 Wi-Fi 인터페이스(wlan)의 IP가 할당되었는지 확인합니다.

   > ⚠️ Wi-Fi 연결에는 약간의 시간이 걸릴 수 있습니다.
   > 할당된 IP 주소를 복사해 두세요.

---

#### ✅ Step 2. 노트북과 라즈베리파이 무선 연결

* 이더넷 케이블을 제거하고, **무선(Wi-Fi)으로 연결**합니다.
* 복사해둔 IP 주소를 사용하여 SSH 접속합니다:

  ```bash
  ssh simulsimul@<라즈베리파이 IP 주소>
  ```

---

#### ✅ Step 3. Docker 이미지 다운로드

* 다음 명령어로 Docker 이미지를 내려받습니다:

  ```bash
  docker pull ybkim4053/simulsimul:latest
  ```

  > 💡 참고: Wi-Fi가 연결된 상태라면 자동으로 최신 이미지를 받도록 설정되어 있습니다.
* 이미지가 정상적으로 설치되었는지 확인합니다:

  ```bash
  docker images
  ```

---

#### ✅ Step 4. 컨테이너 실행

* 다음 명령어로 컨테이너를 시작합니다:

  ```bash
  sudo systemctl start turtlebot-auto
  ```
* 컨테이너 실행 여부를 확인합니다:

  ```bash
  docker ps
  ```
* 만약 실행되지 않았다면, 아래 명령어로 재시작해봅니다:

  ```bash
  sudo systemctl restart turtlebot-auto
  ```

---

#### ✅ Step 5. 실행 로그 확인 및 로봇 동작 확인

* 로그를 실시간으로 보며 터틀봇이 정상적으로 동작하는지 확인합니다:

  ```bash
  sudo docker logs turtlebot-auto -f
  ```

---


----
### 5. 개발 기간 및 작업 관리



----
### 6. 역할 분담




----
### 7. 개선 목표



----
### 8. 프로젝트 후기

