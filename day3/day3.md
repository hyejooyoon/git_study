
# Day 3 학습 내용

## CSS (Cascading Style Sheets)
CSS는 HTML 문서를 스타일링 하는 언어를 말합니다. 디자인 목업 파일(PSD, Sketch 그래픽 시안)에서 스타일링 요소들(레이아웃, 컬러, 타이포그래피 등)을 분석하여 CSS 언어를 사용하여 스타일링 합니다.

- 구조와 디자인을 구분해야함
- Cascade : 레이어드, 겹침
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

## [CSS 상속(Inherit)](https://developer.mozilla.org/ko/docs/Web/CSS/inherit)

inherit CSS 값은 요소가 부모 요소로부터 속성(property)의 계산값(computed value)을 갖도록 지정되게 합니다. 모든 CSS 속성에 허용됩니다.

상속되는 속성(inherited properties)의 경우, 이는 기본 동작(behavior)을 강화하고 오직 다른 규칙을 재정의(override / 위에 겹쳐쓰기)해야 합니다. 상속되지 않는 속성(non-inherited properties)은, 이는 보통 비교적 거의 의미가 없는 동작을 지정하고, 대신 initial 혹은 all 속성에 unset 사용을 고려할 지도 모릅니다.

상속(Inheritance)은 심지어 부모 요소가 포함(containing) 블록이 아니더라도, 항상 문서 트리(body) 내 부모 요소로부터입니다.

- 상속되는 속성(글자색, 글자 디자인에 관련된 것)
- 상속되지 않는 속성(공간에 관련된 것, outline border margin 같은 것) 

## [겹침(Cascade)](https://developer.mozilla.org/ko/docs/Web/CSS/Cascade)

종속(Cascade)이란 서로 다른 원점에서 가져온 속성 여럿을 조합해 최종 결과를 도출하는 알고리즘입니다. Cascading Style Sheets라는 이름에서도 알 수 있듯 종속은 CSS의 중심입니다. 이 글은 종속이 무엇인지, 선언한 CSS 정의가 어떤 순서로 종속되는지, 그리고 여러분, 즉 웹 개발자에게 어떤 영향을 주는지 설명합니다.

- 기본적으로는 마지막에 선언한 것이 우선함
- !important 선언을 하면 다른 선언보다 우선권을 가짐(최대한 사용하지 않기)
  e.g. p { color: red !important; } 
- 구체성(Specificity) : 좀 더 구체적으로 말하는 것. 선택자의 우선권에 대한 척도.    

> ##### 요소 선택자 < 클래스선택자 < ID 선택자 < 인라인스타일
> * 이 때 *, >, +, ~등 콤비네이터, :not() 가상클래스는 특성에 영향을 주지않음
> * 선택자를 몇 개 썼는지를 체크

| 예시 | Inline Style | ID | Class | Element |
|:--------|:--------:|:--------:|:--------:|:--------:|
| P | 0 | 0 | 0 | 1 |
| .note | 0 | 0 | 1 | 0 |
| p.note | 0 | 0 | 1 | 1 |
| #outer a | 0 | 1 | 0 | 1 |

## CSS Typography

- 글꼴(모양) font-family, 크기 font-size, 굵기 font-weight, 이탤릭 font-style
- 컬러값 
  1) color keywords : red, green, blue ...
  2) hex color code(#RRGGBB → #000000는 #000 으로 줄여서 쓸 수 있음)
  3) rgb, rgba(alpha 투명도 추가) e.g. rgba(127,255,0,0.3)
  4) hsl, hsla : Hue, Saturation, Lightness을 각도값으로 입력(0도는 red)

