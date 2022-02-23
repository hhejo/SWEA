# 4874 Forth



```python
for TC in range(1, int(input()) + 1):
    S = input().split()
    stk, ans = [], 'error'
    for s in S:
        if s.isdecimal():
            stk.append(s)
        elif '.' == s:
            if 1 == len(stk):
                ans = stk.pop()
        else:
            if len(stk) < 2:
                break
            else:
                b = int(stk.pop())
                a = int(stk.pop())
                if '+' == s:
                    stk.append(str(a + b))
                elif '-' == s:
                    stk.append(str(a - b))
                elif '*' == s:
                    stk.append(str(a * b))
                elif '/' == s:
                    stk.append(str(a // b))
    print(f'#{TC} {ans}')
```


