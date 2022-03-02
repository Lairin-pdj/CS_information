## BFS(너비 우선 탐색)
  
### 그래프에서 찾기
  
### 2차원 경로 찾기
주로 2차원 배열에서 최단거리를 이동 혹은 탐색 할 경우 자주 사용되는 기법
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
