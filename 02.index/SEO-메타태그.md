## 🔎 SEO

 SEO 작업은 검색환경에 맞게 내 웹사이트를 최적화하는것을 뜻한다.  SEO 작업이 잘 되어 있을 수록 내 웹사이트의 검색 결과가 더 좋은곳에 위치할 수 있다. 이는 곧 유입률과 연관있기 때문에 SEO 최적화는 중요하다. 

<br>

**SEO를 위한 메타 태그**

최적화 작업중 가장 기본은 메타태그 설정(최적화)이다. 메타태그란, 웹페이지의 정보를 담고 있는 태그라고 생각하면 된다.

**사이트맵 제출**

이는 간단하게 말하면 웹사이트의 설계도면과 같다. 보통 XML 파일형식으로 사이트맵을 구성하게 된다. 처음 SEO를 하는 사람들은 직접 셋팅하기에는 힘들기 때문에 [XML 자동생성 사이트](https://www.xml-sitemaps.com/)의 도움을 받는 것이 좋다.

**robots.txt 설정**

이는 현실로 따지면 문지기와 같다. 내 웹사이트에 검색로봇이 들어올 수 있게 허가를 해주는거라고 생각하면 된다.  이 파일을 내 호스팅에 접근제한을 줘서 업로드할 경우 특정 폴더, 파일, 또는 웹사이트 전체를 구글 검색엔진이 들어오지 못하게 차단할 수도 있다. 

**적합한 컨텐츠**

검색엔진이 제일 중요하게 생각하는 것중 하나가 키워드에 맞는 컨텐츠의 여부이다.  보통 검색엔진은 콘텐츠를 읽어갈 때 텍스트와 이미지로 판단하게 된다.  때문에 키워드에 맞는 "텍스트 콘텐츠"와 "이미지 alt 속성" 적용해준다.

<br>

## 📰 메타태그

**메타태그란❓**

메타태그는 검색엔진 및 웹사이트 방문자에게 페이지 콘텐츠를 설명하는 HTML 태그의 일부이다.  

<br>

**2021년 SEO를 위한 가장 중요한 메타태그**
1.  **Title tag**
2.  **Meta description**
3.  **Canonical Tag**
4.  **Alternative text (Alt) Tag**
5.  **Robots meta tag**
6.  **Social Media Meta Tags (Open Graph and Twitter Cards)**
7.  **Responsive Design Meta Tag**

<br>

**Title tag**

`<title>타이틀</title>`

`<meta name="title" content="페이지 타이틀">`

- 제목 태그. 메타 제목의 권장 길이는 `600px` 이다.  👉 공백 포함 최대 60자 이내로 쓴다. 이보다 길면 잘린다.
- 타이틀과 메타타이틀은 정의한 내용과 동일하기 때문에 SEO의 측면에서는 큰 의미가 있지 않다. 만약 둘의 내용이 다를 경우에 검색엔진은 타이틀 태그의 값을 검색 결과에서 보여준다.

<br>

**Meta description**

`<meta name ="description" content="메타 설명 샘플입니다. 최대 160 자까지 추가 할 수 있습니다.">`

- 사이트를 요약하는 HTML 요소이다. 검색 엔진은 일반적으로 제목 태그 아래의 검색 결과에 메타 설명을 표시한다. 
- PC에서 평균 길이는 300~160자이다. 스니펫의 모바일 문자는 평균 130자이다.

<br>

**Canonical Tag**

`<link rel ="canonical" href="http://example.com/">`

- 다른 여러 페이지 URL과 동일한 콘텐츠가 있는 단일 페이지 URL이 있는 경우 사용된다.
- 해당 URL이 기본 페이지임을 검색 엔진에 알리고 다른 중복 페이지 URL의  index 생성을 방지한다.

<br>

**Alternative text (Alt) Tag**

`<img src ="http://example.com/xyz.jpg"alt ="xyz">`

- 대체 텍스트 태그
- 모든 이미지에는 유익한 파일 이름이 있어야 한다.
- 짧고 명확해야 한다.
- 50~55자(최대 16단어) 사용

<br>

**Robots meta tag**

`<meta name ="robots" content ="noindex, nofollow">` 

👉 색인을 생성하지 않거나 이 사이트를 따르지 않음

`<meta name ="robots" content ="index, follow">`

👉  색인을 의미하고 이 사이트를 따른다.

- 사이트의 색인을 생성할 지 아니면 생성하지 않을지에 대한 지침을 웹 크롤러에게 제공
- 로봇 메타 태그에는 검색 엔진 크롤러에 대한 네 가지 주요 값이 있다.
	-   FOLLOW – 검색 엔진 크롤러가 해당 웹 페이지의 모든 링크를 따라간다.
	-   INDEX – 검색 엔진 크롤러가 전체 웹 페이지의 색인을 생성한다.
	-   NOFOLLOW – 검색 엔진 크롤러가 페이지와 해당 웹 페이지의 링크를 따르지 않는다.
	-   NOINDEX – 검색 엔진 크롤러가 해당 웹 페이지의 색인을 생성하지 않는다.
	
👉 이중에서 중요한것은 NOFOLLOW, NOINDEX이다. 그 이유는 검색 엔진 로봇은 meta 요소로 지정하지 않은 경우에도 자동적으로 페이지를 순회하기 때문에, 페이지를 검색 엔진에 Index하고 싶을 때는 아무런 설정을 하지 않아도 되기 때문이다.

<br>

**Social Media Meta Tags (Open Graph and Twitter Cards)**

페이스북, 링크드인, 구글 및 이러한 플랫폼에서 공유한 웹 사이트 URL 간의 통합을 위해 설계되었다.

`<meta  property="og:type"  content="article">`

`<meta  property="og:title"  content="TITLE OF YOUR POST OR PAGE">`

`<meta  property="og:description"  content="DESCRIPTION OF PAGE CONTENT">`

`<meta  property="og:image"  content="LINK TO THE IMAGE FILE">`

`<meta  property="og:url"  content="PERMALINK">`

`<meta  property="og:site_name"  content="SITE NAME">`

트위터는 아래와 같이 사용한다.

`<meta  name="twitter:card"  content="summary_large_image">` 

`<meta  name="twitter:title"  content="TITLE OF POST OR PAGE">`

`<meta  name="twitter:description"  content="DESCRIPTION OF PAGE CONTENT">`

`<meta  name="twitter:image"  content="LINK TO IMAGE">`

`<meta  name="twitter:site"  content="@USERNAME">`

`<meta  name="twitter:creator"  content="@USERNAME">`

<br>

**Responsive Design Meta Tag**

반응형 디자인 메타태그, 뷰포트 메타 태그를 사용하여 모바일 브라우저에서 웹 페이지의 레이아웃을 제어한다.

`<meta  name="viewport"  content="width=device-width, initial-scale=1">`

`<meta  name="viewport"  content="width=device-width, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0, user-scalable=no">`

<br>

**Meta Tags to ignore**

마지막으로 아래 메타태그들은 무시한다.

✔ **Keywords tag**  (악용한 경우가 많아서 더이상 사용하지 않는다)

✔ **Site verification**

✔ **Copyright**


<br>

** 🤔[메타태그 생성기](https://lewdev.github.io/apps/meta-tag-gen/)**

메타태그를 자동으로 생성해주는 사이트. 참고용으로 좋다.


<br><br>

>참고 : 
>[구글 SEO 2021 최신 트렌드](https://backlinkpro.tistory.com/28)
>
> [Meta Tags in 2021: Why are They Important in SEO?](https://www.advancedwebranking.com/blog/meta-tags-important-in-seo/)
>
>[메타요약문](https://www.ascentkorea.com/meta-description-seo/)
>
>[head태그에는 무엇이 있을까?](https://developer.mozilla.org/ko/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML)
