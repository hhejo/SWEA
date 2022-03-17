# 5174 subtree



## 1.

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



## 2.

```python
def postorder(n):
    if 0 == n:  # 0이면 유효하지 않은 노드
        return 0
    global tree
    # 왼쪽 서브트리의 노드 개수 + 오른쪽 서브트리의 노드 개수 + 나(1)
    return postorder(tree[n][0]) + postorder(tree[n][1]) + 1


for T in range(1, int(input()) + 1):
    E, N = map(int, input().split())
    tree = [[0, 0] for _ in range(E + 2)]  # 트리. 왼쪽, 오른쪽 자식 인덱스
    arr = list(map(int, input().split()))  # 노드 번호 쌍
    for i in range(E):
        if tree[arr[i*2]][0]:  # 왼쪽 자식 있으면
            tree[arr[i*2]][1] = arr[i*2+1]  # 오른쪽 자식 추가
        else:
            tree[arr[i*2]][0] = arr[i*2+1]  # 왼쪽 자식 추가
    print(f'#{T} {postorder(N)}')
```

