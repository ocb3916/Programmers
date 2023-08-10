```python
def solution(n, arr1, arr2):
    answer = []
    temp = []
    
    for i, j in zip(arr1, arr2):
        temp.append(format(i | j, 'b').zfill(n))
        
    for i in temp:
        temp  = i.replace('1', '#').replace('0', ' ')
        answer.append(temp)
    
    return answer
```
<hr>

문제에서 지도1, 2 중 하나라도 벽이었던 곳은 전체 지도에서도 벽이라는 점, 공백은 양쪽다 공백이어야 공백이라는 점. 그리고, 암호화 된 배열이 2진수로 주어진다는 힌트를 통해 OR 연산을 통해 전체지도를 얻어낸다는 것을 유추했다.

arr1, 2의 원소간의 OR연산을 format 함수로 진행했다. bin함수를 쓸 수도 있지만 접두어가 붙기 때문에 format 함수를 선택했다. 그리고 zfill(n)을 이용해 벽의 길이 만큼 이진수의 길이를 설정하였다. 예를 들어 OR 연산의 결과값이 4인 경우 100으로 나타나게 되는데 이 경우 만약 지도의 벽의 길이가 6이라면 앞에 3칸의 공백이 있다는 것을 표현하지 못하는 문제가 생기기 때문이다.

OR 연산을 통해 얻은 이진수를 문제 요구조건에 맞게 벽인 1은 #으로, 공백인 0은 ' '으로 replace하여 정답을 출력했다.