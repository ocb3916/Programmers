```python
def solution(k, m, score):
    answer = 0
    packagingCount = len(score) // m
    score.sort()
    
    while(packagingCount):
        temp = 0
        for i in range(m):
            temp = score.pop()
        answer += temp * m
        packagingCount += -1
    
    return answer
```
<hr>

최대한 높은 수를 한 상자안에 넣어야 최대 이익을 얻을 수 있으므로 그리드 알고리즘을 사용하면 된다고 판단했다. 받는 리스트를 오름차순으로 정렬하고 pop()을 이용해 조건에 맞게끔 상자를 만들어 최대 이익을 얻어냈다.

그런데 다른 사람의 풀이를 보니 리스트를 정렬하고 슬라이싱 [len(score)%m::m]을 이용했더라면 더 빠르고 최적화된 코드를 작성할 수 있었겠다는 생각이 들었다.