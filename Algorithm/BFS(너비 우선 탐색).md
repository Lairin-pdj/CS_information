## BFS(너비 우선 탐색)
  
### 그래프에서 탐색
dictionary를 이용한 그래프에서 주로 사용
  
### 2차원 배열에서 탐색
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
  
### 관련문제
* 10026_적록색약
* 16236_아기 상어
