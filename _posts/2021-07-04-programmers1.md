---
title : "[C++] 두 정수 사이의 합 ⭐"
excerpt: "프로그래머스 두 정수 사이의 합 | 난이도 : ⭐"

categories:
 - Programmers
tags:
 - [ Programmers, Coding Test, C++ ]

toc: true
toc_sticky: false

date: 2021-07-04
last_modified_at: 2021-07-04
mainfont: Bareun_hipi
---

## 🍦 [프로그래머스 두 정수 사이의 합](https://programmers.co.kr/learn/courses/30/lessons/12912) 
난이도 : ⭐ 

## ⛄ 문제
![image](\assets\images\pr1.png)

## ☃️ 내 풀이 
```c++
#include <string>
#include <vector>
#include <iostream>
using namespace std;

long long solution(int a, int b) {
    int i;
    long long answer = 0;
    if (b > a) {
        for (i = a; i <= b; i++) {
            answer = i + answer;
        }
    }
   if (a == b)answer = a;

   if (a > b) {
       for (i = b; i <= a; i++) {
           answer = i + answer;
       }
   }
    return answer;
}

int main() {
    int a, b;

    cin >> a;
    cin >> b;
    solution(a, b);
}
```