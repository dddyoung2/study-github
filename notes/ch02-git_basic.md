# ch02. git basic
> 깃에서 자주 쓰이는 명령어들을 정리했습니다.

## git 버전관리 상태 및 내용
- 깃의 추적을 받는 디렉터리는 `.git`이라는 숨김 디렉터리가 존재하는데, 이를 지우면 추적이 불가능함
- Unstaged files: 최초 생성하여, 깃에서 추적이 되지 않는 상태. 이때는 `git commit -am`의 비대상자임
- Staged: 현재 수정한 파일을 곧 commit할 예정인 상태
- Committed: 수정한 파일이 안전히 로컬 데이터베이스에 저장된 상태
- Tracked files-Modified: 이전에 기록했던 파일이 수정된 상태, Unstaged files와 다르게 `git commit -am`의 대상자임
    - 이전에 기록했던 파일이 commit만 되고 그대로라면 Unmodified 상태임
- 즉, 파일 생성 - 상태(status) 확인 - 스테이지 올리기(staged) - 상태 확인 - 스테이지 내리기(commited or unstaged) - 상태 확인
## 명령어
- `git status`: git 상태 확인
- `git add {file-name}`: 해당 파일들을 staged상태로 올림
    - file-name에 *이 오면, .으로 시작하는 파일을 제외하고 모두 스테이징
    - file-name에 .이 오면, 그냥 모두 스테이징
- `git commit`: staged된 파일들을 로컬 데이터베이스에 저장함, 그냥 `git commit`만 하면 편집기가 켜지며 내용을 기록할 수 있음
    - 첫 번째는 줄 제목, 이후(두 번째 줄 띄우고, 세 번째 줄)는 상세 내용
    - opt
        - `-m "commit-message"`: 편집기 창 안보고 내용 적기 가능.
        - `-a`: 추적되는 파일들이 modified 상태라면, add + commit을 한 번에 함
            - 조합하여 `-am`처럼 쓸 수 있음
        - `--amend`: 
- `git log`: 현재 위치한 브랜치의 커밋 이력(히스토리) 및 추적 상태를 최신 먼저, 오름차순으로 확인
    - opt
        - `-{num}`: 최근 히스토리 `num`개만 출력
        - `--oneline`: 각 커밋 히스토리들을 한 줄로 요약하여 출력
        - `--graph`: 브랜치와 머지 히스토리를 리버스 트리 형태로 출력
        - `--all`: 내가 위치하지 않은 다른 브랜치까지 합쳐서 즉, 모든 브랜치에 대한 히스토리를 출력함
        - 조합해서 `git log --oneline --graph --all` 사용 가능
- `git help`: 명령어 검색
- `git push`: 로컬 깃을 호스팅 사이트에 업로드 및 저장
    - origin: 리모트 저장소 이름
    - main: 기본적으로 생성되는 브랜치 이름 (구. master)
    - 깃허브에 등록되지 않은 최초의 브랜치면, `git push -u {remote-repo-name} {branch-name}`를 해야함. 이력이 있다면 그냥 `git push`해도 업로드 됨
    - 리모트 저장소에 쓰기 권한이 있고, clone 이후에 아무도 리모트 서버에 push를 하지 않은 경우 가능. 즉, 쓰기 권한을 가졌다고 할 때 리모트 서버랑 내 로컬과의 버전이 동일하게 최신이어야 한다는 뜻
    - 만약, 리모트 서버에 수정이 있는 경우, pull로 다시 데이터를 가져와 최신화 이후 push해야 함
    - 깃허브에 업로드하기 위해 토큰 인증 등의 자격 증명을 요구할 수 있음. 생성한 토큰은 1회만 표시하므로, 별도 기록하지 않으면 다시 해당 값을 불러올 수 없음.
- `git pull`: 호스팅 사이트에 업로드 된 내용을 불러옴, 로컬 깃 최신화할 때 씀, `git fetch` + `git merge origin/main`
- `git tag`: 
    커밋에 태그를 다는데, 하나의 커밋에 여러 서로 다른 태그 가능. 즉, 여러 커밋에 같은 이름의 태그하는 것은 불가능 하다는 것
    - `git tag`만 하면 태그 정보만 표시
    - `git tag {tag-name}`: 까지만 하면 커밋 히스토리만 보기 가능
    - opt
        - `-l "{tag-name}"`: tag list
        - `-a {tag-name}`: 주석 포함하여 태그 달기 (vs no '-a' opt: 태그명만 나오고 바로 커밋 히스토리만 나오지만, 옵션이 생기면 태그명과 함께 태그를 단 사람과 일자가 찍힘)
        - `-m "{message}"`: 해당 태그에 대한 message 주석을 기록함
        - `-d`: tag 제거
    - 체크섬을 이용해 나중에 태깅해도 됨
    - `git show {tag-name}`을 이용해 해당 태그의 정보를 볼 수 있음
- `git rm {file-name}`: Git으로부터 더 이상 추적되지 않으며, 해당 디렉터리의 명령어 **대상이었던 파일은 삭제됨**
    - opt: `--cached`: opt을 주면, 해당 디렉터리의 명령어 **대상이었던 파일은 삭제되지 않고 보존됨**  
    *즉, 추적되면 안될 파일들을 실수로 넣은 경우에 사용함. 따라서, 이 옵션을 쓰는 경우 `.gitignore`를 사용할 것을 염두에 둬야 함.*  
    - 공통적으로 이 명령어 후 staged 상태가 되므로 적용을 원하면 commit 해야 함
- `git mv {file_from} {file_to}`: `{file_from}`에서 `{file_to}`로 파일명 변경
    - `git mv`명령어를 쓰지 않으면 다음과 동일한 행동을 해야함  
    ``` bash
    mv {file_from} {file_to}
    rm {file_from}
    git add {file_to}
    ```  
    - 파일명을 바꾸는 순간 git에서는 두 가지 파일로 분리 인식함. 기존 것은 삭제된 상태로, 바뀐 것은 Untracked 상태로 기록 됨.