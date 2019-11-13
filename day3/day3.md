
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

> <br> <b>요소 선택자 < 클래스선택자 < ID 선택자 < 인라인스타일</b>
> * 이 때 *, >, +, ~등 콤비네이터, :not() 가상클래스는 특성에 영향을 주지않음
> * 선택자를 몇 개 썼는지를 체크 
> <br>

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

## [CSS 기본 박스모델(BOX Model)](https://developer.mozilla.org/ko/docs/Web/CSS/CSS_Box_Model) (*중요!)

CSS Basic Box Model은 각 요소에 대해 [시각적 서식 모델](https://developer.mozilla.org/ko/docs/Web/Guide/CSS/Visual_formatting_model)에 따라 생성하고 배치하는 사각형 박스(안팎 여백 포함)를 위한 CSS 모듈입니다.

- [display](https://developer.mozilla.org/ko/docs/Web/CSS/display)
- [box-sizing](https://developer.mozilla.org/ko/docs/Web/CSS/box-sizing)
- [width](https://developer.mozilla.org/ko/docs/Web/CSS/width)
- [height](https://developer.mozilla.org/ko/docs/Web/CSS/height)
- [margin](https://developer.mozilla.org/ko/docs/Web/CSS/margin)
- [border](https://developer.mozilla.org/ko/docs/Web/CSS/border)
- [padding](https://developer.mozilla.org/ko/docs/Web/CSS/padding)

<br>

> <b>블록(Block, Flow contents) vs 인라인(Inline, Phrasing Contents)</b>
- 블록 박스 : 여백 포함 (너비 width, 높이 height 설정 가능) → 위에서 아래로 쌓여내려가는 형태
  *검사(개발툴) > style > displayed 또는 computed > display 에서 뭔지 파악 
- 인라인 박스 : 컨텐츠만 (너비, 높이 설정 불가)
- 인라인 블록박스 : 인라인 성질을 가지지만 블록 박스처럼 높이, 너비 설정 가능
  *width 기본 값 : 100%(부모값)
- 블록, 인라인, 인라인블록박스는 정렬 기법(상자를 가운데에 놓고 싶어요) 사용 불가 → flex 박스는 가능

> <b>margin-box(외부공간) > border-box(테두리공간) > padding-box(내부공간) > content-box(콘텐츠공간)</b>
- 나머지는 색상 지정 가능, margin box는 배경색이 먹지 않음(여백 제어에만 사용)
- margin box의 negative margin : 음수값을 적용할 수 있음
- 인라인박스는 좌/우 방향으로는 마진, 패딩이 바로 보이는데 상/하 방향으로는 마진, 패딩을 설정해도 <b>투명하게 겹쳐져서</b>(높이에 영향을 주지않음, 대신 링크를 주면 겹친만큼 링크 영역은 확장됨) 렌더링 상에선 눈으로 변화가 보이지 않음
- margin : t r b l (top right bottom left) e.g. margin : 20px 10px 10px 20px
- margin 50px auto (두번째 값 auto는 좌우값) / margin 50px 0px 0px auto 하면 오른쪽으로 딱붙는 박스가 되지만 여백이 투명해서 안보일 뿐임
- text-align : 블록 박스일 때만 사용가능 (x축 기준)
- line-height : 글자 포함 상하 높이를 설정
- Dimension 설정 : 블록박스, 인라인블록박스의 수치 설정으로 박스 크기를 변경 (width, height)

- <b>박스사이징 속성</b>
  *content-box 방식 (기본 박스방식) : 기본 width 및 height에 추가로 보더(아웃라인) 값을 더해야함
  *border-box 방식 : width와 height에 border, padding 값 포함 (*{box-sizing: border-box;})


## [플렉시블 레이아웃(Flexible Layout)](https://developer.mozilla.org/ko/docs/Glossary/Flex)

flex는 CSS display속성에 새롭게 추가 된 값입니다. inline-flex동시에 사용하는 것으로, Element에 Flex 컨테이너 가 적용됩니다. 또한 그 Element의 자식 Element 각각은 Flex 항목 이 적용됩니다. flex 항목이 적용 된 Element는 flex layout을 구성하고 CSS Flexible Box Layout Module에 정의되어있는 속성의 모든이 적용되는 것입니다.

flex속성은 flexbox 속성을 줄여서 나타낸 속성입니다. flex-grow나 flex-shrink, flex-basis 등이 있습니다.

> *참고사이트 : [Flex CSS Tricks](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)


<!-- <div style="overflow: hidden">
  <div style="width: 50%; float: left;"><img src="./img/01-container.svg" alt=""></div>
  <div style="width: 50%; float: left;"><img src="./img/02-items.svg" alt="">
</div>
<br> -->

<img src="./img/01-container.svg" alt="" width="400">
<img src="./img/02-items.svg" alt="" width="400">


- flex-container 부모 요소 > flex-items 자식 요소
- flex-container로 지정하려면 display 값을 flex로 주면됨
- 기본 흐름이 위→아래에서 flex로 바꾸면 row 방향(X축)으로 변경
  *flex-container 하단에 <b>flex-direction</b> 값으로 main axis(메인축)을 column(y축) 또는 row(x축), column-reverse(y축 거꾸로), row-reverse(x축 거꾸로 5-4-3-2-1)까지 설정 가능  
  *축은 정렬을 하기 위해 설정  
  *시작점 flex start > 중앙점 center > 종료점 end  
<br>
- <b>justify-content 설정 (주축 정렬)</b>
  e.g. justify-content:center 중앙점부터 배치
  
  1) space-between(박스 사이만의 여백을 동일하게 : grid system의 거터)  
  2) space-around(박스의 양쪽 여백을 동일하게 - 박스 사이 여백이 양 쪽 끝 여백의 두 배)  
  3) space-evenly(박스의 모든 여백을 동일하게) 
  *알파마진, 오메가마진 등 자동균등분할이 가능  
  4) flex-wrap : wrap; 줄바꿈 허용 / nowrap 자동축소  
  5) flex-shrink : 축소 비율 결정 (디폴트값 1)  
  6) flex-grow : 확대 비율 결정 (디폴트값 0)  
  7) flex-basis  
 
- item (교차축 정렬)
- item의 order값을 통해 정렬 변경 가능 (.item4 {order: -1;})
- normal 배치에서는 상하 마진값이 자동겹쳐서 균등 배치 되는데, flex 배치에서는 동일하게 안됨

#### 그 외 
 - .container>.item*4 (.앞에 아무것도 안쓰면 div가 생성됨)
 - .container>.item.item$*4 (공통으로 아이템 숫자 생성)
 - ctrl + ? : 주석처리
 - top: initial ← 위에서 설정해놓은 것을 초기화
 - caniuse 사이트에서 검색 후 polyfill (대안 방법)을 찾을 수 있음

## [포지션 레이아웃](https://developer.mozilla.org/ko/docs/Web/CSS/position)

position CSS 속성은 문서 상에 요소를 배치하는 방법을 지정합니다. top, right, bottom,  left 속성이 요소를 배치할 최종 위치를 결정합니다.

- 포지셔닝 : 기본 레이아웃 흐름(Normal Layout Flow)을 재정의 (e.g. layer나 스크롤와 상관없이 같은 곳에 계속 띄우기, 고정 위치에 반투명한 헤더/네비 출력 등 자유로운 배치 가능)
- 유지보수가 어려운 단점이 있음

### 배치 유형
배치 요소는 position의 계산값이 relative, absolute, fixed, sticky 중 하나인 요소입니다. 즉 static이 아닌 요소입니다. 

상대적 배치 요소는 position의 계산값이 relative인 요소입니다. top과 bottom은 원래 위치에서의 세로축 거리를, left와 right은 원래 위치에서의 가로축 거리를 지정합니다.  

절대적 배치 요소는 position의 계산값이 absolute 또는 fixed인 요소입니다. top, right, bottom, left는 요소 컨테이닝 블록 모서리로부터의 거리를 지정합니다. 요소가 바깥 여백을 가진다면 거리에 더합니다.  

끈끈한 배치 요소는 position의 계산값이 sticky인 요소입니다. 상대적 배치 요소로 동작하다가 컨테이닝 블록이 플로우 루트flow root(또는 스크롤 중인 컨테이너)의 임계값을 넘으면, 컨테이닝 블록의 반대편 모서리를 만날 때까지 "부착"됩니다.

1) 정적 위치(static) : 기본값(위치값을 지정하지 않았을 때 기본값)
   > 기본값입니다. static이 지정된 요소는 document의 일반적인 흐름(normal flow)을 따라 배치됩니다. top, right, bottom, left, z-index 속성들이 static에서는 아무런 효과도 주지 못합니다. 

