# Quest 01. HTML과 웹의 기초

## Introduction

-   HTML은 HyperText Markup Language의 약자로, 웹 브라우저에 내용을 표시하기 위한 가장 기본적인 언어입니다. 이번 퀘스트를 통해 HTML에 관한 기초적인 사항들을 알아볼 예정입니다.

## Topics

-   HTML의 역사
    -   HTML 4.01, XHTML 1.0, XHTML 1.1
    -   XHTML 2.0과 HTML5의 대립
    -   HTML5와 현재
-   브라우저의 역사
    -   Mosaic와 Netscape
    -   Internet Explorer의 독점시대
    -   Firefox와 Chrome의 등장
    -   iOS Safari와 모바일 환경의 브라우저
    -   Edge와 Whale 등의 최근의 Chromium 계열 브라우저
-   HTML 문서의 구조
    -   `<html>`, `<head>`와 `<body>` 등의 HTML 문서의 기본 구조
    -   시맨틱 엘리먼트
    -   블록 엘리먼트와 인라인 엘리먼트의 차이

## Resources

-   [MDN - HTML](https://developer.mozilla.org/ko/docs/Web/HTML)
-   [HTML For Beginners](https://html.com/)
-   [History of the web browser](https://en.wikipedia.org/wiki/History_of_the_web_browser)
-   [History of HTML](https://en.wikipedia.org/wiki/HTML)
-   [StatCounter](https://gs.statcounter.com/)

## Checklist

-   HTML 표준의 역사는 어떻게 될까요?
    -   HTML 표준을 지키는 것은 왜 중요할까요?
    -   XHTML 2.0은 왜 세상에 나오지 못하게 되었을까요?
    -   HTML5 표준은 어떤 과정을 통해 정해질까요?
-   브라우저의 역사는 어떻게 될까요?
    -   Internet Explorer가 브라우저 시장을 독점하면서 어떤 문제가 일어났고, 이 문제는 어떻게 해결되었을까요?
    -   현재 시점에 브라우저별 점유율은 어떻게 될까요? 이 브라우저별 점유율을 알아보는 것은 왜 중요할까요?
    -   브라우저 엔진(렌더링 엔진)이란 무엇일까요? 어떤 브라우저들이 어떤 엔진을 쓸까요?
    -   모바일 시대 이후, 최근에 출시된 브라우저들은 어떤 특징을 가지고 있을까요?
-   HTML 문서는 어떤 구조로 이루어져 있나요?
    -   `<head>`에 자주 들어가는 엘리먼트들은 어떤 것이 있고, 어떤 역할을 할까요?
    -   시맨틱 태그는 무엇일까요?
        -   시맨틱 엘리먼트를 사용하면 어떤 점이 좋을까요?
        -   `<section>`과 `<div>`, `<header>`, `<footer>`, `<article>` 엘리먼트의 차이점은 무엇인가요?
    -   블록 레벨 엘리먼트와 인라인 엘리먼트는 어떤 차이가 있을까요?

## Quest

-   [이 화면](screen.png)의 정보를 HTML 문서로 표현해 보세요. 다만 CSS를 전혀 사용하지 않고, 문서의 구조가 어떻게 되어 있는지를 파악하여 구현해 보세요.
    -   [CSS Naked Day](https://css-naked-day.github.io/)는 매년 4월 9일에 CSS 없는 웹 페이지를 공개하여 내용과 마크업에 집중한 HTML 구조의 중요성을 강조하는 행사입니다.
-   폴더에 있는 `skeleton.html` 파일을 바탕으로 작업해 보시면 됩니다.
    -   화면을 구성하는 큰 요소들을 어떻게 처리하면 좋을까요?
    -   HTML 문서상에서 같은 층위에 비슷한 요소들이 반복될 때는 어떤 식으로 처리하는 것이 좋을까요?

## Advanced

-   XML은 어떤 표준일까요? 어떤 식으로 발전해 왔을까요?
-   YML, Markdown 등 다른 마크업 언어들은 어떤 특징을 가지고 있고, 어떤 용도로 쓰일까요?

---

## 시맨틱태그

<aside>
💡 HTML 문서에서 콘텐츠의 의미와 구조를 더 명확하게 사용되는 태그들. 시맨틱 태그를 사용하면 웹 브라우저와 검색 엔진은 문서를 더 잘 이해하고 해석하며 웹 접근성을 개선할 수 있다.

</aside>

-   **header** : 문서나 섹션의 머리말을 정의한다. 주로 제목, 로고, 네비게이션 메뉴 등의 요소를 포함시킨다
-   **nav** : 웹사이트의 주요 메뉴나 네비게이션 역할을 하는 링크를 그룹화할때 사용한다
    -   ol or ul : 목록을 나타내며(정렬 비정렬) li 태그를 둘러싸고 있어야 한다
-   **main** : 문서의 주요 컨텐츠를 정의, 하나의 문서에는 한번만 사용되어야한다
-   **article** : 독립적인 콘텐츠 조각을 정의한다. 예로 뉴스 기사, 블로그 포스트, 게시물 등등
-   **section** : 문서의 섹션을 정의하며 주제별로 그룹화한다 주로 시맨틱 구조를 만들때 사용
-   **aside** : 주요 컨텐츠와 연관된 보조 컨텐츠를 정의, 주로 사이드바, 광고, 사이트 부가정보 등등
-   **footer :** 문서나 섹션의 바닥글을 정의, 주로 저작권 정보, 연락처, 관련링크 등을 포함
-   **mark** : 텍스트를 강조할때 사용
-   **time** : 시간 또는 날짜 정보를 정의
-   **details** : 추가 정보 또는 내용을 접을 수 있는 펼첨식 위젯으로 정의, 주로 FAQ 목록을 만들때 사용
    -   summary : 요약 또는 제목을 정의, 사용자가 접을때 표시되는 제목을 나타낼때 사용

## BEM

<aside>
💡 Block Element Modifier 컨벤션으로 요소를 더 명확하게 식별할 수 있도록 도와준다.

개인마다 정의하는 바가 다를 수 있지만 프로젝트 진행시 컨벤션을 정하고 시작하면 유지보수에 도움된다.

</aside>

1. **Block** : 페이지의 큰 부분 또는 구성 요소를 나타낸다.
2. **Eelment** : 블록에 속한 특정 부분을 나타낸다
   ex) button 블록 내의 엘리먼트로 text, icon, label 등이 있을 수 있으며 이런 엘리먼트는 button\_\_text or ButtonText로 나타낸다.
3. **Modifier** : 블록 또는 엘리먼트의 상태, 스타일, 변형을 나타낸다
   ex) button—large, button—small, button—icon—small 등등

### Block Naming

-   **Wrapper** : 주요 컨테츠영역을 래핑하거나 특정 섹션을 둘러싸는 역할
-   **Container** : 하나 이상의 요소를 포함할 수 있는 구조를 둘러싸는 역할
-   **Box** : 완전한 컨텐츠 블록을 나타낸다.
    -   UI 에 따라 Card, Circle등으로 대체

**Wrapper VS Container**

> 프로그래밍 관점으로 Container은 하나 이상의 요소를 포괄하는 개체를 지칭하며 wrapper는 하나의 개체만 포함하는 것을 뜻한다.
> https://stackoverflow.com/questions/4059163/css-language-speak-container-vs-wrapper
