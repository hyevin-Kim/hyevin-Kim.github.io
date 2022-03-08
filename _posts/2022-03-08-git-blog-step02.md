---
bg: "./gitblog/basic.jpeg"
layout: post
title: "[git blog]step02 - utterances으로 댓글 기능 만들기"
crawlertitle: "[git blog]step02"
date: 2022-03-08
summary: "댓글 기능 수난기"
category: "git-blog"
tags: [git blog]
author: vvney
---

# utterances란?
> 공식 홈페이지<br>
    [utterances](https://utteranc.es/)

utterances는 깃허브의 이슈기능을 가지고 댓글을 생성해준다고 합니다.<br>
게시글 하나가 이슈 하나와 한 쌍이 되고, 게시글에 댓글을 달면 해당 이슈에 댓글이 달립니다.<br>
댓글 창은 iframe으로 동작하며 해당 페이지가 로드 될 때, 페이지의 URL, pathname, 혹은 title을 가지고 issue search API를 통해 해당 이슈에 달린 댓글을 로딩하여 댓글 창에 로딩시켜준다고 합니다!  
<br>

# utterances 장점!
>1. 댓글 알림을 받을 수 있습니다.  
 -github issues를 댓글 쓰레드로 사용하는 utterances는 댓글이 등록되면,  
 새로운 issue가 등록된 것이므로 메일 알림을 받을 수 있습니다.<br>
>2. 설치 및 설정이 쉽습니다.  
-utterances앱을 깃허브 계정에 추가, 댓글 저장 용도로 사용될 신규 레포지토리에 권한을 주면 됩니다.  
-이후 댓글 영역에 스크립트 코드 한 줄만 추가해주면 셋팅이 끝납니다.
>3. Markdown 문법을 이용하여 댓글 작성이 가능합니다.  
-github 플랫폼 이용으로 마크다운 문법 사용이 가능합니다.  

<br>

# utterances 적용!
참고한 블로그 [공부하는 식빵맘](https://ansohxxn.github.io/blog/utterances/)님
#### 1. 댓글 Issue가 올라올 저장소를 정하거나 혹은 생성합니다.
#### 2. utterance 를 Install 설치 합니다.
#### 3. 설치 후 페이지에서 설정해줍니다.
사진 참고
참고한 블로그에서는 코드를 사용하지 않아도 되지만, 제가 사용하는 테마는 없기때문에  
코드를 사용해서 만들어봅니다!
#### 4. 포스트 아래 댓글 생성기
##### 4-1. _includes > my-comments.html
~~~html
<aside class="comments" role="complementary">
    <h2>Comments</h2>
    <hr/>
    #복사한 코드는 여기에 붙여넣어주세요.
    <script src="https://utteranc.es/client.js"
        repo="vveny/-comments"
        issue-term="pathname"
        theme="github-light"
        crossorigin="anonymous"
        async>
    </script>
</aside>
~~~
