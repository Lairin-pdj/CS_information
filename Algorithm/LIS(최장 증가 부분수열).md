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
for a, b in lines:
    idx = bisect.bisect_left(lis, b)
    if idx >= len(lis):
        lis.append(b)
    else:
        lis[idx] = b
```
  
  
### 관련 문제 
- 2565_전깃줄
- 2568_전깃줄-2
