---
title : "[C++] 키패드 누르기 ⭐"
excerpt: "프로그래머스 [카카오 인턴] 키패드 누르기 난이도 : ⭐"

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

# 프로그래머스 [카카오 인턴] 키패드 누르기 
난이도 : ⭐ 

## ⛄ 문제
![image](D:\github\vscode\dozzs.github.io\assets\images\키패드.png)

## ☃ 내 풀이 
```c++
#include <string>
#include <vector>
#include <cmath>

using namespace std;

string solution(vector<int> numbers, string hand) {
    string answer = "";

    int leftHand = 10, rightHand =12, leftDist = 0, rightDist = 0;

    for(int i=0; i< numbers.size(); i++){
        if(numbers[i] == 1|| numbers[i] == 4||numbers[i] == 7){
            answer += "L";
            leftHand = numbers[i];
        }
        else if(numbers[i] == 3||numbers[i] == 6||numbers[i] == 9){
            answer +="R";
            rightHand = numbers[i];
        }
        else{
            if(numbers[i]==0) numbers[i]=11;
            int tmp_l = abs(leftHand - numbers[i]);
            int tmp_r = abs(rightHand - numbers[i]);
            
            leftDist = (tmp_l/3)+(tmp_l%3);
            rightDist = (tmp_r/3) + (tmp_r%3);
            
            if(leftDist == rightDist){
                if(hand == "right"){
                    answer +="R";
                    rightHand=numbers[i];
                }
                else{
                    answer += "L";
                    leftHand = numbers[i];
                }
            }
            else if(leftDist < rightDist){
                answer+="L";
                leftHand = numbers[i];
            }
            else{
                answer += "R";
                rightHand = numbers[i];
            }
        }
    }
    return answer;
}
```