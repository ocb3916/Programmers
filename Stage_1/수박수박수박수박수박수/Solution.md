```python
import math
def solution(n):
    answer = ''
    repeat = math.ceil(n / 2)
    st = '수박' * repeat
    answer = st[:n]
    
    return answer
```
<hr>
<p>
처음에는 조건에 맞춰서 '수' '박' 하나하나 answer에 + 해줄 생각을 했는데 '너무 비효율적이다'라는 생각이 들었음. 그래서 그냥 n개 만큼 '수박'을 반복하고 n인덱스 까지 슬라이싱 하면 되겠다는 생각이 듬.
</p>

<p>
근데 n번 무작정 '수박'을 반복하고 슬라이싱하면 슬라이싱 하고자 하는 글자보다 2배 이상의 길이가 나옴. 따라서 n을 2로 나누고 올림하여 '수박'을 반복하고 슬라이싱해서 낭비되는 공간을 최대로 줄이고자 하였음.
</p>