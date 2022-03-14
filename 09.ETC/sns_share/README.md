# 페이스북 API 만들기
1. 페이스북 개발자 사이트 로그인 [https://developers.facebook.com/?locale=ko_KR](https://developers.facebook.com/?locale=ko_KR)
2. 로그인 후, 상단 메뉴 '내 앱'
3. 내 앱이 없으면 '앱 만들기'
4. 앱 유형 선택 : 비즈니스, 표시 이름 : 프로젝트명, 앱 목적 : 회원님 또는 비즈니스
5. 설정 - 기본 설정에서 앱 도메인, 개인정보처리방침 URL, 서비스 약관 URL 작성
6. 하단의 플랫폼 추가 - website
7. 웹사이트에 사이트 URL 입력 후, 빠른 시작 클릭하면 API 생성
8. Javascript용 Facebook SDK 설정 스크립트를 소스에 붙여넣기 (API)

웹 도메인, 개인정보처리방침 URL, 서비스 약관 URL 필수

*-설정해야 할 목록이 많기 때문에 보통 페이스북, 카카오톡 등의 API 정보는 기획자분이 전달해주신다.*

<br>

# 매타태그 (공유했을 때 보이는 썸네일, 텍스트 설정)
```swift
  <!-- 참고 예시 -->
  <meta property="og:url" content= "https://stickinteractive.github.io/fint-event/"/>
  <meta property="og:type" content= "website"/>
  <meta property="og:title" content= "페이스북 메타태그 타이틀을 작성해주세요."/>
  <meta property="og:description" content= "페이스북 메타태그 디스크립션을 작성해주세요."/>
  <meta property="og:image" content= "https://stickinteractive.github.io/fint-event/assets/image/share_facebook.jpg"/><!-- 공유할 썸네일 이미지의 절대경로 작성 -->
  <meta property="og:image:width" content="1200">
  <meta property="og:image:height" content="630">
  <meta property="fb:app_id" content="252522600275458">
```

url, title, decription, 썸네일로 사용할 image 정보 필요 (기획자가 전달)

카카오톡 공유하기 기능을 사용한다면 카카오ID 정보와 JavaScript 키 값이 필요하다.  
1. https://developers.kakao.com/ 카카오 개발자 사이트 접속
2. 상단 메뉴의 내 어플리케이션 클릭
3. 사용할 앱 선택 (앱이 없다면 만들어야 한다.)
4. ID와 JavaScript 키 복사해서 사용하기

*-캐시를 삭제해도 매타태그 공유 썸네일이 변경이 안된다면 이미지명 바꿔서 해결한다.*

<br>

# 공유하기 캐시삭제
트위터 캐시 삭제 : https://cards-dev.twitter.com/validator  
카카오톡 캐시 삭제 : https://developers.kakao.com/tool/clear/og  
페이스북 캐시 삭제 : https://developers.facebook.com/tools/debug/?locale=ko_KR

<br>

# head 작성순서
1. 메타태그
2. 타이틀
3. 메타 og태그
4. 파비콘
5. css (link)
6. js (script)
7. GA
