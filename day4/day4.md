# Day 4 학습 내용

- [Troy Web](http://troy.labs.daum.net/) : 실 디바이스 환경에서 어떻게 보이는지 체크할 때 사용
- <b>픽셀 밀도(pixel density)</b> : 공간(inch)에 픽셀이 들어가는 물리적인 수치(첫 맥킨토시는 인치당 72px이었음)
- <b>디바이스의 픽셀 밀도(device pixel density)</b> : 애플이 2010년 픽셀을 x2(가로와 세로가 2배 = 72X4이므로 4배만큼 훨씬 촘촘해짐)로 올린 레티나(Retina Display) 공개 
  → 물리적인 디바이스 크기는 그대로지만 고해상도를 지원하도록 디자인(설계) 과정에서 픽셀 밀도를 고려해야하게 됨
- Bitmap → Vector(css, svg img, text도 vector) 기반으로 변화 중이므로 이를 고려해야함
- 요소검사 개발툴(F12) > console tab > window.devicePixelRatio 검색하면 모니터의 비율을 알 수 있음
- normalize.css를 쓰는 이유 : 모바일 디바이스에서 세로모드(Potrait mode)에서 가로모드(landscape mode)로 전환(orientation change) 시 iOS에서 장평이 변화하는 등의 문제 등을 기본적으로 수정 적용
- css 파일에서 : : 는 상태선택자


## 이디야 웹제작실습
- meta name="viewport" content="width=device-width, initial-scale=1.0"  
  → "width=device-width"가 반응형웹에서 모바일 물리 디바이스 해상도에 맞춰서 표현하라는 것
- section, aticle, nav, aside는 암묵적으로 heading을 가지며 head는 '제목'이 필요함
  → 제목 텍스트를 출력하진 않지만 보이스 오버로 읽어주는 숨김 명령어 : <b>a11y-hidden</b>
- H1.brand>a (.은 클래스 지정, >는 자식요소를 만들겠다는 뜻) → 엔터치면 H1 class="brand" a href="" 가 됨
- Span class="ir" 은 IR 이미지를 배경으로 쓰겠다는 것 
  → IR은 배경 처리 되어서 대체텍스트를 줄 수 없기 때문에 title(툴팁)과 aria-label로 레이블링 해줘야 함


1. 마크업 순서 결정 (brand name → drawer btn → main contents)
2. 구조 짜기 : 각 영역의 제목(class)을 지정해 줌 ([tota11y chrome plug-in](https://chrome.google.com/webstore/detail/tota11y-plugin-from-khan/oedofneiplgibimfkccchnimiadcmhpe)으로 체크)
3. 드로워(네비게이션) 열기 버튼 삽입 
  → 이미지 입력 시 대체 텍스트 삽입
  → 열렸을 때 메뉴를 ul 안에 li로 작성
  → 드로워 닫기 버튼을 만들기
     > button type="button"(버튼 타입은 button으로) title="메뉴 닫기" aria-label="메뉴 닫기"(보이스오버를 위해 마크업)>
  span aria-hidden="true" X /span  → aria-hidden은 보이스오버에서 X를 읽지 않도록 하는 명령어
4. 음료 정보를 어떻게 표현할 건지 순서 구조 고민하기
  → 음료들의 순서가 중요하지 않으므로 ul > li로 만들자
  → 음료 전체 이미지는 clickable하기 때문에 button으로 써야하지만, figure 태그를 쓸 수 없음(문법 오류) 
  → 그러므로 비슷한 성격의 '앵커(a)' 태그를 사용하자. 근데 앵커 태그를 사용하면 보이스오버가 '~링크'라고 읽음. 그러므로 role="button"을 줘서 버튼으로 동작하도록 명령(보이스오버가 ~버튼이라고 읽어줌)
  → 이 때 a 태그에 aria-haspopup="dialog" 프로퍼티를 함께 주면 보이지는 않지만 보이스오버로 버튼을 누르면 다이얼로그가 뜬다고 알려주게됨
  → a 태그에 추가로 aria-pressed="false" 눌러지지 않은 상태임을 설정(nor 상태)
5. 모달 윈도우 만들기 → 안에 내용이 너무 많으므로 div로 구분
   → div / h3 / div(dl) / close button
   → div의 역할모델(role)을 dialog로. hidden 해놨다가 aria-pressed="true"가 되면 스크립트로 hidden을 날려서 보여주는 것
   > → 참고 영상 : [dialog role을 활용한 레이어팝업](https://youtu.be/Yv0dBR-ygg8)
      → div class="ediya-menu__item--detail" hidden role="dialog" aria-modal="true" aria-labelledby="edia-menu__item1"
    다이얼로그로 role을 주면 labbedby로 연결을 시켜줘야함
    → aria-modal 은 열렸을 때 다른 것의 제어권을 블락할지 말지 정하는 것(true=다른 것 누를 수 있게)
6. 하단 P 목록 작성 dl(쌍을 이루는) > dt / dd를 통해 셋트로 묶어줌
7. 윈도우 닫기 버튼 만들기 
8. 특수문자 사용시 &copy; 저작권 C 표시 & c o p y ; 로 써야함


## CSS 실습
- nav a {
  color: inherit; 컬러값을 부모에 상속하겠다
  text-decoration: none; 밑줄을 긋지 않겠다
  
- a img {
  vertical-align: middle; 이미지를 중간에 위치하게

- clip-path: polygon(0 0,0 0,0 0);
  → [참조 사이트](https://bennettfeely.com/clippy/)

- 커서 모양 바꾸기 : cursor: crosshair;

- [user select](https://developer.mozilla.org/ko/docs/Web/CSS/user-select)
