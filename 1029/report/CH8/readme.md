# 강의 요약: HTML DOM 객체와 동적 문서 구성

## 1. HTML DOM 개념
- **DOM(Document Object Model)**: HTML 문서의 각 태그를 객체화한 구조
- HTML 태그마다 DOM 객체가 생성되고, 포함 관계에 따라 **트리 형태(DOM 트리)**로 구성
- DOM 객체를 통해 태그의 내용, 스타일, 속성 등을 동적으로 제어 가능

---

## 2. DOM 객체의 구성 요소
- DOM 객체는 다음 5가지 요소로 구성됨:
  - **프로퍼티(property)**: 태그의 속성을 반영 (예: id, innerHTML 등)
  - **메소드(method)**: HTML 태그를 제어하는 함수 (예: click(), setAttribute())
  - **컬렉션(collection)**: 자식 DOM 객체들을 배열 형태로 저장 (children 등)
  - **이벤트 리스너(event listener)**: 이벤트 처리용 함수 (onclick 등)
  - **CSS3 스타일(style)**: 태그의 스타일 정보 (color, border 등)

---

## 3. 주요 DOM 관련 객체와 메소드

### (1) document 객체
- HTML 문서 전체를 대표하는 객체 (DOM 트리의 루트)

#### 주요 프로퍼티
- `document.title`, `document.URL`, `document.body`, `document.head`
- `document.domain`, `document.readyState`, `document.lastModified`

#### 주요 메소드
- `getElementById(id)`  
- `getElementsByTagName(tag)`  
- `getElementsByClassName(class)`  
- `write()`, `writeln()`  
- `open()`, `close()`  
- `createElement(tag)`  
- `appendChild(node)`, `removeChild(node)`  

---

### (2) innerHTML 프로퍼티
- 시작 태그와 종료 태그 사이의 HTML 콘텐츠를 읽거나 변경  
```javascript
let p = document.getElementById("firstP");
p.innerHTML = "나의 <img src='puppy.jpg'> 강아지입니다.";
```

---

### (3) CSS 스타일 동적 변경
- DOM 객체의 `style` 프로퍼티를 통해 태그의 모양 변경 가능  
```javascript
let span = document.getElementById("mySpan");
span.style.color = "green";
span.style.fontSize = "30px";
span.style.border = "2px solid magenta";
```

---

### (4) this 키워드
- 이벤트가 발생한 현재 객체 자신을 가리킴  
```html
<button onclick="this.style.backgroundColor='orange'">버튼</button>
```

---

## 4. DOM 객체 탐색

| 메소드 | 설명 | 반환값 |
|---------|------|--------|
| `getElementById(id)` | 특정 id의 객체 반환 | 단일 객체 |
| `getElementsByTagName(tag)` | 같은 태그 이름의 객체들 | 컬렉션 |
| `getElementsByClassName(class)` | 같은 클래스 이름의 객체들 | 컬렉션 |

---

## 5. document.write() / writeln()
- 문서에 새로운 HTML 콘텐츠를 추가하는 메소드
- `write()` : 줄바꿈 없음  
- `writeln()` : 줄바꿈 포함  
- ⚠️ **주의:** 문서가 완전히 로드된 후 사용 시 기존 내용이 모두 삭제됨

---

## 6. 동적 문서 구성

### 새로운 태그(객체) 생성
```javascript
let newDiv = document.createElement("div");
newDiv.innerHTML = "새로 생성된 DIV입니다.";
newDiv.style.backgroundColor = "yellow";
```

### DOM 트리에 삽입
```javascript
parent.appendChild(newDiv);
```

### DOM 객체 삭제
```javascript
parent.removeChild(newDiv);
```

---

## 7. 요약 포인트
- **DOM**은 HTML 문서를 객체 트리 형태로 표현  
- **document** 객체는 DOM 트리의 루트이며 HTML 전체를 대표  
- `innerHTML`, `style`, `this`를 이용해 태그 콘텐츠와 모양을 제어  
- `createElement`, `appendChild`, `removeChild`로 동적 페이지 구성 가능  
- `getElementById`, `getElementsByTagName`, `getElementsByClassName` 등으로 객체 탐색

