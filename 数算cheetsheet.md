
⼀些错误总结：
Compile Error：
1. 这个多半是变量名字打错了，或者多打；：之类的，这个好查，⼀般本地都运⾏不了。
2. OJ 的 pylint 是静态检查，有时候报的 compile error 不对。解决⽅法有两种，如下：
1）第⼀⾏加# pylint: skip-file
2）⽅法⼆：如果函数内使⽤全局变量（变量类型是 immutable，如 int），则需要在程序最开始声明⼀下。如
果是全局变量是 list 类型，则不受影响。
Runtime Error：
3. 指针越界，⽐如⻓度为 5（index 为 0，1，2，3，4）的数组你去获取 list[5]，但是注意 list[-5]是合法的（index
可以为-1，-2，-3，-4，-5）。
4. 数组开太⼤了，⽐如开到 1000000000（9 个 0）就会
5. 递归爆栈：这个⽤以下代码解决
6. 输⼊读取错误，⼀般是输⼊没读完就 exit（） （所以要谨慎使⽤这个函数）
7. 除以 0，检查⼀下变量是不是可以是 0
Wrong Answer
这个需要好好审⼀遍代码
如果没有逻辑性的错误，就查⼀下边界值，⽐如 0 啊 1 啊什么的，很可能在这些地⽅出错
如果还不⾏，就仔细审题，看看哪个地⽅理解错了
Presentation Error
只遇到过⼀次，就是该输出空⾏的时候没输出空⾏
Time Limit Exceeded
8. 死循环（这种在 BFS 类⾥容易碰到，要注意 visited 的逻辑是否正确）
9. 算法问题（注意每次读题时注意数据量，以便快速确定算法）
10. 卡常数，这种情况⽤pypy 3 就可以了，或者再优化⼀下代码，去除⼀些鸡肋的 O（n）操作
Memory Limit Exceeded
数组开太⼤了，⼀般 DP 难题会遇到，这时候就要考虑压缩空间了。
还有就是 BFS 的时候 queue 可能会超，要考虑进堆的数据的优化
# 数学知识

```python
from collections import defaultdict  
  
dic=defaultdict(list)
```
筛法（欧拉筛）
* 筛出 1<=i<=n 所有的素数
* 输入范围 n, 输出 1~n 的素数列表
* 如果你想查询一个很大的数是不是素数, 把里面 prime 一开始做成集合再返回用来查询
  ```python
  def ES(n):
    isprime=[True for _ in range(n+1)]
    prime=[]
    for i in range(2,n+1):
        if isprime[i]:
            prime.append(i)
        for j in range(len(prime)):
            if  i*prime[j]>n:break
            isprime[i*prime[j]]=False
            if i%prime[j]==0 :break

    return prime
```

卡特兰数
```python
import sys
from functools import lru_cache

sys.setrecursionlimit(1<<30)
@lru_cache(maxsize=None)
def dfs(i,j):
    if i==0:
        return 1
    if j==0:
        return dfs(i-1,j+1)
    return dfs(i-1,j+1)+dfs(i,j-1)

print(dfs(int(input()),0))
```

前缀和
1. 定义
前缀和是一种将数组中**前 i 项的和预处理出来**的技巧，主要用于快速计算任意区间的和。
给定一个数组 `a`，其前缀和数组 `s` 定义为：`s[0] = 0 s[i] = a[0] + a[1] + ... + a[i-1] （从1开始）`即：`s[i] = s[i-1] + a[i-1]`
2. 快速求区间和
若要求区间 `[l, r]`（从索引 l 到 r-1，半开区间）的和：
`区间和 = s[r] - s[l]`
3. 使用场景
- 快速求任意区间的和
- 多次查询区间和
差分数组
1. 定义
差分数组是用来**快速进行区间修改**的一种技巧。
给定数组 `a`，我们构造一个差分数组 `d`：`d[0] = a[0] d[i] = a[i] - a[i - 1]  （i >= 1）`有了差分数组后，可以通过：`a[i] = d[0] + d[1] + ... + d[i]`恢复原数组。
2. 快速区间修改
如果我们要对区间 `[l, r]` 中的每个数加上一个数 `x`，只需要：
`d[l] += x ; d[r + 1] -= x  （如果 r+1 在数组范围内）`
这使得所有操作可以压缩成 O(1) 进行，最后一次性用前缀和恢复即可。
3. 使用场景
- 区间加法修改（高效）
- 多次修改后一次性生成结果

