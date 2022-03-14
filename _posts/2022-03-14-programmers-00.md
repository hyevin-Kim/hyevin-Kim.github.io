---
bg: "./programmers/basic.png"
layout: post
title: "[programmers]level 1 - 폰켓몬"
crawlertitle: "level 1 - 폰켓몬 문제풀이"
date: 2022-03-14
summary: "level 1 - 폰켓몬"
category: "programmers"
tags: [programmers, 문제풀이, 코딩테스트]
author: vvney
---
### 문제
> N마리 폰켓몬의 종류 번호가 담긴 배열 nums가 매개변수로 주어질 때, N/2마리의 폰켓몬을 선택하는 방법 중, 가장 많은 종류의 폰켓몬을 선택하는 방법을 찾으세요.  

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
int[] test = new int[nums.length]; //폰켓몬 종류별로 담을 배열선언 
int select = nums.length / 2; //뽑을 수 있는 수 선언 
int answer = 0; //최종적으로 리턴 될 값 
        
//폰켓몬 종류 담기
for(int i= 0; i < nums.length; i++) {
    int check = 0;
    //중복제거 for문 
	for(int j= 0; j < i; j++) { 
        if(test[j] == nums[i]) { //동일한 값이 있다면
            check = 1;
            break;
        }
	}
    if(check == 1)//동일한 값이 있다면 넣지 않고 다음 배열 확인 
		continue;
        test[i] = nums[i]; //동일 값이 없다면 test배열에 추가 
	}
	
    //종류 수 체크 
	for(int i= 0; i < test.length; i++) {
        if(test[i] != 0)
            answer++;
	}
    
    //종류가 보다 뽑는 수가 적다면 뽑는 수 리턴
    if(select < answer)
        return select;
	else// 이외엔 종류 리턴
		return answer;
~~~