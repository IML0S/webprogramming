# 강의 요약: 자바스크립트 코어 객체와 배열

## 1. 객체 개념
- 현실 세계의 사물(사람, 자동차 등)을 객체로 표현
- 객체는 고유한 속성(프로퍼티)과 기능(메소드)을 가짐

## 2. 자바스크립트 객체 구성
- 객체는 프로퍼티(속성)와 메소드(함수)로 구성
- 객체 생성 방법:
  - new Object()로 생성 후 프로퍼티/메소드 추가
  - 리터럴 표기법 {} 사용
  - 프로토타입(생성자 함수) 사용

## 3. 자바스크립트 객체 종류
- 코어 객체: Array, Date, String, Math 등
- HTML DOM 객체: HTML 태그를 객체화
- 브라우저 객체: BOM 기반 브라우저 제어용 객체

## 주요 코어 객체와 메소드

### Date 객체
- 시간 정보 처리용 객체
- 주요 메소드:
  - getFullYear(), getMonth(), getDate()
  - getHours(), getMinutes(), getSeconds()
  - getMilliseconds(), toLocaleString(), toUTCString()

### String 객체
- 문자열 처리용 객체
- 주요 메소드:
  - charAt(), concat(), indexOf(), slice()
  - substr(), toUpperCase(), replace(), trim()
  - split(), toString()

### Array 객체
- 배열 처리용 객체
- 주요 메소드:
  - concat(), join(), reverse(), slice()
  - sort(), toString()
- 프로퍼티:
  - length (배열 크기)

### Math 객체
- 수학 계산용 객체 (new 없이 사용)
- 주요 메소드:
  - Math.sqrt(), Math.PI
  - Math.random(), Math.floor()

## 사용자 객체 생성 방법
- new Object() 방식
- 리터럴 표기법 {} 방식
- 프로토타입(생성자 함수) 방식
