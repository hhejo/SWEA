# 1208 Flatten



```python
for T in range(1, 11):
    D = int(input())  # 최대 가능 덤프 횟수
    H = list(map(int, input().split()))  # 상자 높이의 리스트
    # 덤프 횟수, 높이 차, 최대 높이 인덱스, 최소 높이 인덱스
    dump = diff = max_idx = min_idx = 0
    while True:
        # 최대 높이, 최소 높이 인덱스 탐색
        for i in range(100):
            if H[max_idx] <= H[i]:
                max_idx = i
            if H[min_idx] >= H[i]:
                min_idx = i
        diff = H[max_idx] - H[min_idx]  # 높이 차
        # 덤프 횟수 초과 or 높이 차 1 이하
        if dump == D or diff <= 1:
            break
        # 덤프 시행
        H[max_idx] -= 1
        H[min_idx] += 1
        dump += 1
    print(f'#{T} {diff}')
```

상자를 옮기면 작업한 두 위치의 높이가 달라지므로 주의
