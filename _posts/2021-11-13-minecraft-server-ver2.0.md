---
layout: post
title:  "[minecraft] 마인크래프트 서버 오픈 Ver2.0"
date:   2021-11-13 09:00:00 +0900
categories: [minecraft,server]
---

### 1. 페이퍼 구축기 다운로드
> [https://papermc.io/downloads](https://papermc.io/downloads)

### 2. server.bat 만들기
```
java-Xms1G -Xmx2G -jar paper-27.jar
pause
```

### 3. eula.txt -> eula:true

### 4. server.bat 실행

### 5. 포트포워딩 설정 (TCP/UDP : 25565)

### 6. 고급 NAT 설정 (DMZ 체크)

### 7. 포트포워딩 테스트
> [https://www.yougetsignal.com](https://www.yougetsignal.com)  
> Port Forwading Tester // IP:25565 Check 후 초록깃발 확인

### 8. server.properties
```
- spawn-protection=16 : 스폰지역으로부터 몇 블록까지 지역보호 할지 설정
- allow-nether=true
- gamemode=survival : creative/survival
- difficulty=easy : easy/peaceful/hard/normal
- spawn-monsters=true
- pvp=true
- level-type=default : default/flat(평지맵)/largebiome(넓은생물군계)/amplified(증폭)
=> world 폴더 삭제 후 재실행
- hardcore=false : 서버에서 죽으면 다시 서버로 못 들어오게 할 것인지 설정
- enable-command-block=true: 명령 블록 사용을 허용할 지 설정, 레드스톤 회로
- max-players=20
- server-port=25565 - 포트포워드 포트
- server-ip=  - 빈칸으로 둘 것
- spawn-npcs=true
- allow-flight:true
- resource-pack=....
- spawn-animals=true
- white-list=false
- generate-structures=true : 유적지/피라미트/NPC 마을등의 구조물 설정 가능 여부
- max-build-height=256 : 블럭을 쌓을 수 있는 최대 높이
- online-mode=false : 서버 정품 유저만 들어오게 하기
- motd=A DL-linza Servere : 서버 설명
```
<br>
