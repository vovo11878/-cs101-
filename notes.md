1、d = {'c': 3, 'a': 1, 'b': 2}  
dp = sorted(d.items())  对键进行排队
print(dp)  # 输出：[('a', 1), ('b', 2), ('c', 3)]

2、from collections import defaultdict
d = defaultdict(list)

![image-20240520134553683](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240520134553683.png)

3、中序转后序
def infix_to_postfix(expression):
    precedence = {'+':1, '-':1, '*':2, '/':2}
    stack = []
    postfix = []
    number = ''

    for char in expression:
        if char.isnumeric() or char == '.':
            number += char
        else:
            if number:
                num = float(number)
                postfix.append(int(num) if num.is_integer() else num)
                number = ''
            if char in '+-*/':
                while stack and stack[-1] in '+-*/' and precedence[char] <= precedence[stack[-1]]:
                    postfix.append(stack.pop())
                stack.append(char)
            elif char == '(':
                stack.append(char)
            elif char == ')':
                while stack and stack[-1] != '(':
                    postfix.append(stack.pop())
                stack.pop()
    
    if number:
        num = float(number)
        postfix.append(int(num) if num.is_integer() else num)
    
    while stack:
        postfix.append(stack.pop())
    
    return ' '.join(str(x) for x in postfix)

n = int(input())
for _ in range(n):
    expression = input()
    print(infix_to_postfix(expression))

4、二叉树深度=高度+1   （根节点为1）![image-20240520142109176](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240520142109176.png)![image-20240520142038377](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240520142038377.png)

5、括号嵌套树

![image-20240520145022409](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240520145022409.png)

![image-20240520145039883](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240520145039883.png)

6、中后序生成前序遍历树

![image-20240520151439770](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240520151439770.png)

前中序生成后序

![image-20240520151519898](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240520151519898.png)

7、二叉搜索树

给前序生成后序

![image-20240520154307165](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240520154307165.png)

给一串数字建立树，然后按层次遍历

![image-20240520155224722](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240520155224722.png)

去除重复元素

8、平衡二叉树avl

![image-20240520161949254](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240520161949254.png)

![image-20240520162010820](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240520162010820.png)

![image-20240520162036439](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240520162036439.png)

9、并查集

![image-20240520162158647](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240520162158647.png)

<img src="C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240527232408174.png" alt="image-20240527232408174" style="zoom:80%;" />

10.小组队列

![image-20240526162452948](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240526162452948.png)

![image-20240526162511499](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240526162511499.png)

11.数字小到大遍历树

![image-20240526163037760](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240526163037760.png)

集合的加减![image-20240526163120045](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240526163120045.png)

12、图

![image-20240526182321273](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240526182321273.png)

![image-20240526182344953](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240526182344953.png)

13、最大连通域权值

![image-20240526190926677](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240526190926677.png)

14、trie

![image-20240526192021451](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240526192021451.png)

<img src="C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240526192114158.png" alt="image-20240526192114158" style="zoom:80%;" />

![image-20240526192139572](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240526192139572.png)

15、数的镜面映射

![image-20240526195845453](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240526195845453.png)

![image-20240526195910359](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240526195910359.png)

![image-20240526195937792](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240526195937792.png)

16、前中序输出后序![image-20240526214325106](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240526214325106.png)

17、bfs示例（鸣人）

![image-20240526223559469](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240526223559469.png)

18、走山路Dijkstra   （堆保证最短路径，q中t最小的最后进行）

![image-20240526224100073](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240526224100073.png)

兔子樱花

![image-20240601202640762](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240601202640762.png)

![image-20240601202718316](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240601202718316.png)

19、prim算法（兔子星空)

![image-20240526224610891](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240526224610891.png)

![image-20240526224623030](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240526224623030.png)

![image-20240526224639006](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240526224639006.png)

最小权值和

20、![image-20240526225908338](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240526225908338.png)

result为1-8的所有排列

21、判断无向图是否连通有无回路

<img src="C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240526233132341.png" alt="image-20240526233132341" style="zoom:80%;" />

![image-20240526233147980](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240526233147980.png)

22、层次遍历，输出每行最后一个

![image-20240527000547724](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240527000547724.png)

23、单调栈

![image-20240527000640560](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240527000640560.png)

第一个大于第i个元素的下标

24、有向图是否有环

![image-20240527000810127](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240527000810127.png)

25、

<img src="C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240527001012665.png" alt="image-20240527001012665" style="zoom:80%;" />![image-20240527000945616](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240527000945616.png)

26、dfs注意回溯

<img src="C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240527210202292.png" alt="image-20240527210202292" style="zoom:80%;" />

27、遍历

![image-20240601232741661](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240601232741661.png)

![image-20240601232825762](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240601232825762.png)

28、

![image-20240601153513704](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240601153513704.png)

![image-20240601154955509](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240601154955509.png)

输出为元组

import heapq

`heapify(x)`  **用途**：将列表 `x` 原地转换为堆。     `heappush(heap, item)`  用途：将 `item` 加入到堆 `heap` 中，并保持堆的不变性。heappop(heap)   用途**：弹出并返回 `heap` 中最小的元素，保持堆的不变性。

`heapreplace(heap, item)`**用途**：弹出堆中最小的元素，并将新的 `item` 插入堆中，效率高于先 `heappop()` 后 `heappush()`。

`heappushpop(heap, item)`**用途**：先将 `item` 压入堆中，然后弹出并返回堆中最小的元素。

`nlargest(n, iterable, key=None)` 和 `nsmallest(n, iterable, key=None)`

**用途**：从 `iterable` 数据中找出最大的或最小的 `n` 个元素。

29、

![dij](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240601200313247.png)

30、

![image-20240601203139038](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240601203139038.png)

![image-20240601203205626](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240601203205626.png)
