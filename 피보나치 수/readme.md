**URL: https://school.programmers.co.kr/learn/courses/30/lessons/12945**

**Solution1: 재귀**
```python
def f(n):
    if n<2: return n
    else: v = (f(n-1) + f(n-2)) %1234567
    return v

n = int(input('입력'))
print(f(n))
```
> 런타임 에러 , 시간 초과 오류 발생(시간 복잡도: O(2^n))

<br>

**Solution2: 메모이제이션**
```python
def f(n):
    if n in m: return m[n]
    if n<2: return n
    else: m[n] = (f(n-1) + f(n-2)) % 1234567
    return m[n]

m = {}
n = int(input('입력'))
print(f(n))
```
> 런타임 에러 발생, 전체적으로 각 숫자에 대해 한 번씩만 계산이 수행됨 (시간 복잡도: O(n), 공간 복잡도: O(n))
> 아마 재귀의 깊이 제한이나 메모이제이션의 메모리 사용량이 너무 많아서 발생하는 듯

</br>

**Solution3: 반복문**
```python
def f(n):
    if n < 2: return n
    x, y = 0, 1
    for _ in range(2, n + 1):
        x, y = x, (x + y) % 1234567
    return y

n = int(input('입력: '))
print(f(n))
```
> 반복문은 range(2, n + 1)로 설정되어 있어, 정확히 n−1번 반복 (시간 복잡도: O(n), 공간 복잡도: O(1) - 상수 개수의 변수만 사용)
