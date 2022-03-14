# 5174 subtree



```python
for T in range(1, int(input()) + 1):
    E, N = map(int, input().split())
    li = list(map(int, input().split()))
    tr = [[] for _ in range(E + 2)]
    for i in range(0, E * 2, 2):
        tr[li[i]].append(li[i+1])
    stk = []
    cnt = 1
    if tr[N]:
        stk.extend(tr[N])
    while stk:
        now = stk.pop()
        cnt += 1
        for node in tr[now]:
            stk.append(node)
    print(f'#{T} {cnt}')
```

