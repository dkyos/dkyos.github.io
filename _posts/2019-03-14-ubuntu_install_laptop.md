---
title: "노트북에 Ubuntu 설치"
date: 2019-03-14 00:00:00 -0900
categories: ML Engineer
---

우분투(18.04) 설치 과정
---------------
* 회사에서 개발/시연 등으로 사용하는 노트북이 하나 있습니다. 
* Nvidia GPU 노트북(NT800G5W-XD7S 모델)으료 교체할 수 있는 기회가 생겨서 우분투 설치를 시도했습니다. 
* UEFI, Nouveau 로 고생 끝에 결국 설치를 완료했습니다. 

우분투 설치 과정
---------------
* UEFI(Unified Extensible Firmware Interface) 관련 이슈 #1
  * BIOS 설정 들어가서 인터넷 자료 보고 Secure Boot Off하고 booting 순서 바꾸면 문제 없이 설치 진행합니다. 
  * UEFI 모드 진입 단축키: F2

* Nouveau(우분투 기본 그래픽 드라이버) 관련 이슈
  * Nvidia 그래픽 카드 장착 노트북의 경우 설치 화면이나 우분투 사용 화면에서 Nouveau 드라이버가 문제가 되어 Hang(Freeze) 이슈가 발생합니다. 
  * 설치 혹은 부팅 과정에서 "shift" 키로 복구 모드에서 부팅 옵션에 아래 사항을 추가해야 합니다. 
  * "quiet splash" 부분 없애고 "nouveau.modeset=0" 추가 후 F10으로 부텅하면 이슈가 해결됩니다. 
  * 우분투 설치 후 Nvidia 그래픽 드라이버 설치하면 문제 발생하지 않습니다. 
 
* UEFI(Unified Extensible Firmware Interface) 관련 이슈 #1
  * 파티션 구성할 때 Ubuntu가 알아서 구성하도록 선택하면 정상 설치/동작됩니다. 
  * 기타를 선택해서 예전 BIOS 방식처럼 Booting  영역 잡고 등으로 파티션을 구성하면 부팅 영역을 찾지 못해서 문제가 발생합니다. 
  * 귀찮아서 우분투가 알아서 구성하도록 했습니다. 개인에 맞추어 파티션 구성을 원할 경우 인터넷 자료 잘 찾아보고 파티션 구성하면 되겠습니다. 
