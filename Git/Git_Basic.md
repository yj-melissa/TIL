# Git

## 개요
  - 코드의 히스토리(버전)을 관리
  - 개발되어온 과정 파악 가능
  - 이전 버전과의 변경 사항 비교 및 분석
  - 중앙 집중식과 다르게 서버, 작업 컴퓨터가 모두 자료 보관
- 대표 서비스: GitLab, GitHub, Gitbucket

## Repository(Repo)
- 특정 디렉토리(폴더)를 버전 관리하는 저장소
- remote(Github, GitLab) / local(PC)로 분류
- **git init** 명령어로 로컬 저장소를 생성
- .git 디렉토리에 버전 관리에 필요한 모든 것이 들어있음 → 삭제하면 버전관리 불가능
- local(현재 사용중인 컴퓨터)

## Git Bash
| touch | 파일을 생성하는 명령어 |
| --- | --- |
| ls | 현재 작업중인 디렉토리의 파일/폴더를 보여주는 명령어 |
| mkdir 폴더명 | 폴더를 만드는 명령어 |
| cd 폴더명 | 현재 작업 중인 디렉토리를 변경하는 명령어 |
| cd .. | 상위 폴더로 이동 |
| start, open | 폴더/파일을 여는 명령어(Windows에서는 start, Mac에서는 Open) |
| code 파일명 | VScode 설치돼있을 때 vscode로 파일 열 수 있음 |
| rm 파일명 | 해당 파일 삭제(폴더 삭제x) |
| rm -rf 폴더명 | 폴더 삭제/ 휴지통에 들어가지 않고 완전 삭제되므로 주의 |

## 커밋(commit)

- 커밋(commit)은 아래 3가지 영역을 바탕으로 동작

| Working Directory | 내가 작업하고 있는 실제 디렉토리 | untracked → modified |
| --- | --- | --- |
| Staging Area | 커밋(commit)으로 남기고 싶은, 특정 버전으로 관리하고 싶은 파일이 있는 곳 | staged |
| Repository | 커밋(commit)들이 저장되는 곳 | committed |


## git bash 명령어

| git init | git 최초 연동 |
| --- | --- |
| git status | 해당 폴더 상태 확인(ex. untracked, staged, committed, modified) |
| git add |  |
| git commit -m “commit message” | 커밋 메시지는 자세하게 작성하기 |
| git config --global user.email "user@email.com" |  |
| git config --global user.name "username" |  |
| git commit -m "commiti message” |  |
| git remote add 레포별명 레포주소 |  |
| git remote -v | origin 등록 상태 확인 |
| git push 레포별명 브랜치명 |  |
| git clone 레포주소 | remote repo를 local로 복사 |
| git pull origin master | local repo 최신 commit을 remote repo로 push |
| git log | commit 히스토리 확인 / git log —oneline은 더 간편 |
| git diff | 두 commit 간 차이 확인 |