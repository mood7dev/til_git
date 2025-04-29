# Git

## 1. Git 프로그램 설치

- 프로그램 다운로드 https://git-scm.com/
- 64-bit Git for windows Setup 설치

## 2. Git 버전 확인

- 윈도우 키보드 + R 키보드 : `cmd` 입력

```bash
    git --version
```

- 출력창 확인

## 3. VSCode 에 Git 설정하기

### 3.1.터미널 환경을 git bash로 설정하기

- 윈도우, 맥, 리눅스의 명령창을 통일하기 위함.
- 관리도구 선택 > 설정메뉴 선택
- 설정화면 > `default:Windows` 입력
- `Git Bash` 선택
- 설정화면 닫고, VSCode 재실행 추천

### 3.2. VSCode에서 Git 옵션 설정하기

- 터미널 실행 : `Ctrl + 백틱` 추천
- git 버전 확인

```bash
git --version
```

- 기본 브랜치명을 `main` 으로 설정

```bash
git config --global init.defaultBranch main
```

- 윈도우, 맥, 리눅스 환경에서 Enter 키 처리를 통일함.

```bash
git confing --global core.autocrlf true
```

- 깃 Commit 명령을 VSCode 에서 작성하도록 설정

```bash
git confing --global core.editor "code --wait"
```

- 깃 사용자 아이디 설정하기

```bash
git config --global user.name "아이디"
```

-깃 사용자 아이디 확인하기

```bash
git config --global user.name
```

- 깃 사용자 이메일 저장하기

```bash
git config --global user.email "이메일"
```

- 깃 사용자 이메일 확인하기

```bash
git config --global user.email
```

## 4. 깃 작업하기 (실습)

### 4.1. 깃 프로젝트 관리 초기화 하기

```bash
git init
```

### 4.2. 깃 현재 상태 파악하기

```bash
git status
```

### 4.3. 깃 현재 수정된 파일, 폴더 등을 저장하기

- 원하는 파일만 저장

```bash
git add README.md
```

- 모든 파일 및 폴더 저장하기(추천)

```bash
git add .
```

### 4.4. 수정 내역 메모 남기기

- 한줄 작업 메모

```bash
git commit -m "한줄메모"
```

- 여러줄 메모 작성하기

```bash
git commit
```

### 4.5. 커밋 내용 컨벤션 알아보기

```bash
[커밋타입](옵션) : 커밋 메시지
```

- 커밋 타입 : 작업의 분류
- 옵션 : 이슈 또는 수정이 된 작업커밋 번호 또는 추가정보
- 커밋 메시지 : 무엇을 했는지 짧은 내용

### 4.5.1. 커밋타입

- `[feat]` : 새로운 기능 추가
  (예) [feat] 게시글 작성 기능추가

- `[fix]` : 버그 수정
  `(예) [fix] 로그인 오류 수정

- `[docs]` : 문서 수정 (코드 변경 없이 README나 주석 등만 변경할 때)
  `(예) [docs] README 사용법 추가

- `[style]` : 코드 포맷팅, 세미콜론 누락 등 기능이나 로직 변화 없는 수정
  `(예) [style] : 코드 들여쓰기 정리

- `[refactor]` : 코드 리팩토링(기능 변경, 코드 정리 등)
  `(예) [refactor] 중복 코드 제거

- `[test]` : 테스트 코드 추가나 수정
  `(예) [test] 유닛 테스트 추가

- `[chore]` : 기타 (빌드 설정, 패키지 업데이트 등)
  `(예) [chore] eslint 설정 추가

- `[perf]` : 성능 개선
  `(예) [perf] 렌더링 속도 개선

- `[ci]` : CI 관련 설정 수정 (예: GitHub Actions, Travis 등)
  `(예) [ci] 배포 파이프라인 설정 추가

