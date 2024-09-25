# Hamonikr Desktop PolicyKit

이 패키지는 데스크탑 사용자가 GUI 애플리케이션의 권한을 관리하는 데 주로
사용됩니다.

이 패키지를 이용하여 sudo 입력을 요구하는 프로그램을 비밀번호 없이 실행할 수
있도록 설정합니다.

## 현재 적용된 설정

- gparted
- user and group management

## 참고 사항

Polkit은 GUI 애플리케이션의 권한을 관리하는 데 주로 사용되며, 터미널 명령어에
대한 비밀번호 프롬프트를 제어하지 않습니다.

Polkit 규칙을 통해 apt update, apt upgrade, apt install 명령어를 비밀번호 없이 실행할 수 있도록 설정하는 것은 일반적으로 불가능합니다. 


