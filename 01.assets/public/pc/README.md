
# Style Guide

 1. 가이더가 프로젝트에서 공통으로 쓸 수 있는 것들을 컴포넌트화 한다.
 2. 디자이너가 스타일가이드를 만들어서 줬을땐 그 기준으로 가이드를 잡는다.
 3. 스타일가이드가 없을 땐 시안을 보며 공통적으로 뺄 수 있는 것들 추린 후 가이드를 잡는다.
 4. 작업 중 재 사용이 될 것 같은 컴포넌트가 생겼을 시 협의 후 가이드에 추가해도 된다.
 


## 스타일가이드 컴포넌트 리스트
 - color
 - text
 - form
 - button
 - icon
 - tab
 - modal
 - list
 - table 
 - layout
 - 등등


### 스타일 가이드 참고링크
1. 현대모비스 : http://stage-mobis.stickinteractive.com/kr/styleguide
2. 스틱 인트라넷 : http://stage-intra.stickinteractive.com/styleguide
3. 쿠첸몰 : http://stage-cuchen.stickinteractive.com/_common.html

&nbsp;

## oocss 방법론
여러가지 방법이 있지만 우리팀은 oocss방법론을 사용중인듯 하다.
추 후 BEM 방법론을 프로젝트에 적용해봐도 좋을 듯.

&nbsp;
- oocss 방법론이란?
css를 모듈방식으로 코딩하여 중복을 최소화하는 기법

 1. 구조(width, height, padding, margin ....)와 외형(background-color, color....)을 분리한다.
```
.btn {
	//...공통스타일
	
	&.large {
		width: 100px;
	}
	&.red {
		background-color: red;
	}
}
```
2. 컨테이너와 내용 분리한다.<br>
특정 위치에 해당하는 스타일을 정의하지 않고, 다른 영역에서도 사용할 수 있게 속성을 분리하면 중복코드를 줄일 수 있다.
```
// bad
.main-list {
	position: relative;
	width: 200px;
	height: 200px;
	padding: 40px;
	margin-bottom: 30px;
	font-size: 14px;
}

// good
.common-list {
	position: relative;
	width: 200px;
	height: 200px;
	padding: 40px;
	
	&.main-type {
		margin-bottom: 30px;
		font-size: 14px;
	}
}

```

### 네이밍
항상 네이밍을 할때는 확장성을 열어두고 지으며, 클래스 이름은 최대한 간결하고 명료하게 짓는다.
특정 위치, 특정 스타일의 네이밍 보다, 어떤 페이지에서도 쓸 수 있는 포괄적이고 직관적인 네이밍을 정의하는게 추 후 유지보수에 용이하다.



참고: https://wit.nts-corp.com/2015/04/16/3538, https://whales.tistory.com/33