队列中位数：
```python
import sys
import heapq
from collections import deque, defaultdict

input = sys.stdin.readline

class DualHeap:
    def __init__(self):
        # 大根堆（存放较小的一半，用负数模拟）
        self.small = []  
        # 小根堆（存放较大的一半）
        self.large = []  
        # 延迟删除的记录
        self.delayed = defaultdict(int)
        # 两个堆中有效数据的个数
        self.small_size = 0  
        self.large_size = 0  

    def prune(self, heap):
        # 清理堆顶已经被延迟删除的元素，不再调整size（因为在remove中已扣减）
        if heap is self.small:
            while heap and self.delayed[-heap[0]] > 0:
                num = -heapq.heappop(heap)
                self.delayed[num] -= 1
        else:
            while heap and self.delayed[heap[0]] > 0:
                num = heapq.heappop(heap)
                self.delayed[num] -= 1

    def balance(self):
        # 保持 small 比 large 多 0 或 1 个有效元素
        if self.small_size > self.large_size + 1:
            self.prune(self.small)
            num = -heapq.heappop(self.small)
            self.small_size -= 1
            heapq.heappush(self.large, num)
            self.large_size += 1
        elif self.small_size < self.large_size:
            self.prune(self.large)
            num = heapq.heappop(self.large)
            self.large_size -= 1
            heapq.heappush(self.small, -num)
            self.small_size += 1

    def add(self, num):
        # 插入新数时，根据大小决定进入哪个堆
        if not self.small or num <= -self.small[0]:
            heapq.heappush(self.small, -num)
            self.small_size += 1
        else:
            heapq.heappush(self.large, num)
            self.large_size += 1
        self.balance()

    def remove(self, num):
        # 延迟删除：标记待删除，同时减少对应堆的有效元素数量
        self.delayed[num] += 1
        if self.small and num <= -self.small[0]:
            self.small_size -= 1
            if num == -self.small[0]:
                self.prune(self.small)
        else:
            self.large_size -= 1
            if self.large and num == self.large[0]:
                self.prune(self.large)
        self.balance()

    def median(self):
        # 查询中位数前先清理堆顶
        self.prune(self.small)
        self.prune(self.large)
        total = self.small_size + self.large_size
        if total % 2 == 1:
            return -self.small[0]
        else:
            return (-self.small[0] + self.large[0]) / 2

if __name__ == '__main__':
    n = int(input())
    dh = DualHeap()
    # 使用 deque 记录入队顺序，确保del操作删除最先添加的数
    q = deque()
    results = []
    for _ in range(n):
        parts = input().split()
        op = parts[0]
        if op == 'add':
            x = int(parts[1])
            dh.add(x)
            q.append(x)
        elif op == 'del':
            x = q.popleft()
            dh.remove(x)
        elif op == 'query':
            med = dh.median()
            # 若中位数为整数则去除小数部分
            if med == int(med):
                results.append(str(int(med)))
            else:
                results.append(str(med))
    print("\n".join(results))

```

滑动窗口
```python
#外层循环扩展右边界，内层循环扩展左边界
l=0
for r in range(len()):
	//当前考虑的元素
	while l<=r and check():
		l+=1
		#扩展左边界
    //区间[left,right]符合题意，统计相关信息
```

