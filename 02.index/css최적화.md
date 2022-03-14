## 📢CSS 성능 최적화

**CSS는 렌더링을 막는다.**
CSS 존재만으로도 CSS가 파싱되기 전까지 브라우저는 렌더링이 지연된다.

<br>

**CSS는 HTML 파싱도 막을 수 있다.**
브라우저가 CSS가 파싱되기 전까지 콘텐츠를 보여주지 않아도 HTML의 로딩된 부분만을 먼저 보여줄 수 있다. 그러나 스크립트의 경우 `aync` `defer` 이 없다면 파싱을 막게 된다.

브라우저가 CSS관련 작업을 진행중이라면, 이 작업이 완료될 때 까지 기다렸다가 스크립트를 실행한다.

스크립트가 실행되기 전까지 문서 파싱을 할 수 없기 때문에, CSS는 더이상 렌더링은 차단하는 요소로 작용되지 않는다(하단 그림 참조) 문서의 외부 스타일시트 및 스크립트 순서에 따라서 때로는 HTML 파싱도 중지할 수 있다.

![css-can-block-html-parsing](https://web-now-rbviiass9-calibreapp.vercel.app/_next/image?url=%2Fimages%2Fblog%2Fcss-performance%2Fparser-blocking-css.png&w=1920&q=75)

👉 파싱을 차단하는 상황을 피하기 위해서는, CSS를 최대한 빨리 불러와야 하고, 리소스를 최적의 순서로 불러야 한다.

<br>

**CSS 압축하고 최소화하기**

<br>

**사용하지 않는 CSS 제거**

<br>

**CSS 우선순위 정하기**

첫 렌더링 시의 라운드트립(클라이언트와 서버간의 데이터 왕복 과정)을 최소화 하기 위해서는, above-the-fold(-   웹페이지에서 아무 행동(스크롤, 클릭 등)을 하지 않은 부분) content의 크기를 14kb내로 유지해야 한다.(압축시)

<br>

**CSS 비동기로 불러오기**

```html
<link
  rel="stylesheet"
  href="non-critical.css"
  media="print"
  onload="this.media='all'"
/>
```
- `print` 미디어 타입이란, 사용자가 체이지를 프린트를 하려고 하는 경우에만, 브라우저가 해당 스타일 시트를 불러오는 것으로 렌더링에는 영향을 미치지 않는다.
- `onload` 이벤트로 `this.media='all'` 을 추가한다면, 스타일 시트가 로드가 완료되면 미디어 속성을 다시 `all` 로 바꾸면서 스타일 시트가 적용된다.

<br>

**@import 사용 자제하기**

`@import` 는 CSS파일의 렌더링 속도를 느리게 한다. 특히 `@import url(~.css)` 와 같은 코드는 네트워크 흐름을 아래와 같이 바꿔버린다.

![@import](https://web-now-rbviiass9-calibreapp.vercel.app/_next/image?url=%2Fimages%2Fblog%2Fcss-performance%2Fcss-import-blocking.png&w=1920&q=75)


그러나 두 파일을 별개로 분리하면 이런식으로 동시에 다운로드 하게 된다.

![parallel](https://web-now-rbviiass9-calibreapp.vercel.app/_next/image?url=%2Fimages%2Fblog%2Fcss-performance%2Fcss-parallel-download.png&w=1920&q=75)

<br>

**효과적인 CSS 애니메이션 사용하기**

- `height` `width` 대신 `transform: scale()` 을 쓴다.
- `top` `right` `bottom` `left`  대신 `transform: translate()`  를 쓴다.
- 배경에 `blur` 를 먹이고 싶다면, opacity를 바꾸는 것보다 그냥 blur 된 이미지를 불러오는게 낫다.

<br>

**contain 속성**

[contain](https://developer.mozilla.org/en-US/docs/Web/CSS/contain)은 브라우저에 요소와 하위 요소가 그 문서 트리와 무관한 것으로 간주된다는 것을 알려주는 속성이다.
페이지의 하위 트리와 나머지 페이지를 분리한다. 그런 다음, 브라우저는 페이지에서 독립된 부분의 렌더링을 최적화하여 성능을 향상 시킬 수 있다.

페이지 내부에서 독립적으로 작동하는 위젯 등에서 매우 효과적이다. 이 속성을 활용하여 위젯의 내부에서의 변경사항이 바깥으로 전파되는 것을 막을 수 있다.

<br>

## **📝CSS로 폰트 로딩 최적화하기**

<br>

**폰트 로딩 중에는 보이지 않는 텍스트를 두지 않기**

일부 브라우저는 폰트가 로딩되기 전까지 텍스트를 숨긴다. (FOIT, flasf of invisible text)
속도를 최적화하기 위해서는 FOIT를 피하고, 시스템 폰트를 기본으로 사용하여 즉시 사용자에게 콘텐츠를 보여주는 것이 좋다.
폰트가 로딩 되면, 시스템 기본 글꼴로 로딩된 폰트를 대체 하는 FOUT(flash of unstyled text) 현상이 일어날 것이다.

이를 위한 방법 중 하나가 [font-display api](https://developer.mozilla.org/ko/docs/Web/CSS/@font-face/font-display)를 사용하는 것이다. `swap` 을 사용하면, 브라우저가 폰트가 다운로드 되지 전에는 즉시 시스템 글꼴로 보여줘야 한다는 것을 알려줄 수 있다.

<br>

**variable font를 사용하여 파일 크기 줄이기**

하나의 파일에 여러가지 다양한 폰트를 통합해줄 수 있도록 한다.

<br>

**CSS 선택자의 속도에 대해서 걱정할 필요는 없다.**

선택자를 매칭 시키는 속도는 굉장히 빠르므로 굳이 걱정할 필요는 없다.





<br><br>

> 참고 : [CSS 성능 향상 시키기](https://yceffort.kr/2021/03/improve-css-performance)


<br><br>

## Repaint가 일어나지 않는 CSS 속성

![](https://blog.kakaocdn.net/dn/WzQPK/btqxbc2lP7u/OIndy8VwyRSfVMPUBZKnU0/img.jpg)

<center>style 속성 변경시 Reflow, Repaint 과정</center>

<br>

**Reflow, Repaint 줄이기**

* 사용하지 않는 노드에는 visibility: invisible 보다는 display: none을 사용하기
* Reflow, Repaint 가 발생하는 속성 사용 피하기
 👉 Reflow가 일어나면 Repaint는 필연적으로 일어나야 하기 때문에 가능하다면 Reflow가 발생하는 속성보다 Repaint만 발생하는 속성을 사용하는것이 좋다.

	
> Reflow가 일어나는 대표적인 속성 👉 position, width, height, left, top, right, bottom, margin, padding, border, border-width, clear, display, float, font-family, font-size, font-weight, line-height, min-height, overflow, text-align, vertical-align, white-space ....  

> Repaint가 일어나는 대표적인 속성 👉  background, background-image, background-position, background-repeat, background-size, border-radius, border-style, box-shadow, color, line-style, outline, outline-color, outline-style, outline-width, text-decoration, visibility ....

  
* 영향을 주는 노드 줄이기
* 프레임 줄이기



<br><br>

> 참고 : [렌더링 과정](https://boxfoxs.tistory.com/408)
> 
> 참고 : [렌더링 성능](https://developers.google.com/web/fundamentals/performance/rendering/?hl=ko)
