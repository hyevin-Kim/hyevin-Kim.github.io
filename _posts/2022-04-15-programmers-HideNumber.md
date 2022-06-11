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
1. 문자열 개수를 확인 후 마지막 4자리를 전까지의 숫자를 index로 선언 후
2. 4자리 전까지 *로 변환해서 answer에 저장했습니다.
3. 그 후 answer에 마지막 4자리 파싱해서 리턴해줍니다.


### 제출코드
<details>
<summary>펼치기</summary>
<div markdown="1">
~~~java
class Solution {
    public String solution(String phone_number) {
        String answer = "";

         //length()로 문자열 개수를 확인 후 마지막 4자리 제외한 숫자를 index 선언
        int index= phone_number.length()-4;

         //4자리 전까지 * 변환
        for(int i= 0; i < index; i++){
            answer += "*";
        }

        //마지막 4자리 추출해서 값 추가
        //substring(시작값,끝값)
        answer += (phone_number.substring(index, phone_number.length()));
        return answer;
    }
}
~~~

