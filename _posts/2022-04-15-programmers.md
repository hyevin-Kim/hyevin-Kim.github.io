---
bg: "./programmers/basic.png"
layout: post
title: "[programmers]level 1 - 핸드폰 번호 가리기"
crawlertitle: "level 1 - 핸드폰 번호 가리기"
date: 2022-04-15
summary: "level 1 - 핸드폰 번호 가리기"
category: "programmers"
tags: [programmers, 문제풀이, 코딩테스트]
author: vvney
---
### 문제
> 마지막 4자리 제외 모든 입력 문자열을 *로 대체하세요.

로 해석했습니다.

### 해결순서
1. 먼저 뽑을 수 있는 숫자 변수를 선언했습니다.
2. 폰켓몬 종류 수를 알아야하기때문에 중복 없이 새로운 배열에 담았습니다.
3. 종류가 가져갈 수 있는 수보다 많을 때, 가져갈 수 있는 수가 종류보다 많을 때, 둘이 동일할 때를 구분해서 return해주었습니다.


### 제출코드
<details>
<summary>펼치기</summary>
<div markdown="1">
~~~java
String answer = "";

        //length()로 문자열 개수를 확인 후 마지막 4자리 제외한 숫자를 index 선언
        int index= phone_number.length()-4;

        //4자리 전까지 * 변환
        for(int i= 0; i < index; i++){
            answer += "*";
        }

        //마지막 4자리 추출해서 값 추가
        //substring(시작값,끝값)
        answer += phone_number.substring(index, phone_number.length());
~~~