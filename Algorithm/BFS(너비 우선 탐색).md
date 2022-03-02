## BFS(너비 우선 탐색)

### 경로 찾기
```python
dx, dy = [-1, 0, 0, 1], [0, -1, 1, 0]

queue = deque([(startX, startY)])
check = set([(startX, startY)])

while queue:
    x, y = queue.popleft()
       
    if break condition:
        break

    for i in range(4):
        ax = x + dx[i]
        ay = y + dy[i]

        if 0 <= ax < n and 0 <= ay < n and (ax, ay) not in check and another condition:
            check.add((ax, ay))
            queue.append([(ax, ay)])
```
