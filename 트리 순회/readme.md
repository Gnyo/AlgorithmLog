**URL: https://www.acmicpc.net/problem/1991**

**Solution: **
```python
tree = {} # Tree 집합

n = int(input())
for _ in range(n): # n만큼 반복
    root, l, r = input().split()
    tree[root] = (l, r)

def traverse(node, order):
    if node == '.':
        return ''
    
    left, right = tree[node] #변수에 값 넣기
    
    if order == '전위':
        return node + traverse(left, order) + traverse(right, order)  # 전위 순회
    elif order == '중위':
        return traverse(left, order) + node + traverse(right, order)  # 중위 순회
    elif order == '후위':
        return traverse(left, order) + traverse(right, order) + node  # 후위 순회

print(traverse('A', '전위'))
print(traverse('A', '중위'))
print(traverse('A', '후위'))
```
