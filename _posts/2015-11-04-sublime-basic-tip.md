---
layout: entry
title: "Sublime Text 빠르게 적응하기"
author: jessica
author-email: jessica@spoqa.com
description: Sublime Text 초보 사용자를 위한 팁을 공유합니다.
publish: true
---

오늘은 제가 Sublime Text를 사용하면서 자주 썼고 유용하다고 생각되었던 것들을 몇 가지 공유해보려고 합니다. 이 포스트를 통해 Sublime Text를 처음 접하시는 분들은 지난 포스트를 먼저 읽으시길 추천드립니다.

[관련 글 - SublimeText 시작하기](http://spoqa.github.io/2015/11/11/install-sublime-text.html)


## Syntax 구분으로 코드 가독성 높이기 

Sublime Text에는 다른 코드작성용 텍스트 에디터와 마찬가지로 언어 구조에 맞게 색상이 자동으로 입혀지는 Syntax Highlighting 기능을 제공하고 있습니다. 

<figure>
<img src="/images/2015-11-04/plain-text.png"
     style="margin-right:auto; margin-left:auto;" />
<figcaption>
    (위) syntax highlight 미적용
</figcaption>
</figure>

<figure>
<img src="/images/2015-11-04/html-extension.png"
     style="margin-right:auto; margin-left:auto;" />
<figcaption>
    (위) syntax highlight 적용
</figcaption>
</figure>

이 기능은 문법 구조 별로 다른 색상이 적용되고 그 색상의 대비가 크기 때문에 코드의 구조와 문법적 오류를 빠르게 파악할 수 있습니다. 실제로 코드 상의 오류를 찾는데 걸리는 시간을 줄여준다는 연구도 있습니다.[^1] Syntax highlighting로 인해 텍스트의 의미나 기능이 달라지는 것은 아니며 이것은 오로지 사람이 읽을 때의 편의성을 위한 장치입니다. 이 때 사용되는 컬러는 텍스트 에디터/테마 설정/사용자 설정에 따라 바뀔 수 있습니다.

### 1.Extension 설정 확인하기

우선 SublimeText 하단 우측(분홍색으로 표시된 부분)에 현재 쓰고 있는 파일 형식과 동일한 Extension이 설정되어 있는지 확인하세요.
<img src="/images/2015-11-04/extension-location.png" /> 

만약 기본값인 Plain text로 되어 있거나 다른 Extension으로 되어 있다면 알맞은 언어를 선택하여 알맞게 highlight되도록 하면 됩니다.
<img src="/images/2015-11-04/extension.png" />     

### 2.Package Control 설치하기

만약 기본 Extension에서 제공해주지 않는 언어라면 어떻게 해야할까요? 추가적으로 HTML과 CSS를 도와주는 보조 언어/라이브러리를 설치하여 작성하다보면 HTML나 CSS는 언어 구조에 따라 자동으로 컬러가 입혀져 입는 반면에 보조 언어로 쓰여진 부분은 아래 그림처럼 highlighting이 되어 있지 않습니다.
<figure>
<img src="/images/2015-11-04/just-html.png"
     style="margin-right:auto; margin-left:auto;" />
<figcaption>
(위) html 언어 사이에 html가 아닌 언어가 섞여 있다.
</figcaption>
</figure>

이것은 지정된 기존의 언어와 다르기 때문에 생기는 현상입니다. 이 경우에는 syntax highlighting을 도와주는 일종의 플러그인이라고 할 수 있는 Package Control을 설치하면 됩니다. 

<figure>
<img src="/images/2015-11-04/jinja-syntax.png"
     style="margin-right:auto; margin-left:auto;" />
<figcaption>
(위) html뿐만 아니라 다른 언어(jinja)에도 syntax highlighting이 적용되었다.
</figcaption>
</figure>

만약 Sass에 대한 syntax highlighting이 필요하다면, `sublime text syntax highlighting for Sass` 등의 키워드로 검색하여 설치 방법을 쉽게 찾으실 수 있습니다. 지난 글에서 Material design 테마를 Package Control을 통해 설치하는 방법을 소개해드렸는데 따라해보셨다면 필요한 패키지를 어떻게 설치해야 하는지 감잡기 쉬우실 겁니다.


## 보는 방식으로 코드 가독성 높이기 

#### `view` - `word wrap column`

<img src="/images/2015-11-04/column-wrap.png"
     style="margin-right:auto; margin-left:auto;" />

간혹 살펴보아야할 코드가 가로로 꽤 길어서 가로 스크롤이 길어지는 경우가 있을 수 있습니다. 이를 한눈에 잘 볼 수 있도록 가상의 열을 만들어주는 기능으로, 코드에는 변화가 없습니다.


<figure>
<img src="/images/2015-11-04/auto.png"
     style="margin-right:auto; margin-left:auto;" />
<figcaption>
    (위) word wrap column - auto 적용시
</figcaption>
</figure>

<figure>
<img src="/images/2015-11-04/70.png"
     style="margin-right:auto; margin-left:auto;" />
<figcaption>
    (위) word wrap column - 70적용시
</figcaption>
</figure>

auto는 반응형으로 창 크기에 맞게 열 너비가 변화하지만 텍스트 커서를 키보드로만 움직일 때에는 스크롤이 움직이지 않도록 wrap column을 좁게하여  쓰는게 편할 수 있습니다. 
  

#### `view` - `layout`

<img src="/images/2015-11-04/layout-menu.png"
     style="margin-right:auto; margin-left:auto;" />

한번에 여러가지 문서 보면서 수정할 때 굉장히 유용한 기능입니다. 해상도에 따른 작업환경이나 멀티태스킹을 해야할 때 유용한데, 저는 `Columns:2`를 애용합니다. 진행하는 이슈 종류나 사용하는 언어에 따라 편한 레이아웃을 골라 사용하시면 됩니다. 

<figure>
<img src="/images/2015-11-04/columns2.png"
     style="margin-right:auto; margin-left:auto;" />
<figcaption>
    (위) Columns:2 적용시
</figcaption>
</figure>

<figure>
<img src="/images/2015-11-04/row3.png"
     style="margin-right:auto; margin-left:auto;" />
<figcaption>
    (위) Rows:3 적용시
</figcaption>
</figure>


## 고치고 싶은 부분 쉽게 찾기

웹뷰로 되어 있는 부분의 스타일을 수정하려고 할 때에는 보통 아래의 절차로 진행합니다.

1. 웹 브라우저에서 요소 검사(Inspect Element)하여 고치고 싶은 부분을 찾는다.
2. Sublime Text에서 고쳐야 하는 부분을 찾아 코드를 수정한다.

1과 2의 사이에서 내가 고치고 싶은 코드를 어떻게 하면 빠르게 찾을 수 있을지 처음에는 알기 어려울 수 있습니다. 이를 테면 어느 파일 몇 번째 줄에 있는지, 찾아야 하는 코드가 두 군데 이상에 적용되어 있을 때 등의 경우에 고민이 생기게 될 것입니다. Sublime Text의 `Find`메뉴에서 제공하는 여러가지 검색 기능으로 해결할 수 있습니다. 

<img src="/images/2015-11-04/sublimetext-find-menu.png"
     style="margin-right:auto; margin-left:auto;" />   

그 중 제가 굉장히 자주 썼던 검색 기능 몇 가지를 소개합니다. 


#### Find `⌘` + `F`

현재 보고 있는 파일 내에서 특정한 단어를 찾을 때 사용합니다.

<img src="/images/2015-11-04/find-example.png"
     style="margin-right:auto; margin-left:auto;" />   


#### Find in Files `⌘` + `shift` + `F`

Where에 쓰인 디렉토리 안에 있는 모든 파일에서 검색어가 있는 부분들을 검색합니다. 특정 부분이 어느 파일의 몇 번째 줄에 작성되어 있는지 모를 때 유용한 기능입니다. 검색어가 쓰여진 곳은 모두 검색 결과에 나오기 때문에 찾고자 여러 군데 쓰이는 단어보다는 찾고자하는 부분에만 쓰이는 클래스 이름 등을 작성하면 찾기가 더 쉽습니다.

<img src="/images/2015-11-04/findinfiles-0.png"
     style="margin-right:auto; margin-left:auto;" />   

1.찾고 싶은 검색어를 입력합니다. 저는 spoqa 폴더 내에서 `margin-left: auto;`가 써진 곳을 모두 찾고 싶다고 가정하고 써보았습니다.

<img src="/images/2015-11-04/findinfiles-1.png"
     style="margin-right:auto; margin-left:auto;" />   

2.그러면 Find Results 탭이 생기면서 검색 결과를 보여줍니다. 어떤 디렉토리의 어떤 파일에 몇 번째 줄에 검색어가 써져 있는지 쉽게 알 수 있습니다. 또한 파일이름 부분을 더블 클릭하면 바로 그 파일로 이동합니다.


#### Goto anything `⌘` + `P`

<img src="/images/2015-11-04/goto-anything.png"
     style="margin-right:auto; margin-left:auto;" />   

Sublime Text 3에서 제공하는 기능으로 특정한 파일이나 행(line)으로 이동할 때 사용합니다. 디렉토리를 뒤질 필요 없이 보고 싶은 파일 이름을 검색하여 빠르게 열 수 있습니다. 

폴더 채로 열려있는 상태라면 `⌘` + `T`도 동일한 역할을 하는데 이 기능은 현재 열려있는 탭 리스트 중에서만 선택하여 이동할 수 있습니다.


#### 특정한 행으로 이동하기  `Goto anything`에서 `:123`

<img src="/images/2015-11-04/goto-anything.png"
     style="margin-right:auto; margin-left:auto;" />   

긴 스크롤에 방해받지 않고 특정 행을 바로 보고 싶다면 이 기능도 유용합니다. 만약 123번째 줄로 이동하고 싶다면 Goto anything 기능을 키고 `:123`을 입력하면 됩니다. 


##

이 외에도 Sublime Text에는 많은 기능을 제공하고 있지만 이것들만 알아도 사용하는데 큰 무리가 없습니다. 더 다양한 기능을 알고 싶다면 메뉴를 구석구석 눌러보면서 직접 경험하거나 검색만 하더라도 무궁무진한 팁을 발견할 수 있습니다. 혹은 [sublimetexttips](http://sublimetexttips.com/) 같은 뉴스레터를 구독하는 것도 방법이겠지요.

짧은 글이지만 Sublime Text를 통해 코드에 입문하는 사람에게 도움이 되면 좋겠습니다. 다음에도 유용한 글로 찾아뵙겠습니다. 읽어주셔서 감사합니다!


---

[^1]: https://en.wikipedia.org/wiki/Syntax_highlighting
https://blog.generalassemb.ly/sublime-text-3-tips-tricks-shortcuts/