# 강의 요약: 자바스크립트 이벤트 처리

## 1. 이벤트 개념
- **이벤트(Event)**: 사용자의 행동(클릭, 키 입력 등)이나 문서·브라우저의 상태 변화를 자바스크립트 코드에 알려주는 신호  
- **이벤트 리스너(Event Listener)**: 이벤트 발생 시 실행되는 자바스크립트 코드  
- HTML5에서는 약 70여 가지의 이벤트가 존재하며, 리스너 이름은 이벤트 이름 앞에 `on`을 붙임  
  - 예: `onclick`, `onkeydown`, `onload`

---

## 2. 이벤트 리스너 작성 방법

### (1) HTML 태그 내 작성
```html
<p onmouseover="this.style.backgroundColor='orchid'"
   onmouseout="this.style.backgroundColor='white'">
   마우스 올리면 색 변경
</p>
```

### (2) DOM 객체의 이벤트 리스너 프로퍼티에 작성
```javascript
let p = document.getElementById("p");
p.onmouseover = over;
p.onmouseout = out;
```

### (3) addEventListener() 메소드 이용
```javascript
p.addEventListener("mouseover", over);
p.addEventListener("mouseout", out);
```

### (4) 익명 함수 사용
```javascript
p.onmouseover = function () {
  this.style.backgroundColor = "orchid";
};
```

---

## 3. 이벤트 객체 (Event Object)
- 발생한 이벤트에 대한 **정보(타입, 타겟, 좌표, 키 등)**를 담은 객체
- 이벤트 리스너 함수의 **첫 번째 매개변수로 전달**
- HTML 태그 리스너에서는 `event`라는 이름으로 접근 가능  

```javascript
function f(e) {
  alert(e.type); // 이벤트 종류 출력
}
document.getElementById("p").onmouseover = f;
```

### 주요 프로퍼티
| 프로퍼티 | 설명 |
|-----------|------|
| `type` | 이벤트 종류 |
| `target` | 이벤트가 발생한 객체 |
| `currentTarget` | 현재 이벤트를 받는 객체 |
| `defaultPrevented` | 디폴트 행동 취소 여부 |
| `cancelable` | preventDefault() 사용 가능 여부 |

---

## 4. 이벤트의 기본 동작 제어
- HTML 태그에는 **디폴트 행동(default action)** 이 존재함  
  예)  
  - `<a>` 클릭 → 링크 이동  
  - `<form>`의 submit → 데이터 전송  
  - `<input type="checkbox">` 클릭 → 선택 토글

### 디폴트 행동 막기
1. `return false` 사용  
2. `event.preventDefault()` 호출  

```html
<a href="http://www.naver.com" onclick="return false">이동 안됨</a>
```

---

## 5. 이벤트 흐름 (Event Flow)

### 이벤트 전파 단계
1. **캡처 단계 (capturing phase)**  
   - window → target까지 이벤트 전달  
2. **버블 단계 (bubbling phase)**  
   - target → window 방향으로 다시 전달  

```javascript
button.addEventListener("click", capFunc, true);  // 캡처 리스너
button.addEventListener("click", bubbleFunc, false); // 버블 리스너
```

- `addEventListener()`의 세 번째 인자:
  - `true` → 캡처 단계  
  - `false` → 버블 단계  
- 이벤트 전파 중단: `event.stopPropagation()`

---

## 6. 마우스 이벤트

| 이벤트 | 설명 |
|---------|------|
| `onclick` | 클릭 시 |
| `ondblclick` | 더블클릭 시 |
| `onmousedown` / `onmouseup` | 마우스 버튼 누르기/떼기 |
| `onmouseover` / `onmouseout` | 태그 위로 진입 / 벗어날 때 |
| `onwheel` | 마우스 휠 굴릴 때 |
| `onmousemove` | 마우스 이동 시 |

### 예제: onwheel 사용
```javascript
obj.onwheel = function(e) {
  if (e.wheelDelta < 0) width--; // 휠 아래
  else width++; // 휠 위
  obj.style.borderWidth = width + "px";
};
```

---

## 7. oncontextmenu (오른쪽 클릭 방지)
```javascript
document.oncontextmenu = function() {
  alert("오른쪽 클릭 금지");
  return false;
};
```

---

## 8. onload (문서 및 이미지 로딩 완료)
- **window 객체**에서 발생  
- 페이지나 이미지 로딩 완료 시 실행  

```html
<body onload="alert('페이지 로드 완료!')">
```

### 이미지 onload 활용
```javascript
let img = document.getElementById("myImg");
img.onload = function() {
  console.log(img.width + "x" + img.height);
};
img.src = "banana.png";
```

---

## 9. new Image()로 이미지 로딩
```javascript
let bananaImg = new Image();
bananaImg.src = "banana.png";

let myImg = document.getElementById("myImg");
myImg.src = bananaImg.src;
```

---

## 10. 포커스 이벤트
| 이벤트 | 설명 |
|---------|------|
| `onfocus` | 포커스를 얻었을 때 |
| `onblur` | 포커스를 잃었을 때 |

```javascript
function checkFilled(obj) {
  if (obj.value == "") obj.focus();
}
```

---

## 11. 폼 관련 이벤트

### (1) 라디오버튼
```javascript
let radios = document.getElementsByName("city");
for (let i = 0; i < radios.length; i++) {
  if (radios[i].checked) alert(radios[i].value);
}
```

### (2) 체크박스 계산
```javascript
let sum = 0;
function calc(box) {
  sum += box.checked ? parseInt(box.value) : -parseInt(box.value);
  document.getElementById("sumtext").value = sum;
}
```

### (3) select와 onchange
```javascript
function drawImage() {
  let sel = document.getElementById("fruits");
  let img = document.getElementById("fruitimage");
  img.src = sel.options[sel.selectedIndex].value;
}
```

### (4) onreset / onsubmit
- `<form>` 태그에 작성  
- `false`를 리턴하면 초기화 또는 전송이 취소됨  

```html
<form onreset="return false" onsubmit="return false">
```

---

## 12. 키 이벤트

| 이벤트 | 설명 |
|---------|------|
| `onkeydown` | 키를 누르는 순간 |
| `onkeypress` | 문자 키 입력 시 추가 호출 |
| `onkeyup` | 키를 떼는 순간 |

### 예제
```javascript
function whatKeyDown(e) {
  let text = "key=" + e.key + "<br>code=" + e.code;
  document.getElementById("div").innerHTML = text;
}
```

### 응용: 방향키로 셀 이동
- `window.onkeydown` 사용  
- `ArrowUp`, `ArrowDown`, `ArrowLeft`, `ArrowRight` 키로 이동 제어  

---

## 13. 요약 포인트
- 이벤트는 **사용자 입력이나 시스템 변화**를 감지하는 신호  
- 리스너 작성 방법은 4가지 (`HTML`, `프로퍼티`, `addEventListener`, `익명 함수`)  
- `event` 객체를 통해 이벤트 정보 접근 가능  
- `preventDefault()`로 기본 동작 취소, `stopPropagation()`으로 전파 중단  
- **onload**, **onfocus**, **onblur**, **onchange**, **onkeydown** 등 상황별 이벤트 처리 가능

