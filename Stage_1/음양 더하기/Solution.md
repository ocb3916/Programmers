```python
def solution(absolutes, signs):
    answer = 0
    
    for i, j in zip(absolutes, signs):
        if j == True:
            answer += i
        else:
            answer += -i
    
    return answer
```
<hr>

zip 함수를 이용해 두 개의 길이가 같은 리스트를 함께 읽어서 조건에 맞게 계산을 수행함.