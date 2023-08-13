```python
import collections

def solution(participant, completion):
    answer = ''
    result = collections.Counter(participant) - collections.Counter(completion)
    answer = list(result)[0]
    return answer
```
<hr>

처음에는 참가자 목록을 for문으로 돌려 완주자와 비교해서 있으면 완주자 목록에서 소거하고 다음 요소와 비교하는 방식으로 하려고 했으나 예상대로 효율성 테스트를 통과하지 못했다.
그래서 집합으로 바꿔서 차집합을 구해볼까 했는데 참가자 중에는 동명이인이 있을 수 있다는 조건 때문에 이것도 사용하지 못했다.
1시간 정도 검색을 해봤지만 모르겠어서 정답을 찾아봤는데 collections 모듈에 Counter라는 메소드를 사용하면 리스트에서 요소들이 몇 번씩 사용되었는지 딕셔너리로 반환할 수 있었다.
문제 조건에 의해 완주하지 못한 사람은 1명 밖에 없으므로 두 딕셔너리를 뺄셈하여 리스트로 변환해 첫 번째 인덱스를 출력하여 정답을 구했다.

<hr>

이렇게 푸는 방법도 있지만 Hash를 이용해 푸는 풀이도 있었는데, Hash를 아직 잘 몰라 이해하기 어려웠다. Hash에 대한 추가 학습이 필요할 것 같다.