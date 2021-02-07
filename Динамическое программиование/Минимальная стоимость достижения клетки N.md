##### Фибоначи
$$O(N)$$
```py
def fib(n):
    fib = [0,1] + [0]*(n-1)
    for i in range(2, N+1):
        fib[i] = fib[i-1] + fib[i-2]
    return fib[n]
```

### Минимальная стоимость достижения клетки N
priсe[i] - цена посещения конкретной клетки N
cost[i] - минимальная стоимость достижения клетки N
возможные ходы:
1) +1
2) +2

i-2, i-1 - промежуточные
i - конечный пункт
$C_i=price_i+min(C_{i-1},C_{i-2})$
**крайний случай:**
*крайняя клетка не достижима, ее стоимость бесконечна*
$C_1 = price_1$
$C_2 = price_1 + price_2$

```py
def count_min_cost(N, price:list):
    cost = [float("-inf"), price[1], price[1]+price[2]] + [0]*(N-2)
    for i in range(3, N+1):
        cost[i] = price[i] + min(cost[i-1], cost[i-2])
    return cost[N]

print(count_min_cost(6, [1, 2, 2, 3, 4, 40, 70, 112]))
```