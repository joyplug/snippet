---
layout: post
title:  "[minecraft] 마인크래프트 서버 오픈 Ver1.0"
date:   2021-11-12 09:00:00 +0900
categories: [minecraft,server]
---

### 다운로드
> [https://www.oracle.com/java/technologies/downloads/#java16](https://www.oracle.com/java/technologies/downloads/#java16)
> [https://getbukkit.org/download/craftbukkit](https://getbukkit.org/download/craftbukkit)

<br>

### server.bat
```bash
@echo off
java -Xms128M -Xmx1G -jar craftbukkit-1.17.1.jar
pause
```
<br>

### eula.txt
```
#By changing the setting below to TRUE you are indicating your agreement to our EULA (https://account.mojang.com/documents/minecraft_eula).
#Fri Sep 24 12:27:33 KST 2021
eula=true
```
<br>

### server.properties
```
allow-nether //지옥활성화 여부 설정
level-name //맵의 이름 설정
allow-flight //플레이어가 날 수 있을 지 여부 설정
level-type //DEFAULT(기본), FLAT(평지), LARGEBIOME(증폭)
spawn-npcs //NPC 소환 여부 설정
white-list //화이트리스트에 허용된 유저만 접속할 지 여부 설정
spawn-animals //동물의 소환 여부 설정
hardcore //서버의 게임모드를 하드코어 (죽을 시, 서버에서 밴당함)
pvp //플레이어간의 공격을 허용할 지 설정
difficulty //서버의 난이도를 설정 0(평화), 1(쉬움), 2(보통), 3(어려움)
enable-command-block //커맨드블록을 사용할 지 설정
max-players //서버 최대 동시접속자
motd //서버-닉의 motd를 설정합니다. 영어로만 설정
```
<br>

### 포트 포워딩
```
1. 포트포워드 설정 : UDP 기본포트 19132 로 IP 포트포워드 설정
2. DMZ/TwinIP설정 : DMZ, 현재 접속된 PC의 IP주소로 설정 후 적용
3. 외부 IP 주소로 서버 주소 공유하기
4. 필요시 codns.com 도 사용가능
```
<br>

### 도메인 설정
> [https://내도메인.한국](https://내도메인.한국)  
> ![image](/snippet/static/img/_posts/domain_korea.png)

<br>

### 플러그인(server/plugins && /pl)
https://dev.bukkit.org/bukkit-plugins
```
1. EssentialsX
2. WorldEdit for Bukkit
```
<br>

### 서버 스폰 지역 설정
```
1. https://www.youtube.com/watch?v=9m6rQFBZiIQ&list=PL7GExJh5AB98hND1YMxWr_zXUDUAilp58&index=6
2. /setspawn - 자신이 서 있는 곳을 서버의 스폰지점으로 설정함 (EssentialX 플러그인)
3. 엔더상자 - 아이템 초기화 방지 관리
4. 표지판 - 환영인사 & 서버규칙
```
<br>

### World Edit & //copy & //paste
```
1. //wand - 나무도끼
2. Left click : 첫번째 지점 #1
3. Right click : 두번재 지점 #2
4. 대각 방향으로 click
5. 두번째 지점에서 //copy
6. 이동해서 //paste
```
<br>

### World Edit & //replace
```
1. //wand
2. 잔디블록(2) -> 눈블록(70)
3. //replace 2 80
4. 자작나무잎(18:2) -> 꽁꽁언얼음(174)
5. //replace 18:2 174
```
<br>

### World Edit & //set
```
1. //wand
2. Left click #1 -> Right click #2
3. 양털(35:x)
4. //set 35,35:14
5. //undo
6. //set 35,35:14,35:4,35:2,35:15
7. //wand
8. Left click #1 -> Right click #2
7. //walls 57,42
8. //wand
9. Left click #1 -> Right click #2
10. //hcyl 5:1,5,5:2 5 5 (빈원기둥)
```
<br>

### 자신이 원하는 맵 서버 적용
```
1. 맵다운로드 후 압축풀기
2. 푼 파일을 world 폴더 안 지운후 복사하기
3. 오류발생 시 players와 MCEDIT 폴더 삭제해보기
```
<br>

### 서버 오류 FAQ
```
1. 윈도우 방화벽 해제
2. Bad Login : server.properties && online-mode= false //정품유저 뿐만이 아니라 복돌유저도 접속 가능
```
<br>

### 버킷 없이 LAN 서버 열기
> [https://www.vpn.net](https://www.vpn.net)
```
1. 싱글플레이
2. 새로운 세계 맵 만들어 들어가기
3. 하마치 설치 및 가입
4. 네트워크 -> 새 네트워크 만들기 -> 네트워크 아이디 & 비밀번호 설정 -> 만들기
5. 친구에게 하마치 깔라고 요청
6. 친구는 네트워크->기존 네트워크에 가입 눌러서 네트워크 아이디/비밀번호 입력
7. ESC && LAN 서버 열기
8. '로컬 게임이 포트 XXX에서 열렸습니다'
9. 하마치에서 IPv4 주소 복사
10. "IP주소:포트" 친구에게 공유해주기
```
<br>

### 서버에 리소스팩 적용하기
> [https://www.9minecraft.net/tag/popular-resource-packs](https://www.9minecraft.net/tag/popular-resource-packs)
```
1. 리소스팩 다운로드
2. 다음블로그에 업로드(~10MB) 후 등록
3. 리소스팩 파일의 {링크주소} 따기
4. server.properites && resource-pack={링크주소}
5. 서버접속 시 서버리소스 팩 사용 물어보기 확인
```
<br>

### 명령어로 인벤토리 초기화 안되게 하는 방법
```
/gamerule keepInventory true
```
<br>

### 서버 아이콘 적용하기
```
1. 구글검색 && herobrine && 이미지 && 사용권한 && 수정 후 재사용 가능 
2. 포토샵 64x64로 리사이즈 && png로 저장
3. 서버버킷폴더로 아이콘 이미지 복사 (server-icon.png)
```

<br>

