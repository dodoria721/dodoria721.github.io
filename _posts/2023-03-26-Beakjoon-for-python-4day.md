---
layout: post
toc: true
title: 문자열 반복
categories: study
tags: [Python]
author:
  - Kim Dowon
---

백준 파이썬 4일차

## 백준 2675번 문자열 반복 

```
T = int(input())

for i in range(T):
    R, S = input().split()
    input_x = list(S)
    P = ''

    for j in range(len(input_x)):
        input_x[j] = input_x[j] * int(R)
        P += input_x[j]

    print(P)
```

## 문제 해석

문자열 S를 입력받은 후에, 각 문자를 R 번 반복해 새 문자열 P를 만든 후 출력하는 프로그램을 작성하는 문제이다.   
좀 더 간단하게 할 수 있었을 지도 모르지만 내 수준에 있어서 최선의 코드였다고 자부한다.   
   
문제에서 원하는 것은 첫째 줄에 테스트 케이스의 개수가 주어지는 것이므로 T를 변수로 해서 T 만큼 반복문이 수행 되도록 했다.   
   
바깥쪽 반복문에서는 R(반복 횟수), S(문자열)를 입력받은 후에 S(문자열)을 리스트 자료형으로 바꿨다.   
만약 `S = ABC` 라면 `list(S) = ['A', 'B', 'C']` 로 바뀐다.   
리스트는 인덱스로 접근 가능하기 때문에 for 문 이랑 쓰기 좋을 것 같아서 번거롭지만 이 과정을 거쳤다.   

안쪽 반복문에서는 R 만큼 반복된 문자를 앞서 만든 리스트에 넣은 후 그 문자를 다시 하나로 합치는 일을 수행한다.   
   
마지막에는 열심히 만들었던 새로운 문자열을 출력해주면 완성   

### for 와 range()

우선 `for`는 흔히 알고 있듯이 우리가 원하는 행동을 반복 해준다.

```
for 카운터 변수 in range(반복횟수):
	반복해서 실행할 명령
  
for x in range(5):
  print(x)
  
--> 1,2,3,4
```

`for 반복문`은 이런 식으로 구성된다. 

또한 반복문은 연속된 숫자(정수)를 만들어주는 `range()` 함수와 자주 쓰인다.

```
range(start, stop, step)
※start, step 은 생략 가능. 자동적으로 start = 0, step = 1로 해준다.

range(1, 11)
--> 1,2,3,4,5,6,7,8,9,10

range(0,10,2)
--> 0,2,4,6,8
```

`range(start, stop, step)` start 부터 시작해서 stop-1 까지 step 만큼 이동시켜 정수를 만들어 주는 함수이다.
