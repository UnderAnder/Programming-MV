### Проверка равенства строк
$$O(N)$$
A = "строки"
B = "равны"
```py
def equal(A, B): # O(N)
    if len(A) != len(B):
        return False
    for i in range(len(A)):
        if A[i] != B[i]:
            return False
    return True
```