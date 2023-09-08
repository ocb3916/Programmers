```python
def solution(food):
    answer = ''
    
    for n, p in list(enumerate(food))[1:]:
        if p > 1:
            answer += f'{n}' * (p//2)
            
    answer += '0'
    
    for n, p in list(enumerate(food))[:0:-1]:
        if p > 1:
            answer += f'{n}' * (p//2)
    
    return answer
```
<hr>

##### 문제 포인트
* 음식을 두명이서 나눠 먹고 남은 은식은 버림
* 두 명은 양 끝에서 음식을 먹기 시작하고 칼로리가 낮은 순 부터 먹을 수 있도록 해야함
* 가운데에는 물이 있음

##### 풀이
* enumerate 함수로 리스트의 인덱스와 값을 불러옴
* 2명이서 똑같이 나눠 먹으므로 값이 1인 음식은 버리고 그보다 큰 음식은 2로 나눠 그 몫을 배열함
* 가운데에 0을 넣고 리스트를 거꾸로 다시 읽어서 반대편 선수가 먹을 음식을 배열함

> 야매로 풀었음 굳이 for문을 두 번 돌릴게 아니라 한 번만 하고 answer + '0' + answer[::-1] 을 return 하면 됨