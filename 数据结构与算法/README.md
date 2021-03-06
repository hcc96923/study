### 数据结构与算法
- 1.学习数据结构与算法为了大厂的面试
- 2.理解第三方库框架的原理，这些基础框架一般都是用数据结构与算法
- 3.写出更高效的代码更快更省的代码
### 高效学习数据结构与算法
- 1.数据结构就是指一组数据的存储结构组织方式，算法就是操作数据的一组方法
- 2.数据结构就是指数据在内存中摆放的方式，而算法就是操作这些数据的方法
- 3.数据结构是为算法服务的，算法要作用在特定的数据结构之上才能更高效的运行
- 4.学习它的来历，自身的特点，适合解决的问题以及实际的应用场景
- 5.学知识的过程是反复迭代，不断沉淀的过程
- 6.每周周末把本周学习的数据结构与算法的题练习一遍
### 最常用的数据结构与算法
- 10个数据结构：数组，链表，队列，二叉树，栈，堆，散列表，图，跳表，Trie树
- 10个算法：递归，排序，二分查找，搜索，哈希算法，分治算法，贪心算法，回溯算法，动态规划，字符串匹配算法
### 时间复杂度
- 1.大O时间复杂度表示**代码执行时间随数据规模增长的变化趋势**也叫渐进时间复杂度。T(n) = O(2n+2)
- 2.当n很大时那些常量就可以忽略，因为它们不足以影响变化趋势或者对变化趋势的影响很小。T(n) = O(n)
- 3.计算时间复杂度的三个方法：
  - 3.1只关注循环次数最多的一段代码
    - 我们通常会忽略掉公式中的常量、低阶、系数，只需要记录一个最大阶的量级就可以了
    - 我们在分析一个算法、一段代码的时间复杂度的时候，也只关注循环执行次数最多的那一段代码就可以了
  - 3.2总复杂度等于量级最大的那段代码的复杂度
    - 比如一个复杂度为O(n2+n+10000) => O(n2)，这里的n和10000都对增长趋势没有影响
  - 3.3嵌套代码的复杂度等于嵌套内外代码复杂度的乘积
  - 一个函数有1000行赋值语句它的复杂度也是O(1)因为代码总的执行时间并没有因为数据量的改变而改变
- 时间复杂度：表示算法的执行时间与数据规模之间的增长关系。
  - 常见的复杂度有：O(1)，O(logn)等比数列，O(n)，O(nlogn)，O(n2)，O(n3)，O(2n)，O(!n)
- 空间复杂度：表示算法的存储空间与数据规模之间的增长关系。
  - 常见的复杂度有：O(1)，O(n)，O(n2)
- 只要代码的执行时间不随n的增大而增长这样代码的时间复杂度都为O(1)
- 最好情况时间复杂度。
- 最坏情况时间复杂度。
- 平均情况时间复杂度。
- 均摊时间复杂度。
### 空间复杂度
- 1.表示算法的存储空格键与数据规模之间的增长关系也叫渐进空间复杂度
- 2.空间复杂度指的是除了原本的数据存储空间外，算法运行还需要额外的存储空间
### 数组
- 数组是一种线性表数据结构。它用一组连续的内存空间，常见的线性数据结构还有数组，链表，队列，栈，跳表，散列表。
- 线性表的特点是数据之间是简单的前后关系/相反非线性表二叉树，堆，图就不是简单的前后关系
- 数组存储的数据在内存中的地址是连续的，这也是其支持快速随机访问的原因。
- `a[i]_address = base_address + i * data_type_size`。根据首地址，要查找的元素的索引，元素的内存大小就可以计算出要查找的元素的地址。
- 数组查找的时间复杂度为O(1)。插入和删除的时间复杂度为O(n)。
- 插入或删除第k个元素则为了保持数组中的元素在内存中的连续性，所以需要移动k-n个元素的位置，这就是数组插入和删除低效率的原因。因为我们在每个位置插入的概率一样所以平均情况时间复杂度为(1+2+3+...+n)/n = O(n)
### 链表
- 链表分为单项链表，循环链表，双向链表。
- 单向链表：头节点记录了链表的基地址，有了它就可以遍历整个链表，尾节点的指针指向null表示这是链表的最后一个节点。
  - 在链表中进行插入与删除的操作是非常快速的。O(1)（实际上这种说法并不准确，删除或者插入也需要知道要操作的节点的前置节点还是需要遍历，只不过插入/删除这一行操作的时间复杂度是O(1)）。当然没有完美的数据结构，链表的查找相较于数组就比不上了。因为它需要遍历所有的节点去找出要查找的节点。可以把链表当作一个队伍，队伍中的每人都知道自己后面是谁，所以当我们要找出第k位的人是谁的时候，就需要从第一个人开始，一个一个地往下数。O(n)
