```python
def solution(number, limit, power):
    answer = 0
    swordPower = []
    knight = list(range(1, number + 1))
    
    for i in knight:
        count = 0
        for j in range(1, int(i**0.5) + 1):
            if i % j == 0:
                count += 1
                if (j**2) != i:
                    count += 1
        swordPower.append(count)
        
    for i in range(len(swordPower)):
        if swordPower[i] > limit:
            swordPower[i] = power
            
    answer = sum(swordPower)
            
    
    return answer
```
<hr>
<h5>문제풀이</h5>

<p>처음 약수의 개수를 구하는 과정에서 <strong><span style="color:#14a492"> 1부터 입력된 숫자까지 하나씩 </span></strong> 올라가며 나누어 떨어지는 지를 검사하는 방식으로 약수를 구했는데, 이 때문에 시간복잡도가 올라 <strong><span style="color:#f13700"> 시간초과</span></strong>로 문제를 해결하지 못하였음.<br>구글링을 통해 약수를 구하는 효율적인 알고리즘에 대해 찾아보았고 우리가 약수를 구할 때 6 = 2 * 3 이런 식으로 구하면 한 번에 약수를 한 쌍 구할 수 있음. 따라서 <strong><span style="color:#14a492">for문에서 i를 n까지 아닌 n 제곱근까지 범위를 정하고 나머지 짝을 찾는 알고리즘을 사용</span></strong>하니 제한시간을 통과함.</p>