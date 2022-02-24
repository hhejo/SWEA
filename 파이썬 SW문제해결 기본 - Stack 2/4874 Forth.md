# 4874 Forth



```python
for TC in range(1, int(input()) + 1):
    S = input().split()
    stk, ans = [], 'error'  # 스택, 정답
    # 후위표기식 연산 시작
    for s in S:
        # 숫자 : 정수로 변환하고 스택에 push
        if s.isdecimal():
            stk.append(int(s))
        # 종료 : 스택 원소 개수 확인
        elif '.' == s:
            # 스택에 하나만 남았으면 그것이 정답. 아니라면 오류
            if 1 == len(stk):
                ans = stk.pop()
        # 연산자 : 연산
        else:
            # 연산을 해야 하는데 스택 원소 1개 이하이면 실패
            if len(stk) < 2:
                break
            # 스택 원소 2개 이상이면 연산
            else:
                # 숫자 2개 pop
                b = stk.pop()
                a = stk.pop()
                # 해당하는 연산 수행하고 다시 스택에 push
                if '+' == s:
                    stk.append(a + b)
                elif '-' == s:
                    stk.append(a - b)
                elif '*' == s:
                    stk.append(a * b)
                elif '/' == s:
                    stk.append(a // b)
    print(f'#{TC} {ans}')
```

