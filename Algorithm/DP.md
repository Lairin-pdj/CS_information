## DP(Dynamic Programming)

순차적인 배열을 통해 문제를 해결하는 방법

<br>

### 1. 점화식

피보나치 수열과 같은 일정한 규칙을 찾아 그를 최적화된 계산 방식으로 빠르게 답을 찾는 방식입니다.

```python
for i in range(1, n):
    for j in range(n - i):
        if i == 1:
            dp[j][j + i] = m[j][0] * m[j + 1][0] * m[j + 1][1]
        else:
            dp[j][j + i] = math.inf
            for k in range(j, j + i):
                dp[j][j + i] = min(dp[j][j + i], dp[j][k] + dp[k + 1][j + i] + (m[j][0] * m[k][1] * m[j + i][1]))
```

<br>

### 2. 누적합

위 점화식에서 특수한 케이스로 현재 값들을 계속 더해나가는 방식으로 부분 합까지 사용하는 방식입니다.

```python
for i in range(1, n):
    something[i] += something[i - 1]

# a ~ b의 부분 합
result = something[b] - something[a - 1]
```

<br>

### 관련문제
* 1328_고층 빌딩
* 2143_두 배열의 합
* 3020_개똥벌레
* 3114_사과와 바나나
* 9527_1의 개수 세기
* 11049_행렬 곱셈 순서
* 11066_파일 합치기
* 23327_리그전 오브 레전드