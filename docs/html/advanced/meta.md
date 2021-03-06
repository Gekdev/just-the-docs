---
layout: default
title: Meta
parent: Advanced
grand_parent: HTML
nav_order: 1
---

# Meta Element
{: .no_toc .text-beta .fw-700}

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Meta Element Attributes

### Charset

```html
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
```

현재 페이지의 **인코딩(문자셋)을 어떠한 방식으로 출력할 지 결정**하는 속성. 

만약 제작한 웹 페이지의 한글이 깨져 보인다면, 거의 이 메타정보와 실제 페이지의 문자셋이 달라 생긴 문제일 가능성이 매우 큼. 

(이 메타 정보가 아예 선언되지 않았을 때에도 종종 발생하므로, 올바른 문자셋 정보를 꼭 넣는 것을 권장합니다)

국내 : **'UTF-8'**(다른 언어 사용시에도 좋음), 'EUC-KR'을 많이 사용 

### Description & Keyword

주로 검색엔진과 관련있음

```html
<meta name="Description" content="소개 내용" />
<meta name="Keywords" content="키워드들의 나열, abc, 123" />
```

* description 
    
    **현재 페이지를 간략히 소개하는 문구**
    
    이를 검색한 검색엔진이 페이지 제목과 같이 표현하며, '공유하기' 같은 것을 했을 때에 활용이 될 수도 있음.

* keyword 
    
    **페이지에 대한 키워드 정보** 
    
    페이지의 주요한 단어들을 콤마(,)로 구분하여 값을 넣어줘야함
    
    이 키워드 정보는 검색엔진이 보다 검색엔진을 용이하도록 만들지만, 다른 단어들을 무작위로 넣으면 검색엔진이 해당 페이지를 스팸 페이지로 인지할 수 있으니 주의. (이런 이유 때문에 요새 검색엔진은 이 키워드 정보를 아예 수집하지 않는다는 의견도 있다)

### Author & Generator

```html
<meta name="author" content="your name" />
<meta name="generator" content="dreamweaver cs6" />
```

* author

    **페이지의 저자**

    content의 값으로 저자를 나타내는 문자열을 써야함
    
    이 메타정보가 큰 의미를 가지진 않지만, 소스 상에서 누가 제작했는지를 명시

* generator

    **페이지를 생성한 프로그램**
    
    content의 값은 해당 프로그램의 명칭을 씀
    
    다만 이 정보는 손으로 직접 코딩 한 경우에는 이 값을 사용하지 말아야 함 (예로 메모장에서 작업한 경우는 직접 코딩 한 경우이므로, 값으로 'notepad'같은 것이 들어갈 일은 없다) 이 정보는 프로그램이 알아서 코드를 생성한 경우에 사용하기 때문에, 보통 그러한 프로그램을 사용할 경우 자동으로 추가가 될 가능성이 큼. 그런 이유로 이 메타정보를 쓸 일은 없다.
 
### Refresh

```html
 <meta http-equiv="refresh" content="30" />
```

**웹 페이지를 주기적으로 새로고침**

예상치 못하는 새로고침은 사용자 불편을 야기함, 특히 스크린리더로 접근하는 사람은 더욱 불편함. 

따라서 부분적인 영역의 새로고침으로 부분적으로 해결하는 것이 좋습니다. (자바스크립트를 통해)

요새 이 메타 요소를 사용하는 서비스는 별로 없으며, 이 요소는 사용하지 않음.

추가적으로 이 요소에 'content'값을 약간 수정하면 페이지를 우회 시킬 수 있습니다.

```html
<meta http-equiv="refresh" content="10;url=http://google.com/" />
```

content 값에 기존 숫자를 ';'으로 구분 짓고서 'url='로 시작하는 부분에 URL 주소를 넣어준다면, 해당 숫자만큼의 초가 지나면 해당 주소의 페이지로 이동하게 됩니다. (예를 들어 어떤 페이지가 '공사 중 입니다. 10초 후에 다른 페이지로 이동합니다' 라는 식의 문구를 가진 페이지는 보통 이런 방식을 사용)

해당 숫자를 '0'으로 바꾼다면 접속하자마자 해당 url로 이동

&#8594; 기존 링크이동과는 다르게 히스토리와 뒤로 가기가 남아있지 않음

접근성에 안좋음(사용자에게 예상치 못한 상황을 발생시키기 때문) 

검색엔진에 있어서도 좋지 않음 

구글에서도 이와 같은 방식을 권장하지 않음

따라서 해당 페이지의 URL을 변경해야 하는 경우 : '301 리디렉션'을 사용하길 권장 (구글 - 301 리디렉션으로 페이지 URL 변경)

### IE mode

```html
<meta http-equiv="X-UA-Compatible" content="IE=edge" />
```
 
