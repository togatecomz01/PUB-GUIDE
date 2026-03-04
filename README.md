# Overview (개요)
- 프로젝트 이름: MG캐피탈 웹퍼블리싱 소스 공통
- 프로젝트 설명: MG캐피탈 홈페이지 리뉴얼 프로젝트 종료 후, 웹퍼블리싱 소스를 재사용 가능한 공통 포맷으로 구조화한 가이드 프로젝트.

<br/>
<br/>

# Browser Support
<p>금융권 환경을 고려하여 다음 브라우저를 지원합니다.</p>

- IE11

- Chrome 104 이하

- Edge (Chromium 기반)

- 최신 Chrome

<p>대응 전략</p>

- IE 전용 스타일은 `ie.css`에서 별도 관리

- 최신 기능은 `@supports`를 활용하여 분기 처리

- 최신 브라우저 우선 설계 → 하위 브라우저 보완 방식 적용

- ie.css는 향후 추가 요구사항 및 브라우저 이슈에 따라 지속적으로 보완 예정

<br/>
<br/>

# Technology Stack (기술 스택)
## Language
|  |  |
|-----------------|-----------------|
| HTML5    |<img src="https://github.com/user-attachments/assets/2e122e74-a28b-4ce7-aff6-382959216d31" alt="HTML5" width="100">| 
| CSS3    |   <img src="https://github.com/user-attachments/assets/c531b03d-55a3-40bf-9195-9ff8c4688f13" alt="CSS3" width="100">|
| Javascript    |  <img src="https://github.com/user-attachments/assets/4a7d7074-8c71-48b4-8652-7431477669d1" alt="Javascript" width="100"> | 

<br/>

## Frotend
|  |  |  |
|-----------------|-----------------|-----------------|
| Swiper    |  <img src="https://swiperjs.com/images/swiper-logo.svg" alt="Swiper" width="100"> |11.2.10|
| jquery    |  <img src="https://img.shields.io/badge/jQuery-0769AD?style=flat-square&logo=jQuery&logoColor=white" alt="jquery" width="100"> |1.12.4|

<br/>
<br/>

# UI Components (기본 공통 컴포넌트)
- **Alert**: 알림창 및 경고 메시지 UI 컴포넌트
  - [guide/sample/alert.html](guide/sample/alert.html)

- **Button**: 다양한 스타일의 버튼 컴포넌트
  - [guide/sample/button.html](guide/sample/button.html)

- **Input**: 입력 필드 및 폼 컴포넌트
  - [guide/sample/input.html](guide/sample/input.html)

- **Popup**: 모달 및 팝업 윈도우 컴포넌트
  - [guide/sample/popup.html](guide/sample/popup.html)

- **Tab**: 탭 네비게이션 컴포넌트
  - [guide/sample/tab.html](guide/sample/tab.html)

- **Table**: 데이터 테이블 컴포넌트
  - [guide/sample/table.html](guide/sample/table.html)

- **Toggle**: 토글 스위치 컴포넌트
  - [guide/sample/toggle.html](guide/sample/toggle.html)

- **Terms**: 약관 동의 UI 컴포넌트
  - [guide/sample/terms.html](guide/sample/terms.html)

<br/>
<br/>

# Getting Started
- css 로드 순서
```html
  <link rel="stylesheet" href="assets/css/com/common.css">
  <link rel="stylesheet" href="assets/css/com/style.css">
```
- js 로드 순서
```html
  <script src="assets/js/lib/jquery-1.12.4.js"></script>
  <script src="assets/js/lib/swiper-bundle.min.js"></script>
  <script src="assets/js/ui-util.js"></script>
```

# Project Structure (프로젝트 구조)
<h2>구조 전략</h2>
- 컴포넌트 단위 분리
- 유틸 클래스 분리 관리
- IE 대응 CSS 별도 분리

