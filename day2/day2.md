# Day 2 학습 내용

## HTML 기본
Hyper Text Markup Language의 약자로 웹 문서를 제작할 때 사용하는 언어이다.
그리고 마크업은 구조를 설계하는 언어로 컨텐츠 관점에서 시멘틱하게 작성하는 것이 필요하다. (컨텐츠를 구조적이고 명확하게)
HTML 언어를 학습할 때 알아야 할 기본 용어는 다음과 같다.
- 요소 : Element (tag의 시작과 종료 - 하나의 명령어 덩어리)

- 단락 : paragraphs
- 시작태그 : Open tag
- 종료태그 : Close tag
- 모든 요소는 open tag와 close tag로 이루어져 있음
- img 태그는 empty tag로 /img를 사용하지않음 또는 img / 로 사용(XHTML = extensible HTML)
- meta 태그도 empty tag 
- 속성 : attribute 
 *attribute(속성)는 open tag에만 사용가능
- 값 : value

- 제목 : heading 요소
- Style : 기본적인 에이전트 스타일을 태그마다 다 가지고 있음
- em(엠) : 단위, 상속받은 글자크기 곱하기 몇 배 (지정받은 기본 글자 크기는 16px → e.g. 2em = 32px)

## 표준 모드와 호환 모드
- 문서 유형 정의(Dcument Type Definition)을 말함 
> SM(표준 mode)
> QM(호환 mode) : DTD를 정의하지 않으면 자동으로 호환모드로 적용됨
> AlmostStandardMode

- HTML 4.01과 XHTML 1.0은 Stripts(엄격) / transition(호환) / frameset으로 나뉘었었는데 HTML5는 하나로 통일 → 문서의 유형을 정의해줘야함 (우리나라의 대부분은 transition 형태로 되어있음)

- 세계5대 브라우저 : 구글 크롬, MS IE, Apple Safari, Mozila Fire fox, OperaSoftware Opera → Webkit으로 변화 중


## 웹 접근성 (Web Accessibility)

- 시각장애인 용 보이스오버를 위해서 lang 을 ko-kr로 설정
- 웹사이트에서 제공하는 정보를 차별 및 제한없이 동등하게 이용할 수 있도록 보장하는 것
- 사람(장애인 및 고령자를 포함한 모든 사람)과 환경(다양한 플랫폼 및 디바이스와 웹브라우저 등 모든 환경) 고려
- 웹 접근성을 고려한 UI 제작 준비 : 웹접근성 가이드라인 준수, 웹표준 기술의 활용
  > 웹접근성 지침 : W3C WCAG 2.1(Web content accessibility Guidelines)
  > 웹 표준 기술 : 웹에서 표준적으로 사용되는 기술이나 규칙 
  > 1. 견고한 구조설계를 위한 HTML
  > 2. 레이아웃 및 스타일을 위한 CSS
  > 3. 동작 및 제어를 위한 Dom과 javascript)
  > 4. WAI-ARIA 기술 (예시 : 모달 다이얼로그 떴을 때 보이스오버가 접근을 못하는데 Wai-aria는 접근 가능)
  *다이얼로그 마크업 시 디자인 기반으로 상위부터 하는게 아니라 컨택스트 기반으로 해야함(예시 : 컨텐츠 읽은 후 닫기버튼을 마지막으로 접근해야함)


##HTML 실습 
- ! 입력 시 자동 emmet (HTML 기본 틀 만들어줌)
- 메타 태그(인코딩 선언)가 타이틀보다 먼저 나와야함 (메타를 뒤에 넣으면 타이틀이 깨짐)
- shift + alt + 아래쪽 방향키(↓) : 코드 복사
- 우클릭 open with live server 입력 시 브라우저에서 확인 가능
- 인스펙터(개발툴) : 브라우저에서 우클릭 > 검사 → elements(HTML 소스) / style 확인 가능
  > styles 탭에서 computed > font-size 입력하면 em 단위를 px로 변경해서 알려줌
