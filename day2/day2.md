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
- 다이얼로그 마크업 시 디자인 기반으로 상위부터 하는게 아니라 컨택스트 기반으로 해야함(예시 : 컨텐츠 읽은 후 닫기버튼을 마지막으로 접근해야함)



## HTML 실습   

- ! 입력 시 자동 emmet (HTML 기본 틀 만들어줌)
- 메타 태그(인코딩 선언)가 타이틀보다 먼저 나와야함 (메타를 뒤에 넣으면 타이틀이 깨짐)
- shift + alt + 아래쪽 방향키(↓) : 코드 복사
- 우클릭 open with live server 입력 시 브라우저에서 확인 가능
- 인스펙터(개발툴) : 브라우저에서 우클릭 > 검사 → elements(HTML 소스) / style 확인 가능
  > styles 탭에서 computed > font-size 입력하면 em 단위를 px로 변경해서 알려줌
- 문법검사([html validator](https://validator.w3.org/))
  > 웹사이트는 URI에서 URL 입력하여 검사
  > Validate by file upload 탭에서 파일 선택 후 에러 검사



## 이미지 실습  

- figure : 캡션을 포함할 수 있는 그룹(표, 이미지, 동영상 포함)
- caption : 이미지에 대한 설명 텍스트(출처 등 표기)
- img src : 이미지 주소 / img alt : 대체 내용, 대체 텍스트
- html 문서는 img를 임베드하지 않고 링크해서 사용(용량, 성능 문제 때문)
- img src 입력 시 ./ 누르면 현재 폴더 내용 확인
- html에서 img src 요소에서 width, height를 바꿀 때는 단위를 입력하지 않음(CSS로 할 수 있으므로 필수 요소 아님)
- 배치나 정렬은 HTML 말고 CSS로 작업



## 제목 및 단락 요소   

- 사용자가 가장 먼저 읽는 콘텐츠는 제목(Heading Level 1-6)으로 제목은 Hn 요소로 구성됨
- 사용자가 가장 많이 읽는 콘텐츠는 단락(Paragraph)로 단락은 P 요소로 구성됨



## 피규어(figure) 및 이미지  

- HTML 문서에 연결되어 화면에 표시되는 이미지 요소와 동영상, 차트, 표, 이미지 등을 캡션과 함께 묶어주는 요소가 바로 피규어(figure)임
- 이미지에 alt 속성을 잘 설정해두면 시각장애인이 아니더라도 도움을 받을 수 있음. 이미지 링크가 깨질 경우, 화면에 alt 속성 값이 출력되어 어떤 이미지 였는지 정보를 제공할 수 있음. alt 속성은 바로 이미지를 볼 수 없는 환경에서 이미지를 대체할 수 있는 정보이기 때문.
- 이미지 삽입 예시    
![From A to Z Zucchini](./img/logo.gif)  
- src 속성 : 이미지 파일
- alt 속성 : 대체 텍스트/
- with/height 속성 : 이미지의 가로 및 세로 크기



## 목록(Lists)  

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


## 앵커와 하이퍼링크      
  
- 앵커 (같은 페이지 내에서 이동. 주로 비순서형 컨텐츠. e.g. 책갈피, 최상단으로, 네비게이션)
  > [MDN web docs - Anchor](https://developer.mozilla.org/ko/docs/Web/HTML/Element/a)
  > HTML a 요소 (앵커 요소)는 다른 페이지, 파일, 같은 페이지의 어느 위치, 이메일 주소나 그 외 다른 URL로 연결할 수 있는 하이퍼링크를 만듭니다.
- 하이퍼링크(다른 페이지로 이동)
- a href 태그에서 title로 툴팁 내용 추가 가능 (목적지를 명확히 알려줄 수 있음)
- a href 태그에서 target="_blank" 새 창에서 띄우기


## 명령어 추가  
  
- 드래그 후 보기 > 명령팔레트 > emmet : 약어로 줄별 래핑 > 명령어 입력
- 셋팅 > 바로가기키 > 단축키 설정 가능


## 문서의 섹션 및 관련 구조 요소

### [Section 요소](https://developer.mozilla.org/ko/docs/Web/HTML/Element/section)

HTML Section 요소 (section) 는 문서의 일반적인 구획을 나타냅니다. 즉, (전형적으로 제목을 가지고 있는) 컨텐츠의 주제 그룹을 말합니다. 각 section은 식별되어야하며, 일반적으로 (h1-h6 요소들을 자식으로 가집니다.

### [Article 요소](https://developer.mozilla.org/ko/docs/Web/HTML/Element/article)

HTML article 요소는 문서, 페이지, 애플리케이션,  또는 사이트 안에 독립적으로 구분되거나 재사용 가능한 영역(예: 신디케이션)을 구성할 수 있습니다. 포럼의 글, 매거진/신문의 기사, 블로그 글 등이 여기에 포함됩니다.

### [Nav 요소](https://developer.mozilla.org/ko/docs/Web/HTML/Element/nav)

HTML nav 요소는 현재 페이지 안 또는 다른 페이지로 가는 링크를 보여주는 페이지의 한 구획을 말합니다. 주로 태그 안에 메뉴, 목차, 색인 등이 들어갑니다.

### [Main 요소](https://developer.mozilla.org/ko/docs/Web/HTML/Element/main)

HTML main 요소는 문서나 앱 body의 주요 콘텐츠를 나타냅니다. 주요 콘텐츠 구역은 문서의 핵심 주제나 애플리케이션의 핵심 기능성에 대해 부연, 또는 직접적으로 연관된 콘텐츠들로 이루어집니다.

### [Header 요소](https://developer.mozilla.org/ko/docs/Web/HTML/Element/header)

HTML header 요소는 소개나 탐색을 돕는것의 그룹을 나타냅니다. 이것은 일부 제목 요소들을 포함할수도 있지만, 로고나 구획의 제목, 탐색 폼 과 같은것들이 포함수도 있습니다.

### [Footer 요소](https://developer.mozilla.org/ko/docs/Web/HTML/Element/footer)

HTML footer 요소는 가장 가까운 구획화 콘텐츠나 구획화 루트의 푸터를 나타냅니다. 푸터는 일반적으로 작성자 구획,저작권 데이터,관련된 문서의 링크에 대한 정보를 포함합니다

- 헤더(머릿말) : 로고, 글로벌/로컬 네비게이션(NAV), 링크 목록, 검색
  *NAV(네비게이션) : body의 보조 섹션, 보조섹션이기 때문에 제목을 입력해 줘야하지만 디자인을 위해 숨길 수 있음
  *aside : 내용이 삭제되더라도 메인컨텐츠 이해에 영향을 주지 않는 부가 섹션 (주식, 시세, 날씨, 광고 등)
- 메인 : 웹 페이지에 한 번밖에 못 쓰는 메인 컨텐츠
  *article : 기사 (독립적으로 사용가능한 컨텐츠 블록), 섹션안에 아티클을 표현할 수도 아티클 안에 섹션을 표현할 수도 있음
- 푸터(footer) : 저작권, 연락처, 사이트 정보, 네비게이션
- 3단 vs 4단 차이점 : 3단은 main만 있고(내비게이션은 헤더 안에 위치), 4단은 메인 상단에 내비게이션 위치
- 바디 메인 안에 여러개의 보조 섹션 존재(컨텐츠를 카테고리 별로 그룹핑 할 때)
- 네이티브 : header, main, footer → wai-ara : div role="banner", div role="main" div role"contentinfo" 식으로 role을 지정하여 div로 메인/헤더/푸터 구분을 못하는 점을 보완
- 섹셔닝 콘텐츠는 헤딩과 풋터의 범위를 결정하는 콘텐츠이다. 각 섹셔닝 콘텐츠 요소에는 잠재적으로 heading과 outline을 암묵적으로 가짐
   > - heading
   > - outline
     -명시적 outline(명시적으로 연관성 있는 섹션이며 섹션의 이름이 무엇인지 지정해주고 아웃라인을 구성) / 암묵적 outline(과거에 사용하던 것으로, 내용을 묶진 않았지만 H1과 P로 암묵적 아웃라인이 구성되어 섹션처럼 동작) 
- 헤딩들을 모두 뽑으면 목차가 되기 때문에 헤딩을 잘 설정하여야함
- 숨김 제목을 지정해야하는 이유는 보이스오버(스크린리더) 사용자가 컨텐츠를 쉽게 이해하고 사용하기 쉽게 하기 위함


## 명도 대비
- 텍스트 콘텐츠와 배경 간의 명도대비는 4.5대 1 이상이어야 한다.
- 화면 확대/축소를 지원하는 경우에는 3대 1까지 허용된다.
- 명도 대비 확인 : accessibility CCA (colour contrast analyser) 
  *단축키 - 전경색 f11 배경색 f12
- 한국형웹 콘텐츠 접근성 지침 (미래창조과학부) 5.3.3. 참조
- 웹 접근성 품질인증 표준심사지침 (미래창조과학부)

## 폼(Forms) 요소

텍스트필드, 버튼, 체크박스와 같은 폼 컨트롤을 포함하는 웹페이지의 컴포너트 양식 요소(e.g. 회원 가입 같은 사용자 입력을 받아서 서버에 전송하는)

### [Form 요소](https://developer.mozilla.org/ko/docs/Web/HTML/Element/form)

HTML form 요소는 웹 서버에 정보를 제출하기 위한 대화형 컨트롤을 포함한 문서의 구획을 나타냅니다.

### [Fieldset 요소](https://developer.mozilla.org/ko/docs/Web/HTML/Element/fieldset)

The HTML fieldset 요소는 웹 폼 내에서 label 과 같은 여러 컨트롤을 그룹화 하는데 사용됩니다.

### [Legend 요소](https://developer.mozilla.org/ko/docs/Web/HTML/Element/legend)

HTML legend 요소는(또는 HTML Legend Field 요소) 부모 요소 fieldset의 캡션을 의미합니다.

### [Label 요소](https://developer.mozilla.org/ko/docs/Web/HTML/Element/label)

HTML label 요소는 유저 인터페이스 내 아이템의 캡션을 나타낸다.

### [Input 요소](https://developer.mozilla.org/ko/docs/Web/HTML/Element/input)

HTML input 요소는 사용자로부터 데이터를 받아들이기 위한 웹을 기초로 하는 폼의 상호적인 제어를 만들어 내곤합니다. input의 의미는 타입 속성의 값에 따라서 상당히 달라집니다.

 > 참조 : [Web Forms 2.0 demo page](https://miketaylr.com/pres/html5/forms2.html)

- text (한 줄 글상자)
- password (비밀번호 입력상자)
- search (검색어 입력상자)
- email (이메일 주소)
- url (URL 값)
- tel (전화번호 : 숫자만 가능)

### [Button 요소](https://developer.mozilla.org/ko/docs/Web/HTML/Element/button)

HTML button 요소는 클릭할수 있는 버튼을 나타냅니다.

### 실습 메모

- form action="서버주소" method="GET"
- method(대문자로 써야함) : GET(기본), POST(민감한 정보)
- input : 사용자의 데이터를 입력 받을 수 있는 폼 컨트롤 (input type=text, password, email, number, url)
  > - label : 컨트롤에 레이블(이름)을 붙이고자 할 때 사용
  > - placeholder : textfield 내 입력값 힌트
  > - maxlength : 최대글자수 지정
  > - minlength : 최소글자수 지정
  > - readonly : 읽기전용값 (readonly value=출력할 기본값 입력)
  > - required : 필수입력사항 (입력 안하면 버튼 입력 시 에러)
  > - autofocus list="아이디" : 특정 아이디를 가진 입력상자로 오토포커스

- 입력상자와 submit(전송) 버튼은 같은 폼 안에 있어야함 
- button type : submit(전송), button(일반), reset(초기화)

- Form 태그 내부에 연관성 있는 태그를 field set으로 묶고 legend 요소로 마크업 (e.g. css 제거 시 보이는 아웃라인이 field set이고 설명 타이틀이 legend)
- Field Set : 연결성 있는 서식끼리 그룹핑 (e.g. 필수 입력 서식, 선택 입력 서식을 나누고 싶으면 field set을 2개로 구성하고 legend를 필수 / 선택 두 개 입력)
  *form>fieldset>legend


## 테이블(Table) 요소

### [Table 관련 요소](https://developer.mozilla.org/ko/docs/Web/HTML/Element/table)
HTML table 요소는 2차원 이상의 데이터를 나타냅니다.

- table 로 시작 /table 로 끝
- table caption : 테이블 태그 안에 존재하는 캡션(제목)
- table row(행) = tr 태그 
- table column(열) = 태그 없음
- 셀의 제목(헤더셀) = th
- 데이터 셀 = td
- 셀병합 = colspan / rawspan
- 표는 왼쪽에서 오른쪽으로, 위에서 아래로 읽음 → 제목셀과 내용셀의 연결고리가 필요(scope 또는 id headers)
  * 각각 셀의 이름을 정해준 다음 headers로 연결
    td headers="America First FirstIncome" 100 : 미국 (첫번째)수입 수입 100 (table.html 파일 참조)

## 그 외
- 네이밍 작명 규칙
  > - 파스칼 케이스 : First Incom(첫번째를 무조건 대문자로)
  > - 카멜 케이스 : firstIncome
  > - 스네이크 케이스 : first_income
  > - 케밥 케이스 : first-income
