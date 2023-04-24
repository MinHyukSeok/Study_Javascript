# Browser APIs
- 웹 브라우저에 내장된 API로, 웹 브라우저가 현재 컴퓨터 환경에 관한 데이터를 제공하거나, 오디오를 재생하는 등 여러가지 유용하고 복잡한 일을 수행할 수 있게 함
- JavaScript로 Browser API들을 사용해서 여러가지 기능을 사용할 수 있음
- 종류
  - DOM
  - Geolocation API
  - WebGL 등

## 브라우저가 웹 페이지를 불러오는 과정
- 웹 페이지를 브라우저로 불러오면, 브라우저는 코드(HTML, CSS, JavaScript)를 실행 환경(브라우저 탭)에서 실행
- JavaScript는 DOM API를 통해 HTML과 CSS를 동적으로 수정, 사용자 인터페이스를 업데이트하는 일에 가장 많이 쓰임
# DOM
- 문서 객체 모델 (Document Object Model)
- 문서의 구조화된 표현을 제공하며 프로그래밍 언어가 DOM 구조에 접근할 수 있는 방법을 제공
  - 문서 구조, 스타일, 내용 등을 쉽게 변경할 수 있게 도움
  - HTML 콘텐츠를 추가, 제거, 변경하고 동적으로 페이지에 스타일을 추가하는 등 HTML/CSS를 조작할 수 있음
- HTML 문서를 구조화 하여 각 요소를 객체로 취급
- 단순한 속성 접근, 메서드 활용 뿐만 아니라 프로그래밍 언어적 특성을 활용한 조작이 가능함

## DOM Tree
- DOM은 문서를 논리 트리로 표현
- DOM에서 모든 것은 Node
- 즉, HTML 요소, 속성, 텍스트 모든 것이 노드
- 각 노드는 부모, 자식 관계를 형성하고 이에 따라 상속 개념도 동일하게 적용됨
### Node
- DOM의 구성 요소 중 하나
- HTML 문서의 모든 요소를 나타냄

### DOM의 주요 객체
- window
- document
- navigator, location, history, screen

## window object
- DOM을 표현하는 창
- 가장 최상위 객체


## document object
- 브라우저가 불러온 웹 페이지
- 페이지 컨텐츠의 진입점 역할을 하며, body 등과 같은 수많은 다른 요소들을 포함하고 있음

# DOM 조작
- Document가 제공하는 기능을 사용해 웹 페이지 문서 조작하기
- DOM 조작 순서
    1. 선택
    2. 조작
       - 생성, 추가, 삭제 등

## 선택 관련 메서드
- document.querySelector(selector)
  - 제공한 선택자와 일치하는 element 한 개 선택
  - 제공한 CSS seletor를 만족하는 첫 번째 element 객체를 반환 (없다면 null 반환)
- document.querySelectorAll(selector)
  - 제공한 선택자와 일치하는 여러 element를 선택
  - 매칭 할 하나 이상의 셀렉터를 포함하는

### NodeList
- DOM 메서드를 사용해 선택한 노드의 목록
- 배열과 유사한 구조를 가짐
- Index로만 각 항목에 접근 가능
- 배열의 forEach 메서드 및 다양한 배열 메서드 사용 가능
- querySelectorAll()에 의해 반환되는 NodeList는 DOM의 변경사항을 실시간으로 반영하지 않음


## 조작 관련 메서드 (생성)
- Node.innerText
  - Node 객체와 그 자손의 텍스트 컨텐츠를 표현
  - 사람이 읽을 수 있는 요소만 남김
  - 즉, 줄 바꿈을 인식하고 숨겨진 내용을 무시하는 등 최종적으로 스타일링이 적용된 모습으로 표현됨
- Node.appendChild()
  - 한 Node를 특정 부모 Node의 자식 NodeList 중 마지막 자식으로 삽입
  - 한번에 오직 하나의 Node만 추가할 수 있음
  - 추가된 Node 객체를 반환