```plaintext
PUB-GUIDE/
├── index.html                           # 메인 HTML 파일
├── README.md                            # 프로젝트 개요 및 사용법
├── assets/                              # 정적 파일 및 라이브러리
│   ├── css/                             # 스타일시트
│   │   ├── swiper-bundle.min.css        # Swiper 라이브러리 CSS
│   │   └── com/                         # 공통 컴포넌트 CSS
│   │       ├── default.css              # 기본 초기화 및 베이스 스타일
│   │       ├── common.css               # 공통 스타일 정의
│   │       ├── fonts.css                # 폰트 스타일
│   │       ├── layout.css               # 레이아웃 스타일
│   │       ├── button.css               # 버튼 스타일
│   │       ├── input.css                # 입력 필드 스타일
│   │       ├── nav.css                  # 네비게이션 스타일
│   │       ├── style.css                # 메인 스타일
│   │       ├── tab.css                  # 탭 스타일
│   │       ├── table.css                # 테이블 스타일
│   │       ├── ie.css                   # IE 호환성 스타일
│   │       └── ui-util.css              # UI 유틸 스타일
│   ├── fonts/                           # 폰트 파일
│   ├── images/                          # 이미지 파일
│   │   └── com/                         # 공통 이미지
│   │       ├── ie11/                    # IE11 호환 이미지
│   │       └── svg/                     # SVG 파일
│   └── js/                              # 자바스크립트 파일
│       ├── include.js                   # 공통 include 처리
│       ├── lib/                         # 외부 라이브러리
│       │   ├── jquery-1.12.4.js         # jQuery 라이브러리
│       │   ├── jquery-ui.min.js         # jQuery UI 라이브러리
│       │   ├── swiper-bundle.min.js     # Swiper 라이브러리
│       │   └── ui_plugin.js             # UI 플러그인
│       └── ui/                          # UI 스크립트
│           ├── ui-util.js               # UI 유틸리티
│           └── com/                     # 공통 UI 스크립트
│               ├── accordion.js         # 아코디언
│               ├── datepicker.js        # 날짜 선택기
│               ├── fake_select.js       # 커스텀 셀렉트
│               ├── finance.js           # 재무 관련 스크립트
│               ├── input.js             # 입력 필드 스크립트
│               ├── layout.js            # 레이아웃 스크립트
│               ├── nav.js               # 네비게이션 스크립트
│               ├── popup.js             # 팝업 스크립트
│               ├── tab.js               # 탭 스크립트
│               ├── table.js             # 테이블 스크립트
│               └── terms.js             # 약관 스크립트
├── guide/                               # 가이드 및 샘플
│   ├── css/                             # 가이드 스타일
│   │   ├── pub-worklist.css             # 작업 리스트 스타일
│   │   └── sample.css                   # 샘플 스타일
│   ├── js/                              # 가이드 자바스크립트
│   │   ├── jquery-1.11.3.min.js         # jQuery 라이브러리
│   │   └── jquery.form.min.js           # jQuery Form 라이브러리
│   └── sample/                          # HTML 샘플 파일
│       ├── alert.html                   # 알림 샘플
│       ├── button.html                  # 버튼 샘플
│       ├── input.html                   # 입력 필드 샘플
│       ├── popup.html                   # 팝업 샘플
│       ├── tab.html                     # 탭 샘플
│       ├── table.html                   # 테이블 샘플
│       ├── terms.html                   # 약관 샘플
│       ├── toggle.html                  # 토글 샘플
└── views/                               # 페이지 뷰
    └── COMMON/                          # 공통 컴포넌트
        ├── footer.html                  # 푸터
        └── header.html                  # 헤더
```

<br/>
<br/>

# Coding Convention
## 명명 규칙
* **상수**: 영문 대문자 + 스네이크 케이스
```javascript
const MAX_WIDTH = 1200;
const DEFAULT_TIMEOUT = 5000;
```

* **변수 & 함수**: 카멜케이스
```javascript
// 일반 변수
let currentCount = 0;
let isActive = false;
let userList = [];

// DOM 요소: 'el'로 시작
const elButton = document.querySelector('.btn');
const elModal = document.getElementById('modal');

// 배열 - 복수형 이름 사용
const items = [];
const elements = document.querySelectorAll('.item');

// 정규표현식: 'r'로 시작
const rEmail = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
const rPhoneNumber = /^\d{10,11}$/;

// 이벤트 핸들러: 'on'으로 시작
const onClick = function(e) {};
const onChange = function(e) {};

// 반환 값이 불린인 경우: 'is'로 시작
const isVisible = true;
const isDisabled = false;

// 함수: 동작을 나타내는 동사로 시작
const getData = function() { ... };
const setData = function(data) { ... };
const removeItem = function(id) { ... };
```

<br/>

## 블록 구문
```javascript
// 한 줄짜리 블록일 경우라도 {}를 생략하지 않고, 명확히 줄 바꿈 하여 사용한다
// Good
if (true) {
  return 'hello';
}

// Bad
if (true) return 'hello';
```

<br/>

## 함수
```javascript
// 함수 선언식 또는 함수 표현식 사용
// Good
const fnName = function() { };
function fnName() { }

// jQuery 콜백
$(element).on('click', function(e) {
  // 구현부
});
```

<br/>

## HTML 요소 네이밍
HTML 요소의 class와 id 네이밍 규칙을 준수하여 의미 전달을 명확하게 한다.<br/>
요소명이 길어지더라도 의미 전달의 명확성에 목적을 두어 작성한다.<br/>
```html
<!-- 전체 컨테이너 -->
<div class="container">
  <!-- 영역 묶음 -->
  <div class="content-area">
    <div class="content-item">...</div>
    <div class="content-item">...</div>
  </div>
  <!-- 버튼 영역 -->
  <div class="button-group">
    <button class="btn btn-primary">확인</button>
    <button class="btn btn-secondary">취소</button>
  </div>
</div>
```

<br/>

## 폴더 네이밍
소문자와 하이픈(kebab-case)을 사용하여 일관성 있게 관리한다.
```
// Good
assets/
js/
userdata/

// Bad
Assets/
Js/
UserData/
```

<br/>

## 파일 네이밍
```
// JavaScript 파일
script.js
ui-util.js

// CSS 파일
style.css
button.css

// HTML 파일
index.html
alert.html

// 공통 UI 스크립트의 경우 기능명으로 명명
accordion.js (아코디언)
datepicker.js (날짜 선택기)
popup.js (팝업)
```

<br/>
<br/>

# Improvements (개선점)
<h2>향후 개선 예정 사항</h2>

- CSS 테마 분리 구조 확장
- ES6 기반 리팩토링 검토
- jQuery 의존성 최소화 검토
- 컴포넌트 모듈화 고도화
- 금융권 브라우저 대응 전략 고도화
