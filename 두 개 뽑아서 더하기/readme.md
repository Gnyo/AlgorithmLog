**URL: https://school.programmers.co.kr/learn/courses/30/lessons/68644**

**Solution:**
```python
def solution(numbers):
    answer = set( )

    for i in range(len(numbers)):
        for j in range(i+1, len(numbers)):
            answer.add(numbers[i] + numbers[j]

return sorted(answer)

![image](https://github.com/user-attachments/assets/afdfa733-d682-4062-8e8a-8dce06f56188)
```
