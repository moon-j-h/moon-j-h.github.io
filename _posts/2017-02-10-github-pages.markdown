---
layout: post
title:  "Github Pages 설정"
subtitle : "깃허브 블로그 만드는 방법"
date:   2017-02-10 00:19:42 +0900
categories: githubpages
---

> ## Jekyll 생성

예전부터 생각했었다. 학교 과제든 개인 프로젝트이든 내가 작성한 코드 및 공부 내용을 정리해서 블로그에 올리고 싶다고... 
하지만 네이버는 다른 용도로 이미 블로그를 사용중이고(아니어도 네이버에 하진 않았을거 같지만...) 티스토리는 시도해 봤지만 별로 손이 안가고
구글 블로그도 마찬가지... 아 어디다 하지?? 라는 고민 몇 개월째하다 결국 여기로 정착하기로 정했다.

근데.. 엄청난 삽질을... 깃허브를 사용하기는 하지만 그렇게 익숙하지는 않고 깃허브 페이지는 또 처음 접해보고.. 
어제 하루 종일 날리고 이제 좀 감이 와서 한번 정리해 본다.

 깃허브 페이지를 사용하기 위해서는 `ruby` `jekyll` `python` `rouge` 가 필요하다.
 windows 에 저 4가지를 설치하는 방법은 [이곳][whatap-windows-jekyll]에서 참고했다.

위 4가지를 설치했으면 jekyll를 실행할 디렉토리로 가서 cmd를 연 후,

{% highlight text %}
jekyll new [Directory_Name]
{% endhighlight %}

를 입력하면 minima 테마의 jekyll 블로그 파일들이 생성된다.

생성된 디렉토리로 이동하여

{%highlight text %}
cd [Directory_Name]

jekyll serve
{% endhighlight %}
한 후 `localhost:4000`을 확인하면 jekyll가 잘 작동하는 지를 확인할 수 있다.

> ## Github Pages
> ### user page : [user_name].github.io

나중 추가...


> ### project page : [user_name].github.io/[repository_name]

`/[repository_name]` 에 블로그를 올리기 위해서는 두 가지 방법이 있다.
1. `master branch / docs 디렉토리`에 블로그 관련 파일 푸시
2. `gh-pages branch` or  `master branch` 에 블로그 관련 파일 푸시

나는 branch를 따로 만드는 것은 귀찮고 한 repository에 블로그 파일들과 실습파일을 푸시할 거기 때문에
1번째 방법을 사용했다.

사용할 디렉토리에 가서 `jekyll new docs`를 한 다음

{%highlight text %}
$ git init

$ git remote add origin [remote-repository-url]

$ git add .

$ git commit -m "commit message"

$ git push origin master
{% endhighlight %}

를 하고 `https://moon-j-h.github.io/[repository_name]`에 접속하려하면 아마 에러 날 것이다.

repository 의 `settings`의 `GitHub Pages`에 가서 `Source`를 `master branch /docs folder`로 수정해 주면
`https://moon-j-h.github.io/[repository_name]`에 접속할 수 있다



[whatap-windows-jekyll]: http://tech.whatap.io/2015/09/11/install-jekyll-on-windows/
