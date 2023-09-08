```python
def solution(s, n):
    answer = ''
    alphabetNumber = 26
    
    for i in s:
        if i == ' ':
            answer += i
        elif i.isupper() == True:
            answer += chr(ord('A') + (ord(i) + n - ord('A')) % alphabetNumber)
        else:
            answer += chr(ord('a') + (ord(i) + n - ord('a')) % alphabetNumber)
    
    return answer
```
<hr>

##### 문제 포인트
* 주어진 문자의 n번째 후 문자를 출력
* Z 다음에는 A, z 다음에는 a가 출력되어야 함
* 공백문자는 그대로 출력됨

##### 풀이
* 공백문자는 그대로 넘기고 대소문자 구분을 함
* 알파벳 개수는 26개인 점을 이용해 해당 문자의 아스키 값이 알파벳 범위를 벗어나지 않고 루프를 타도록 함