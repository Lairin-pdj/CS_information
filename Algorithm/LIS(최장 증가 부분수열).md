## Longest Increasing Subsequence(최장 증가 부분수열)

### 1. dp(n^2)  
각 위치마다 전 값을 비교하며 갱신해나가는 방법
```cpp
int d[n + 1] = {1, 0,};
int answer = 0;
for (int i = 1; i < n; i++) {
    int temp = 0;
    for (int j = 0; j < i; j++) {
        if (vec[j].second < vec[i].second) {
            temp = max(temp, d[j]);
        }
    }
    d[i] = temp + 1;
    answer = max(answer, d[i]);
}
```
  
### 2. 이분탐색(nlogn)  
이분탐색을 이용하여 lis 배열에서의 위치를 체크하는 방식
lis 배열은 실제 LIS와는 다르므로 실제 LIS를 알고 싶은 경우 추가적인 코드가 필요하다.
```python
lis = []
for a in lines:
    idx = bisect.bisect_left(lis, a)
    if idx >= len(lis):
        lis.append(a)
    else:
        lis[idx] = a
```
  
### *최장수열을 알고싶은 경우 
이분탐색에서 각 idx를 저장하는 배열을 확인하여 역추적이 가능  
```python
for i in range(n - 1, -1, -1):
    if index[i] == temp:
        answer.append(lines[i])
        temp -= 1
```
  
### *최장수열 갯수가 알고싶은 경우
2차원 배열 및 이분탐색을 통해 가능한 경우의 수를 체크하는 것이 가능
```python
dp = [[0] for _ in range(len(lis))]
for i in range(n - 1, -1, -1):
    target = 1
    if index[i] + 1 < len(lis):
        temp = bisect.bisect_right(dic[index[i] + 1], lines[i])
        target = dp[index[i] + 1][-1] - dp[index[i] + 1][temp]
    dic[index[i]].append(lines[i])
    dp[index[i]].append((target + dp[index[i]][-1]))
```
  
### 관련 문제 
- 2565_전깃줄
- 2568_전깃줄-2
- 11053_가장 긴 증가하는 부분 수열
- 11054_가장 긴 바이토닉 부분 수열
- 11055_가장 큰 증가 부분 수열
- 11722_가장 긴 감소하는 부분 수열
- 12015_가장 긴 증가하는 부분 수열 2
- 12738_가장 긴 증가하는 부분 수열 3
- 14002_가장 긴 증가하는 부분 수열 4
- 14003_가장 긴 증가하는 부분 수열 5
- 17411_가장 긴 증가하는 부분 수열 6