- 문법검사([html validator](https://validator.w3.org/))
  > 웹사이트는 URI에서 URL 입력하여 검사
  > Validate by file upload 탭에서 파일 선택 후 에러 검사


##이미지 실습
- figure : 캡션을 포함할 수 있는 그룹(표, 이미지, 동영상 포함)
- caption : 이미지에 대한 설명 텍스트(출처 등 표기)
- img src : 이미지 주소 / img alt : 대체 내용, 대체 텍스트
- html 문서는 img를 임베드하지 않고 링크해서 사용(용량, 성능 문제 때문)
- img src 입력 시 ./ 누르면 현재 폴더 내용 확인
- html에서 img src 요소에서 width, height를 바꿀 때는 단위를 입력하지 않음(CSS로 할 수 있으므로 필수 요소 아님)
- 배치나 정렬은 HTML 말고 CSS로 작업


##제목 및 단락 요소
- 사용자가 가장 먼저 읽는 콘텐츠는 제목(Heading Level 1-6)으로 제목은 Hn 요소로 구성됨
- 사용자가 가장 많이 읽는 콘텐츠는 단락(Paragraph)로 단락은 P 요소로 구성됨


##피규어(figure) 및 이미지
- HTML 문서에 연결되어 화면에 표시되는 이미지 요소와 동영상, 차트, 표, 이미지 등을 캡션과 함께 묶어주는 요소가 바로 피규어(figure)임
- 이미지에 alt 속성을 잘 설정해두면 시각장애인이 아니더라도 도움을 받을 수 있음. 이미지 링크가 깨질 경우, 화면에 alt 속성 값이 출력되어 어떤 이미지 였는지 정보를 제공할 수 있음. alt 속성은 바로 이미지를 볼 수 없는 환경에서 이미지를 대체할 수 있는 정보이기 때문.
- 이미지 삽입 예시    
![From A to Z Zucchini](./img/logo.gif)  
- src 속성 : 이미지 파일
- alt 속성 : 대체 텍스트/
- with/height 속성 : 이미지의 가로 및 세로 크기


##목록(Lists)
HTML 문서 작성 시, 목록은 매우 빈번하게 사용 되는 요소들이며 비순차 목록, 순차 목록이 있음
- 비순차(unordered) : 뭘 먼저 봐도 상관없는
  > [MDN web docs - Unordered List](https://developer.mozilla.org/ko/docs/Web/HTML/Element/ul)
  > HTML unordered list 요소 li는 리스트에서의 순서가 의미없는, 숫자 순서를 가지고 있지 않은, 정렬되지 않은 항목들의 리스트를 나타냅니다. 일반적으로, 정렬되지않은 리스트의 항목들은 굵은 점과 함께 표시됩니다.
- 순차(ordered) : 순서가 중요한 (best 1~5 같은)
  > [MDN web docs - ordered List](https://developer.mozilla.org/ko/docs/Web/HTML/Element/ol)
  > HTML ol 요소는 정렬된 리스트의 항목들을 나타냅니다. 일반적으로, 정렬된 리스트의 항목들은 앞에 번호와 함께 표시되며, 이 번호는 순자,문자,로마 숫자,간단한 점과 같이 어떤 형태로든 나타날수 있습니다.
- List item
  > [MDN web docs - Li](https://developer.mozilla.org/ko/docs/Web/HTML/Element/li)
  > HTML List item 요소 (li) 는 리스트 항목을 나타낼때 사용됩니다. 이 요소는 자신이 리스트에서 하나의 개체를 나타내는 정렬된 리스트(ol), 정렬되지 않은 리스트(ul), 메뉴(menu) 에 포함되어야 합니다. 메뉴와 정렬되지 않은 리스트에서, 리스트 항목들은 일반적으로 글머리 기호와 함께 표시됩니다. 정렬된 리스트에서는,  숫자나 글자가 내림차순으로 왼쪽에 같이 표시됩니다.
- list item는 li(목록항목요소) 순차는 ol 비순차는 ul
- ul>li*3 하면 비순차 리스트 3개가 생김 
- ol>li*5 하면 순차 리스트 5개가 생김


##앵커와 하이퍼링크
- 앵커 (같은 페이지 내에서 이동. 주로 비순서형 컨텐츠. e.g. 책갈피, 최상단으로, 네비게이션)
 > [MDN web docs - Anchor](https://developer.mozilla.org/ko/docs/Web/HTML/Element/a)
 > HTML a 요소 (앵커 요소)는 다른 페이지, 파일, 같은 페이지의 어느 위치, 이메일 주소나 그 외 다른 URL로 연결할 수 있는 하이퍼링크를 만듭니다.
- 하이퍼링크(다른 페이지로 이동)
- a href 태그에서 title로 툴팁 내용 추가 가능 (목적지를 명확히 알려줄 수 있음)
- a href 태그에서 target="_blank" 새 창에서 띄우기


##명령어 추가
- 드래그 후 보기 > 명령팔레트 > emmet : 약어로 줄별 래핑 > 명령어 입력
- 셋팅 > 바로가기키 > 단축키 설정 가능
