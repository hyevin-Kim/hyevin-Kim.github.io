---
bg: "./gitblog/basic.jpeg"
layout: post
title: "[git blog]step02 - utterances으로 댓글 기능 만들기"
crawlertitle: "[git blog]step02"
date: 2022-03-08
summary: "댓글 기능 수난기"
category: "git blog"
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
적용하는 방법으로 참고한 블로그는 [공부하는 식빵맘](https://ansohxxn.github.io/blog/utterances/)님입니다!
<br><br>

#### 1. 댓글 Issue가 올라올 저장소를 정하거나 혹은 생성합니다.  

#### 2. utterance 를 Install 설치 합니다.
<https://github.com/apps/utterances> 사이트로 이동 후 설치합니다.  
![00](/assets/images/gitblog/22-03-08/00.png){: width="400" height="400"}
위 사진처럼 설정하고 request 눌러줍니다.<br>

#### 3. reques 후 페이지에서 설정해줍니다.
설치가 된 후 페이지에서 configuration부분을 찾아줍니다. 
![01](/assets/images/gitblog/22-03-08/01.png)

**repo: 댓글 Issue가 올라올 곳으로 선택한 저장소의 permalink를 작성합니다.(github아이디/저장소이름)
ex)vveny/-comments** <br>
![02](/assets/images/gitblog/22-03-08/02.png)
Blog post <–> Issue: 매핑 방식을 선택
1. pathname  
포스트의 pathname으로 이슈를 생성합니다.  
이 경우 /blog/2020/12/18/utterances- 적용으로 이슈가 생성되어 매핑된다고합니다.  
![03](/assets/images/gitblog/22-03-08/03.png)
Theme: 테마 중 자신의 블로그 테마와 어울리는 것으로 선택합니다.  
아래 코드: 복사합니다.

#### 4. 복사 코드
참고한 블로그에서는 이미 _config.yml부분에 있어서 설정만 해주셨지만...  
제가 선택한 테마는 없어서 따로 넣어주었습니다.  
<br>

붙여넣을 코드  
~~~markdown
<!--댓글기능 첨부-->
  <div>
    <h3>🙌COMMENTS</h3>
    <!--이곳에 자신이 복사한 코드를 붙여주면 됩니다!-->
    <script src="https://utteranc.es/client.js"
        repo="vveny/-comments"
        issue-term="pathname"
        theme="github-light"
        crossorigin="anonymous"
        async>
    </script>
  </div>
~~~  

_layouts폴더 중 post.html에 들어갑니다.  
![04](/assets/images/gitblog/22-03-08/04.png){: width="400" height="400"}
<br>

아래 사진처럼 댓글이 들어가면 좋을 곳에 붙여줍니다.
저는 포스트 옆으로 이동하는 것 이후에 넣어주었습니다!
![05](/assets/images/gitblog/22-03-08/05.png)

git에 commit 및 push합니다!  
이러면 아래에 보이는 것처럼 완성됐습니다!