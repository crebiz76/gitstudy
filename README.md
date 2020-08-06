# gitstudy

## Git-flow 전략의 필요성
- 하나의 제품을 만들기 위해 여러 아이템들의 통합 개발이 필요하다. 

  └ 형상 관리 및 유지 보수가 무엇보다도 중요하다. 

  └ 개발 단계에서 실시간성이 보장되어야 한다. 



- 각 아이템별로 형상 관리를 위해 하나의 형상 관리 툴을 사용해야 한다. 

  └ 일관성 없는 툴의 사용은 개발 단계에서 형상 관리의 문제점을 낳는다. 

  └ 개발 단계뿐만 아니라, 배포 단계에서도 문제가 발생할 수 있다. 



- 형상 관리 툴은 유지 보수 및 중앙 집중형 방식이 아닌 분산형 방식을 사용해야 한다. 

  └ 중앙 집중형 방식은 서버(Server)에 문제 발생 시 작업을 할 수가 없다. 

  └ 여러 명의 작업자가 동시에 사용 가능하도록 해야 한다. 
  
## Git-flow 전략


## Git-flow 따라하기 

git-flow의 예제를 기반으로  동일하게 구현함으로써 git의 사용법을 익히고 git-flow를 이해한다. 

시간의 흐름대로 작성한다. 
각 브랜치는 브랜치명과 동일한 텍스트 파일(.txt)을 만든다. 

### 저장소 초기화
git init gitflow_ex
### 폴더 이동
cd gitflow_ex
### 파일 생성(master.txt)
echo "master" > master.txt
### 추가
git add master.txt
### 커밋
git commit -am "master 1"
### 태그
git tag 0.1

### develop 브랜치 생성 & 체크아웃
git checkout -b develop
### 파일 생성(develop.txt)
echo "develop" > develop.txt
### 추가
git add develop.txt
### 커밋
git commit -am "develop 1"

### 파일 수정(develop.txt)
echo "develop" >> develop.txt
### 커밋
git commit -am "develop 2"
### 파일 수정(develop.txt)
echo "develop" >> develop.txt
### 커밋
git commit -am "develop 3"

### feature 브랜치 생성
git branch feature/a
git branch feature/b
### feature/a 체크아웃
git checkout feature/a
### 파일 생성(feature_a.txt)
echo "feature/a" > feature_a.txt
### 추가
git add feature_a.txt
### 커밋
git commit -am "feature/a 1"

### develop 체크아웃
git checkout develop
### 파일 수정(develop.txt)
echo "develop" >> develop.txt
### 커밋
git commit -am "develop 4"
### feature/b 체크아웃
git checkout feature/b
### 파일 생성(feature_b.txt)
echo "feature/b" > feature_b.txt
### 추가
git add feature_b.txt
### 커밋
git commit -am "feature/b 1"

### master 체크아웃
git checkout master
### hotfix 브랜치 생성 & 체크아웃
git checkout -b hotfix
### 파일 생성(hotfix.txt)
echo "hotfix" > hotfix.txt
### 추가
git add hotfix.txt
### 커밋
git commit -am "hotfix 1"

### master 체크아웃
git checkout master
### 파일 수정(master.txt)
echo "master" >> master.txt
### 커밋
git commit -am "master 2"
### hotfix 머지
git merge --no-ff hotfix
### 태그
git tag 0.2

### feature/a 체크아웃
git checkout feature/a
### 파일 수정(feature_a.txt)
echo "feature/a" >> feature_a.txt
### 커밋
git commit -am "feature/a 2"

### feature/b 체크아웃
git checkout feature/b
### 파일 수정(feature_b.txt)
echo "feature/b" >> feature_b.txt
### 커밋
git commit -am "feature/b 2"

### develop 체크아웃
git checkout develop
### 파일 수정(develop.txt)
echo "develop" >> develop.txt
### 커밋
git commit -am "develop 5"
### hotfix 머지
git merge --no-ff hotfix
### hotfix 브랜치 삭제하기
git branch -d hotfix

### feature/b 체크아웃
git checkout feature/b
### 파일 수정(feature_b.txt)
echo "feature/b" >> feature_b.txt
### 커밋
git commit -am "feature/b 3"

### develop 체크아웃
git checkout develop
### 파일 수정(develop.txt)
echo "develop" >> develop.txt
### 커밋
git commit -am "develop 6"
### feature/b 머지
git merge --no-ff feature/b
### feature/b 브랜치 삭제
git branch -d feature/b

### release 브랜치 생성 & 체크아웃
git checkout -b release
### 파일 생성(release.txt)
echo "release" > release.txt
### 추가
git add release.txt
### 커밋
git commit -am "release 1"
### 추가
echo "release" >> release.txt
### 커밋
git commit -am "release 2"

### develop 체크아웃
git checkout develop
### 파일 수정(develop.txt)
echo "develop" >> develop.txt
### 커밋
git commit -am "develop 7"
### release 머지
git merge --no-ff release

### feature/a 체크아웃
git checkout feature/a
### 파일 수정(feature_a.txt)
echo "feature/a" >> feature_a.txt
### 커밋
git commit -am "feature/a 3"

### develop 체크아웃
git checkout develop
### feature/b 생성 & 체크아웃
git checkout -b feature/b
### 파일 수정(feature_b.txt)
echo "feature/b" >> feature_b.txt
### 추가
git add feature_b.txt
### 커밋
git commit -am "feature/b 4"

### release 체크아웃
git checkout release
### 추가
echo "release" >> release.txt
### 커밋
git commit -am "release 3"

### feature/b 체크아웃
git checkout feature/b
### 파일 수정(feature_b.txt)
echo "feature/b" >> feature_b.txt
### 커밋
git commit -am "feature/b 5"

### release 체크아웃
git checkout release
### 추가
echo "release" >> release.txt
### 커밋
git commit -am "release 4"

### develop 체크아웃
git checkout develop
### 파일 수정(develop.txt)
echo "develop" >> develop.txt
### 커밋
git commit -am "develop 8"
### release 머지
git merge --no-ff release

### feature/b 체크아웃
git checkout feature/b
### 파일 수정(feature_b.txt)
echo "feature/b" >> feature_b.txt
### 커밋
git commit -am "feature/b 6"

### master 체크아웃
git checkout master
### 파일 수정(master.txt)
echo "master" >> master.txt
### 커밋
git commit -am "master 3"
### release 머지
git merge --no-ff release
### 태그
git tag 1.0
### release 브랜치 삭제
git branch -d release

### feature/a 체크아웃
git checkout feature/a
### 파일 수정(feature_a.txt)
echo "feature/a" >> feature_a.txt
### 커밋
git commit -am "feature/a 4"

### develop 체크아웃
git checkout develop
### 파일 수정(develop.txt)
echo "develop" >> develop.txt
### 커밋
git commit -am "develop 9"
### feature/b 머지
git merge --no-ff feature/b
### feature/a 머지
git merge --no-ff feature/a
### feature/b 삭제
git branch -d feature/b
### feature/a 삭제
git branch -d feature/a

### release 브랜치 생성 & 체크아웃
git checkout -b release
### 추가
echo "release" >> release.txt
### 커밋
git commit -am "release 5"

### develop 체크아웃
git checkout develop
### 파일 수정(develop.txt)
echo "develop" >> develop.txt
### 커밋
git commit -am "develop 10"
### release 머지
git merge --no-ff release

### master 체크아웃
git checkout master
### 파일 수정(master.txt)
echo "master" >> master.txt
### 커밋
git commit -am "master 4"
### release 머지
git merge --no-ff release
### release 브랜치 삭제
git branch -d release
