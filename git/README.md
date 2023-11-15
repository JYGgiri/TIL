# 멀티미디어실습 <font size= "2"> 2023년 가을학기에 진행한 git 수업 정리</font>

## 2023-11-15
### 다른 작업자의 브랜치와의 충돌 해결
- 만일 다른 사람의 브랜치와 나의 브랜치에서 같은 내용을 수정했을 때 충돌이 발생한다.
- commit과 push가 이루어졌고 Pull Request를 하면 Conflict와 같은 메시지가 출력되며 Merge가 불가능하다고 한다.
- vs code 또는 github 내부에서 충돌을 해결을 해야한다.


### 일감 생성 및 브랜치 생성
- Projects 탭에서 New Issue를 생성하고 브랜치를 생성한다.
- Local Repository에서 브랜치 접근하는 순서
```
1. git fetch origin
Remote Repository에 있는 것을 Local로 가져오는 작업

2. git checkout <브랜치명>
사전에 생성해둔 브랜치에 접근
```
> 이러한 방식으로 Remote Repository에서 브랜치를 먼저 생성하고 Local Repository에서 브랜치에 접근했을 때 이미 연결되어 있음.

## 2023-11-01
### 브랜치
> 정의 : Branch in git is light-weight moveable pointer to one of these commits.
- 회사에서는 일감에 해당하는 이슈를 만든다.
- 이슈에 해당하는 브랜치를 만든다.
### 칸반 보드 (Kanban Board)
- Todo, In Progress, Done 3개의 column으로 구성
- IT 계열에서 테스터가 존재할 경우 In Test 항목이 있을 수 있음
- 경우에 따라 BackLog에 담당자가 정해지지 않은 일감을 쌓아둠
### Repository 보호
- Settings &#8594; Branches &#8594; Branch Protection Rules &#8594; Add Rule 또는 Edit 으로 접근
- Lock Branch : 사용자가 이 브랜치에 푸시하지 못하도록 설정
### Pull Request
- 내가 로컬 머신에서 작업했던 브랜치에 있는 커밋들을 원격 저장소의 main 브랜치에 반영하기 위해 pull request 작성
### 브랜치 병합 (merge, 합치기)
- 'git checkout <브랜치명>' 으로 브랜치 접근
- git merge <브랜치명>

## 2023-10-18
### 저장소
- 일반 폴더와 저장소의 차이는 '.git' 숨김폴더가 없냐 있냐 이다.
<br>- 일반 폴더는 '.git' 숨김폴더가 없음
<br>- 저장소는 '.git' 숨김폴더가 있음

- 'git' 숨김폴더를 삭제하면 커밋 이력등도 같이 삭제됨

### 브랜치
- 브랜치 &#8592; 커밋을 가리키는 포인터

- 이슈를 만들고 이슈에 해당하는 브랜치를 생성
<br>- 'git branch' &#8592; 만들어진 브랜치 확인
<br>- 'git branch 브랜치명' &#8592; 새로운 브랜치 생성

- 작업을 시작할 때는 생성한 브랜치로 전환(switch)함
<br>- 'git switch 브랜치명'
<br>- 'git checkout 브랜치명'

## 2023-10-04
### 스테이징 영역
- IT프로젝트는 여러 파일을 동시에 다루게 된다.
- 일반 문서 수정과 같이 '저장' 버튼 클릭만으로 한번에 수정한 파일들을 저장하게 하면, 불필요한 파일들이 커밋에 포함되는 일들이 발생한다.
    - <b> Example : </b> '.vs' : visual studio로 프로젝트 열었을 때 자동 생성되는 폴더
- 그래서 'staging area'라는 영역을 따로 두고, 커밋에 포함시킬 코드(파일)만 스테이징 영역에 추가하게 한 다음, 커밋을 만든다.
    - <b>스테이징 영역에 파일을 추가할 때 쓰는 명령어 :</b> git add 파일명
### gitignore 파일
- 루트 경로에 있는 .gitignore 파일은 버전관리 하지 않을 파일의 목록을 관리하는 용도로 쓰인다.
- 사용하는 운영체제, 에디터, 프로그래밍 언어, SDK, 라이브러리 등의 종류에 따라 사람이 의도하지 않은 파일이 생성되는데, 이런 파일들은 버전관리 대상이 아니므로 .gitignore 파일에서 관리한다.
    - <b> Example : </b> https://github.com/OpenHogwarts/hogwarts/blob/master/.gitignore
- 처음 프로젝트 세팅하는 사람은 여러 툴을 사용해 자동으로 .gitignore 파일에 들어갈 내용을 생성한다.
    - 웹사이트
        - 구글에서 'gitignore generator'로 검색
        - https://www.toptal.com/developers/gitignore/
    - VSCode Extension
        - gitignore by CodeZombie

## 2023-09-27
- commit 이란? 
<br>- git의 기본 단위로, 논리적 변경이 있을 때 만듬 (사진찍기와 유사)

- commit 메시지
<br>- 코드 변경분을 한 마디로 설명함
- 명령어
<br>- git commit -m "커밋 메시지를 이곳에 입력"
<br>- git commit --message "커밋 메시지를 이곳에 입력"
- 얼마나 자주 커밋을 만들어야하나
<br>- 너무 작지도, 크지도 않게 한다. (조직에 따라, 프로젝트 성격에 따라 다름)
<br>- 커밋 단위가 너무 작을 경우 불필요한 커밋들이 생성됨
<br>- 커밋 단위가 너무 클 경우 장애가 났을 때 빠른 대응이 힘듬
<br>- 예시: 30분 안에 리뷰 가능하도록 커밋 크기 조절