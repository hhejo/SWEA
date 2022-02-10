# 4828 1일차 - min max



## 1.

```python
for t in range(1, int(input())+1):  # 테스트케이스 t 입력받고 t번 반복
    n = int(input())  # 양수의 개수 n
    nums = list(map(int, input().split()))  # n개의 양수 ai
    max_value, min_value = 1-1, 1000000+1  # 최댓값, 최솟값 초기화
    for num in nums:  # n개의 양수 하나씩 반복
        max_value = num if num > max_value else max_value  # 현재 수가 최댓값보다 크면 최댓값에 대입
        min_value = num if num < min_value else max_value  # 현재 수가 최솟값보다 작으면 최솟값에 대입
    diff = max_value - min_value  # 최댓값과 최솟값의 차
    print(f'#{t} {diff}')

```

틀린 코드다. 왜지?

```
7번째 줄에서 else 다음을 min_value로 써야 하는데 max_value로 써서 틀렸다.
```



## 2.

```python
for t in range(1, int(input())+1):  # 테스트케이스 t 입력받고 t번 반복
    n = int(input())  # 양수의 개수 n
    nums = list(map(int, input().split()))  # n개의 양수 ai
    max_value, min_value = 1-1, 1000000+1  # 최댓값, 최솟값 초기화
    for num in nums:  # n개의 양수 하나씩 반복
        max_value = num if num > max_value else max_value  # 현재 수가 최댓값보다 크면 최댓값에 대입
        min_value = num if num < min_value else min_value  # 현재 수가 최솟값보다 작으면 최솟값에 대입
    diff = max_value - min_value  # 최댓값과 최솟값의 차
    print(f'#{t} {diff}')
```

1번 코드 해결



## 3.

```python
for t in range(1, int(input())+1):  # 테스트케이스 t 입력받고 t번 반복
    n = int(input())  # 양수의 개수 n
    nums = list(map(int, input().split()))  # n개의 양수 ai
    max_value = min_value = nums[0]  # 최댓값, 최솟값 초기화
    for num in nums:  # n개의 양수 하나씩 반복
        max_value = num if num > max_value else max_value  # 현재 수가 최댓값보다 크면 최댓값에 대입
        min_value = num if num < min_value else min_value  # 현재 수가 최솟값보다 작으면 최솟값에 대입
    diff = max_value - min_value  # 최댓값과 최솟값의 차
    print(f'#{t} {diff}')
```

4번째 줄 최댓값, 최솟값 초기화를 리스트 원소의 맨 처음 값으로 해도 됨



## 4.

```python
for t in range(1, int(input())+1):  # 테스트케이스 t 입력받고 t번 반복
    n = int(input())  # 양수의 개수 n
    nums = list(map(int, input().split()))  # n개의 양수 ai
    diff = max(nums) - min(nums)  # 최댓값과 최솟값의 차
    print(f'#{t} {diff}')
```

파이썬 내장함수 `max()`, `min()` 사용



## 5.

```python
for T in range(1, int(input())+1):
    N = int(input())
    max_value, min_value = 0, 1000001
    for value in map(int, input().split()):
        max_value = value if value > max_value else max_value
        min_value = value if min_value > value else min_value
    print(f'#{T} {max_value - min_value}')
```

실습 과제
