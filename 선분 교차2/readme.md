**URL: https://www.acmicpc.net/problem/17387**

**Solution:**
```python
def solution(numbers):
    answer = []

    for i in range(len(numbers)):
        answer.append(((numbers[i] ^ (numbers[i] + 1)) >> 2) + numbers[i] + 1)

    return answer

print(solution([2, 7]))
```