- 循环链表：是一种特殊的单向链表。循环链表的尾节点的指针指向链表的头节点。
- 双向链表有两个指针prev和next分别指向了前置节点和后直节点这样无论是查找还是插入和删除相比单项链表效率都要提高很多（空间换时间）
### 栈
- LIFO先进后出操作受限制的线性数据结构
- 栈是如何实现浏览器的前进后退？
- 两个栈A和B
- 首次浏览的页面压入栈A，后退的时候再依次从A中出栈压入栈B
- 再点击前进的时候再从栈B弹出
### 队列
- FIFO先进先出操作受限制的线性数据结构一端入队列另一端出队列
- 队列可以把它想象成排队吃饭，后来的人只能在后面不能插队，先来的可以先买饭
### 递归
- 递归需要满足的三个条件
- 1.一个问题的解可以分解为几个子问题的解
- 2.这个问题与分解之后的子问题除了数据规模不同，求解思路完全一样
- 3.**存在递归终止的条件**
- 4.写出递推公式找出终止条件
- 编写递归代码的关键是，只要遇到递归，我们就把它抽象成一个地推公式，不用想一层层的调用关系
- 不要试图用人脑去分解递归的每个步骤
### 排序
- 带着问题去学习是最有效的学习方法？插入排序实际比冒泡排序使用的更多
- 考量排序算法的好坏有三个方面
  - 1.排序算法的效率
    - 1.1最好，最坏，平均情况时间复杂度
    - 1.2时间复杂度的系数，常数，低阶
    - 1.3比较次数和交换（或移动）次数
  - 2.排序算法的内存消耗
    - 2.1针对排序算法的空间复杂度。原地排序算法就是特指空间复杂度是O(1)的排序算法
  - 3.排序算法的稳定性
    - 3.1稳定性就是指：待排序的序列中存在值相等的元素，经过排序之后，相等元素之间原有的先后顺序不变
- 冒泡排序，插入排序，选择排序O(n2)
  - 1.冒泡排序
    - 1.1冒泡排序只会操作**相邻的两个数据**。每次冒泡都会对相邻的两个元素进行比较，看是否满足大小关系要求。如果不满足就交换他们俩的位置。一次冒泡至少会让一个元素移动到它改在的位置，重复n次，就完成了n个数据的排序工作
  - 2.插入排序
    - 2.1将数组中的数据分为两个区间，已排序区间和未排序区间。初始已排序区间只有一个元素就是数组的第一个元素。插入算法的核心思想是提取未排序区间的元素，在已排序区间寻找合适的位置插入，并保证已排序区间始终有序。重复这个过程，直到未排序区间元素为空。
  - 3.选择排序 
    - 3.1选择排序首先在未排序的数组中找到最小的元素放到已排序区间，然后从剩余的未排序区间中找最小的元素放到已排序区间的末尾
    - 3.2选择排序不是稳定的排序算法
- 归并排序，快速排序O(nlogn)
  - 1.归并排序
    - 1.1创建一个临时存储数组temp，比较两数组第一个元素，将较小的元素加入临时数组若左右数组有一个为空，那么此时另一个数组一定大于temp中的所有元素，直接将其所有元素加入temp
  - 2.快速排序
    - 2.1通过一趟排序将要排序的数据分割成独立的两部分，其中一部分的所有数据比另一部分的所有数据要小，再按这种方法对这两部分数据分别进行快速排序
### 二分查找
- 二分查找针对的是一个**有序的数据集合**，查找思想有点类似分治思想。每次都通过跟区间的中间元素对比，将待查找的区间缩小为之前的一半，直到找到要查找的元素，或者区间被缩小为 0
- 不适合数据量太小或太大的查找太小的可以直接遍历查找，二分查找的底层依赖数组的索引查找而数组必须是连续的内存空间所以较大的数据也不适合用二分查找
- 时间复杂度O(logn)。每次折半——等比数列
- 如何快速通过 IP 地址来查找 IP 归属地的功能
### 跳表
- Redis用的就是跳表
- 跳表使用空间换时间的设计思路，通过构建多级索引来提高查询的效率，实现了基于链表的“二分查找”。跳表是一种动态数据结构，支持快速地插入、删除、查找操作，时间复杂度都是 O(logn)。
- 跳表的空间复杂度是 O(n)。
### 散列表
- 散列表用的是数组支持按照下标随机访问数据的特性，所以散列表其实就是数组的一种扩展，由数组演化而来。可以说，如果没有数组，就没有散列表
- 散列表用的就是数组支持按下标随机访问的特点，时间复杂度O(1).通过散列函数把元素的键值映射为下标然后将数据存储在数组中对应下标的位置。按照键值查询元素时，用同样的散列函数，将键值转换为数组下标，从对应数组下标的位置读取数据
- 相同的值经过散列函数得到的散列值也应该是相等的
- 散列表两个核心问题是散列函数设计和散列冲突解决。散列冲突有两种常用的解决方法，开放寻址法和链表法。
- 哈希算法的应用：安全加密（MD5，SHA256，SHA384），唯一标识（标识文件），数据校验（例如BT下载的P2P协议一个2GB的文件分布在不同的计算机上，每一台计算机上的一部分文件都代表一部分哈希值，种子文件存储了整个文件合成之后的哈希值）
### 二叉树
- 二叉树，顾名思义，每个节点最多有两个“叉”，也就是两个子节点，分别是左子节点和右子节点。
- 二叉树有的只有左子节点有的只有右子节点
- 满二叉树：所有的叶子节点都在最底层，除了叶子节点所有的节点都有左子节点和右子节点
- 叶子节点都在最底下两层，最后一层的叶子节点都靠左排列，并且除了最后一层，其他层的节点个数都要达到最大，这种二叉树叫做完全二叉树
- 二叉树的遍历：前序遍历，中序遍历，后序遍历