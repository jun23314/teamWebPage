+++
title = "Container - Second Blog"
date = "2023-05-21T13:50:46+02:00"
tags = ["Container"]
categories = ["container"]
authors = ["부승민"]
+++

Container - First Blog에 이어서

운영체제 수준의 가상화 & 빠른 속도와 효율성

Virtual Machines(하드웨어 레벨의 가상화)
Virtual Machines(VM ware, VirtualBox) 의 경우 하이퍼바이저(virtual box, Xen, KVM, VMware) 위에 Guest OS가 올라가는데 그 위에 Binary와 라이브러리 등을 모두 구성해야 하기에 무겁고 성능 저하가 발생합니다. (오버헤드 발생)

Docker(Linux)(운영체제 레벨의 가상화)
VM과 HostOS 까지 설치는 동일합니다. 하이퍼바이저가 필요 없고 도커 엔진만 있으면 그 위에 어플리케이션과 바이너리 및 라이브러리가 포함된 컨테이너만 올리면 되는 구성입니다.

가상화 종류:
1. 개발환경 가상화
 개발 인터프리터
 라이브러리
2. OS 수준 가상화:리눅스 컨테이너
 OS의 독립돤 공간 격리
 isolation(격리, 고립)
3. 머신 가상화
 HW를 emulation(모방 경쟁)
 하이퍼바이저

도커 설치(wsl Ubuntu):

공식 홈페이지 참고 : https://docs.docker.com/engine/install/ubuntu/
설치 확인 : docker --version, ps -ef |grep docker
현재 최신 버전 : 23.0
사전 작업 : 저장소 설정(도커 설치를 위한 저장소를 설정)
• 1. apt 패키지 인덱스(소스 리스트) 업데이트하고 필요 패키지 설치
sudo apt-get update
sudo apt-get install \
ca-certificates \
curl \
gnupg
• 2. 도커 공식 GPG 키 추가
sudo mkdir -m 0755 -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
• 3. 저장소 셋업(아래는 하나의 명령)
echo \
"deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] 
https://download.docker.com/linux/ubuntu \
"$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
설치
• apt 패키지 인덱스(소스 리스트) 업데이트
sudo apt-get update
• 도커 엔진, containerd, 도커 컴포즈 설치
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