**IE(인터넷 익스플로러)가 하위 버전 IE모드로 렌더링 하도록 만들어 줌** 

예를 들어 content속성 값에 "IE=EmulateIE7"로 넣는 경우, IE8 이상의 최신 IE 브라우저라도 IE7 버전처럼 페이지를 렌더링 합니다.

하위 렌더링 모드는 버전 업이 되면서, 조금씩 버그들이 생겨서 부득이한 경우가 아니라면 하위 모드는 사용하지 마시고, "IE=edge"를 넣어 해당 브라우저가 가장 표준적인 페이지로 렌더링 되도록 해아한다.

### Viewport

```html
<meta name="viewport" content="width=1200" />
```

이 메타정보는 해당 페이지의 콘텐츠 너비를 명시 해줍니다. 만약 이 메타 정보를 명시하지 않고, 쇼핑몰 같은 곳에 들어가는 '최근 본 상품' 윙 영역 같은 부분이 있다면, 해당 윙 영역이 계산되지 않은 채 화면에 가려질 수 있습니다. 또한, 스마트폰에서 자동으로 맞게 축소하는 것은 부정확한 크기로 보여질 수 있으니, 이 메타 요소를 명시해 주는 것이 좋습니다.

뷰포트값을 웹 페이지 너비와 같은 값을 줬을 땐 페이지가 꽉 차서 보이지만, 웹 페이지보다 큰 너비를 줄 경우 상대적으로 페이지가 작어 보입니다. 뷰포트 너비에 따른 페이지 비교
또한 이 속성은 PC버전용 페이지를 모바일 기기에서 접속했을 때 보다, 모바일용 페이지에서 더욱 중요한 역할을 합니다. content 속성 값에 "width" 말고 다른 속성을 넣을 수 있습니다.

```html
<meta name="viewport" content="initial-scale=1.0" />
```

이 내용을 처음 크기를 1:1 비율로 보여줌 (2.0 이라면 크기를 두 배)

모바일용 페이지라면 화면이 처음에 축소된 모습을 보이지 말아야 하기 때문에, 반드시 넣어줘야 하는 값입니다. 그리고 사실 이 속성값 말고도 추가적으로 더 넣어줍니다.

```html
 <meta name="viewport" content="width=device-width,initial-scale=1.0,minimum-scale=1.0,maximum-scale=1.0,user-scalable=no" />
```

* width=device-width
    
    페이지 너비를 기기의 너비와 동일하게 합니다. 'initial-scale=1.0'과 동일하다 할 수 있다.

* initial-scale=1

    **기기 독립적 픽셀과 CSS 픽셀 간에 1:1 관계를 설정** 페이지에서 전체 가로 너비를 활용할 수 있다.

* minimum-scale=1.0

    기기에서 줌 아웃을 할 때 가장 줄어들 수 있는 비율. 예를 들어 0.8이라면 실제 페이지의 80%까지 더 축소할 수 있습니다. 1이면 실제 페이지에서 축소가 안됨
    
* maximum-scale=1.0

    기기에서 줌 인을 할 때 가장 커질 수 있는 비율입니다. 2라면 두 배까지 확대 가능 합니다. 역시 1이라면 확대가 되지 않는니다.

* user-scalable=no

    줌 인, 줌 아웃을 할 수 없도록 만듦
    
    minimum-scale=1.0, maximum-scale=1.0 이 두 가지를 선언 한 것과 같은 기능이라 할 수 있습니다.


모바일 기기 중에는 메타 정보 중에 몇 가지는 지원하지 않을 수 있기 때문에, 호환성을 위해 중복된 기능을 담은 내용을 같이 넣어야함.

모바일 기기에서 페이지를 접근 시, 사용자가 원하는 대로 줌 인, 줌 아웃을 할 수 있도록 하는 게 좋다.

minimum-scale, maximum-scale, user-scalable : 이들 속성이 설정된 경우, 사용자가 뷰포트를 확대/축소할 수 없으므로 접근성에 문제가 생길 수 있다

하지만, 모바일 페이지의 경우 확대/축소 시 레이아웃 깨짐이 발생할 수 있기 때문에 이를 방지하고 접근성을 향상시키기 위해 꼭 글자 크기를 조절할 수 있는 옵션(js)을 만들어 주는 것이 좋다. (대부분의 확대/축소는 글자를 보기 위함) 

!Note
{: .label .mt-3}
<div class="code-example" markdown="1">
구버전의 브라우저가 올바로 속성을 파싱할 수 있도록, 쉼표를 사용하여 해당 속성을 구분합니다.
</div>

[참조 페이지](https://developers.google.com/web/fundamentals/design-and-ux/responsive/?hl=ko)
