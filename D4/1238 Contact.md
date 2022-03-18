# 1238 Contact



## 1.

```python
def bfs(adj, s):
    que = []
    que.append(s)
    visited = [0] * 101
    visited[s] = 1
    sol = s
    while que:
        c = que.pop(0)
        if visited[sol] < visited[c] or visited[sol] == visited[c] and sol < c:
            sol = c
        for j in range(1, 101):
            if adj[c][j] and not visited[j]:
                que.append(j)
                visited[j] = visited[c] + 1
    return sol


T = 10
for test_case in range(1, T + 1):
    N, S = map(int, input().split())
    ARR = list(map(int, input().split()))
    adj = [[0] * 101 for _ in range(101)]
    for i in range(0, N, 2):
        adj[ARR[i]][ARR[i+1]] = 1
    ans = bfs(adj, S)
    print(f'#{test_case} {ans}')
```

인접행렬



## 2.

```python
def bfs(adj, s):
    que = []
    que.append(s)
    visited = [0] * 101
    visited[s] = 1
    sol = s
    while que:
        c = que.pop(0)
        if visited[sol] < visited[c] or visited[sol] == visited[c] and sol < c:
            sol = c
        for j in adj[c]:
            if not visited[j]:
                que.append(j)
                visited[j] = visited[c] + 1
    return sol


T = 10
for test_case in range(1, T + 1):
    N, S = map(int, input().split())
    ARR = list(map(int, input().split()))
    adj = [[] for _ in range(101)]
    for i in range(0, N, 2):
        adj[ARR[i]].append(ARR[i+1])
    ans = bfs(adj, S)
    print(f'#{test_case} {ans}')
```

인접리스트?

