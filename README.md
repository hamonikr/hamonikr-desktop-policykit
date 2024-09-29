# Hamonikr Desktop PolicyKit

이 패키지는 데스크탑 사용자가 GUI 애플리케이션의 권한을 관리하는 데 사용됩니다.

리눅스를 데스크탑으로 사용하다보면 비밀번호 없이 프로그램을 실행해야 하는 경우가 있습니다.

이 패키지를 이용하여 sudo 입력을 요구하는 프로그램을 비밀번호 없이 실행할 수 있도록 설정합니다.

## 현재 적용된 설정

- gparted
- user and group management
- gufw
- mintsources
- boot-select
- file operations
- nemo root

## 참고 사항

Polkit은 GUI 애플리케이션의 권한을 관리하는 데 주로 사용되며, 터미널 명령어에
대한 비밀번호 프롬프트를 제어하지 않습니다.

Polkit 규칙을 통해 apt update, apt upgrade, apt install 명령어를 비밀번호 없이 실행할 수 있도록 설정하는 것은 일반적으로 불가능합니다. 

## pkaction

pkaction 명령어를 사용하여 특정 애플리케이션에 대한 권한을 설정할 수 있습니다.

```
pkaction --verbose --user-context=user:user --action-id=org.freedesktop.policykit.exec -- --help
```

### 액션 전체 조회

```
pkaction
```

### 액션 조회

```
pkaction --verbose --action-id org.debian.apt.upgrade-packages
```

### 액션 추가

```
pkaction --add --action-id org.debian.apt.upgrade-packages --description "Upgrade all packages to their latest versions" --message "The upgrade will require a restart" --icon-name "system-software-update" --confirm-button "Upgrade" --cancel-button "Cancel" --default-button "Upgrade" --verb "Upgrade" --user-context=user:user
```

### 액션 삭제

```
pkaction --remove --action-id org.debian.apt.upgrade-packages
```

### 액션 수정

```
pkaction --modify --action-id org.debian.apt.upgrade-packages --description "Upgrade all packages to their latest versions" --message "The upgrade will require a restart" --icon-name "system-software-update" --confirm-button "Upgrade" --cancel-button "Cancel" --default-button "Upgrade" --verb "Upgrade" --user-context=user:user
``` 