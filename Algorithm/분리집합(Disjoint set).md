## 분리집합(Disjoint set)

그래프에서 각 각의 연결관계를 통해 분리된 집합이 어떻게 형성되는지 체크하기 위한 알고리즘

<br>

### 주요 구현법

* find

  >```python
  >def find(x):
  >    if x != root[x]:
  >        root[x] = find(root[x])
  >    return root[x]
  >```
  >위 코드는 전부 부모의 노드에 달도록 하기 위한 코드이며 간선의 상황이나 필요한 경우에 따라 세부조정하는 것 또한 가능합니다. 

* union

  >```python
  >def union(x1, x2):
  >    root[find(x2)] = find(x1)
  >```
  >
  >서로의 부모를 체크하고 같도록 해주는 코드이며, 높이를 조절하기 위해 추가적인 코드를 작성할 수도 있습니다.

* root 및 간선 적용

  >```python
  >root = [i for i in range(n + 1)]
  >for _ in range(m):
  >    a, b = map(int, input().split())
  >    union(a, b)
  >```

<br>

### 관련문제
* 1717_집합의 표현
* 1936_중량제한
* 1976_여행 가자
* 2162_선분 그룹
* 4195_친구 네트워크
* 16562_친구비
* 20040_사이클 게임
* 23324_어려운 모든 정점 쌍 최단 거리