2) 상대 위치(relative) : 자신의 기준(t r 오른쪽상단/ b l 왼쪽하단)
   - e.g. top: 30px; right: -100px → 위에서 30 오른쪽에서 100만큼 이동
   - z-index : 겹치는 것을 정함 (숫자가 클수록 위로, 같은 숫자라면 나중에 작성된 게 우선권을 가짐)
   > relative가 지정된 요소 역시 document의 일반적인 흐름(normal flow)을 따라 배치됩니다. 그리고 요소 자신에 대한 상대적인 top, right, bottom, left 속성에 의한 좌표로 배치됩니다. (relative는 별도의 거리 속성을 주지 않으면 static과 동일하게 동작합니다.)이때 요소의 좌표는 다른 요소들의 위치에 영향을 주지 않습니다. 따라서, 페이지 레이아웃에서 요소에게 지정된 공간은 static일 때와 동일합니다. relative는 z-index의 값이 auto가 아닐 경우에 새로운 stacking context를 만듭니다. table-*-group, table-row, table-column, table-cell, table-caption 요소에 relative가 주는 효과는 정의되지 않았습니다.

3) 절대 위치(absolute) : layer의 개념(float), 부모 내에서 위치
   > 요소가 일반적인 문서(document) 흐름에서 제거됩니다. 페이지 레이아웃에서 요소에 대한 공간이 생성되지 않습니다. 대신, 가장 가까운 위치에있는 조상에 대해 상대적 위치로 배치됩니다. 그렇지 않으면 초기 컨테이닝 블록을 기준으로 배치됩니다. 최종 위치는 top, right, bottom, left 값에 의해 결정됩니다. 이 값은 z-index가 auto가 아닌 경우에 새로운 stacking context를 생성합니다. 절대적으로 배치된(positioned) 박스(box)들은 마진을 가질 수 있으며 다른 마진에 의해 망가지지 않습니다.


