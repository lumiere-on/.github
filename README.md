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

#### 3.2 Turtlebot 
📁 turtlebot  
├── 📁 controllers  
│   ├── 📁 wall_follower  
│   │   ├── data.csv  
│   │   └── wall_follower.py  
│   └── 📁 wall_follower_PID  
│       ├── data.csv  
│       └── wall_follower.py   
└── 📁 worlds  
    └── final_world.wbt
----
### 4. 환경 구현 및 동작 



----
### 5. 개발 기간 및 작업 관리



----
### 6. 역할 분담




----
### 7. 개선 목표



----
### 8. 프로젝트 후기

