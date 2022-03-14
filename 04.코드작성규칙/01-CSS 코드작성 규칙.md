## ✔CSS 스타일 규칙
- css 스타일 규칙은 선택자옆 오른쪽 공백, 선언블록("{,}") 양쪽 공백, 속성과 속성값의 공백을 주며, 아래의 예시처럼 따른다. <br/>
  👉 selector { width: 100%; height: 100%; }
- 모든 속성의 방향은 top, right, bottom, left 순으로 선언한다.
- 소수점은 0을 생략한다. <br/>
  👉 0.5s -> .5s 
- 16 진수가 둘씩 반복될 경우 축약 한다.<br/>
  👉 #ffffff -> #fff<br/>
  👉 #eebbcc -> #ebc
- background와 border는 축약 하지만 font는 축약하지 않는다. <br/>
  👉 background: color image repeat position / size attachment; <br/>
  👉 border: 1px solid #fff;

&nbsp;

## ✔CSS 속성 선언 순서
- 속성을 선언할때는 쓰임새가 레이아웃과 관련이 큰 것에서 시작하여 레이아웃과 무관한 것 순서로 선언한다.

|속성|설명|
|---|---|
|display||
|overflow||
|float||
|position|top, right, bottom, left|
|width||
|height||
|margin|margin-top, margin-right, margin-bottom, margin-left|
|padding|padding-top, padding-right, padding-bottom, padding-left|
|border||
|background|background-color, background-image, background-repeat, background-position, background-attachment|
|color||
|font|font-family, font-size, font-weight, font-style|
|line-height||
|text-align||
|text-decoration||
|text-indent||
|vertical-align||
|white-space||
|animation||
|기타||
|z-index|최소 10, 최고 1000이며 10단위로 증감한다. <br/> 단, 10단위 사이의 예외 변수가 발생하면 1단위 값을 지정할 수 있다.|

