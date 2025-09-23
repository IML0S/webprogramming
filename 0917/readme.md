# HTML5 문서 구조화 및 웹 폼 이해

## 기존 HTML의 한계
- `<div>`, `<table>` 등 비시맨틱 태그 사용 → 의미 전달 어려움
- 검색 엔진 최적화에 불리함

## 시맨틱 태그의 등장
- 의미 있는 구조 전달 가능
- 주요 태그: `<header>`, `<nav>`, `<section>`, `<article>`, `<aside>`, `<footer>`

## 예제 페이지
- 엘비스 프레슬리와 모차르트를 주제로 시맨틱 태그를 활용한 구조화 예시

## 시맨틱 태그 설명

| 태그        | 설명 |
|-------------|------|
| `<header>`  | 페이지나 섹션의 머리말 |
| `<nav>`     | 내비게이션 링크 모음 |
| `<section>` | 문서의 장이나 절 구성 |
| `<article>` | 독립적인 콘텐츠 영역 |
| `<aside>`   | 본문 외의 참고 정보 |
| `<footer>`  | 저작권, 작성자 정보 등 꼬리말 |

---

## 웹 폼(Form) 이해

### 폼의 목적
- 사용자 입력 수집 (로그인, 검색, 예약 등)

### 주요 태그
- `<form>`, `<input>`, `<textarea>`, `<select>`, `<button>`, `<label>`

### 속성 설명
- `action`: 데이터를 보낼 서버 주소
- `method`: 전송 방식 (GET, POST)
- `name`, `target`, `enctype` 등

---

## 다양한 폼 요소 예제

- 텍스트 입력: `<input type="text">`, `<textarea>`
- 비밀번호 입력: `<input type="password">`
- 버튼: `<input type="submit">`, `<button>`
- 체크박스/라디오버튼: `<input type="checkbox">`, `<input type="radio">`
- 날짜/시간 입력: `<input type="date">`, `<input type="time">`, `<input type="datetime-local">`
- 색상 선택: `<input type="color">`
- 숫자 입력: `<input type="number">`, `<input type="range">`
- 데이터 목록: `<datalist>`와 `<option>`
- 형식 검사: `<input type="email">`, `<input type="url">`, `<input type="tel">`, `<input type="search">`

---

## 스타일링과 구조의 분리

- 시맨틱 태그는 구조만 담당
- CSS3를 통해 위치, 색상, 모양 지정

---

## 실습 중심 구성

- 각 개념마다 HTML 예제 코드 포함
- 실습을 통해 직접 구조화 및 폼 작성 가능
