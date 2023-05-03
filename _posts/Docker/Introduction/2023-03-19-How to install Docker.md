---
title: Docker 설치
author: Hajun
date: 2023-05-03 21:30:00 +0900
categories: [Docker, Introduction to Docker]
tags: [docker, installation, macos, ubuntu, linux]
---

![datatype](../../../image/docker.png)

## 1. 도커 설치 in Mac OS
- - -
  1. https://docs.docker.com/desktop/install/mac-install/ 링크 접속.
  2. Intel chip이면 왼쪽, M1 or M2를 사용하면 오른쪽 선택.
  3. 설치.
  4. docker 입력 후 여러 명렁어 나오면 설치 완료.



## 2. 도커 설치 in Linux(Ubuntu)
- - - 
  1. Ubuntu에서 Terminal 열기
  2. sudo apt-get update
  3. sudo apt install docker.io
  4. sudo snap install docker
  5. docker --version or docker -v
  6. sudo docker run hello-world
  7. sudo docker images
  8. sudo docker ps -a
  9. sudo docker ps

#### 2.1 sudo 없이 도커 실행
- - -
  1. 도커 그룹 생성
  ```
  sudo group add docker
  ```
  2. 도커 그룹에 유저 추가
  ```
  sudo usermod -aG docker ${USER}
  ```
  3. 도커 재시작
  ```
  sudo service docker restart
  ```
  4. 현재 사용자 재로그인
  ```
  sudo su -       //root로 변경
  su - username   //user로 변경 
  ```
  5. 테스트
  ```
  docker run hello-world
  ```