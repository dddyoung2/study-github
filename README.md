# study-github
> github 공부

## 목적
오픈소스기반기초설계 퀴즈 대비겸 깃허브 및 깃 공부 복습 루틴 설계

## 공부
### 0. 배경 및 특징
- 프로그램을 개발하면서 버전 업데이트를 할때, 기존 버전을 유지하면서 진행하고 싶으면 많은 백업파일들로 불편함 발생 -> 버전관리 시스템 활용
- 중앙집중형은 서버가 죽으면 코딩이 불가능 함 -> 분산 버전 관리 시스템 출시
- Git은 버전별로 추적 및 관리 가능하며, 버전 관리 위해 백업 파일 및 디렉터리 이름 매번 안바꿔줘도 됨
- Git으로 관리하는 요소들 보관하는 호스팅 사이트
- 깃허브로 시간 제약 없이 사용 가능
- Fork: 원본 변경 시 반영은 되지 않음, 다른 레포를 내 레포로 가져오는 것
- Star: 원본 변경 시 반영되며, 언제나 방문 및 변경 보기 가능
  
### 1. 준비
#### Git 사용자 정보 설정
``` bash
git config --global user.name "{user.name}"
git config --global user.email "{user.email}"
```

#### 깃허브  프로젝트를 로컬로 복제하기
먼저, 복제할 깃허브 프로젝트의 URL을 복사한다.
![캡처1](https://github.com/user-attachments/assets/3d1740ee-73c3-43ce-9fd1-66240eb29924)

``` bash
git clone {repo-URL}
```

#### 복제 확인하기
``` bash
ls
cd {repo-name}
ls -a
git remote -v
```
- 상위 디렉터리에서 복제한 레포 이름이 잘 출력되는지 확인
- 복제한 레포로 이동한 후, 해당 레포 내 파일 정보를 a 옵션을 활용해 .git이 있는지 확인
- 이후 `git remote -v` 로 잘 연결되었는지 확인.

#### Git 파일 상태
- Untracked File
    - dd
- Staged
- Committed
