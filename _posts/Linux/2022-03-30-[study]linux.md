---
title: "Linux"
excerpt: "About Linux and useful commands"
excerpt_separator: "<!--more-->"
categories:
  - Linux
tags:
  - Linux
last_modified_at: 2022-03-30T20:40:00
---

<!--more-->

<br>

## LINUX

#### LINUX란?

- LINUX는 오픈소스 운영체제(Operating System, OS)로서, CPU, 메모리, 스토리지와 같은 시스템 하드웨어와 리소스를 직접 관리하는 소프트웨어이다.
- 그러나 실제로는 OS라기 보다는 OS의 핵심 소스코드 역할인 커널이다.
- OS = App(응용 프로그램) + Shell ==> 즉, 리눅스에 App과 Shell을 추가하여 만든 하나의 운영체제를 리눅스 배포판이라고 한다.
- **Shell: 운영체제 내부에 접근하기 위한 프로그램. 시스템 사용자와 커널의 인터페이스 역할을 담당한다. 즉, 커널을 제어할 수 있는 프로그램이다. 단, 모든 OS에 반드시 포함되지는 않는다.**

#### LINUX 구조

![LINUX Structure](/assets/img/linux structure.png)

- UNIX와 상당 부분 유사하게 설계되어 있다.
- 하드웨어 위에 운영체제가 있고, 운영체제가 제공해주는 환경에서 응용 프로세스들이 실행된다.
- LINUX 포함 요소
  - 커널: OS의 기본 구성 요소
  - 시스템 사용자 공간: 설정 및 소프트웨어 설치와 같은 시스템 수준 태스크를 위한 관리 계층.
  - 애플리케이션: 태스크를 수행할 수 있도록 지원하는 소프트웨어 유형.
- 그 중 핵심은 커널(Kernel)로서, 커널의 역할은 다음과 같다.
  - OS를 구성하는 프로세서와 OS의 제어로 수행되는 프로그램에 대하여 자원을 할당하는 역할을 한다.
  - 프로세스 관리, 메모리 관리, 태스크 관리, 시스템 관리 등이 있다.
- 커널은 항상 메인 메모리에 상주하며 하드웨어를 추상화시켜 사용자 레벨 프로세스에 서비스를 제공한다. ==> 시스템 콜 방식 사용
- **시스템콜(System Call): 운영 체제의 커널이 제공하는 서비스에 대해, 응용 프로그램의 요청에 따라 커널에 접근하기 위한 인터페이스.**

#### LINUX 특징

- LINUX는 프로세스를 제외한 모든 것을 파일로 취급한다. 디렉토리 역시도 파일이다.
  - 프로세스: 컴퓨터 내에서 프로그램을 실행하는 주체.
  - 파일: LINUX 시스템 내의 모든 정적 요소
- LINUX의 파일 시스템은 "/"에서 파일 관리를 시작한다. 이 경로는 Root 경로이다.
  - 파일 시스템: 파일을 관리하는 방법
  - 파일 시스템의 이름은 NTFS, EXT4, FAT32 등이 있다.
- 윈도우의 디렉토리와 리눅스의 디렉토리는 다음과 같이 대응한다.
  - 윈도우 Program Files: 리눅스 /bin
  - 윈도우 Windows\System: 리눅스 /sbin
  - 윈도우 "사용자": 리눅스 Home

#### LINUX 장단점

- 장점

  - 무료
  - CLI를 기반으로 사용하면 매우 가볍다.
  - 네트워킹 기능이 강력하다. ==> 다중 사용자
  - 다른 플랫폼에 대한 이식성이 뛰어나다.
  - 다양한 파일 시스템을 지원한다.
  - 보안성이 비교적 뛰어나다.
  - 다양한 응용 프로그램이 존재한다.

- 단점
  - 기술 지원이 부족하다.
  - 특정 하드웨어에 대해서는 따로 세팅이 필요하다.
  - 사용자의 진입장벽이 높다.
  - 꾸준한 업데이트에 따라가기 위해 사용 방법에 대한 공부가 지속적으로 필요하다.

#### LINUX 기본 명령어

1. 터미널 실행: [Ctrl] + [Alt] + T
2. 터미널 종료: exit
3. 디렉토리 목록: ls

- a 옵션: 숨김파일까지 출력 <== 숨김파일은 .으로 시작한다.
- l 옵션: 리스트 형태로 상세 보기

4. 컴퓨터 종료: sudo halt -p
5. 컴퓨터 재시작: sudo reboot
6. 복사: [Ctrl] + [Insert]
7. 붙여넣기: [Shift] + [Insert]
8. 터미널 스크롤 올리기: [Shift] + [PageUp]
9. 현재 디렉토리 확인: pwd
10. 화면(콘솔 창) 지우기: clear OR [Ctrl] + l
11. 디렉토리 이동: cd [디렉토리 이름]

- cd .. : 상위 디렉토리로 이동
- cd ~ : 홈 디렉토리로 이동
- cd - : 이전 디렉토리로 되돌아가기
- cd / : 루트 디렉토리로 이동

12. 새 탭 열기: [Ctrl] + [Shift] + T
13. 탭 전환: [Alt] + 1, 2, 3...
14. 탭 닫기: [Ctrl] + [Shift] + W
15. 화면 출력 중단: [Ctrl] + S
16. 화면 출력 재시작: [Ctrl] + Q
17. 파일 복사: cp [파일명 or 폴더명]
18. 새로운 빈 파일 생성: touch [파일명]

- 여러 이름을 공백으로 구분하여 기재하면 동시에 생성 가능하다.

19. 파일 삭제: rm [파일명]

- 여러 이름을 공백으로 구분하여 기재하면 동시에 삭제 가능하다.

20. 디렉토리 생성: mkdir [디렉토리명]

- p 옵션: 디렉토리 하위 메뉴까지 동시에 생성한다.
- ex) mkdir -p ./aaa/bbb/ccc

21. 디렉토리 삭제: rmdir [디렉토리명]

- 기본적으로는 디렉토리 안에 파일이 있으면 삭제가 되지 않는다.
- r 옵션: 디렉토리 내부 파일까지 모두 삭제한다.

22. 명령어 내역 출력: history

- ![번호] : history의 출력 결과 중 번호에 해당하는 명령어를 실행한다.

## APT

#### APT

- 빌드 된 패키지 설치할 수 있게 돕는 프로그램
- 빌드 전 소스코드 형태 패키지 설치 가능(직접 빌드 필요)
- CLI로 구성되어 있다.
- GUI로는 우분투 소프트웨어가 있으나, 우분투 소프트웨어는 빌드 된 패키지만 설치가 가능하다.
- apt는 dependency(의존 패키지)를 자동으로 관리해주기에 어떤 프로그램을 다운로드 받을 때 중간 과정을 모두 수동으로 거칠 필요가 없다.

#### sudo

- 관리자 권한으로 명령어를 수행할 때 사용하는 명령어
- sudo를 사용하려면 root로부터 권한을 부여받아야 한다.
- 시스템에 영향이 갈 것 같은 명령어에는 본 명령어를 바탕으로 사용해야 한다.
- 프로그램 설치, 삭제, 서버 환경설정, 버전 변경 등에는 필수적.

#### APT 관련 명령어

1. 설치된 apt list 출력: apt list --installed

- apt라는 프로그램(파일)을 실행
- list: apt의 명령
- --installed : 옵션

2. 특정 이름을 포함한 apt list 출력: apt list | grep <키워드>
3. 대상 파일 삭제: apt remove <대상>
4. 대상 파일 삭제 및 관련 설정 파일 삭제: apt purge <대상>
