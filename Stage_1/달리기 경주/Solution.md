```python
def solution(players, callings):
    player_dict = {player: idx for idx, player in enumerate(players)}
    
    for call in callings:
        idx = player_dict[call]
        
        players[idx], players[idx-1] = players[idx-1], players[idx]
        
        player_dict[players[idx]] = idx
        player_dict[players[idx-1]] = idx-1
    
    return players
```
<hr>

처음에는 Swap을 이용해서 단순히 callings에서 부른 선수의 인덱스와 앞선 선수의 인덱스를 바꾸는 형식으로 문제를 접근했는데 시간초과가 나왔다.

그래서 검색을 해본 결과 딕셔너리를 이용해 시간 복잡도를 줄이는 방법이 있었다. 기존의 방법은 순차 검색을 하기 때문에 해당 선수의 인덱스를 찾는 과정의 시간 복잡도는 O(n)이므로 상당히 비효율적이다. 하지만 위 방법처럼 딕셔너리를 통해 선수와 그 인덱스를 저장해놓으면 선수의 인덱스를 찾는 시간 복잡도는 O(1)이 되므로 아까보다 훨씬 빠르다.

문제를 푸는 방법은 내가 처음에 했던 것과 다를 바가 없지만, 인덱스를 검색하는 방식에 따라 시간 복잡도가 달라져서 오답이 나왔던 문제였다. 시간 복잡도라는 개념에 대해 큰 인사이트를 얻을 수 있었던 좋은 문제였다.