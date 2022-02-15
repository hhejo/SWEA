# 1210 Ladder1



```python
for _ in range(10):
    T = int(input())
    li = [list(map(int, input().split())) for _ in range(100)]
    # 종착점 y 좌표 탐색
    x = y = 99
    for j in range(100):
        if li[-1][j] == 2:
            y = j
    # 시작점이 될 때까지 반복
    while x > 0:
        for dx, dy in [(0, -1), (0, 1), (-1, 0)]:  # 좌, 우, 상
            nx, ny = x + dx, y + dy  # 이동할 좌표
            if 0 <= nx <= 99 and 0 <= ny <= 99 and li[nx][ny] == 1:  # 유효 범위 내 사다리
                li[x][y], x, y = 2, nx, ny  # 현재 위치 2로 기록하고 이동
                break
    print(f'#{T} {y}')
```

현재 위치를 다르게 기록하고 옮겨야 함
