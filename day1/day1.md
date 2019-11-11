# Day 1 학습 내용
## 개발 환경설정

- 웹 브라우저 설치 ([Chrome](https://www.google.com/intl/ko/chrome/))
- 에디터 설치([VS code](https://code.visualstudio.com/download))
> VS code에서 보기 메뉴에 설정이라는 메뉴를 선택한 후 fontsize, tabsize, minimap에 대한 설정값을 변경한다.
- git 설치 ([Git](https://git-scm.com/downloads))
- github 가입하기([GitHub](https://github.com/))
Git을 설치하고 나서 가장 먼저 해야 하는 것은 사용자 이름과 이메일 주소를 설정하는 것이다. Git은 커밋할 때마다 이 정보를 사용한다. 한 번 커밋한 후에는 정보를 변경할 수 없다. 그리고 git으로 사용할 기본 에디터를 Visual Studio Code로 등록하는 것이 편리하다.

> $ git config --global user.name "hyejooyoon"  

> $ git config --global user.email yoonhyejoo@gmail.com   

> $ git config --global core.editor "code --wait"


## Git 명령어

- git status (상태 확인하기)
- git add (스테이지에 추가하기)
- git commit -m (수정내용 확정하기)
- git push (Remote 저장소로 파일보내기)
- git pull (Remote 저장소 내용을 local로 가져오기)
- git commit --amend (마지막 커밋 코멘트 수정하기)


### Git Branch

여러 개발자들이 동시에 다양한 작업을 할 수 있게 만들어 주는 기능이 바로 '브랜치(Branch)' 입니다. 각자 독립적인 작업 영역(저장소) 안에서 마음대로 소스코드를 변경할 수 있습니다. 이렇게 분리된 작업 영역에서 변경된 내용은 나중에 원래의 버전과 비교해서 하나의 새로운 버전으로 만들어 낼 수 있습니다.

- git branch (브랜치 목록 보기)
- git branch [브랜치 이름] (브랜치 생성)
- git checkout [브랜치 이름] (브랜치 변경)
- git switch [브랜치 이름] (브랜치 변경 - 2.23 버전 이상)

-------------------------------------------

## 마크다운 (Markdown)
![마크다운](../asset/mark.png)

HTML 또는 CSS 코드 삽입할 때 

```html
<!DOCTYPE html>
<html lang="ko-KR">
<head>
  <meta charset="UTF-8">
  <title> 첫번째 HTML 문서 </title>
</head>
<body>
  본문 영역
</body>
</html>
```