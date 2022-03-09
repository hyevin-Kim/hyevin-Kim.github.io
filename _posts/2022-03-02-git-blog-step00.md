---
bg: "./gitblog/basic.jpeg"
layout: post
title: "[git blog]step00 - 테마 Voyager 적용"
crawlertitle: "[git blog]step00"
date: 2022-03-02
summary: "테마 Voyager 적용기"
category: "git blog"
tags: [git blog]
author: vvney
---
# git blog를 시작하게 된 이유
원래 3월 전에 git blog를 만들고, 배운 것을 기록하려고 했으나...생각보다 만드는 것이 오래걸렸습니다.<br>
강의를 보면서 만드는 데도 다른 테마로 만들어서 "오류 -> 해결"의 반복을 겪다가 여기까지 왔습니다.<br>
시간이 생각보다 많이 걸렸고, 사실 지금도 마음에 쏙 들게 완성이 된 것은 아니지만...<br>
그래도 틀은 잡힌 것 같아서 지금부터 기록을 작성해보려고 합니다!<br>
테마 "Voyager"를 어떻게 변경했는지를 다루려고 하기 때문에<br>
github 레파지토리 만드는 것까지 작성하진 않았습니다😆
<br><br>

# jekyll? & 사용하는 이유
처음 git blog를 만드려고 했을 때 jekyll를 사용해서 만들어야 한다는 것을 알고..왜?<br>
라는 생각을 했고, 찾아봤습니다. <br>

> Jekyll은 Markdown 형식의 텍스트 파일을 HTML 파일로 변환해 주는 하나의 변환 도구

이처럼 Jekyll이 HTML 파일로 만들어 주니까 사용자는 블로그에 포스팅시 Markdown으로 작성하고<br>
나중에 Jekyll로 빌드해서 서버에 올리면 된다고합니다.

> 공식 홈페이지<br>
    [jekyll](https://jekyllrb.com/docs/)

<br><br>

# Homebrew, Ruby, gem 설치
~~~bash
# 1번
# Mac에서는 Homebrew로 패키지를 설치 및 관리하는 것이 좋다고 합니다!
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# 2번
# brew를 사용하여 rbenv라는 Ruby 버전 관리자를 설치합니다.
brew install rbenv

# 3번
# rbenv를 초기화 해준 후
rbenv init

# 4번
# 설치가 제대로 되었는지 확인합니다.
curl -fsSL https://github.com/rbenv/rbenv-installer/raw/main/bin/rbenv-doctor | bash

# 5번
# 전 강의를 보면서 해서 Ruby버전 2.7.2를 rbenv를 사용하여 설치해서 진행했습니다.
rbenv install 2.7.2

# 6번
# 2.7.4버전을 Main으로 고정한 뒤
rbenv global 2.7.2

# 7번
# 현재 실행 버전을 테스트합니다.
ruby -v

# 마지막으로 이렇게 결과가 나왔을 때 다음으로 진행했습니다!
ruby 2.7.2
~~~
<br><br>

# 테마 선택 - Voyager
강의에서 선택한 사이트는 제 마음에 들지 않아서 새로운 사이트를 찾아봤고, 이 테마 말고<br>
2-3개 정도 다른 사이트로 설정해봤으나,,,무엇인가 오류가 나고, 적용이 되지 않아서..ㅜ<br>
아직까지 오류가 나지 않고 새롭게 바꾸는 것에도 적용이 잘 되고 있는 이 테마로 정착했습니다!<br>
아래 사이트에서 "Voyager"로 검색헤서 적용하면 됩니다!<br>
> [jekyll 테마 사이트](http://jekyllthemes.org/)

<br>
사실 다른 테마를 사용하셔도 "_config.yml"파일만 변경해주시면, 어렵지 않습니다!
<br><br>

# 테마 설정 변경
_config.yml 파일 설정부분!
~~~yml
# Site settings

# 블로그 타이틀 설정
title: vveny's blog
# 자신의 이메일 설정
email: viin99@naver.com
description: > # this means to ignore newlines until "baseurl:", 메타정보입니다.
    하루하루 공부한 내용을 정리하는 블로그입니다! java, Spring Boot, Back-end
# 아마 블로그 검색시 나오게 되는 정보인 것 같습니다만....아직 검색에 문제가 생겨...확실하진 않습니다ㅠ

# 아래 url과 같이 적거나 공백. 서브 경로가 있는 경우에만 적어줍니다.
baseurl: ''
# 언어 설정해줬습니다!
lang: 'ko'
# 자신의 깃블로그 주소를 적어줍니다.
url: 'https://vveny.github.io'
# 이부분은 트위터 있으시면 작성해주시면 됩니다! 저는 트위터는 없어서 주석 그대로 두었습니다.
# twitter_username:
# github에서 사용 중인 이름을 작성해줍니다.
github_username: vveny
# disqus_username:
~~~
위처럼 설정했습니다! 다른 부분들은 모르는 부분이라....그대로 두었습니다.<br>
혹여 다른 사항을 알게 되면 수정하겠습니다!
<br><br>

# 테마 적용 확인 방법
vscode로 진행했기에 프로그램을 열고, 자신의 블로그 root폴더로 가줍니다.<br>
![01](/assets/images/gitblog/22-03-02/01.png)
터미널을 열고 아래 명령어를 순서대로 입력해줍니다.<br>
~~~bash
# 1번
gem install bundler jekyll minima jekyll-feed tzinfo-data rdiscount

# 2번
bundle install

# 3번
bundle update

# 4번
bundle exec jekyll serve
~~~

#### 오류...
위의 방법대로 설치하다가 오류가 나서 푸른쿠우님 [블로그](https://choijaegwon.github.io/githubblog/GithubBlog1/)를 보면서 다시 설치했습니다ㅜ
무슨 오류인지는 다시 정리하겠습니다! 검색해도 찾기 힘들어서....많이 슬펐던...<br>
물론 아예 삭제하고 새로운 파일에다가 재설치하니 잘 작동했습니다! ^ㅁ^ <br>
설치를 잘못했던 건지 아니면 진짜 무슨 오류였던 건지는 새로운 파일에 다시 설치해보고 수정하겠습니다!!

<br>
3번 명령어 실행시 
> _plugins, _site, .jekyll-cache, .sass-cache

위의 파일이 생성되면 성공입니다!👏<br>
아래에 있는 사진처럼 다 나오는 건 아니고, 위의 파일들이 대략적으로 생성되면 됩니다!
<br>

![02](/assets/images/gitblog/22-03-02/02.png)
<br>
결과적으로 4번 명령어를 실행하게 되면 위 사진처럼 터미널에 나올 겁니다.<br>
그러면 링크 따라가기로 실행하시면 실시간으로 블로그를 보실 수 있습니다!<br>

