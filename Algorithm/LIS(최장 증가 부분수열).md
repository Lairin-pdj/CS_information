## Longest Increasing Subsequence(최장 증가 부분수열)

### 1. dp(n^2)  
각 위치마다 이어지는 값을 전부 계산하는 방식 
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
길이만을 체크할 때 좋은 방법
```python
lis = []
for a in lines:
    idx = bisect.bisect_left(lis, a)
    if idx >= len(lis):
        lis.append(a)
    else:
        lis[idx] = a
```
  
### 최장수열 자체가 필요한 경우  
이분탐색에서 각 idx를 저장하는 배열을 확인하여 역추적이 가능  
```python
for i in range(n - 1, -1, -1):
    if index[i] == temp:
        answer.append(lines[i])
        temp -= 1
```
  
  
### 관련 문제 
- 2565_전깃줄
- 2568_전깃줄-2
- 11053_가장 긴 증가하는 부분 수열
- 11054_가장 긴 바이토닉 부분 수열
- 11055_가장 큰 증가 부분 수열
- 11722_가장 긴 감소하는 부분 수열
- 12015_가장 긴 증가하는 부분 수열 2
- 14002_가장 긴 증가하는 부분 수열 4
- 14003_가장 긴 증가하는 부분 수열 5
