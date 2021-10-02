---
layout: post
current: post
cover:  assets/built/images/friends4block.png
navigation: True
title: [Lv2] 2018 카카오 코딩테스트 '프렌즈4블록' 문제 해설
date: 2021-09-30 16:40:00
tags: [algorithm]
class: post-template
subclass: 'post tag-python'
author: crosstar
---

{% include algorithm-table-of-contents.html %}


[문제 풀기](https://programmers.co.kr/learn/courses/30/lessons/17679)


# 풀이
1. list element의 용이한 삭제를 위해, 행과 열을 전치한 후 시작
2. 블록이 터져야 할 부분은 index를 set에 저장(중복 방지) 후 0으로 변경
3. 0 개수를 count한 후, 앞(위쪽)으로 재배치. '_'로 변경 후 2번 과정 반복
4. answer에 loop: now_count개수를 더해주다가,loop 안에서 0 개수를 count한 결과가 0개일 경우, return




> Keypoint
> 1. set을 이용해 중복 방지
> 2. Transpose해서 진행
> 3. 0 개수 count를 위한, '_'로의 치환

~~~javascript
## 세팅

m = 4
n = 5
board = ["CCBDE", "AAADE", "AAABF", "CCBBF"]


def del4block(m,n,board):

    now_count=0
    # 중복방지 setlist
    pop_set=set()
  
    for i in range(n-1):
        for j in range(m-1):
            if board[i][j]==board[i+1][j]==board[i][j+1]==board[i+1][j+1] and board[i][j]!='_':
                pop_set |= set([(i,j), (i+1,j), (i,j+1), (i+1,j+1)]) # 터질 부분 indexing 
    # print(pop_set)  

    for i,j in pop_set:
        board[i][j] = 0 # 0으로 만들기

    for i,row in enumerate(board):
        cnt = row.count(0) # 0 개수 세기
      now_count+=cnt# now_count에 더하기
        board[i]=cnt*['_']+ [b for b in row if b!=0] # 앞으로 당기기 및 _ 로 치환하기(개수세기 위함)
    # print(board)
    return board,now_count

def solution(m, n, board):
    answer = 0
    board = [list(row) for row in board] # 알파벳 분리
    board = list(map(list,zip(*board))) # 전치
    while True:
        boardnow_count=del4block(m,n,board)
        if now_count==0: # 더이상 터질 게 없다면
            return answer 
            break;
        answer+=now_count # answer에 loop마다 now_count 더하기
~~~

# 실행 결과
~~~javascript
solution(m,n,board)
>>> 14
~~~
# 14개의 블록이 터진다 펑!

{% gist crosstar1228/e42e3d241997ab6b3c85dc6a3ae242c6 %}