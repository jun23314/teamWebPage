+++
title = "Git"
tags = ["git","github"]
categories = ["git"]
banner = "img/Git/Git.png"
authors = ["전규빈"]
+++

### Git이란 무엇인가
Git이란 버전 관리 시스템의 하나이다.
쉽게 말하면, 말 그대로 '버전'을 관리할 수 있는 수단이다. 수정 사항이나, 업데이트 사항 등을 그때 그때 바로 반영 할 수 있도록 하는 시스템을 말한다.

### Git의 주요 개념
- Repository (저장소) : 소스 코드들이 저장되어 있는 물리적인 공간을 의미한다. 저장소를 통해서 작업자가 진행, 변경했던 사항들에 대해 알 수 있다.

- Working Tree : 흔히 우리가 사용하는 '폴더'를 말한다.

- Index (= Staging Area) : Commit을 실행하기 전의 저장소와 Working tree 사이에 존재하는 공간을 말한다. Working Tree -> Index -> Commit 순의 절차를 거친다.

- Commit : 작업 과정들에 대한 점검을 마친 뒤, 저장소에 남기는 과정을 의미한다. 각각의 커밋 단계는 의미 있는 단계이다. 따라서 커밋 로그를 남긴다. git log라는 명령어를 통해 커밋된 사항들에 대해 확인 할 수 있다.

- Checkout : 특정 시점이나 branch의 소스 코드로 이동하는 것을 의미한다. 이 과정을 통해 과거 여러 시점의 소스 코드로 이동할 수 있다.

- Branch : Commit 단위로 구분된 소스 코드 타임라인에서 분기해서 새로운 commit을 쌓을 수 있는 가지를 만드는 것을 말한다. Branch에서 작업을 완료하면, Merge 작업을 수행한다.

- Merge : Branch와 Branch의 내용을 합치는 작업, 즉 병합을 말한다. Branch와는 다소 반대되는 개념이다. 병합 과정 중 두 branch에서 하나의 동일한 파일에서 서로 다른게 수정한 경우 충돌이 발생하며, 병합이 일시정지 된다. 이 때, 충돌 부분에 대해 직접 수정하거나 Merge Tool 등을 활용하여 충돌을 해결한 뒤 병합을 계속 진행한다.

### Git의 명령어
- git init : 깃 초기화. 이 명령어를 실행해야만 깃이 실행된다. 이 명령어 실행 전까지는 그냥 일반 폴더일 뿐이나, 이후엔 추가적인 명령어들을 통해 작업을 진행 할 수 있다.

- git status : 깃 저장소의 상태를 확인한다. 이 명령어를 통해 현재 상태가 어떤 지 수시로 확인 가능하다.

- git add : 커밋에 파일의 변경 사항을 포함하도록 한다. 이 명령이 저장소에 새 파일들을 직접적으로 추가하진 않는다.

- git commit : "git commit -m '저장명'" 등과 같은 명령어로 주로 사용한다. 이 명령어를 통해 커밋을 생성하고, 변경 사항을 확정하여 반영한다.

- git clone : 기존 소스 코드 다운로드 및 복제한다. 즉, 원격 저장소의 저장소를 로컬에서 이용할 수 있도록 복사해 가져온다.

- git log : 나의 커밋 내역에 대해 알고 싶을 때 사용하면 현재 커밋 목록들을 확인 가능하다.

- git checkout : 브랜치에서 브랜치로 이동 가능하다. 현재 버전에서 이전 버전의 커밋으로 이동하거나 변경 전의 브랜치로 접근 가능하다.

- git checkout master : 이전 버전, 변경 전 브랜치에서 다시 현재의 (master) 브랜치로 되돌아 올 수 있다.

- git push : 소스 코드의 변경 사항을 원격 저장소에 반영한다.

- git pull : 원격 저장소의 변경 내용이 현재 디렉토리로 가져와진 뒤, (fetch) 병합된다.

- git merge : 변경 사항 등이 모두 확정되고 난 후, 브랜치들을 병합한다. 작업 마무리 단계에서 시행한다.