4) 고정 위치(flex) : 스크롤과 상관 없이 같은 곳에 위치(광고 같은 거), 사용자가 보는 화면단(view 포트)이 기준(부모 찾지 않음)
   > 요소가 일반적인 문서(document) 흐름에서 제거됩니다. 페이지 레이아웃에서 요소에 대한 공간이 생성되지 않습니다. 대신, 스크린의 '뷰포트(viewport)를 기준으로 한 위치'에 배치됩니다. 따라서 스크롤되어도 움직이지 않는 고정된 자리를 갖게 됩니다. top, right, bottom, left 값에 의해 최종 위치가 결정됩니다. 이 값은 항상 새로운 stacking context를 생성합니다. 조상의 transform 속성이 none이 아닌 다른 것으로 설정되면, 그 조상은 뷰포트 대신에 컨테이너로 사용됩니다(CSS Transforms Spec). 인쇄된 문서(document)의 경우, 모든 페이지에서 요소가 동일한 위치에 배치됩니다.


5) 달라붙는 위치(sticky) : IE 11 브라우저 미지원 ([작동방식 참고사이트](https://html5-demos.appspot.com/static/css/sticky.html))
   > 요소가 일반적인 문서(document) 흐름에 따라 배치됩니다. 그런 다음 top, right, bottom, left 값을 기준으로 플로우 루트(flow root) 및 해당 요소를 포함하는 블록(containing block)에 대한 상대적(relative) 위치에 자리하게 됩니다. 이 오프셋은 다른 요소들에 영향을 주지 않습니다. 이 값은 항상 새로운  stacking context를 생성합니다. 테이블과 관련된 요소들에 미치는 sticky의 효과는 relative와 동일합니다. 브라우저 사양에 따라 overflow : hidden 또는 auto 요소 내에서 작동하지 않을 수 있습니다. (참조: Github issue on W3C CSSWG)