二分查找
```python
while l<=r:
	mid=(l+r)//2
	if check(mid):
		ans=mid
		r=mid-1
	else:
		l=mid+1
return ans
```
# A 线性结构
## 1 链表
遍历
```python
cur=head
while cur:
	########
	cur=cur.next
```
插入、删除这些基本操作
```python
#以删除为例
dummy=ListNode()
dummy.next=head
cur=dummy
while cur.next:
	if cur.next.val==val:
		cur.next=cur.next.next
	else:
		cur=cur.next
```
- 这里用到了哨兵节点 `dummy` 为的是统一删除的操作，而避免对边界的处理（一般需要对链表进行修改的，用哨兵节点都可以简化问题）
- 与此同时，while 的判断也不一样，这是因为要对节点本身进行操作，此时用 `while cur.next:`，如果是遍历节点用 `while cur:`
反转链表
```python
pre=None
cur=head
while cur is not None:
	pre,pre.next,cur=cur,pre,cur.next
```
## 2 栈的使用
### Ⅰ中序表达式转换 （调度场算法）
```python
n=int(input())
operater={}
operater['+']=1
operater['-']=1
operater['*']=2
operater['/']=2
operater['(']=0
operater[')']=0
for _ in range(n):
    inp=input().strip()
    INP=[]
    cur=''
    for i in inp:
        if i in operater:
            if cur:
                INP.append(cur)
                cur=''
            INP.append(i)
        else:
            cur+=i
    if cur:
        INP.append(cur)
    ans=[]
    stack=[]
    for i in INP:
        if i not in operater:
            ans.append(i)
        elif i==')':
            while stack[-1]!='(':
                ans.append(stack.pop())
            stack.pop()
        elif i=='(':
            stack.append(i)
        else:
            while stack and operater[i]<=operater[stack[-1]]:
                ans.append(stack.pop())
            stack.append(i)
    while stack and stack[-1] in operater:
        ans.append(stack.pop())
    print(*ans)
```
- 中序表达式→后序表达式→解析树
- 建立解析树的过程实际上就是求值的过程
## 3 其他
### 1. KMP 算法
问题：给定模式串，在字符串中寻找是否存在模式串
思想：通过建立 `next` 数组回滚模式串，使得不用回溯字符串指针

```python
# 生成 next 数组
# next[j] 表示下标 j 之前的模式串 p 中，最长相等前后缀的长度
def generateNext(p: str):
    m = len(p)
    next = [0 for _ in range(m)]  # 初始化数组元素全部为 0
    
    left = 0         # left 表示前缀串开始所在的下标位置
    for right in range(1, m):  # right 表示后缀串开始所在的下标位置
        while left > 0 and p[left] != p[right]: 
        # 匹配不成功, left 进行回退, left == 0 时停止回退
            left = next[left - 1]    # left 进行回退操作
        if p[left] == p[right]:         
        # 匹配成功，找到相同的前后缀，先让 left += 1，此时 left 为前缀长度
            left += 1
        next[right] = left              
        # 记录前缀长度，更新 next[right], 结束本次循环, right += 1

    return next

# KMP 匹配算法，T 为文本串，p 为模式串
def kmp(T: str, p: str) -> int:
    n, m = len(T), len(p)
    
    next = generateNext(p)   # 生成 next 数组
    
    j = 0                    # j 为模式串中当前匹配的位置
    for i in range(n):       # i 为文本串中当前匹配的位置
        while j > 0 and T[i] != p[j]:           
        # 如果模式串前缀匹配不成功, 将模式串进行回退, j == 0 时停止回退
            j = next[j - 1]
        if T[i] == p[j]:  
        # 当前模式串前缀匹配成功，令 j += 1，继续匹配
            j += 1
        if j == m:                              
        # 当前模式串完全匹配成功，返回匹配开始位置
            return i - j + 1
    return -1       # 匹配失败，返回 -1
            

```
### 2. 排序算法
Python 内置了非常强大的排序功能，并且对于元组的排序是根据顺序进行的，所以当我们想要进行多数据的排序时
```python
arr.sort(key=lambda x:(x[0],x[1],x[2]))
```

归并排序
原理：归并排序（Merge Sort）是一种基于分治思想的排序算法，它将待排序的数组分成两部分，分别对这两部分递归地进行排序，最后将两个有序子数组合并成一个有序数组

```python
def merge_sort(arr):
    if len(arr) <= 1:
        return arr
 
    # 将数组分成两个部分
    mid = len(arr) // 2
    left_half = arr[:mid]
    right_half = arr[mid:]
 
    # 对左右两部分分别递归调用归并排序
    left_half = merge_sort(left_half)
    right_half = merge_sort(right_half)
 
    # 合并左右两部分
    return merge(left_half, right_half)
 
def merge(left_half, right_half):
    i = j = 0
    merged = []
 
    # 比较左右两部分的元素，将较小的元素添加到 merged 中
    while i < len(left_half) and j < len(right_half):
        if left_half[i] < right_half[j]:
            merged.append(left_half[i])
            i += 1
        else:
            merged.append(right_half[j])
            j += 1
 
    # 将左右两部分中剩余的元素添加到 merged 中
    merged += left_half[i:]
    merged += right_half[j:]
 
    return merged
```

