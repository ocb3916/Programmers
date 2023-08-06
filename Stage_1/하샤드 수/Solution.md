```python
def solution(x):
    answer = True
    
    isHarshad = sum(list(map(int, str(x))))
    
    if x % isHarshad != 0:
        answer = False
    
    return answer
```
<hr>
<p>스트링 타입은 리스트처럼 사용할 수 있다는 것을 이용해 입력을 스트링으로 변환하고 map 함수를 이용해 리스트 요소들을 int로 다시 변환한 후 하샤드 수 조건에 부합하는지 확인하는 과정을 거쳐 정답을 도출한다.</p>
