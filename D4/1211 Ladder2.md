# 1211 Ladder2



```python
for _ in range(10):
    T = int(input())
    li = [list(map(int, input().split())) for _ in range(100)]
    startings = [(0, j) for j in range(100) if li[0][j] == 1]  # 사다리 시작 좌표들
    min_distance = max_y = 10001  # 최단거리, 최단거리 중 가장 오른쪽 y 좌표
    for x, y in startings:  # 사다리 출발할 x, y 좌표
        start_y, distance = y, 1  # 출발 y 좌표, 거리
        _li = [list(map(int, li[i])) for i in range(100)]  # 원본 복제 리스트
        while x < 99:  # 맨 아래 행에 닿을 때까지
            for dx, dy in [(0, 1), (0, -1), (1, 0)]:  # 우 좌 하
                nx, ny = x + dx, y + dy  # 다음 갈 위치
                if 0 <= nx <= 99 and 0 <= ny <= 99 and _li[nx][ny] == 1:  # 유효범위 사다리
                    _li[x][y], x, y = 2, nx, ny  # 현재 위치 2로 수정하고 이동
                    distance += 1  # 이동 거리 1 증가
                    break
        if min_distance >= distance:  # 지금까지의 최단거리보다 작거나 같으면 최단거리 갱신
            min_distance, max_y = distance, start_y
    print(f'#{T} {max_y}')
```

현재 위치를 다르게 기록하고 옮겨야 함