#### 10 单调栈

```python
class Solution:
    def trap(self, height: List[int]) -> int:
        stack = []
        water = 0
        for i in range(len(height)):
            while stack and height[i] > height[stack[-1]]:
                top = stack.pop()
                if not stack:
                    break
                distance = i - stack[-1] - 1
                bounded_height = min(height[i], height[stack[-1]]) - height[top]
                water += distance * bounded_height
            stack.append(i)
        return water

```

关键就是 while 循环的设计，当不单调的时候依次比较末尾元素，并弹出操作


#### 5 区间问题
##### 5.1 区间合并
- 给出一堆区间，要求**合并**所有**有交集的区间** （端点处相交也算有交集）。最后问合并之后的**区间**。
- 如下图所示：

![img](https://pic4.zhimg.com/80/v2-6e3bb59ed6c14eacfa1331c645d4afdf_1440w.jpg)

<center>区间合并问题示例：合并结果包含 3 个区间</center>
- 解题步骤
	- 【**步骤一**】：按照区间**左端点**从小到大排序。
	- 【**步骤二**】：维护前面区间中最右边的端点为 ed。从前往后枚举每一个区间，判断是否应该将当前区间视为新区间。
	- 假设当前遍历到的区间为第 i 个区间 $[l_i,r_i]$，有以下两种情况：
		- $l_i \le ed$：说明当前区间与前面区间**有交集**。因此**不需要**增加区间个数，但需要设置 $ed = max(ed, r_i)$。
		- $l_i > ed$: 说明当前区间与前面**没有交集**。因此**需要**增加区间个数，并设置 $ed = max(ed, r_i)$。

##### 5.2 选择不相交区间
- 给出一堆区间，要求选择**尽量多**的区间，使得这些区间**互不相交**，求可选取的区间的**最大数量**。这里端点相同也算有重复。
- 如下图所示：

![img](https://pic1.zhimg.com/80/v2-690f7e53fd34c39802f45f48b59d5c5a_1440w.webp)

<center>选择不相交区间问题示例：结果包含 3 个区间</center>
- 【**步骤一**】：按照区间**右端点**从小到大排序。
- 【**步骤二**】：从前往后依次枚举每个区间。
	- 假设当前遍历到的区间为第 i 个区间 $[l_i,r_i]$，有以下两种情况：
		- $l_i \le ed$：说明当前区间与前面区间有交集。因此直接跳过。
		- $l_i > ed$: 说明当前区间与前面没有交集。因此选中当前区间，并设置 $ed = r_i$。

##### 5.3 区间选点问题
- 给出一堆区间，取**尽量少**的点，使得每个区间内**至少有一个点**（不同区间内含的点可以是同一个，位于区间端点上的点也算作区间内）
- 如下图所示：

![img](https://pica.zhimg.com/80/v2-a7ef021e1191ec53f20609ba870b44ba_1440w.webp)

<center>区间选点问题示例，最终至少选择 3 个点</center>
- 解题方法：同上找出最大不相交区间，会有一个点

##### 5.4 区间覆盖问题
- 给出一堆区间和一个目标区间，问最少选择多少区间可以**覆盖**掉题中给出的这段目标区间。
- 如下图所示： 
![img](https://pic3.zhimg.com/80/v2-66041d9941667482fc51adeb4a616f64_1440w.webp)

<center>区间覆盖问题示例，最终至少选择 2 个区间才能覆盖目标区间</center>
- 【**步骤一**】：按照区间左端点从小到大排序。
- 【**步骤二**】：**从前往后**依次枚举每个区间，在所有能覆盖当前目标区间起始位置 start 的区间之中，选择**右端点**最大的区间：
	- 假设右端点最大的区间是第 $i$ 个区间，右端点为 $r_i$。
	- 最后将目标区间的 start 更新成 $r_i$
- 注：考虑是否可以单序扫过整个片段

##### 5.5 区间分组问题
- **区间分组**问题大概题意就是：给出一堆区间，问最少可以将这些区间分成多少组使得每个组内的区间互不相交。
- 如下图所示： 

![img](https://pic2.zhimg.com/80/v2-6c6a045d481ddc44c66b046ef3e7d4cd_1440w.webp)

<center>区间分组问题示例，最少分成 3 个组</center>
- 【**步骤一**】：按照区间左端点从小到大排序。
- 【**步骤二**】：从**前往后**依次枚举每个区间，判断当前区间能否被放到某个现有组里面。
	- （即判断是否存在某个组的右端点在当前区间之中。如果可以，则不能放到这一组）
	- 假设现在已经分了 m 组了，第 k 组最右边的一个点是 $r_k$，当前区间的范围是 $[L_i,R_i]$ 。则：
		- 如果 $L_i \le r_k$ 则表示第 i 个区间无法放到第 k 组里面。反之，如果 $L_i > r_k$，则表示可以放到第 k 组。
		- 如果所有 m 个组里面没有组可以接收当前区间，则当前区间新开一个组，并把自己放进去。
		- 如果存在可以接收当前区间的组 k，则将当前区间放进去，并更新当前组的 $r_k = R_i$。
- **注意：**
	- 为了能快速的找到能够接收当前区间的组，我们可以使用**优先队列 （小顶堆）**。
	- 优先队列里面记录每个组的右端点值，每次可以在 O (1) 的时间拿到右端点中的的最小值

## 3 各种树的应用
完全二叉树：
指的是除最后一层外，其他层完全被占据，最后一层的节点都在左侧
表示：
通常采用数组储存，不用占用额外的指针空间
- 父节点 `i//2`
- 左孩子 `2*i`
- 右孩子 `2*i+1`
下面的三个例子都是完全二叉树的应用

最近公共祖先
```python
class Solution: 
def lowestCommonAncestor(self, root: TreeNode, p: TreeNode, q: TreeNode) -> TreeNode: 
if root in (None, p, q): return root 
left = self.lowestCommonAncestor(root.left, p, q) 
right = self.lowestCommonAncestor(root.right, p, q) 
if left and right: # 左右都找到 return root # 当前节点是最近公共祖先 return left or right 
```

验证二叉搜索树
```python
class Solution:  
    pre = -inf  
    def isValidBST(self, root: Optional[TreeNode]) -> bool:  
        if root is None:  
            return True  
        if not self.isValidBST(root.left):  # 左  
            return False  
        if root.val <= self.pre:  # 中  
            return False  
        self.pre = root.val  
        return self.isValidBST(root.right)  # 右
```
### Ⅰ 哈夫曼编码
哈夫曼编码是根据字符使用频率（freq）建立的一种最优的二叉编码树
基本思路是
1. 为每个字符创造一个节点，包括值和频率，并且按频率排序加入堆中
2. 弹出两个频率最小的节点，合并后值为 `None`, 频率 `freq=freq1+freq2`，`left=Node1`，`right=Node2` 再加入堆中
3. 如此重复，直到堆中只剩一个节点的时候，就搭建完哈夫曼树
```python
import heapq
class Node():
    def __init__(self,val,freq):
        self.val = val
        self.freq = freq
        self.left = None
        self.right = None
    def __lt__(self, other):
        if self.freq==other.freq:
            return self.val<other.val
        return self.freq < other.freq

n=int(input())
heap=[]
for i in range(n):
    char,freq=input().split()
    freq=int(freq)
    heap.append(Node(char,freq))
heapq.heapify(heap)
while len(heap)>1:
    left=heapq.heappop(heap)
    right=heapq.heappop(heap)
    node=Node(min(left.val,right.val),left.freq+right.freq)
    node.left=left
    node.right=right
    heapq.heappush(heap,node)
tree=heapq.heappop(heap)
```
### Ⅲ 二叉搜索树
- 这样意味着一个二叉搜索树的中序表达式就是顺序排列

思路：利用递归
```python
def insert(root, val):
    if not root:
        return TreeNode(val)
    if val < root.val:
        root.left = insert(root.left, val)
    elif val > root.val:
        root.right = insert(root.right, val)
    return root
```
### Ⅳ 前缀树
思路：
1. 创造一个节点类：1. 字典保存下一个字符 2. 判断是否为结尾
2. 字典可以用列表替代（空间会少一点？）
3. 注意：前缀树的前提是**按照字符长度排序**

```python
class TrieNode:
    def __init__(self):
        self.children = {}  # 字典保存子节点
        self.is_end_of_word = False  # 标记是否是单词结尾

class Trie:
    def __init__(self):
        self.root = TrieNode()  # 根节点

    def insert(self, word: str) -> None:
        current = self.root
        for char in word:
            if char not in current.children:
                current.children[char] = TrieNode()
            current = current.children[char]
        current.is_end_of_word = True  # 标记单词结束

    def search(self, word: str) -> bool:
        current = self.root
        for char in word:
            if char not in current.children:
                return False
            current = current.children[char]
        return current.is_end_of_word  # 必须精确匹配单词结尾

    def startsWith(self, prefix: str) -> bool:
        current = self.root
        for char in prefix:
            if char not in current.children:
                return False
            current = current.children[char]
        return True  # 只要前缀存在即可
```

### Ⅴ 并查集
并查集是用于高效管理集合的合并与查询
1. **`find(x)`**：查找元素 `x` 所属的集合（通常返回根节点）。
2. **`union(x, y)`**：合并 `x` 和 `y` 所在的集合。
3. **路径压缩** 和 **按秩合并** 优化，使操作接近 O (1)。

简化版本（去掉按秩合并）：
```python
    def __init__(self, n):
        self.parent = list(range(n))  # 初始化每个元素的父节点是自己

    def find(self, x):
        if self.parent[x] != x:
            self.parent[x] = self.find(self.parent[x])  # 路径压缩
        return self.parent[x]

    def union(self, x, y):
        x_root = self.find(x)
        y_root = self.find(y)
        if x_root != y_root:
            self.parent[y_root] = x_root  
```

加上按秩合并：
```python
class DisjointSet:
    def __init__(self, n):
        self.parent = list(range(n))  # 初始化每个元素的父节点是自己
        self.rank = [0] * n          # 按秩合并优化

    def find(self, x):
        if self.parent[x] != x:  # 路径压缩
            self.parent[x] = self.find(self.parent[x])
        return self.parent[x]

    def union(self, x, y):
        x_root = self.find(x)
        y_root = self.find(y)
        if x_root == y_root:  # 已经在同一集合
            return
        # 按秩合并（小树合并到大树）
        if self.rank[x_root] < self.rank[y_root]:
            self.parent[x_root] = y_root
        else:
            self.parent[y_root] = x_root
            if self.rank[x_root] == self.rank[y_root]:
                self.rank[x_root] += 1

```
### 拓扑排序
#### Ⅲ算法（BFS）(Kahn)
思路：在普通 BFS 的基础上维护节点的入度，每次选择入度为 0 的点（没有其他点在其之前）进入队列
1. 统计图中每个点的入度，储存进数组 indegree
2. 选取入度为 0 的节点加入队列
3. 从队列中弹出一个节点
	1. 将该节点加入 res
	2. 把该节点指向的所有节点入度减 1
4. 重复步骤 3，直到 len (q)=0
5. 比较 res 和节点数，判断是否存在 loop

```python
from collections import deque  

def topoSortBfs(self):
    inDeg = {node: 0 for node in self.graph}
    for node in self.graph:
        for adj in self.graph[node]:
            inDeg[adj] += 1

    q = deque([node for node, d in inDeg.items() if d == 0])
    res = []
    while q:
        u = q.popleft()
        res.append(u)
        for v in self.graph[u]:
            inDeg[v] -= 1
            if inDeg[v] == 0:
                q.append(v)
    
    # 检查结果长度是否包含所有节点，若否则存在环
    if len(res) != len(self.graph):
        return None
    return res
```
##### ✅ 无向图中判断是否有环
###### 1. DFS + visited + parent
这是最常见的方法。
- 使用 DFS（深度优先搜索）遍历图。
- 每次 DFS 时，记录当前节点的“父亲节点”。
- ==如果访问到了已经访问过的节点，且不是当前节点的父亲节点，说明存在环。==

**时间复杂度**：`O(V + E)`，其中 V 是节点数，E 是边数。

```python
def has_cycle_undirected(graph):
    visited = set()

    def dfs(node, parent):
        visited.add(node)
        for neighbor in graph[node]:
            if neighbor not in visited:
                if dfs(neighbor, node):
                    return True
            elif neighbor != parent:
                return True
        return False

    for node in graph:
        if node not in visited:
            if dfs(node, -1):
                return True
    return False
```
## 3 图的连通性问题

### 强连通分量 (SCC)
#### Ⅱ算法：tarjan

```python
def tarjan(graph):
    def dfs(node):
        nonlocal index, stack, indices, low_link, on_stack, sccs
        index += 1
        indices[node] = index
        low_link[node] = index
        stack.append(node)
        on_stack[node] = True
        
        for neighbor in graph[node]:
            if indices[neighbor] == 0:  # Neighbor not visited yet
                dfs(neighbor)
                low_link[node] = min(low_link[node], low_link[neighbor])
            elif on_stack[neighbor]:  # Neighbor is in the current SCC
                low_link[node] = min(low_link[node], indices[neighbor])
        
        if indices[node] == low_link[node]:
            scc = []
            while True:
                top = stack.pop()
                on_stack[top] = False
                scc.append(top)
                if top == node:
                    break
            sccs.append(scc)
    
    index = 0
    stack = []
    indices = [0] * len(graph)
    low_link = [0] * len(graph)
    on_stack = [False] * len(graph)
    sccs = []
    
    for node in range(len(graph)):
        if indices[node] == 0:
            dfs(node)
    
    return sccs

```
代码结构与变量说明
- **`graph`** : 输入的邻接表表示的有向图。
- **`index`** : 全局计数器，记录节点被访问的顺序（时间戳）。
- **`stack`** : 保存当前 DFS 路径中的节点，用于回溯形成 SCC。
- **`indices`** : 记录每个节点被访问时的索引（时间戳），初始化为 0 表示未访问。
- **`low_link`** : 记录节点能回溯到的最早的节点索引，初始化为 0。
- **`on_stack`** : 标记节点是否在栈中，避免重复处理。
- **`sccs`** : 存储所有找到的强连通分量。

核心函数：DFS 遍历

1. **初始化节点** ：
    - 当首次访问节点时，分配 `index` 和 `low_link` 值，节点入栈并标记 `on_stack` 为 True。
2. **遍历邻居节点** ：
    - **未访问的邻居** ：递归调用 DFS，递归返回后更新当前节点的 `low_link` 为当前值和邻居 `low_link` 的较小值。
    - **已访问且在栈中的邻居** ：说明存在回边，直接更新当前节点的 `low_link` 为当前值和邻居 `indices` 的较小值。
3. **识别 SCC 根节点** ：
    - 当节点的 `indices` 等于 `low_link` 时，该节点是 SCC 的根节点。此时弹出栈中所有后续节点直至当前节点，形成一个 SCC，并将其添加到结果列表。
算法执行流程
4. **遍历所有节点** ：确保每个未访问的节点都进行 DFS。
5. **SCC 的形成** ：通过栈的后进先出特性，确保每个 SCC 的节点按正确顺序弹出。


## 4 图的生成树问题
### **1）Kruskal**

目的：用最小的边权重链接所有的点（无向图）
思路：
1. 按照边的权重排序（从小到大）
2. 接下来开始链接点（如何表示链接？用并查集）
	1. 先判断是否链接
	2. 如果没有链接把他们连起来

```python
class DisjointSet:
    def __init__(self, num_vertices):
        self.parent = list(range(num_vertices))
        self.rank = [0] * num_vertices

    def find(self, x):
        if self.parent[x] != x:
            self.parent[x] = self.find(self.parent[x])
        return self.parent[x]

    def union(self, x, y):
        root_x = self.find(x)
        root_y = self.find(y)

        if root_x != root_y:
            if self.rank[root_x] < self.rank[root_y]:
                self.parent[root_x] = root_y
            elif self.rank[root_x] > self.rank[root_y]:
                self.parent[root_y] = root_x
            else:
                self.parent[root_x] = root_y
                self.rank[root_y] += 1


def kruskal(graph):
    num_vertices = len(graph)
    edges = []

    # 构建边集
    for i in range(num_vertices):
        for j in range(i + 1, num_vertices):
            if graph[i][j] != 0:
                edges.append((i, j, graph[i][j]))

    # 按照权重排序
    edges.sort(key=lambda x: x[2])

    # 初始化并查集
    disjoint_set = DisjointSet(num_vertices)

    # 构建最小生成树的边集
    minimum_spanning_tree = []

    for edge in edges:
        u, v, weight = edge
        if disjoint_set.find(u) != disjoint_set.find(v):
            disjoint_set.union(u, v)
            minimum_spanning_tree.append((u, v, weight))

    return minimum_spanning_tree
```

在上述代码中，`graph` 是一个二维矩阵，表示带权无向图的邻接矩阵。`graph[i][j]` 表示顶点 i 和顶点 j 之间的边的权重。

Kruskal 算法的时间复杂度为 O (ElogE)，其中 E 是边的数量。排序边集的时间复杂度为 O (ElogE)，并查集操作的时间复杂度为 O (Eα(V))，其中 α 是 Ackermann 函数的反函数，近似为常数。因此，总体上来说，Kruskal 算法的时间复杂度可以近似为 O (ElogE)。

### **2）Prim**
**Prim 算法的基本思想**
1. **初始化**：任选一个顶点作为起点，加入生成树。
2. **扩展生成树**：每次选择 **当前生成树到未加入顶点的最短边**，并将该边的另一个顶点加入生成树。
3. **重复**：直到所有顶点都加入生成树。

- Prim 适合稠密图（边多），Kruskal 适合稀疏图
```python
import heapq  
  
while True:  
    try:  
        n=int(input())  
        mat=[]  
        for i in range(n):  
            mat.append(list(map(int,input().split())))  
        res=0  
        h=[(0,0)]  
        heapq.heapify(h)  
        visit={0}  
        while h and len(visit)<n:  
            dist,cur=heapq.heappop(h)  
            if cur in visit:  
                continue  
            res+=dist  
            visit.add(cur)  
            for i,road in enumerate(mat[cur]):  
                if i==cur or i in visit:  
                    continue  
                heapq.heappush(h,(road,i))  
        print(res)  
    except EOFError:  
        break
```

## 最短路径

```python
import heapq

n, m = map(int, input().split())

# 使用邻接表替代邻接矩阵
adj = [[] for _ in range(n+1)]
for _ in range(m):
    a, b, w = map(int, input().split())
    adj[a].append((b, w))
    adj[b].append((a, w))

INF = float('inf')
dist = [INF] * (n + 1)  # 存储最短距离
dist[1] = 0
parents = {1: None}
heap = []
heapq.heappush(heap, (0, 1))

found = False
while heap:
    current_dist, u = heapq.heappop(heap)
    
    # 提前终止条件：找到目标节点
    if u == n:
        found = True
        break
        
    # 跳过已处理的更优路径
    if current_dist > dist[u]:
        continue
        
    for v, w in adj[u]:
        if dist[v] > dist[u] + w:
            dist[v] = dist[u] + w
            parents[v] = u ###在这里进行更新
            heapq.heappush(heap, (dist[v], v))

if found or dist[n] != INF:
    res = []
    current = n
    while current is not None:
        res.append(current)
        current = parents.get(current)
    res.reverse()
    print(' '.join(map(str, res)))
else:
    print(-1)
```

**多一个限制条件**
对于 Dijkstra 算法其实也能在多一个限制条件的情况下作用
回顾上面的算法，我们是在 `current_dist > dist[u]` 时进行了剪枝，但是在多一种限制条件的情况下我们就不能这么做

我们可以转而对距离进行排序，对另外一个限制条件进行记录并剪枝（因为如果距离短的另一个限制条件也少，那自然不用考虑）

```python
while stack:
            cost, cur, cnt = heapq.heappop(stack)
            if cur == dst:
                return cost
            if cnt >= visit[cur] or cnt > k:#利用限制条件进行剪枝
                continue
            visit[pos] = cnt
            for nex in dct[cur]:
                heapq.heappush(stack, [cost+dct[cur][nex], nex, cnt+1])

```

Bellman-ford
```python
# Bellman–Ford 核心：最多做 N 轮松弛
    for iteration in range(1, N + 1):
        updated = False
        for u, v, rate, fee in edges:
            if best[u] > fee:
                x = (best[u] - fee) * rate
                if x > best[v] + 1e-12:  # 加一点 eps 防止浮点误差
                    best[v] = x
                    updated = True

                    # 如果再次更新回了起始货币 S，且金额大于初始值，立刻输出 YES
                    if v == S and best[S] > V:
                        print("YES")
                        return

        # 如果第 N 轮仍有更新，说明存在正增益回路
        if iteration == N and updated:
            print("YES")
            return

        # 没有任何更新，可提前结束
        if not updated:
            break
```
