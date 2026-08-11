# Git & GitHub Day 2

## 브랜치(Branch)
- 같은 프로젝트 안에서 독립적으로 작업할 수 있는 공간
- 메인 코드를 건드리지 않고 새 기능 개발 가능
- 여러 기능을 동시에 개발할 수 있음

명령어:
- `git branch`: 브랜치 목록 보기
- `git branch 이름`: 새 브랜치 만들기
- `git switch 이름`: 브랜치 전환

## 브랜치 병합(Merge)
- 다른 브랜치의 작업 내용을 현재 브랜치로 합치기
- `git merge 브랜치명`

### Merge Conflict 해결
두 브랜치에서 같은 파일을 다르게 수정하면 conflict 발생.

### Merge Conflict 해결
두 브랜치에서 같은 파일을 다르게 수정하면 conflict 발생.

Git이 자동으로 병합할 수 없으면 파일에 표시가 나타남:

- `<<<<<<< HEAD`: 현재 브랜치 내용 시작
- `=======`: 경계선
- `>>>>>>> 브랜치명`: 다른 브랜치 내용 끝

이 표시들을 지우고 유지할 내용만 남김. (위 예시에서는 "left branch"만 유지)

파일 저장 후:
1. `git add conflict.py`
2. `git commit -m "Resolve merge conflict"`

## GitHub 기초
- 인터넷에 Git 저장소를 올려두는 서비스
- 코드 공유, 협업, 백업 목적

### 원격 저장소 연결


### Push & Pull
- `git push origin main`: 로컬 작업을 GitHub에 올리기
- `git pull`: GitHub의 최신 내용을 로컬로 받기

## 협업 방식

### Clone vs Fork
- Clone: 같은 저장소에서 팀이 함께 작업
- Fork: 다른 사람 저장소를 내 계정으로 복사 (오픈소스 기여)

### Pull Request
- GitHub에서 "이 코드 반영해줄래?"라고 요청하기
- 리뷰 받은 후 승인되면 병합

### Code Review
- 코드를 합치기 전 함께 확인하는 과정
- 버그 방지, 코드 품질 유지

## 자주 쓰는 명령어

**git diff**: 변경사항 비교 보기
- `git diff`: 수정한 파일과 준비 영역 비교
- `git diff --staged`: 준비 영역과 최신 커밋 비교

**git stash**: 작업 중단하고 임시 저장
- `git stash`: 저장
- `git stash pop`: 복구

**git reset**: 커밋 되돌리기
- `git reset --soft HEAD~1`: 커밋만 취소, 파일 유지
- `git reset --hard HEAD~1`: 완전히 되돌리기

**git revert**: 특정 커밋 취소하기 (기록 남김)
- `git revert 커밋해시`