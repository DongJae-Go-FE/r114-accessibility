# 부동산R114 웹 접근성 가이드라인
누구든지 동등하게, 부동산 R114 웹 접근성 가이드라인.

**작성자:IT본부 UI/UX Unit 가동재 사원**

1. [대체 텍스트](#altIr)
2. [자막 제공](#subTitle)
3. [색상](#color)
4. [화면을 400%까지 확대 가능](#zoom)
5. [명확한 지시사항 제공](#instruction)
6. [키보드만으로 조작 가능](#keyboard)
7. [사용할 수 있는 충분한 시간 제공](#time)
8. [동영상 자동 재생 금지 및 발작을 유발하는 콘텐츠를 제공 금지](#seizure)
9. [반복되는 콘텐츠 블록을 건너뛸 수 있다.](#bypass)
10. [모든 문서의 제목은 고유하고 식별할 수 있다.](#title)
11. [콘텐츠 간의 구분](#division)
12. [링크와 버튼 텍스트는 콘텐츠의 목적을 적절하게 제공](#link)
13. [섹션에는 의미 있는 마크업과 헤딩](#outline)
14. [문서의 휴먼 랭귀지 속성을 제공](#lang)
15. [문맥 변경은 예측 가능](#predict)
16. [콘텐츠의 선형화](#linear)
17. [표의 구성](#table)
18. [폼 컨트롤 요소에 설명을 제공](#form)
19. [실수를 예방하고 정정하는 것을 돕는다.](#assist)
20. [HTML 문법을 준수](#html)

그 어떤 누구나 동등하게 차별 없이 부동산 R114 홈페이지를 이용할 수 있도록 하는 것이 저의 목표입니다. 부동산 R114에서 제공하는 모든 웹 서비스는 '**부동산 R114 웹 접근성 가이드라인**'을 준수해야 합니다. 데스크톱, 태블릿, 모바일, 하이브리드 앱에 이르기까지 웹 기술을 통해 구현하는 모든 서비스가 이 가이드라인의 적용 대상입니다.


해당 가이드라인은 [WCAG 2.1](https://www.w3.org/TR/WCAG21/)이 토대로 작성을 하였으며 가이드라인에서 설명하지 않거나 애매한 주제는 WCAG 2.1의 수준 A 항목과 AA 항목의 지침 및 평가 방법을 따라야 합니다.(추후 WCAG 2.2 기반으로 업데이트할 예정입니다.)
부동산 R114 웹 접근성 가이드라인은 부동산 R114 서비스에 대응하는 WCAG 2.1 가이드라인에 대한 이해를 돕고 손쉽게 평가할 수 있도록 소개한 것으로써 고객에게 웹 서비스를 제공하기 전 준수해야 할 최소한의 요구사항입니다.

해당 가이드라인은 기초를 설계하는 기획자부터 디자이너, 퍼블리셔, 개발자들 모두가 지켜야 할 가이드라인입니다.

이 가이드라인은 HTML, CSS, JavaScript 대한 사전 지식을 필요로 합니다.

---

## 1. 대체 텍스트 <a id="altIr" href="#altIr">#</a>
* 텍스트가 아닌 콘텐츠는 오류로 인해 렌더링 또는 불러오기가 불가능할 경우를 대비하여 그 의미나 용도를 이해할 수 있도록 대체 텍스트를 제공해야 한다.
* 대체 텍스트는 중복으로 제공하지 않는다.
* 의미 있는 텍스트가 아닌 콘텐츠(이미지, 영상, 음악 등등 멀티미디어)가 아닌 콘텐츠에 그 의미나 용도를 동등하게 인실할 수 있는 적절한 대체 텍스트를 제공한 경우에 준수한 것으로 인정한다.
* 배경 이미지가 의미 있는 정보를 제공하고 있으나 이를 텍스트 형태의 정보로 제공하지 않은 경우 IR(Image Replacement) 기법을 사용한다. -IR(Image Replacement) 기법 대체 텍스트를 css로 숨기는 css hack
* 찾아오시는 길, 뉴스 사진과 같은 본문 이미지에 대하여 대체텍스트를 빈값으로 제공하고, 본문에 설명을 제공하면 준수한 것으로 인정한다.
* QR코드 등과 같이 시각적인 정보만으로 확인이 가능한 콘텐츠(기능)의 이동 주소 정보 등을 대체텍스트 또는 설명, 링크 등으로 제공하지 않은 경우을 이동하는 페이지 목적지에 대한 설명을 작성해야한다.


```html
<!-- 잘못된 예시 -->
<img src="R114.png">
<img src="R114.png" alt>
<img src="R114.png" alt=""> - list bullet 같은 이미지는 해당 방식을 사용해도 상관없지만 before, affter 같은 가상 선택자로 추가를 해주는 것이 맞다.
<img src="R114.png" title="부동산114">
<img src="R114.png" alt="부동산114" title="부동산114">

<!-- 잘 된 예시 -->
<img src="R114.png" alt="부동산114">

<!-- 잘못된 예시 -->
<a href="/">
    <img src="R114.png" alt="부동산114"> 부동산114
</a>

<!-- 잘 된 예시 -->
<a href="/">
    <img src="R114.png" alt> 부동산114
</a>

<!-- 잘못된 예시 -->
<a href="/" style="background:url(R114.png) no-repeat"></a>

<!-- 잘 된 예시 IR기법 -->
<a href="/" style="background:url(R114.png) no-repeat"><span class="blind">부동산114</span></a>
<!--
  IR기법이란
  IR(Image Replacement) 기법은 이미지를 볼 수 없는 사용자에게 적절한 대체 텍스트를 제공하는 방법
  *class="blind"  보통은 blind 아니면 hidden으로 클래스명 작성한다.

  ex)css
  position: absolute;
  width: 1px;
  height: 1px;
  clip: rect(0 0 0 0);
  overflow: hidden;

 -->

```

### 담당자
* 기획자
* 퍼블리셔
* 개발자

### 기대 효과
* 시각 장애인 사용자에게 텍스트 리더기로 음성 해설을 제공할 수 있다.

### 관련 표준
* [1.1.1 Non-text Content](https://www.w3.org/TR/WCAG21/#non-text-content)

### 평가 도구
* [OpenWAX](https://chrome.google.com/webstore/detail/openwax/bfahpbmaknaeohgdklfbobogpdngngoe?hl=ko)



---



## 2. 자막 제공 <a id="subTitle" href="#subTitle">#</a>
* 자막을 제공하는 것은 영상 디자이너들이, 접근성 검수는 퍼블리셔들이 한다.
* 영상, 음성 콘텐츠에 자막, 원고, 수화 중 하나 이상의 대체 수단을 제공하지 않은 경우를 체크해야 한다.
* 멀티미디어 콘텐츠에 대한 대체 수단의 내용을 불충분 또는 적절하지 않게 제공한 경우를 확인해야 한다.
* 사용자가 등록한 멀티미디어 콘텐츠에 대해 관리자가 대체 수단 입력 기능을 제공해야 한다. - 대체 수단을 등록할 수 있는 영역 필요
* 텍스트만 제공하는 영상 콘텐츠에서 동등한 음성을 제공해야 한다.
* 파일로 제공되는 영상, 음성 콘텐츠도 평가 대상에 포함이 된다. - 첨부파일 등도 확인 가능한 대체 텍스트 등이 필요
* 자막으로 인해 수화가 가려져서는 안된다.
* 원고가 페이지를 벗어나지 말아햐 한다. - 페이지에서 스크롤를 내리면서 동영상과 원고를 따로 봐야 하는 경우 / 요즘은 스크롤을 내리면 영상이 따라오도록 하는 것이 접근성에 기준이다 -ex 트위치
* 모바일에서는 파일로 제공되는 영상, 음성 콘텐츠를 지양한다. -용량 같은 것이 커서 다운로드하다가 문제가 생긴다.

### 담당자
* 디자이너
* 퍼블리셔

### 기대 효과
* 청각 장애인 사용자들에게 원활한 인터넷 사용을 제공할 수 있다.



---



## 3. 색상 <a id="color" href="#color">#</a>
- 배경
* 패턴, 명암(7:1 이상) 등으로 색에 관계없이 직관적으로 인식되도록 제공해야 한다. - 패턴 또는 명암비를 준다.
* 그래프 같은 것은 채도를 빼고 명도만 넣을 경우 색이 구분이 가능한지 체크를 해야 한다.
* 차트 등에 대해 동일한 내용의 대체 콘텐츠를 제공 해야 한다. - 차트 밑에 표를 제공하는 것을 권장
* 색상만으로 구분되었지만 사용자가 직접 선택하여 알 수 있는 경우는 오류 사항이 아니다. - 탭 메뉴
* 색상만으로 구분되어도 주변 정도를 통해 이해할 수 있는 경우도 오류 사항이 아니다. - 차트의 선 라벨
* 글자 모양 변경 등으로 구분 가능한 경우도 오류 사항이 아니다.

- 텍스트
* 보통 문자 크기 16px 텍스트 색상이 명도 대비 4.5:1을 만족해야 한다.
* 문자 크기가 bold 19px 이상 또는 normal 24px 이상인 경우 3:1 이상의 명도 대비를 유지한다.
* 전경 콘텐츠는 정보를 전달하고 있는 '문자, 아이콘, 컨트롤(a, button, input, select, textarea)'의 선과 면을 의미한다.
* 아이콘, 컨트롤 등 시각 정보가 3px 이상 두꺼운 경우 3:1 이상의 명도 대비를 유지한다.
* 마우스 및 키보드 포커스에 의해 변경(Roll Over) 되는 경우 콘텐츠는 그중 명도 대비가 높은 것을 기준으로 평가한다. - 마우스 호버 시 변하는 색상을 기준
* 장비용 이미지, 비활성화(disabled) 영역 등은 예외로 한다.


```html
<!-- 잘못된 예시 -->
<body style="background:#fff">
    <p style="color:#777">부동산R114</p>
</body>

<!-- 잘 된 예시 -->
<body style="background:#fff">
    <p style="color:#767676">부동산R114</p>
</body>

<!-- 잘못된 예시 -->
<body style="background:#fff">
    <input style="border:1px solid #777">
</body>

<!-- 잘 된 예시 -->
<body style="background:#fff">
    <input style="border:1px solid #767676">
</body>
```

### 담당자
* 디자이너
* 퍼블리셔
* 개발자

### 기대 효과
* 저시력 사용자나 색맹 사용자가 내용을 빠르게 인지할 수 있다.

### 관련 표준
* [1.4.3 Contrast(Minimum)](https://www.w3.org/TR/WCAG21/#contrast-minimum)
* [1.4.11 Graphics Contrast](https://www.w3.org/TR/WCAG21/#graphics-contrast)
* [1.4.12 User Interface Component Contrast(Minimum)](https://www.w3.org/TR/WCAG21/#user-interface-component-contrast-minimum)

### 평가 도구
* [OpenWAX](https://chrome.google.com/webstore/detail/openwax/bfahpbmaknaeohgdklfbobogpdngngoe?hl=ko)
* [CCA Color Contrast Analyzer](https://www.tpgi.com/color-contrast-checker/)
* [Colour Contrast Check](https://snook.ca/technical/colour_contrast/colour.html#fg=33FF33,bg=333333)
* [Accessible Color Generator](https://learnui.design/tools/accessible-color-generator.html)



---



## 4. 화면을 400%까지 확대 가능 <a id="zoom" href="#zoom">#</a>
* 너비 1,280 픽셀 해상도 모니터에서 400%까지 확대할 수 있다. 모바일 단말에서는 테스트하지 않는다.
* 화면을 400% 확대한 상태에서 내용과 기능에 손실이 없어야 하고, 2차원 스크롤이 발생하지 않아야 한다.


```html
<!-- 잘못된 예시 -->
http://www.president.go.kr/

<!-- 잘 된 예시 -->
https://www.whitehouse.gov/
```
### 담당자
* 퍼블리셔
* 개발자

### 기대 효과
* 저시력 사용자가 내용을 빠르게 인지할 수 있다.
* 하나의 소스 만으로 모든 해상도의 출력 장치에 대응 가능하다.

### 관련 표준
* [1.4.10 Zoom content](https://www.w3.org/TR/WCAG21/#zoom-content)



---
## 5. 명확한 지시사항 제공 <a id="instruction" href="#instruction">#</a>
* 이 부분의 검사는 퍼블리셔 또는 개발자 직접 수동으로 하나하나 검사를 해야 한다.
* 소리 등 지시사항을 청각정보로만 제공한 경우 - 퀴즈를 풀 때 소리만 나오는 경우도 텍스트도 같이 줘야한다.
* 시각 및 청각을 테스트하는 검사 콘텐츠, 또는 시각, 청각을 통한 게임 콘텐츠 등 특수 목적의 콘텐츠는 예외로 처리한다.

```html
<!-- 잘못된 예시 -->
<p>아래 버튼을 클릭하세요</p>
<button type="button">버튼</button>

<!-- 잘 된 예시 -->
<button type="button">클릭</button>
```
### 담당자
* 퍼블리셔
* 개발자

### 기대 효과
* 

### 관련 표준
* 



---



## 6. 키보드만으로 조작 가능 <a id="keyboard" href="#keyboard">#</a>
* 구현된 키보드 접근 순서는 논리적으로 설명할 수 있어야 한다.
* 초점을 받은 요소는 시각적 단서를 제공해야 한다.
* 키보드로 접근 및 운용이 불가능할 경우 button, a 태그가 아닌 다른 태그에 onClick 이벤트를 달면 마우스로 클릭이 가능하지만 키보드로는 불가능하므로 button과 a 태그를 제외한 다른 곳에 onclick 이벤트를 사용할 경우 주의를 해야 한다.
* 요소에 css overflow: auto를 준 것은 키보드로 스크롤 제어가 불가능하다 이 요소에 스크롤을 제어하기 위해서는 해당 요소에 tabindex="0"를 넣어준다.


```html
<!-- 잘못된 예시 -->
a:hover{ color: #000; }

<!-- 잘 된 예시 -->
a:hover,
a:focus{ color: #000; }

<!-- 잘못된 예시 -->
document.getElementsByClassName("클래스명")[0].addEventListener("mouseover", ".gnb a", function() { ... });

<!-- 잘 된 예시 -->
document.getElementsByClassName[0]("클래스명").addEventListener("mouseover focus", ".gnb a", function() { ... });

<!-- 잘못된 예시 -->
<div style="overflow: auto; max-height: 200px;">
스크롤이 발생합니다.
스크롤이 발생합니다.
스크롤이 발생합니다.
스크롤이 발생합니다.
스크롤이 발생합니다.
스크롤이 발생합니다.
</div>

<!-- 잘 된 예시 -->

<div style="overflow: auto; max-height: 200px;" tabindex="0">
스크롤이 발생합니다.
스크롤이 발생합니다.
스크롤이 발생합니다.
스크롤이 발생합니다.
스크롤이 발생합니다.
스크롤이 발생합니다.
</div>

```
### 담당자
* 퍼블리셔
* 프론트엔드 개발자

### 기대 효과
* 전맹 또는 상지 장애가 있는 사용자와 키보드를 선호하는 사용자의 탐색과 조작을 돕는다.

### 관련 표준
* [2.1.1 Keyboard](https://www.w3.org/TR/WCAG21/#keyboard)
* [2.1.2 No Keyboard Trap](https://www.w3.org/TR/WCAG21/#no-keyboard-trap)
* [2.4.3 Focus Order](https://www.w3.org/TR/WCAG21/#focus-order)
* [2.4.7 Focus Visible](https://www.w3.org/TR/WCAG21/#focus-visible)



---



## 7. 사용할 수 있는 충분한 시간 제공 <a id="time" href="#time">#</a>
* 시간제한이 있는 정보를 시간제한을 끄거나, 또는 최소 20초 이상 10회까지 연장이 가능하다.
* 자동으로 갱신되는 정보에는 '정지, 이전, 다음' 기능을 제공한다.


```html
<!-- 잘못된 예시 -->
10초 후 다음 페이지로 넘어갑니다. [다음 페이지로 즉시 이동]

<!-- 잘 된 예시 -->
20초 후 다음 페이지로 넘어갑니다. [취소] [다음 페이지로 즉시 이동]
20초 후 다음 페이지로 넘어갑니다. [20초 연장] [다음 페이지로 즉시 이동]

<!-- 잘못된 예시 -->
콘텐츠가 자동으로 슬라이드 되고 있는 상황에서 정지하거나 이전, 다음 콘텐츠를 탐색할 수 없다.

<!-- 잘 된 예시 -->
콘텐츠가 자동으로 슬라이드 되고 있지만 정지, 이전, 다음 기능을 제공하고 있다.
```
### 담당자
* 기획자
* 디자이너

### 기대 효과
* 학습장애 또는 난독 증세가 있는 사람들이 내용을 이해할 수 있도록 도와줄 수 있다.

### 관련 표준
* [2.2.1 Timing Adjustable](https://www.w3.org/TR/WCAG21/#timing-adjustable)
* [2.2.2 Pause, Stop, Hide](https://www.w3.org/TR/WCAG21/#pause-stop-hide)



---



## 8. 동영상 자동 재생 금지 및 발작을 유발하는 콘텐츠를 제공 금지 <a id="seizure" href="#seizure">#</a>
* 1초에 3~50회 사이의 번쩍이는 콘텐츠는 광과민성 발작을 유발할 수 있으므로 콘텐츠를 넣을 때 주의해야 한다.
* 광과민성 발작은 소아 또는 간질 경험이 있는 사람에게 더 위험하다.
* 자동적으로 3초 이상 재생되는 배경음은 콘텐츠는 자동 재생을 금지해야 한다.
* 마우스 오버나 키보드 초잠을 받아 자동으로 배경음이 3초 이상 실행이 되는 경우도 자동 재생을 금지해야 한다.
* 깜빡임이 3초 미만인 경우는 예외이다.
* 깜빡임을 중단하는 수단을 제공했더라도 미리 경고하는 문구등을 제공해야한다.


```html

놀라는 영상 - https://youtube.com/shorts/Nx6MgSKIltQ?si=IeAL5YN_U9oOSusH
포켓몬 발작 사고 영상(폴리곤 사건) - https://youtu.be/FjMHgGeHEco?si=IlkA7nDGxXlNgGE6

```

### 담당자
* 기획자
* 퍼블리셔
* 개발자

### 기대 효과
* 소아 또는 간질 경험이 있는 사람의 발작을 예방할 수 있다.
### 관련 표준
* [2.3.1 Three Flashes or Below Threshold](https://www.w3.org/TR/WCAG21/#three-flashes-or-below-threshold)
* [2.3.2 Three Flashes](https://www.w3.org/TR/WCAG21/#three-flashes)



---



## 9. 반복되는 콘텐츠 블록 및 영역을 건너뛸 수 있다. <a id="bypass" href="#bypass">#</a>
* 전맹 또는 상지 장애가 있는 이용자들은 헤더 및 풋터들이 아닌 내용까지 한 번에 이동을 하기 힘들다 즉 키보드 탭 버튼을 수백 번 수천 번 클릭을 해야 한다.
* 일반적으로 글로벌 탐색 바와 로컬 탐색 바는 반복되는 콘텐츠 블록이다.
* 반복되는 콘텐츠 블록이 있는 경우 페이지 시작 위치에 '본문으로 건너뛰기' 링크 및 버튼을 제공한다(html body 태그 바로 다음에 만들어야 한다).
* 본문으로 건너뛰기 버튼은 평소에는 숨겨져 있다가 키보드 탭 버튼을 누르면 나타나게 한다 즉 css로 포커스(:focus)가 되면 나타나게 한다.
* 본문으로 건너뛰기 버튼은 모든 페이지에 다 있어야 한다.
* 스크립트로 화면 이동을 설정하면 스크롤은 되나 실제 키보드 초점(탭)은 이동을 하지 않은 경우가 있으므로 html 및 css로 처리를 한다.


```html
<!-- 잘못된 예시 -->
<body>
    <h1>부동산R114</h1>
    <nav>...</nav>
    <main>...</main>

<!-- 잘 된 예시 -->
<body>
    <a href="#main">본문으로 건너뛰기</a>
    <h1>부동산R114</h1>
    <nav>...</nav>
    <main id="main">...</main>
```

### 담당자
* 기획자
* 퍼블리셔
* 개발자

### 기대 효과
* 전맹 또는 상지 장애가 있는 사용자와 키보드를 선호하는 사용자의 탐색과 조작을 돕는다.

### 관련 표준
* [2.4.1 Bypass Blocks](https://www.w3.org/TR/WCAG21/#bypass-blocks)



---



## 10. 모든 문서의 제목은 고유하고 식별할 수 있다. <a id="title" href="#title">#</a>
* 페이지에 제목을 제공하지 않은 경우 제공해야 한다 입력을 안한 경우 페이지의 url이 타이틀로 들어간다.
* 제목 콘텐츠를 문서마다 다르게 설명함으로써 현재 문서의 용도를 식별할 수 있고 페이지에 적절한 제목을 제공해야 한다.
* 프레임(아이프레임 요소)에도 제목(타이틀)을 제공해야 한다.
* 프레임(아이프레임 요소)에 내용 또는 기능이 없어도 "빈 프레임", "내용 없음"과 같이 title를 제공해야 함
* 콘텐츠 블록 제목은 헤딩(Headings) 요소 사용 및 레벨 구조화를 권장하되, 다른 요소를 사용한 구분 또는 WAI-ARIA 기법 등도 순수한 것으로 인정
* 콘텐츠 블록 제목은 display:"none";, visibility: hidden;을 사용하지 않아야 하며 숨겨야 하는 경우 postion으로 사용하여 제공하도록 함


```html
<!-- 잘못된 예시 -->
<head>
    <title>부동산R114<title>

    <div>
        <iframe title="" src="" frameborder="0"></iframe>
    </div>
<!-- 잘 된 예시 -->
<head>
    <title>HDC현대산업개발 - 부동산R114 - RDS<title>

    <div>
        <iframe title="타이틀이 들어가야합니다." src="" frameborder="0"></iframe>
    </div>
```

### 담당자
* 기획자
* 퍼블리셔
* 개발자

### 기대 효과
* 전맹 사용자가 링크 이동 결과를 음성으로 확인할 수 있다.
* 문서의 용도를 빠르게 파악할 수 있다.
* 검색엔진이 올바른 페이지를 수집하도록 돕는다.
* 유저 에이전트 탭의 식별 가능성이 높아진다.

### 관련 표준
* [2.4.2 Page Titled](https://www.w3.org/TR/WCAG21/#page-titled)



---



## 11. 콘텐츠 간의 구분 <a id="division" href="#division">#</a>
* 디자인을 할 때 콘텐츠 간의 구분이 있어야 한다.
* 테두리를 이용하여 구분한다.
* 서로 다른 무늬를 이용하여 구분한다.
* 콘텐츠 배경색 간의 명도대비(채도)를 달리하여 구분한다.
* 줄 간격 및 글자 간격을 조절하여 구분한다.
* 기타 콘텐츠를 시각적으로 구분한다.
* 테두리는 배경색과 명도 대비를 4.5:1 이상으로 제공한다.


```html
<!-- 잘못된 예시 -->
<div>
    <div>박스1</div>
    <div>박스2</div>
    <div>박스3</div>
    <section>
        <h2>섹션1</h2>
    </section>
        <section>
        <h2>섹션2</h2>
    </section>
        <section>
        <h2>섹션3</h2>
    </section>
</div>

<!-- 잘 된 예시 -->
<head>
<div>
    <div>박스1</div>
    <div>박스2</div>
    <div>박스3</div>
    
    <hr> <!-- 구분선 -->
    
    <section>
        <h2>섹션1</h2>
    </section>
        <section>
        <h2>섹션2</h2>
    </section>
        <section>
        <h2>섹션3</h2>
    </section>
</div>
```

### 담당자
* 디자이너
* 퍼블리셔

### 기대 효과
* 난독증 환자가 콘텐츠를 쉽게 이해가 가능하다.
### 관련 표준
* [2.4.2 Page Titled](https://www.w3.org/TR/WCAG21/#page-titled)



---



## 12. 링크와 버튼 텍스트는 콘텐츠의 목적을 적절하게 제공 <a id="link" href="#link">#</a>
* 주변 콘텐츠와 분리하여 독립적으로 접근해도 링크 또는 버튼의 목적을 알 수 있어야 한다.
* 링크 또는 버튼에 독립적으로 접근하여 이해하기 어려운 경우 동일한 단락, 목록, 셀, 연결된 헤더 셀(p, li, td, th)에 링크 또는 버튼의 목적을 설명해야 한다.
* 목적이나 용도를 알기 어려운 링크 텍스트를 제공한 경우 a 태그에도 title로 상세 텍스트를 제공할 수 있다.
* '확인', '취소', '이전', '다음', '다운로드', '상세보기',' 더보기' 등과 같이 링크의 목적을 논리적 순서나 맥락을 통해 이해할 수 있으면 인정
* 링크 텍스트를 단순히 URL경로로 만 제공한 경우 주변 맥락을 통해 링크의 목적을 이해할 수 있으면 인정
* 용도나 목적을 이해할 수 없는 빈 링크 텍스트를 제공한 경우 오류로 간주


```html
<!-- 잘못된 예시 -->
<a href="#" download>설치하기</a>
<button type="button">삭제하기</button>

<!-- 잘 된 예시 -->
<a href="#" download>부동산R114 안드로이드 애플리케이션 설치하기</a>
<p>부동산R114 안드로이드 애플리케이션 <a href="#" download>설치하기</a></p>
<li>부동산R114 안드로이드 애플리케이션 <a href="#" download>설치하기</a></li>
<td>부동산R114 안드로이드 애플리케이션 <a href="#" download>설치하기</a></td>
<tr>
    <th scope="row">부동산R114 안드로이드 애플리케이션</th>
    <td><a href="#" download>설치하기</a></td>
</tr>

<!-- 잘 된 예시 -->
<button type="button">구매내역 삭제하기</button>
<p>구매내역 <button type="button">삭제하기</button></p>
<li>구매내역 <button type="button">삭제하기</button></li>
<td>구매내역 <button type="button">삭제하기</button></td>
<tr>
    <th scope="row">구매내역</th>
    <td><button type="button">삭제하기</button></td>
</tr>

<!-- 잘 된 예시 -->
<div>
  <p>예</p>
  네이버 페이지로 이동<a href="#http://naver.com">http://naver.com</a>
</div>

```
### 담당자
* 기획자
* 디자이너
* 퍼블리셔

### 기대 효과
* 전맹 사용자가 링크 또는 버튼에 독립적으로 또는 순차적으로 접근하는 경우 링크 또는 버튼의 목적을 음성으로 전달할 수 있다.

### 관련 표준
* [2.4.4 Link Purpose(In Context)](https://www.w3.org/TR/WCAG21/#link-purpose-in-context)

### 평가 도구
* [OpenWAX](https://chrome.google.com/webstore/detail/openwax/bfahpbmaknaeohgdklfbobogpdngngoe?hl=ko)



---



## 13. 섹션에는 의미 있는 마크업과 헤딩 <a id="outline" href="#outline">#</a>
* 섹션 콘텐츠는 의미에 알맞은 article, section, nav, aside 요소로 마크업 한다.
* 섹션 콘텐츠에는 문서의 개요 체계에 알맞은 헤딩(h1~h6)을 제공한다.
* 명시적 헤딩 기법을 사용한다. 명시적 헤딩 기법은 하나의 문서에 h1 요소를 한 번 사용한다.


```html
<!-- 잘못된 예시 -->
<div class="article">...</div>
<div class="section">...</div>
<div class="nav">...</div>
<div class="aside">...</div>

<!-- 잘 된 예시 -->
<article>
    <h2>...</h2>
    ...
</article>
<section>
    <h2>...</h2>
    ...
</section>
<nav>
    <h2>...</h2>
    ...
</nav>
<aside>
    <h2>...</h2>
    ...
</aside>
```

### 담당자
* 퍼블리셔

### 기대 효과
* 보조 기기 사용자가 원하는 탐색 지점으로 빠르게 건너뛸 수 있다.
* 검색엔진이 올바를 페이지를 수집하도록 돕는다.
* 유저 에이전트 확장 기능 사용자에게 문서 개요를 전달할 수 있다.

### 관련 표준
* [2.4.6 Headings and Labels](https://www.w3.org/TR/WCAG21/#headings-and-labels)
* [2.4.10 Section Headings](https://www.w3.org/TR/WCAG21/#section-headings)

### 평가 도구
* [HTML5 Outliner](https://chrome.google.com/webstore/detail/html5-outliner/afoibpobokebhgfnknfndkgemglggomo)



---



## 14. 문서의 휴먼 랭귀지 속성을 제공 <a id="lang" href="#lang">#</a>
* html 요소에 lang 속성을 제공한다.
* 한글, 영문, 일문, 중문에는 이를 식별하기 위한 [ISO-639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) 코드값 ko, en, ja, zh가 있다.
* 문서 타입에 맞는 기본 언어를 제공해 줘야 사용자가 사용하는 화면 낭독기 언어에 맞춰 자연스럽게 읽어준다.  


```html
<!-- 잘못된 예시 -->
<html>

<!-- 잘 된 예시 -->
<html lang="ko">

<!-- 잘못된 예시 -->
한글문서
<html lang="en">
    
<!-- 잘 된 예시 -->
한글문서
<html lang="ko">

```

### 담당자
* 퍼블리셔

### 기대 효과
* 보조 기기와 검색엔진이 문서의 휴먼 랭귀지를 식별할 수 있다.

### 관련 표준
* [3.1.1 Language of Page](https://www.w3.org/TR/WCAG21/#language-of-page)
* [3.1.2 Language of Parts](https://www.w3.org/TR/WCAG21/#language-of-parts)

### 평가 도구
* [OpenWAX](https://chrome.google.com/webstore/detail/openwax/bfahpbmaknaeohgdklfbobogpdngngoe?hl=ko)



---



## 15. 문맥 변경은 예측 가능 <a id="predict" href="#predict">#</a>
* 사용자가 실행하기 전까지는 문서를 갱신(이동, 추가, 삭제, 재배치) 하거나, 팝업(새 창, 레이어)을 띄우거나, 초점을 다른 곳으로 옮기지 않는다.
* 사용자가 초점을 넣거나 마우스를 올리는 것은 기능을 실행하기 위한 의도로 보지 않기 때문에 문맥을 변경하면 안 된다.
* '대한민국' 선택의 결과로 대한민국의 '시/군/구'를 선택하는 항목이 등장했다면 이것은 문맥의 변화가 아니다.


```html
<!-- 잘못된 예시 -->
초점을 넣었을 뿐인데 자동으로 페이지 갱신 또는 이동.
페이지 로드 시 자동 팝업.
초점 자동 이동.

<!-- 잘 된 예시 -->
클릭 또는 리턴(엔터) 키를 통해 페이지 갱신 또는 이동.
클릭 또는 리턴(엔터) 키를 통해 팝업 생성.
초점을 자동으로 옮기지 않음.
```
### 담당자
* 퍼블리셔

### 기대 효과
* 보조 기기 사용자가 혼란에 빠지는 것을 예방할 수 있다.

### 관련 표준
* [3.2.1 On Focus](https://www.w3.org/TR/WCAG21/#on-focus)
* [3.2.2 On Input](https://www.w3.org/TR/WCAG21/#on-input)
* [3.2.5 Change on Request](https://www.w3.org/TR/WCAG21/#change-on-request)



---


## 16. 콘텐츠의 선형화 <a id="linear" href="#linear">#</a>
* 디자인이 된 html의 css를 제거해도 맥락이 이해가 가능해야 한다. 즉 콘텐츠의 순서를 논리적으로 제공하지 않아 전후 맥락이 이해가 가야 한다.
* 콘텐츠의 구조를 논리적으로 제공하지 않아 주종 관계를 이해할 수 없는 경우
* 제목과 내용 사이에 관련 없는 콘텐츠를 포함하고 있더라도 제목과 내용을 앵커 a 태그 기능으로 연결했다면 논리적인 순서로 제공을 한 것으로 인정

```html
<!-- 잘못된 예시 -->
<a href="#">부동산R114 구성</a>
<div>오늘 점심 뭐 먹지?</div>
<div>오늘 점심 뭐 먹지?</div>
<div>오늘 점심 뭐 먹지?</div>
<div>IT 본부</div>

<!-- 잘 된 예시 -->
<a href="R114">부동산R114 구성</a>
<div>오늘 점심 뭐 먹지?</div>
<div>오늘 점심 뭐 먹지?</div>
<div>오늘 점심 뭐 먹지?</div>
<div id="R114">IT 본부</div>

```

### 담당자
* 퍼블리셔

### 기대 효과
* 

### 관련 표준
* 


---


## 17. 표의 구성 <a id="table" href="#table">#</a>
* 표의 제목과 요약 정보는 caption 태그를 통해 제공을 해야 한다.
* table의 summary 속성은 html5에서 없어졌으므로 사용을 자제해야 하며, caption 태그를 통해 제목을 포함하며 표의 요약, 구조, 탐색 방법 들의 정보를 제공하면 준수한 것으로 인정
* 제목 세로가 내용 셀은 각각 th, td 태그로 구분을 해야 한다.
* 다단, 병합 등 복잡한 표를 제공 시 headers, id 속성을 통해 제목셀과 내용 셀을 연결해야 한다.
* 표의 정보를 이해하기 어려운 중첩 표(표 안의 표)를 넣어 정보를 제공한 경우는 접근성 위반이다.
* 어쩔 수 없이 배치만 하는 테이블을 제공해야 하는 경우 th, caption 속성을 사용하지 말아햐 함


```html
<!-- 잘못된 예시 -->
    <table summary="연습용 테이블">
      <thead>
        <tr>
          <th id="th1">타이틀1</th>
          <th id="th2">타이틀2</th>
          <th id="th3">타이틀3</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th rowspan="3" id="th4">첫줄1</th>
          <td>내용1</td>
          <td>내용1</td>
          <td>내용1</td>
        </tr>
        <tr>
          <th id="th5">첫줄2</th>
          <td>내용2</td>
          <td>내용2</td>
          <td>내용2</td>
        </tr>
        <tr>
          <th id="th6">첫줄3</th>
          <td>내용3</td>
          <td>내용3</td>
          <td>내용3</td>
        </tr>
      </tbody>
    </table>

<!-- 잘 된 예시 -->
    <table>
      <caption>연습용 테이블</caption>
      <thead>
        <tr>
          <th id="th1">타이틀1</th>
          <th id="th2">타이틀2</th>
          <th id="th3">타이틀3</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th rowspan="3" id="th4">첫줄1</th>
          <td headers="th1 th4">내용1</td>
          <td headers="th2 th4">내용1</td>
          <td headers="th3 th4">내용1</td>
        </tr>
        <tr>
          <th id="th5">첫줄2</th>
          <td headers="th1 th5">내용2</td>
          <td headers="th2 th5">내용2</td>
          <td headers="th3 th5">내용2</td>
        </tr>
        <tr>
          <th id="th6">첫줄3</th>
          <td headers="th1 th6">내용3</td>
          <td headers="th2 th6">내용3</td>
          <td headers="th3 th6">내용3</td>
        </tr>
      </tbody>
    </table>

```

### 담당자
* 퍼블리셔

### 기대 효과
* 

### 관련 표준
* 


---


## 18. 폼 컨트롤 요소에 설명을 제공 <a id="form" href="#form">#</a>
* 모든 input, textarea, select 요소에는 컨트롤을 설명하는 label 요소를 매핑하거나 또는 title 속성을 제공한다.
* input, textarea, select 태그에 1:1 대응하는 label를 제공해야 한다.
* label 태그를 사용 가능하지만 생략하고 title만 사용한 경우는 접근성 미준수이다.
* input 태그의 id와 label의 for는 무조건 같아야 한다.
* input 태그의 id와 페이지 안에 같은 id가 있어서는 안된다 즉 중복 id가 존재 불가
* select 태그의 첫 번째 option 태그가 레이블을 역할을 대신하는 경우에는 title을 무조건 제공해야 한다.
* title 속성보다 lable 태그를 우선으로 사용해야 한다.


```html
<!-- 잘못된 예시 -->
<form>
    <input type="search">
    <button type="button">검색</button>
</form>

<!-- 잘 된 예시 -->
<form>
    <label for="search">검색</label>
    <input id="search" type="search">
    <button type="button">검색</button>
</form>

<!-- 잘 된 예시 -->
<form>
    <input type="search" title="검색">
    <button type="button">검색</button>
</form>
```

### 담당자
* 퍼블리셔

### 기대 효과
* 보조 기기가 폼 컨트롤에 독립적으로 접근했을 때 컨트롤에 대한 설명을 제공할 수 있다.

### 관련 표준
* [2.4.6 Headings and Labels](https://www.w3.org/TR/WCAG21/#headings-and-labels)
* [3.3.2 Labels or Instructions](https://www.w3.org/TR/WCAG21/#labels-or-instructions)

### 평가 도구
* [OpenWAX](https://chrome.google.com/webstore/detail/openwax/bfahpbmaknaeohgdklfbobogpdngngoe?hl=ko)



---



## 19. 실수를 예방하고 정정하는 것을 돕는다. <a id="assist" href="#assist">#</a>
* 입력 오류를 자동으로 감지할 수 있는 경우에만 이 지침을 적용한다. 예를 들면 이름을 잘못 입력하는 경우 정정 의견을 제시할 수 없다.
* 오류 항목이 무엇인지 식별할 수 있도록 문자로 알리고 정정 의견을 제시한다. 예를 들면 "생년월일 양식에 오류가 있습니다. 입력 형식은 yyyy-mm-dd 입니다."
* 정정 의견은 보안을 유지하는 수준에서 제시한다. 예를 들면 "아이디 또는 비밀번호 입력 오류."
* 입력 내용을 전송하기 전 검토 후 교정할 수 있다. 또는 제출한 내용을 되돌릴 수 있다.
* 서식의 전송 버튼을 눌렀을 때, 입력 내용이 모두 사라지는 경우도 오류이다.


```html
<!-- 잘못된 예시 -->
오류 입력 양식에 붉은색 보더 처리. // 시각에 의존하고 있다. 문자로 알려야 한다.
"입력 양식에 오류가 있습니다." // 오류 식별 불가.
"로그인 오류. 비밀번호는 특수문자, 숫자, 알파벳을 하나 이상 포함해야 합니다." // 정정 의견이 보안을 해치고 있음.
여러 단계(여러 페이지)에 걸쳐 작성한 내용 중 이전 단계의 내용을 검토할 수 없고 제출 후 수정할 수 없음. // 제출 전 또는 제출 후 수정할 수 있어야 한다.

<!-- 잘 된 예시 -->
"생년월일 양식에 오류가 있습니다. 입력 형식은 yyyy-mm-dd 입니다." // 오류 식별 가능. 정정 의견 제시.
"아이디 또는 비밀번호 입력 오류. 5회 이상 오류 발생 시 계정 잠금 상태로 전환합니다." // 오류 식별 가능. 정정 의견 제시. 보안을 해치지 않음.
여러 단계(여러 페이지)에 걸쳐 작성한 내용 중 이전 단계의 내용을 검토 후 수정할 수 있음. 또는 이전 단계의 내용을 수정할 수 없지만 제출 후 수정할 수 있음.
```

### 담당자
* 개발자

### 기대 효과
* 사용자가 실수하지 않도록 예방하고 실수를 교정할 수 있다.

### 관련 표준
* [3.3.1 Error Identification](https://www.w3.org/TR/WCAG21/#error-identification)
* [3.3.3 Error Suggestion](https://www.w3.org/TR/WCAG21/#error-suggestion)
* [3.3.4 Error Prevention (Legal, Financial, Data)](https://www.w3.org/TR/WCAG21/#error-prevention-legal-financial-data)
* [3.3.6 Error Prevention (All)](https://www.w3.org/TR/WCAG21/#error-prevention-all)



---



## 20. HTML 문법을 준수 <a id="html" href="#html">#</a>
* 시작 태그에서 닫는(self-closing) 요소를 제외하고 시작 태그, 종료 태그, 따옴표를 생략하지 않는다.
* 명세에 따라 중첩한다.
* 속성을 중복 선언하지 않는다.
* 모든 id 속성의 값은 하나의 문서 안에서 중복 없이 유일하다.

```html
<!-- X -->
<div><span>...</div> // span 종료 태그 생략 오류.
<span><a><div>...</div></a></span> // span 요소가 div를 감싼 것은 오류.
<div class="aaa" class="bbb">...</div> // 속성은 한 번만 선언해야 한다.
<div id="xyz">...</div><div id="xyz">...</div> // xyz 값은 페이지에서 유일해야 한다.

<!-- O -->
<div><span>...</span></div>
<div><a><div>...</div></a></div>
<div class="aaa bbb">...</div>
<div id="abc">...</div><div id="xyz">...</div>
```

### 담당자
* 퍼블리셔

### 기대 효과
* 보조기기의 웹 문서 해석 오류를 예방할 수 있다.

### 관련 표준
* [4.1.1 Parsing](https://www.w3.org/TR/WCAG21/#parsing)

### 평가 도구
* [W3C Markup Validation Service](https://validator.w3.org/)

## 관련 표준
* [WCAG 2.1](https://www.w3.org/TR/WCAG21/)(WD)
* [HTML 5.2](https://www.w3.org/TR/html52/)(R)
* [WAI-ARIA 1.1](https://www.w3.org/TR/wai-aria/)(R)



---



## License
Under MIT License. Copyright &copy; R114.
