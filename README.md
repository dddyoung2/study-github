# study-github
> github 공부

## 목적
오픈소스기반기초설계 퀴즈 대비겸 깃허브 및 깃 공부 복습 루틴 설계

## 공부
### 0. 준비
#### Git 사용자 정보 설정
``` bash
git config --global user.name "{user.name}"
git config --global user.email "{user.email}"
```

#### 깃허브  프로젝트를 로컬로 복제하기
먼저, 복제할 깃허브 프로젝트의 URL을 복사한다.
![캡처1](https://github.com/user-attachments/assets/3d1740ee-73c3-43ce-9fd1-66240eb29924)
<img width="1055" height="560" alt="image" src="https://github.com/user-attachments/assets/84f3bcad-7c71-4b52-90c0-c3685b019488" align="center"/>

``` bash
git clone {repo-URL}
```

#### 복제 확인하기
``` bash
ls
cd {repo-name}
ls
git remote -v
```
