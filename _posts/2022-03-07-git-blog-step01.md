---
bg: "./gitblog/basic.jpeg"
layout: post
title: "[git blog]step01 - 내가 기억하려고 작성한 마크다운 문법!"
crawlertitle: "[git blog]step01"
date: 2022-03-07
summary: "검색하기 귀찮아서 모아놓은 자주 사용하는 마크다운 문법?"
category: "git blog"
tags: [git blog]
author: vvney
---
## 마크다운 문법

지금 위에서 설명한것만으로 벌써 마크다운의 문법을 사용하였다.  
사용한것부터 시작하여 마크다운 문법을 봐보자.


### 1. 헤더
~~~
# this is a h1
## this is a h2 
### this is a h3 
#### this is a h4 
##### this is a h5 
###### this is a h6
~~~

### 2. 코드블럭

1. ```<pre><code>```
2. <code>```</code> 또는 <code>~~~</code>
3. 들여쓰기
4. 언어별 코드블럭 

#### 2.2 ```<pre><code>```
~~~
<pre>
<code>
def func(a,b):
    return a+b

print(func(2,3))
</code>
</pre>
~~~

#### 2.3 들여쓰기
탭이나 스페이스 4번을 통해 코드블럭을 만들수 있다.

~~~
    def func(a,b):
        return a+b

    print(func(2,3))
~~~

#### 2.4 언어별 코드블럭
개인적으로 편리하다고 생각합니다.<br>
python 사용방법
<pre>
<code>
~~~python
def func(a,b):
    return a+b

print(func(a,b))
~~~
</code>
</pre>

~~~python
def func(a,b):
    return a+b

print(func(a,b))
~~~

- **그밖에 언어들**  
    - Bash (bash)
    - C# (cs)
    - CSS (css)
    - Diff (diff)
    - HTML, XML (html)
    - Ini (ini)
    - JSON (json)
    - Java (java)
    - JavaScript (javascript)
    - PHP (php)
    - Perl (perl)
    - Python (python)
    - Ruby (ruby)
    - SQL (sql)

### 3. BlockQuote(인용문)

~~~
> This is a first blockquote
~~~



~~~
>> This is a second blockquote
~~~



~~~
>>> This is a third blockquote
~~~

#### blockquote 안에 다른 마크다운 요소를 포함 가능

~~~
> ## This is a h3
> * list1
> * list2
>   ~~~
>   code
>   ~~~
~~~


### 4. 글머리 기호

~~~
+ 글머리
  + 글머리2
    + 글머리3
      + 글머리 4
~~~

### 5. 강조 

~~~
*single asterisks*  
_single underscores_  
**double asterisks**  
__double underscores__  
~~cancelline~~  
~~~

### 6. 기호표시

Markdown에서 이미 사용되는 기호 표기하기

Markdown 문법에 사용되는 기호를 있는 그대로 표시하고 싶을 경우가 있습니다.<br>
예를 들어 \#을 기호 그대로 사용하고 싶지만 그냥 쓰면 H1 헤더로 출력합니다.<br> 
그런 기호들입니다.

~~~
\   backslash
*   asterisk
_   underscore
{}  curly braces
[]  square brackets
()  parentheses
#   hash mark
+   plus sign
-   minus sign (hyphen)
.   dot
!   exclamation mark
~~~

이런것들을 사용하고 싶다면 기호앞에 \(=back slash)를 사용하면됩니다.


### 7. 수평선
~~~
* * *

***

*****

----

- - -
~~~

### 8. 링크 
- 외부 링크   
[링크 키워드]\(링크 url)
~~~ex)
[내 블로그](https://vveny.github.io)
~~~

- 자동 링크  
~~~html
    <https://vveny.github.io>
~~~


### 9. 이미지 

~~~html
![그림1](/assets/images/gitblog/22-03-07/01.jpeg)
![그림2](/assets/images/gitblog/22-03-07/01.jpeg){: width="400" height="400"}
~~~

### 10. 줄바꿈


#### 1. ```<br>``` 사용 

~~~
줄 바꿈시 사용 <br>
줄 바꿈시 사용
~~~

#### 2. Enter 2번 

~~~
줄 바꿈시 사용  


줄 바꿈시 사용
~~~

#### 3. 스페이스바 2번 

### 11. 표

~~~
| ------ | NumPy | PyTorch |
| ------ | -------- | ---------- |
| 선언 | np.array() | torch.FloatTensor, <br/> torch.Tensor()|
| 차원 확인 | .ndim | .dim()|
| 크기 확인 | .shape | .size()|
~~~

| ------ | NumPy | PyTorch |
| ------ | -------- | ---------- |
| 선언 | np.array() | torch.FloatTensor, <br/> torch.Tensor()|
| 차원 확인 | .ndim | .dim()|
| 크기 확인 | .shape | .size()|


### 12. Expander control 

마크다운에서 접기/펼치기 가능한 컨트롤 문법  
마크다운 자체에는 기능이 없고 html을 이용 --> html의 details 사용

#### 1. 
~~~html
<details>
<summary>접기/펼치기 버튼</summary>
<div markdown="1">

|제목|내용|
|--|--|
|1|1|
|2|10|

</div>
</details>
~~~

<details>
<summary>접기/펼치기 버튼</summary>
<div markdown="1">

|제목|내용|
|--|--|
|1|1|
|2|10|

</div>
</details>

#### 2. 
~~~html
<details>
<blockquote>
    숨김숨김
</blockquote>
</details>
~~~

<details>
<blockquote>
    숨김숨김
</blockquote>
</details>
