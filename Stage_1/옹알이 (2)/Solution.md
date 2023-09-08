```python
def solution(babbling):
    answer = 0
    can = ['aya', 'ye', 'woo', 'ma']
    
    for b in babbling:
        for c in can:
            if c * 2 not in b:
                b = b.replace(c, ' ')
        if b.isspace():
            answer += 1
    
    return answer
```
<hr>

###### 몰라서 풀이 검색했음

##### 문제 포인트
* 발음 할 수 있는 단어가 포함되어 있는지 확인할 수 있어야 한다.
* 조건에 따라 발음 할 수 있는 단어가 연속되지 않는지 확인해야 한다.

##### 풀이
* babbling과 can에서 단어를 가져와 비교해서 조건에 맞는 부분을 소거한다.
* 최종적으로 '' 공백이 된다면 해당 단어는 발음할 수 있는 단어가 된다.
* babbling에서 b를 can에서 c를 가져와 c가 두번 반복되지 않는다면 c를 소거한다.
* 소거할 때 '' 대신 ' '를 이용하여 'yayae'처럼 발음할 수 없는 단어를 발음할 수 있다고 오판하지 않도록 방지한다.