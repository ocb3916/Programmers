```python
def solution(a, b, n):
    answer = 0
    giveCola = a
    exchangeCola = b
    emptyCola = n
    
    while(emptyCola >= giveCola):
        myCola = emptyCola // giveCola * exchangeCola
        emptyCola = myCola + emptyCola % giveCola
        answer += myCola
        
    return answer
```
<hr>
<p>마트에 줘야하는 빈 병의 개수 a를 giveCola, a개 당 교환받을 수 있는 콜라의 개수 b를 exchangeCola, 내가 가진 처음 빈 병의 개수 n을 emptyCola로 표현했다.</p> 

<p>while문 안에 빈 병의 개수가 줘야하는 개수 이상일 때만 식을 반복하도록 조건을 걸어두었고, emptyCola // giveCola * exchangeCola = '내가 교환받은 콜라'이므로 myCola로 표현했다.</p>

<p>myCola는 곧 마셔서 빈 병이 되므로 다시 emptyCola는 myCola + emptyCola % giveCola가 된다. 여기서 emptyCola % giveCola는 myCola를 계산할 때의 emptyCola에서 세트가 되지 못한 남은 빈 병을 의미한다.</p>

<p>while문 조건에 맞게 반복하면서 myCola를 answer에 더해주면 n개의 빈 병으로 교환받을 수 있는 콜라의 개수를 구할 수 있다.</p>