- `[build]` : 빌드 관련 파일 수정 (webpack, npm scripts 등)
  `(예) [build] webpack 설정 변경

### 4.5.2. 옵션

-만약 `회원가입 로그인 기능 추가` 라면

- 아래는 이유 #23 번을 해결하고 기능을 추가했다는 것

```
[feat](#23) 회원가입 로그인 기능 추가
```

#### 4.5.3. 커밋 내용

- Enter 키를 기준으로 제목과 내용을 구분합니다.

```
[docs] : 커밋 제목

커밋 상세 내용작성

```

### 4.6. 커밋 내용 확인하기

- 기존의 commit 된 내용을 확인하기
- 상세보기

```bash
git log
```

- 간략하게 보기

```bash
git log --oneline
```

- 하나의 commit 상세보기

```bash
git show 커밋아이디
```

### 4.6.1. 각 항목 관련 사항 이해하기

- commit : 고유한 커밋 번호(아이디)
- Author : 작성자
- Date : 날짜
- 메시지 : 상세 내용

### 4.7. 브랜치 작업해 보기

- `나뭇가지` 라는 의미로 원 줄기로 부터 파생되는 것을 말함.
- 원 `소스`로 부터 파생한 새롭게 `분기한 소스` 관리를 말함.
- 브랜치를 생성시에는 add 와 commit 이 완료되어야 함.

#### 4.7.1. 브랜치 생성하기

```bash
git add .
git commit -m "[docs] : 브랜치 실습 test 생성하기"
git branch test
```

#### 4.7.2. 브랜치 목록보기

```bash
git branch -v
```

#### 4.7.3. 브랜치 이동하기

```bash
git switch test
```

#### 4.7.4. 브랜치 삭제하기

```bash
git branch -d test
- D 는 무조건 지우는 것
git branch -v
```

#### 4.7.5. 브랜치 합치기

- 브랜치를 하나로 합쳐주기
- 주의 사항 : `main 브랜치에서 test 브랜치 합쳐줄 겁니다.`

```bash
git merge 합쳐주고자 하는 브랜치명
```

### 4.8. 깃 브랜치 충돌 해결해 보기

- 깃 브랜치를 merge 하면 많이 발생합니다.

git add .
git commit -m "[docs] : 업무저장"

==> login 업무를 전달합니다.

git branch login
gir branch -v

=====
main
login
나와야함
=====

- login 브랜치에서 나는 로그인 기능을 구현했다.

git switch login
git add .
git commit -m "[feat] : 로그인기능"

- 나는 main 에서 계속 작업을 하고 있었습니다.

git switch main
git add .
git commit -m "[docs] : 내용 수정"

git merge login

Accept Both Changes >> 클릭 : main와 login 둘 다 저장함

- `login 브랜치`에서 나는 로그인 기능을 구현했다.

git add .
git commit -m "[feat] : 로그인 기능 적용"

git branch -D login

# GitHub

## 1. GitHub 회원가입하기

- https://github.com

## 2.GitHub 프로젝트(Repository) 생성하기

- 만약 til_git 프로젝트 생성한다면 GitHub에도 동일하게 생성하자.

- public 으로 셋팅 : 외부로 소스 공개

- description 은 작성해 주자 : 프로젝트 설명

## 3. GitHub 인증하기

### 3.1. 무조건 GitHub 에 로그인 된 상태로 시도하셔야 합ㄴ디ㅏ.

### 3.2. `윈도우 > 자격 증명 관리자 > Windows 자격 증명` 에서 gitHub 확인

- 새로 생성하시길 권장합니다.
  -PC 정리 또는 자리 이동시 반드시 삭제하셔야 합니다.

## 4. GitHub 프로젝트 연결하기

### 4.1. 원격 저장소 주소 지정하기

- `remote` 는 원격(인터넷)을 말합니다.
- `add` : 추가하라
- `origin` 은 http 주소를 간략하게 별칭을 준 것입니다. (단어는 마음대로 하셔도 되요.)
- `원격 이름`을 말함.

```bash
git remote add origin https://github.com/mood7dev/till_git.git
```

### 4.2. 원격 저장소 목록 보기

```bash
git remote -v
```

### 4.3. 원격 저장소에 소스 등록하기

- 습관적으로 하셨으면 좋은 작업(ctrl + s)

```bash
git add .
git commit -m "[docs]:최초등록"
```

- 소스 업로드를 push 한다라고 합니다.

git push -u origin main

- `u` 옵션을 붙이셨다면 이후로는 `git push` 하면 됨.

### 4.4. 원격 저장소 관리하기

- 목록보기

```bash
git remote -v
```

- 삭제하기

```bash
git remote remove 원격이름
```

- 추가하기

```bash
git remote add 원격이름 https주소
```

- 이름바꾸기

```bash
git remote rename 옛이름 새이름
```

---

```
git add .
git commit -m "[docs]:깃학습"
git push origin main
```

### 5. 깃허브의 소스를 복사(Clone) 받아서 작업하는 법

- 깃 주소를 주의하셔야 합니다.
- 코드 소스 기준은 `https`로 진행 중입니다.
- 코드 소스 기준이 `ssh`면 인증을 다시 처리하는 과정 필요.

### 5.1 실습

- 서울로 출장을 갔다. (PC 없이)
- 서울 사무소에 PC를 지급 받았다.
- PC에 환경 설정 진행(VSCode, Git)
- /stdent/`test` 폴더 생성
- gitHub 사이트에 프로젝트를 `clone` 한다.

### 5.2. clone

```bash
git clone 깃허브주소 .
```

```bash
git status
```

```bash
git branch -v
```

```bash
git branch 브랜치명
git switch 브랜치명
```

작업진행

```bash
git add .
git commit -m "작업내용"
```

```bash
git push origin 브랜치명
```

### 5.4. git push 이후 작업

- jeju 폴더는 clone을 하여 진행함.
- `til_git 폴더는 clone 을 할 필요가 있을까요?`
- til_git 은 이미 git 셋팅이 되어 있다. 그래서 clone은 필요 없다.

### 5.5. 기존 프로젝트에서 GitHub 브랜치 적용하기

- 기존 프로젝트에서는 clone 하지 않음
- 기존 프로젝트에서는 fetch 사용
- fetch 는 깃허브에서 모든 브랜치 가져옮

```bash
git fetch -all
```

- 2. 브랜치 목록보기 (전체 즉, 로컬과 깃허브 브랜치 모두)

```bash
git branch -a
```

- 3. `새롭게 작업한 깃허브 브랜치`를 `로컬 브랜치 생성하면서 즉시 만들어서 작업` 하기

```bash
git switch --track -c 생성브랜치명 원격브랜치명
```

- 예) `git switch --track -c jeju remotes/origin/seoul`
