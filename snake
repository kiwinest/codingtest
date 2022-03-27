#뱀
from collections import deque

n=int(input())
board=[[False]*n for _ in range(n)]
for _ in range(int(input())):
    y,x=map(int,input().split())
    board[n-y][x-1]=True

turn=deque()
for _ in range(int(input())):
    x,c=map(str,input().split())
    x=int(x)
    turn.append((x,c))
    
x=0
y=n-1
go='right'
sec=0
snake=deque()
snake.append((0,n-1))
while(1):
    #시간 증가
    sec+=1
    
    #이동
    if go=='right':
        x+=1
    elif go=='left':
        x-=1
    elif go=='up':
        y+=1    
    elif go=='down':
        y-=1
    snake.append((x,y))

    
    #부딪히는 조건
    if snake[-1] in list(snake)[:-1]: #자기 몸에 부딪히거나
        print(sec)
        break
        
    #사과의 유무
    nx,ny=snake[-1]
    if 0<=nx<n and 0<=ny<n:
        if board[ny][nx]: #사과가 있다면
            board[ny][nx]=False #먹고
        else: #사과가 없다면
            snake.popleft() #꼬리자르기
    else: #벽에 부딪히면 종료
        print(sec)
        break
        

   

    #x초가 지난 뒤에 방향전환
    if turn:
        if turn[0][0]==sec:
            s,c=turn.popleft()

            if go=='right' and c=='L':
                go='up'
            elif go=='right' and c=='D':
                go='down'
            elif go=='left' and c=='L':
                go='down'
            elif go=='left' and c=='D':
                go='up'
            elif go=='up' and c=='L':
                go='left'
            elif go=='up' and c=='D':
                go='right'
            elif go=='down' and c=='L':
                go='right'
            elif go=='down' and c=='D':
                go='left'
    
    
