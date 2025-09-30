# 웹 프로그래밍 4장 요약 (CSS3)

## 1. CSS3 개요

* CSS(Cascading Style Sheets): HTML 문서의 색, 모양, 외관을 꾸미는 언어
* CSS 버전: CSS1 → CSS2 → CSS3 (현재는 CSS4 표준화 작업 중)
* 주요 기능: 색상/배경, 텍스트, 폰트, 박스 모델, 비주얼 효과, 리스트, 테이블, UI 등

---

## 2. CSS3 스타일 시트 작성 방법

1. `<style>` 태그에 작성 (HTML 내부, 전체 적용)
2. HTML 태그의 `style` 속성에 작성 (해당 태그만 적용)
3. 외부 `.css` 파일 작성 후 `<link>` 태그나 `@import`로 불러오기

---

## 3. CSS3 규칙

* **상속**: 부모 태그의 스타일이 자식 태그에 전달됨
* **합치기(Cascading) & 오버라이딩**: 여러 스타일이 중복될 경우 우선순위 적용  
  (기본 브라우저 스타일 < 외부 CSS < 내부 `<style>` < inline `style` 속성)

---

## 4. 셀렉터 종류

* **태그 셀렉터**: `h3 { ... }`
* **클래스 셀렉터**: `.classname { ... }` → 여러 태그에 그룹 적용
* **아이디 셀렉터**: `#idname { ... }` → 특정 태그에만 적용 (유일해야 함)
* **자식 셀렉터**: `div > strong { ... }`
* **자손 셀렉터**: `ul strong { ... }`
* **전체 셀렉터**: `* { ... }`
* **속성 셀렉터**: `input[type=text] { ... }`
* **가상 클래스 셀렉터**: `a:visited`, `li:hover`, `h3:first-letter` 등

---

## 5. 색 표현

* **16진수 코드**: `#8A2BE2`
* **RGB 코드**: `rgb(138,43,226)`
* **색 이름**: `blueviolet`  
  CSS3 표준 색 이름: 140개

---

## 6. 텍스트 & 폰트

* 텍스트 꾸미기: `text-align`, `text-indent`, `text-decoration`
* 폰트 제어:
  * `font-family`, `font-size`, `font-style`, `font-weight`
  * 단축 프로퍼티: `font: italic bold 20px consolas;`

---

## 7. 박스 모델

* HTML 태그는 박스로 구성됨: **content, padding, border, margin**
* 프로퍼티: `width`, `height`, `margin`, `padding`, `border`, `border-radius`
* 테두리: `solid`, `dotted`, `dashed`, `double`, `groove`, `ridge`, `inset`, `outset`
* `border-radius`: 둥근 모서리
* `border-image`: 이미지 테두리 적용

---

## 8. 배경 꾸미기

* `background-color`, `background-image`, `background-position`, `background-repeat`, `background-size`
* 단축 프로퍼티:  
  `background : skyblue url("img.png") center center/100px 100px repeat-y;`

---

## 9. 그림자 효과

* **텍스트 그림자**: `text-shadow : 3px 3px 5px red;`
* **박스 그림자**: `box-shadow : 10px 10px 5px gray;`

---

## 10. 마우스 커서 제어

* `cursor: pointer`, `cursor: help`, `cursor: progress`, `cursor: n-resize` 등 다양한 커서 모양 지정 가능

---

# 웹 프로그래밍 5장 요약 (CSS3)

## 1. 개요
* HTML 태그의 위치를 조절할 수 있다.
* 리스트, 표, 폼을 꾸밀 수 있다.
* 애니메이션, 전환(transition), 변환(transform) 효과를 만들 수 있다.

---

## 2. 배치 (Layout)

* 주요 프로퍼티: `display`, `position`, `left/right/top/bottom`, `float`, `z-index`, `visibility`, `overflow`

### 박스 유형
* **블록 박스**: 새 라인에서 시작, 전체 폭 차지
* **인라인 박스**: 한 줄 안에 배치
* `display` 속성
  * `block`, `inline`, `inline-block`, `none`

### position
* `static` (기본)
* `relative` (기본 위치에서 상대 이동)
* `absolute` (기준 컨테이너 내 절대 위치)
* `fixed` (브라우저 화면 기준 고정)
* `float` (좌/우 배치)

### 기타
* `z-index`: 쌓임 순서
* `visibility: hidden`: 공간은 남고 내용만 숨김
* `overflow`: `hidden`, `visible`, `scroll`

---

## 3. 리스트 꾸미기

* 배경색: `background`
* 마커 위치: `list-style-position: inside | outside`
* 마커 종류: `list-style-type: circle, square, decimal, upper-roman, lower-alpha, none`
* 이미지 마커: `list-style-image: url("img.png")`
* 응용: 네비게이션 메뉴 만들기 (inline-block, list-style-type: none)

---

## 4. 표 꾸미기

* **테두리**: `border`, `border-collapse: collapse`
* **셀 크기**: `width`, `height`
* **여백/정렬**: `padding`, `text-align`
* **색상**
  * `thead`, `tfoot` 배경색 지정
  * `tbody tr:nth-child(even)` → 줄무늬 효과
  * `tr:hover` → 마우스 오버 시 색 변경

---

## 5. 폼(Form) 꾸미기

* `input[type=text]`으로 스타일 지정
* 테두리: `border`, `border-radius`
* 마우스/포커스 효과
  * `:hover` → 마우스 올리면 배경색 변화
  * `:focus` → 입력창 활성화 시 글자 크기 확대
* 레이블 정렬: `label`, `span`에 `display: block/inline-block` 활용

---

## 6. CSS3 동적 효과

### 애니메이션 (animation)
* `@keyframes`로 시간별 스타일 변화 지정
* 주요 속성
  * `animation-name`
  * `animation-duration`
  * `animation-iteration-count`
* 예: 글자 색, 크기 변화를 무한 반복

### 전환 (transition)
* CSS 프로퍼티 변화가 **서서히 진행**
* 예: `transition: font-size 5s;`

### 변환 (transform)
* 2D 변환 함수
  * `rotate(deg)` (회전)
  * `skew(x,y)` (기울임)
  * `translate(x,y)` (이동)
  * `scale(x,y)` (확대/축소)
* 마우스 이벤트(`:hover`, `:active`)로 추가 변환 가능
