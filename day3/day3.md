
# Day 3 학습 내용

## CSS (Cascading Style Sheets)
CSS는 HTML 문서를 스타일링 하는 언어를 말합니다. 디자인 목업 파일(PSD, Sketch 그래픽 시안)에서 스타일링 요소들(레이아웃, 컬러, 타이포그래피 등)을 분석하여 CSS 언어를 사용하여 스타일링 합니다.

- 구조와 디자인을 구분해야함
- Cascade : 레이어드, 겹치는
- REC : 표준 스펙 
- 브라우저 및 지원버전, 브라우저 호환 고려 (caniuse.com)

## CSS 문법
- 대상 선택자, 선언구간{}, 속성 :(구분) 값 ;(종료)
  e.g. P {font-family: Arial ;}
- head 내부에서만 사용 (body에 사용하지 않음)
- External Style : style.css (스타일스타일) 파일을 따로 만들어서 head에 css 파일을 link
- class 선택자는 . 으로 구분 
  e.g. p.note(P요소이면서 note class인 것 = and 조건이며 붙여서 써야함)
       p.note.floatLeft(class를 두 개를 붙일수도 있음 = 멀티 class 선택자)
- Descendant selector (자손 선택자 : ~안에 있는 OO를 찾아주세요)
  e.g. p strong (p안에서 strong을 찾아주세요)


## [CSS란?](https://developer.mozilla.org/ko/docs/Glossary/CSS)
CSS(Cascading Style Sheets, 종속형 스타일 시트)는 브라우저에서 웹페이지의 외형을 결정하는 선언형 언어입니다. 브라우저는 선택한 요소에 CSS 스타일 선언을 적용해 화면에 적절히 표현합니다. 하나의 스타일 선언은 속성과 그 값으로 이루어져 있습니다.

CSS는 HTML, JavaScript와 함께 웹의 3대 핵심 기술을 이룹니다. 보통 HTML 요소의 스타일을 결정하지만, SVG와 XML 등 다른 마크업 언어에도 사용할 수 있습니다.

하나의 CSS 규칙은 선택자에 연결된 속성 세트로 구성됩니다.

## [CSS 선택자(Selector)](https://developer.mozilla.org/ko/docs/Glossary/CSS_Selector)

- 전체 선택자(Universal Selectors)
- 태그, 요소 선택자(Type Selectors)
- 클래스 선택자(Class Selectors)
- 아이디 선택자(ID Selectors)
- 속성 선택자(Attribute Selectors) 
- 상태 선택자(State Selectors)

