# Python后端

## Python后端技术栈

### Web请求的流程

* 浏览器
* 负载均衡
* Web框架
* 业务逻辑
* 数据库缓存

### Python语言基础

* 语言特点
* 语法基础
* 高级特性

### 算法与数据结构

* 常用算法和数据结构
* 分析时间、控件复杂度
* 实现常见数据结构和算法

### 编程范式

* 面向对象编程
* 常用设计模式
* 函数式编程

### 操作系统

* 常用Linux命令
* 进程、线程
* 内存管理

### 网络编程

* 常用协议TCP、IP、HTTP
* Socket编程基础
* Python并发库

### 数据库

* Mysql常考，索引优化
* 关系型和NoSQL的使用场景
* Redis缓存

### Python Web框架

* 常用框架对比，RESTful
* WSGI原理
* Web安全问题

### 系统设计

* 设计原则，如何分析
* 后端系统常用组件（缓存、数据库、消息队列等）
* 技术选型和实现（短网址服务、Feed流系统）

### 技术之外，软实力

* 学习能力
* 业务理解能力，沟通交流能力
* 心态

## Python初、中级工程师技能要求

### 初级工程师

* 扎实的计算机理论基础
* 代码规范，风格良好
* 能在指导下靠谱地完成业务要求

### 中级工程师

* 扎实的计算机基础和丰富的项目经验
* 能够独立设计和完成项目要求
* 熟悉成员web组件（缓存、消息队列），具有一定的系统设计能力

### 软技能

* 具有产品意识，技术引导产品
* 沟通交流嫩合理，团队协作能力
* 技术领导能力和影响力

### 面试准备

* 工作内容和业务紧密相关
* 平台决定成长（业务体量）
* 准备面试需要有的放矢，跟职位相匹配

## 简历书写与自我介绍

### 简历内容

* 基本信息（姓名、学校、学历、联系方式等）
* 职业技能（编程语言、框架、数据库、开发工具等）
* 关键项目经验（担任职责，用到了哪些技术）

### 简历加分项

* 知名项目经验
* 技术栈比较匹配 
* 开源项目（GitHub、技术blog、Linux、unix geek）

### 简历注意事项

* 内容精简、突出重点。不宜超过两页、可以套用模板
* 主要格式，推荐PDF
* 信息真实，不弄虚作假。技能要和岗位匹配

### 自我介绍

* 个人信息
* 掌握的技术，参与过的项目
* 应聘的岗位，表达对该岗位的看法和兴趣

![](https://resource-1256956499.cos.ap-beijing.myqcloud.com/img/20190310223336.png)

## 行为面试题与表达技巧

### 什么是行为面试

> 根据候选人过去的行为评测其胜任能力

* 理论依据：行为的连贯性
* 人在面对相似的场景时会倾向于重复过去的行为模式
* 评判人的业务能力，沟通交流能力，语言表达能力，坑压能力等

### 行为面试套路

* 提问方式：说说你曾经
* 说说你做过的这个项目
* 说说你碰到过的技术难题？你是如何解决的？有哪些收获？

### STAR模型

![](https://resource-1256956499.cos.ap-beijing.myqcloud.com/img/20190310223957.png)

### 面试官一般会问：你还有什么要问我的吗？

* 千万别说没了，直接说表明你对岗位缺乏了解和兴趣
* 表现出兴趣：提问工作内容（业务）、技术栈、团队、项目等
* 问自己的感兴趣的问题

### 注意事项

* 态度真诚，力求真实，不要弄虚作假
* 言简意赅，突出重点，省略细枝末节。适当模拟训练
* 采用STAR模型让回答更有条理

## Python语言基础常见考题

### Python是静态还是动态类型？是强类型还是弱类型？

* 动态强类型语言
* 动态还是静态指的是编译期还是运行期确定类型
* 强类型指的是不会发生隐式类型转换

### Python作为后端语言优缺点

* 胶水语言，轮子多，应用广泛
* 语言灵活，生成力高
* 性能问题、代码维护问题、Python2、3兼容问题

### 什么是鸭子类型

* 关注点在对象的行为，而不是类型（duck typing）
* 比如file，StringIO，socket对象都支持read/write方法
* 再比如定义了`__iter__`魔术方法的对象可以用for迭代

### 什么是monkey patch

* 所谓的monkey patch就是运行时替换
* 比如gevent库需要修改内置的socket
* from gevent import monkey; monkey.patch_socket()

### 什么是自省（Introspection）

* 运行时判断一个对象的类型的能力
* Python一切皆对象，用type，id，isinstance获取对象类型信息
* Inspect模块提供了更多获取对象信息的函数

### 什么是列表和字典推导式（List Comprehension）

* 比如`[i for i in range(10) if i % 2 == 0]`
* 一种快速生成list、dict、set的方式。用来替代map、filter等
* `(i for i in range(10))`返回生成器

 ## Python2/3对比

### Python3改进

* print成为函数

* 编码问题。Python3不再有Unicode对象，默认str就是unicode

* 除法变化。Python3返回浮点数

* 类型注解（type hint）。帮助IDE实现类型检查

  * ```python
    def hello(name: str) -> str:
        return 'hello' + name
    ```

* 优化的super()方便直接调用父类函数

  * ```python
    class Base(object):
        def hello(self):
            print('say hello')
     
    class C(Base):
        def hello(self):
            # py2
            return super(C, self).hello()
        
    class C2(Base):
        def hello(self):
            # py3
            return super().hello()
    ```

* 高级解包操作。`a, b, *rest = range(10)`

* Keyword only arguments。限定关键字参数

  * ```python
    def add(a, b, *, c):
        print(a+b+c)
        
    # 会报错
    add(1, 2, 3)
    # 正确写法
    add(1, 2, c=3)
    ```

* Chained exceptions。Python3重新抛出异常不会丢失栈信息
* 一切返回迭代器range, zip, map, dict.values, etc. are all iterators.
* 生成的pyc文件统一放在`__pycache__`
* 一些内置库的修改。urllib，selector等
* 性能优化等

### Python3新增

* yield from链接子生成器
* asyncio内置库，async/await原生协程支持异步编程
* 新的内置库enum,mock,asyncio,ipaddress,concurrent.futures等

### Python2/3工具

* six模块
* 2to3等工具转换代码
* `__future__`

## Python函数常考题

### 以下Python代码分别输出什么？

* ```python
  def flist(l):
      l.append(0)
      print(l)
  
  l = []
  flist(l) #[0]
  flist(l) #[0, 0]
  ```

* ```python
  def fstr(s):
      s + = 'a'
      print(s)
      
  s = 'hehe'
  fstr(s) #'hehea'
  fstr(s) #'hehea'
  ```

* 可变类型参数

* 不可变类型参数

### Python如何传递参数？

* 传递值还是引用呢？都不是。唯一支持的参数传递是共享传参
* Call by Object (Call by Object Reference or Call by sharing)
* Call by sharing(共享传参)。参数形参获得实参中各个引用的副本

### Python可变/不可变对象

* 不可变bool int float tuple str frozenset
* 可变list set dict

### 测试

```python
# 一个小例题，请问这段代码会输出什么结果？
# first
def clear_list(l):
    l = []
    
ll = [1, 2, 3]
clear_list(ll)
print(ll)

# second
# 默认参数只计算一次
def flist(l=[1]):
    l.append(1)
    print(l)
    
flist()
flist()
```

### Python *args, *kwargs

* 用来处理可变参数
* `*args`被打包成tuple
* `**kwargs`被打包成dict

## Python异常机制常考题

### 什么是Python异常？

* Python使用异常处理错误
  * BaseException
    * SystemExit/KeyboardInterrupt/GeneratorExit
    * Exception

### 什么时候需要捕获处理异常？看Python内置异常类型

* 网络请求（超时、链接错误等）
* 资源访问（权限问题、资源不存在）
* 代码逻辑（越界访问、KeyError等）

### 如何处理Python异常

```python
try:
    # func                            # 可能会抛出异常的代码
except (Exception1, Exception2) as e: # 可以捕获多个异常并处理
    # 异常处理代码
else:
    pass                              # 异常没有发生的时候代码逻辑
finally:
    pass                              # 无论异常有没有发生都会执行的代码，一般处理资源的关闭和释放
    
```

### 如何自定义异常

* 继承Exception实现自定义异常（想想为什么不是BaseException）
* 给异常加上一些附加信息
* 处理一些业务相关的特定异常（rasie MyException）

```python
class MyException(Exception):
    pass 

try:
    raise MyException('my exception')
except MyException as e:
    print(e)
```

## Python性能分析与优化，GIL常考题

### 什么是Cpython GIL

* GIL, Global Interpreter Lock
* Cpython解释器的内存管理并不是线程安全的
* 保护多线程情况下Python对象的访问
* Cpython使用简单的锁机制避免多个线程同时执行字节码

### GIL影响

* 限制了程序的多核执行
  * 同一时间只能有一个线程执行字节码
  * CPU密集程序难以利用多核优势
  * IO期间会释放GIL，对IO密集程序影响不大（爬虫，web）
* ![](https://resource-1256956499.cos.ap-beijing.myqcloud.com/img/20190314112533.png)

### 如何规避GIL影响

* CPU密集可以使用多进程
* IO密集可以使用多进程、协程
* cython扩展

![](https://resource-1256956499.cos.ap-beijing.myqcloud.com/img/20190314112754.png)

### 问题

```python
import threading

n = [0]

def foo():
    n[0] = n[0] + 1
    n[0] = n[0] + 1
    
threads = []
for i in range(50000):
    t = threading.Thread(target=foo)
    threads.append(t)
    
for t in threads:
    t.start()
    
print(n)

# 大多数情况下打印10000，偶尔打印9998，Python的多线程并不是绝对安全的
```

### 为什么有了GIL还要关注线程安全

* Python中什么操作才是原子的？一步执行到位
  * 一个操作如果是一个字节码指令可以执行完成的就是原子的
  * 原子的是可以保证线程安全的
  * 使用dis操作才分析字节码

```python
import dis

def update_list(l):
    # 原子操作，不用担心线程安全问题
    l[0] = 1
    
dis.dis(update_list)
'''
  5           0 LOAD_CONST               1 (1)
              2 LOAD_FAST                0 (l)
              4 LOAD_CONST               2 (0)
              6 STORE_SUBSCR             # 字节码操作，线程安全
              8 LOAD_CONST               0 (None)
             10 RETURN_VALUE
'''

def incr_list(l):
    # 危险！不是原子操作
    l[0] += 1
   
dis.dis(incr_list)
'''
  3           0 LOAD_FAST                0 (l)
              2 LOAD_CONST               1 (0)
              4 DUP_TOP_TWO
              6 BINARY_SUBSCR
              8 LOAD_CONST               2 (1)
             10 INPLACE_ADD              # 需要多个字节码操作，有可能在线程执行过程中切到其他线程
             12 ROT_THREE
             14 STORE_SUBSCR
             16 LOAD_CONST               0 (None)
             18 RETURN_VALUE
'''
```

### 如何剖析程序性能

* 使用各种profile工具（内置或者第三方）
  * 二八定律，大部分时间花费在少量代码上
  * 内置的profile、cprofile等工具
  * 使用pyflame（uber开源）的火焰图工具

### 服务端性能优化措施

* web应用一般语言不会成为瓶颈
  * 数据结构和算法
  * 数据库层：索引优化，慢查询消除，批量操作减少IO，NoSQL
  * 网络IO：批量操作，pipeline操作减少IO
  * 缓存：使用内存数据库redis/memcached
  * 异步：asyncio，celery
  * 并发：gevent/多线程

## Python生成器与协程

### 生成器（Generator）

* 生成器就是可以生成值的函数
* 当一个函数里有了yield关键字就成了生成器
* 生成器可以挂起执行并且保持当前执行状态

```python
def simple_gen():
    yield 'hello'
    yield 'world'

gen = simple_gen()
print(type(gen))
print(next(gen))
print(next(gen))
'''
<class 'generator'>
hello
world
'''
```

### 基于生成器的协程

* Python3之前没有原生协程，只有基于生成器的协程
  * PEP 342(Coroutines via Enhanced Generators)增强生成器功能
  * 生成器可以通过yield暂停执行和产出数据
  * 同时支持send()向生成器发送数据和throw()向生成器抛出异常

```python
def coro():
    # yield关键字在=右边作为表达式，可以被send值
    hello = yield 'hello'
    yield hello

c = coro()
# 输出'hello'，这里调用next产出第一个值'hello'，之后函数暂停
print(next(c))
# 再次调用send发送值，此时hello变量赋值为'world'，然后yield产出hello变量的值'world'
print(c.send('world'))
# 之后协程结束，后续再send值会抛出异常StopIteration
```



### 协程注意点

* 协程需要使用send(None)或者next(coroutine)来[预激]（prime）laiqidong
* 在yield处协程会暂停执行
* 单独的yield value会产出值给调用方
* 可以通过coroutine.send(value)来给协程发送值，发送的值会赋值给yield左边的变量value = yield
* 协程执行完成后（没有遇见下一个yield语句）会抛出StopIteration异常

### 协程装饰器

* 避免每次都要用send预激它

```python
from functools import wraps

def coroutine(func):
    '''
    装饰器：向前执行一个yield表达式，预激func
    '''
    @wraps(func)
    def primer(*args, **kwargs):
        gen = func(*args, **kwargs)
        next(gen)
        return gen
    return primer
```

### Python3.5引入async/await支持原生协程（native coroutine）

```python
import asyncio
import datetime
import random

async def display_date(num, loop):
    end_time = loop.time() + 50.0
    while True:
        print('Loop: {} Time: {}'.format(num, datetime.datetime.now()))
        if (loop.time() + 1.0) >= end_time:
            break
        await asyncio.sleep(random.randint(0, 5))
        
      
loop = asyncio.get_event_loop()
asyncio.ensure_future(display_date(1, loop))
asyncio.ensure_future(display_date(2, loop))
loop.run_forever()
```

## Python单元测试

### 什么是单元测试

* Unit Testing
  * 针对程序模块进行正确性检验
  * 一个函数，一个类进行验证
  * 自底向上保证程序正确性

### 为什么写单元测试

* 三无代码不可取（无文档、无注释、无单测）
  * 保证代码逻辑的正确性（甚至有些采用测试驱动开发（TDD））
  * 单测影响设计，易测的代码往往是高内聚低耦合的
  * 回归测试，防止改一处整个服务不可用

### 单元测试相关的库

* nose/pytest较为常用
* mock模块用来模拟替换网络请求等
* coverage统计测试覆盖率

```python
def binary_search(arr, target):
    if not arr:
        return -1
    low, high = 0, len(arr) - 1
    while low <= high:
        mid = low + (high - low) >> 2
        if arr[mid] == target:
            return mid
        elif arr[mid] > target:
            high = mid - 1
        else:
            low = mid + 1
    return - 1


def test():
    '''
    如何设计测试用例：
    - 正常值功能测试
    - 边界值(比如最大最小，最左最右)
    - 异常值(比如None，空值，非法值)
    '''
    # 正常值，包含有和无两种结果
    assert binary_search([0, 1, 2, 3, 4, 5], 1) == 1
    assert binary_search([0, 1, 2, 3, 4, 5], 6) == -1
    assert binary_search([0, 1, 2, 3, 4, 5], -1) == -1
    # 边界值
    assert binary_search([0, 1, 2, 3, 4, 5], 0) == 0
    assert binary_search([0, 1, 2, 3, 4, 5], 5) == 5
    assert binary_search([0], 0) == 0
    # 异常值
    assert binary_search([], 1) == -1
```

## Python基础练习题

### Python深拷贝与浅拷贝

* 什么是深拷贝？什么是浅拷贝？
* Python中如何实现深拷贝？
* 思考：Python中如何正确初始化一个二维数组？

```python
import copy

l1 = [1, 2, 3]
l2 = l1
l3 = copy.copy(l1)
l4 = copy.deepcopy(l1)
print(l1, l2, l3, l4)
'''
[1, 2, 3] [1, 2, 3] [1, 2, 3] [1, 2, 3]
'''
l2[0] = 666
print(l1, l2, l3, l4)
'''
[666, 2, 3] [666, 2, 3] [1, 2, 3] [1, 2, 3]
'''
l3[0] = 888
print(l1, l2, l3, l4)
'''
[666, 2, 3] [666, 2, 3] [888, 2, 3] [1, 2, 3]
'''
l4[0] = 999
print(l1, l2, l3, l4)
'''
[666, 2, 3] [666, 2, 3] [888, 2, 3] [999, 2, 3]
'''
```

## Python内置数据结构和算法常考

| 数据结构/算法 | 语言内置                  | 内置库                                            |
| ------------- | ------------------------- | ------------------------------------------------- |
| 线性结构      | list、tuple               | array(数组，不常用)/collections.namedtuple        |
| 链式结构      |                           | collections.deque(双端队列)                       |
| 字典结构      | dict                      | collections.Counter(计数器)/OrderedDict(有序字典) |
| 集合结构      | set/frozenset(不可变集合) |                                                   |
| 排序算法      | sorted                    |                                                   |
| 二分算法      |                           | bisect模块                                        |
| 堆算法        |                           | heapq模块                                         |
| 缓存算法      |                           | functools.lru_cache(Least Recent Used, python3)   |

### collections模块提供了一些内置数据结构的扩展

* namedtuple

```python
import collections

Point = collections.namedtuple('Point', 'x, y')
p = Point(1, 2)
print(p.x)
'''
1
'''
print(p.y)
'''
2
'''
print(p.x == p[0])
'''
True
'''
```

* deque

```python
import collections

de = collections.deque()
de.append(1)
de.appendleft(0)
print(de)
'''
deque([0, 1])
'''
de.pop()
'''
1
'''
de.popleft()
'''
0
'''
print(de)
'''
deque([])
'''
```

* Counter
* OrderedDict(使用循环双端链表保存key的顺序)
* defaultdict

### Python dict底层结构

* dict底层使用哈希表
  * 为了支持快速查找使用了哈希表作为底层结构
  * 哈希表平均查找时间复杂度O(1)
  * Cpython解释器使用二次探查解决哈希冲突问题

### Python list/tuple区别

* 都是线性结构，支持下标访问
* list是可变对象，tuple保存的引用不可变

```python
t = [1,2], 1, 2
t[0].append(3)
print(t)
'''
([1, 2, 3], 1, 2)
'''
```

* list无法作为字典的key，tuple可以（可变对象不可hash）

### 什么是LRUCache？

* Least-Recently-Used替换掉最近最少使用的对象
  * 缓存剔除策略，当缓存空间不够用的时候需要一种方式剔除key
  * 常见的有LRU, LFU等
  * LRU通过使用一个循环双端队列不断的把最新访问的key放到表头实现

* 字典用来缓存，循环双端链表用来记录访问顺序
  * 利用Python内置的dict+collections.OrderedDict实现
  * dict用来当做k/v键值对的缓存
  * OrderedDict用来实现最新最近访问的key

## Python常考算法

### 排序+查找，重中之重

* 常考排序算法：冒泡排序、快速排序、归并排序、堆排序
* 线性查找，二分查找
* 能独立实现代码（手写），能够分析时间空间复杂度

**常见排序算法的时空复杂度**

| 排序算法 | 最差时间复杂度 | 平均时间复杂度 | 稳定度 | 空间复杂度    |
| -------- | -------------- | -------------- | ------ | ------------- |
| 冒泡排序 | O(n^2)         | O(n^2)         | 稳定   | O(1)          |
| 选择排序 | O(n^2)         | O(n^2)         | 不稳定 | O(1)          |
| 插入排序 | O(n^2)         | O(n^2)         | 稳定   | O(1)          |
| 快速排序 | O(n^2)         | O(n*log2n)     | 不稳定 | O(log2n)~O(n) |
| 堆排序   | O(n*log2n)     | O(n*log2n)     | 不稳定 | O(1)          |

### 排序算法的稳定性

* 相同大小的元素在排序之后依然保持相对位置不变，就是稳定的
* `r[i]=r[j]`且`r[i]`在`r[j]`之前，排序之后`r[i]`依然在`r[j]`之前
* 稳定性对于排序一个复杂结构，并且需要保持原有排序才有意义

### 请写出快速排序

* 快排经常问：分治法(divide and conquer)，快排三步走
  * Partition：选择基准分割数组为两个子数组，小于基准和大于基准的
  * 对两个子数组分别快排
  * 合并结果

```python
def quicksort(array):
  # 递归出口
  if len(array) < 2:
    return array
  else:
    pivot_index = 0
    pivot = array[pivot_index]
    less_part = [i for i in array[pivot_index+1:] if i <= pivot]
    great_part = [i for i in array[pivot_index+1:] if i > pivot]
    return quicksort(less_part) + [pivot] + quicksort(great_part)
 
def test_quicksort():
    import random
    l = list(range(10))
    random.shuffle(l)
    print('排序前：', l)
    res = quicksort(l)
    print('排序后：', res)
    assert res == sorted(l)
```

### 合并两个有序数组

* 要求m+n复杂度内

```python
def merge_sorted_list(sorted_a, sorted_b):
    len_a, len_b = len(sorted_a), len(sorted_b)
    a = b = 0
    res = []
    while a < len_a and b < len_b:
        if sorted_a[a] < sorted_b[b]:
            res.append(sorted_a[a])
            a += 1
        else:
            res.append(sorted_b[b])
            b += 1
    if a < len_a:
        res.extend(sorted_a[a:])
    else:
        res.extend(sorted_b[b:])
    return res

res = merge_sorted_list([0,3,6,7],[0, 0, 23,33])
print(res)
```

### 归并排序

```python
def mergesort(array):
    # 递归出口
    if len(array) <= 1:
        return array
    else:
        mid = int(len(array)/2)
        left_half = mergesort(array[:mid])
        right_half = mergesort(array[mid:])
        return merge_sorted_list(left_half, right_half)
```

### 堆排序

```python
# 借助heapq模块
def heapsort_use_heapq(iterable):
    from heapq import heappush, heappop
    items = []
    for value in iterable:
        heappush(items, value)
    return [heappop(items) for i in range(len(items))]
```

### 二分查找

```python
def binary_search(sorted_array, val):
    if not sorted_array:
        return -1
    start = 0
    end = len(sorted_array) - 1
    while start <= end:
        mid = start + ((end - start) >> 2)
        if sorted_array[mid] == val:
            return mid
        elif sorted_array[mid] > val:
            end = mid - 1
        else:
            start = mid + 1
    return -1
```

## Python常考数据结构

### Python web后端常考数据结构

* 常见的数据结构链表、队列、栈、二叉树、堆
* 使用内置的结构实现高级数据结构，比如内置的list/deque实现栈
* LeetCode或者剑指Offer上的常考题

### 链表

**链表有单链表、双链表、循环双端链表**

* 如何使用Python来表示链表结构

* 实现链表常见操作，比如插入节点，反转链表，合并多个链表等

* LeetCode练习常见链表题目

    * 206反转链表

        ```python
        class ListNode:
            def __init__(self, x):
                self.val = x
                self.next = None
                
        class Solution:
            def reverseList(self, head):
                '''
                :type head: ListNode
                :rtype ListNode
                '''
                pre, cur = None, head
                while cur:
                    cur.next, pre, cur = pre, cur, cur.next
                return pre
        ```

### 队列

**队列（queue）是先进先出结构**

* 如何使用Python实现队列？
* 实现队列的append和pop操作，如何做到先进先出
* 使用collections.deque实现队列

```python
from collections import deque

class Queue:
    def __init__(self):
        self.items = deque()
        
    def append(self, val):
        return self.items.append(val)
        
    def pop(self):
        return self.items.popleft()
    
    def empty(self):
        return len(self.items) == 0
```

### 栈

* 如何使用Python实现栈？
* 实现栈的push和pop操作，如何做到先进后出
* 使用collections.deque实现队列

```python
from collections import deque

class Stack:
    def __init__(self):
        self.itmes = deque()
      
    def push(self, val):
        self.items.append(val)
        
    def pop(self, val):
        return self.items.pop()
      
    def empty(self):
        return len(self.items) == 0
```

### 字典与集合

**Python dict/set底层都是哈希表**

* 哈希表的实现原理，底层其实就是一个数组
* 根据哈希函数快速定位一个元素，平均查找O(1)
* 不断加入元素会引起哈希表重新开辟空间，拷贝之前的元素到新数组

**哈希表如何解决冲突**

* 链接法
    * 元素key冲突之后使用一个链表填充相同key的元素
* 开放寻址法
    * 冲突之后根据一种方式(二次探查)寻找下一个可用的槽
* cpython使用的二次探查

### 二叉树

**先序、中序、后序**

* 先序 根左右
* 中序 左根右
* 后序 左右根

```python
class BinTreeNode:
    def __init__(self, data, left=None, right=None):
        self.data = data
        self.left = left
        self.right = right
        
    def BinTree:
        def __init__(self, root=None):
            self.root = root
            
        def preorder_trav(self, subtree):
            '''先序'''
            if subtree is not None:
                print(subtree.data)
                self.preorder_trav(subtree.left)
                self.preorder_trav(subtree.right)
                
        def inorder_trav(self, subtree):
            if subtree is not None:
                self.inorder_trav(subtree.left)
                print(subtree.data)
                self.inorder_trav(subtree.right)
                
        def lastorder_trav(self, subtree):
            if subtree is not None:
                self.lastorder_trav(subtree.left)
                self.lastorder_trav(subtree.right)
                print(subtree.data)
```

### 堆

**堆其实是完全二叉树，有最大堆和最小堆**

* 最大堆：对于每个非叶子节点V，V的值都比它的两个孩子大
* 最小堆：对于每个非叶子节点V，V的值都比它的两个孩子小
* 最大堆支持每次pop操作获取最大的元素，最小堆获取最小元素
* 常见问题：用堆完成topK问题，从海量数字中寻找最大的K个

```python
import heapq

class TopK:
    '''
    获取大量元素topK大个元素，固定内存
    思路：
    1. 先放入元素前k个建立一个最小堆
    2. 迭代剩余元素：
  	   如果当前元素小于堆顶元素，跳过该元素(肯定不是前k大)
  	   否则替换堆顶元素为当前元素，并重新调整堆
    '''
    def __init__(self, iterable, k):
        self.miniheap = []
        self.capacity = k
        self.iterable = iterable
        
    def push(self, val):
        if len(self.miniheap) >= self.capacity:
            min_val = self.miniheap[0]
            if val > min_val:
                heapq.heapreplace(self.miniheap, val)
        else:
            self.miniheap.append(val)
            
    def get_topk(self):
        for val in self.iterable:
            self.push(val)
        return self.miniheap
      
if __name__ == '__main__':
    import random
    l = list(range(10))
    random.shuffle(l)
    topk = TopK(l, 3)
    res = topk.get_topk()
    print(res)
```

## Python白板编程

### 什么是白板编程

**传说中的手写算法题，白纸或者白板上手写代码**

* ACM/蓝桥杯之类的算法竞赛
* 刷题，LeetCode、《剑指Offer》

### 为什么要手写算法

**工作用不到，为什么还要考？**

* 有些公司为了筛选编程能力强的同学，近年来对算法要求越来越高
* 针对刚出校门的同学问得多，有经验的反而算法考的少(偏向工程经验)
* 竞争越来越激烈，大家水平差不多的优先选取有算法竞赛经验的

### 如何准备

**没有太好的方式，刷常见题。防止业务代码写多了算法手生**

* 刷题，LeetCode，《剑指Offer》
* 面试之前系统整理之前做过的题目，不要靠记忆而是真正的理解掌握
* 打好基础是重点，面试可以刷常见题突击，保持手感

### 面试前练习

**刷题(LeetCode+剑指Offer+不同公司的面经)**

* 《剑指Offer》上常见题用Python实现
* 把LeetCode上常见分类题目刷一遍(GitHub搜LeetCode分类)
* 常见排序算法和数据结构可以手写

## Python常考数据结构之链表

### 链表

**链表涉及指针操作较为复杂，容易出错，经常用作考题**

* 熟悉链表的定义和常见操作

* 常考题：删除一个链表节点

    * LeetCode237

        ```python
        # Definition for singly-linked list.
        # class ListNode:
        #     def __init__(self, x):
        #         self.val = x
        #         self.next = None
        
        class Solution:
            def deleteNode(self, node):
                """
                :type node: ListNode
                :rtype: void Do not return anything, modify node in-place instead.
                """
                node.val = node.next.val
                node.next = node.next.next
        ```



* 常考题：合并两个有序链表

    * LeetCode21

        ```python
        # Definition for singly-linked list.
        # class ListNode:
        #     def __init__(self, x):
        #         self.val = x
        #         self.next = None
        
        class Solution:
            def mergeTwoLists(self, l1: ListNode, l2: ListNode) -> ListNode:
                res = ListNode(0)
                if l1 is None:
                    return l2
                if l2 is None:
                    return l1
                if l1.val < l2.val:
                    res = l1
                    res.next = self.mergeTwoLists(l1.next, l2)
                else:
                    res = l2
                    res.next = self.mergeTwoLists(l1, l2.next)
                return res
        ```

        

### 多写多练

**找到相关的题目，多做一些练习**

* 一般一次很难写对
* 尝试自己先思考，先按照自己的方式写代码，提交后发现问题
* 如果实在没有思路可以先去看其他人的题解

## Python常考数据结构之二叉树

### 二叉树

**二叉树涉及到递归和指针操作，常结合递归考察**

* 二叉树的操作很多可以用递归的方式解决，不了解递归会比较吃力

* 常考题：二叉树的镜像(反转二叉树)

    * LeetCode226

        ```python
        # Definition for a binary tree node.
        # class TreeNode:
        #     def __init__(self, x):
        #         self.val = x
        #         self.left = None
        #         self.right = None
        
        class Solution:
            def invertTree(self, root: TreeNode) -> TreeNode:
                if root:
                    root.left, root.right = root.right, root.left
                    self.invertTree(root.left)
                    self.invertTree(root.right)
                return root
        ```

* 常考题：如何层序遍历二叉树(广度优先)
    * LeetCode102

        ```python
        # Definition for a binary tree node.
        # class TreeNode:
        #     def __init__(self, x):
        #         self.val = x
        #         self.left = None
        #         self.right = None
        
        class Solution:
            def levelOrder(self, root):
                """
                :type root: TreeNode
                :rtype: List[List[int]]
                """
                if not root:
                    return []
                res = []
                cur_nodes = [root]
                next_nodes = []
                res.append([i.val for i in cur_nodes])
                while cur_nodes or next_nodes:
                    for node in cur_nodes:
                       if node.left:
                           next_nodes.append(node.left)
                       if node.right:
                           next_nodes.append(node.right)
                    if next_nodes:
                        res.append([i.val for i in next_nodes])
                    cur_nodes = next_nodes
                    next_nodes = []
                return res
        ```

## Python常考数据结构之栈和队列

### 栈和队列

**后进先出（栈）vs 先进先出（队列）**

* 熟练掌握用Python的list或者collections.deque()实现栈和队列

* 常考题：用栈实现队列

    * LeetCode232

        ```python
        class Stack:
            def __init__(self):
                self.stack = []
                
            def push(self, x: int) -> None:
                self.stack.append(x)
                
            def pop(self):
                return self.stack.pop()
            
            def top(self):
                return self.stack[-1]
            
            def empty(self):
                return self.stack == []
            
        class MyQueue:
        
            def __init__(self):
                """
                Initialize your data structure here.
                """
                self.s1 = Stack()
                self.s2 = Stack()
                
        
            def push(self, x: int) -> None:
                """
                Push element x to the back of queue.
                """
                self.s1.push(x)
                
        
            def pop(self) -> int:
                """
                Removes the element from in front of queue and returns that element.
                """
                if not self.s2.empty():
                    return self.s2.pop()
                
                while not self.s1.empty():
                    self.s2.push(self.s1.pop())
                return self.s2.pop()
                
        
            def peek(self) -> int:
                """
                Get the front element.
                """
                if not self.s2.empty():
                    return self.s2.top()
                
                while not self.s1.empty():
                    self.s2.push(self.s1.pop())
                return self.s2.top()
                
        
            def empty(self) -> bool:
                """
                Returns whether the queue is empty.
                """
                return self.s1.empty() and self.s2.empty()
                
        
        
        # Your MyQueue object will be instantiated and called as such:
        # obj = MyQueue()
        # obj.push(x)
        # param_2 = obj.pop()
        # param_3 = obj.peek()
        # param_4 = obj.empty()
        ```

## Python常考数据结构之堆

### 堆

**堆的常考题基本围绕在合并多个有序（数组/链表）、TopK问题**

* 理解堆的概念，堆是完全二叉树，有最大堆和最小堆

* 会使用Python内置的heapq模块实现堆的操作

* 常考题：合并k个有序链表

    * LeetCode23

    ```python
    # Definition for singly-linked list.
    # class ListNode:
    #     def __init__(self, x):
    #         self.val = x
    #         self.next = None
    
    class Solution:
        def mergeKLists(self, lists: List[ListNode]) -> ListNode:
            # 读取所有节点
            h = []
            for node in lists:
                while node:
                    h.append(node.val)
                    node = node.next
            if not h:
                return
            # 构造一个最小堆
            from heapq import heapify, heappop
            # 转换成最小堆
            heapify(h)
            # 构造链表
            root = ListNode(heappop(h))
            curnode = root
            while h:
                nextnode = ListNode(heappop(h))
                curnode.next = nextnode
                curnode = nextnode
            return root
    ```

    

## Python常考数据结构之字符串

### 字符串

**了解字符串的常用操作**

* Python内置了很多字符串操作，例如split、strip、upper、replace等

* 常考题：翻转一个字符串

    * LeetCode344

        ```python
        class Solution:
            def reverseString(self, s: List[str]) -> None:
                """
                Do not return anything, modify s in-place instead.
                """
                start, end = 0, len(s)-1
                while start < end:
                    s[start], s[end] = s[end], s[start]
                    start += 1
                    end -= 1
        ```

        

* 常考题：判断一个字符串是否为回文

    * LeetCode9

        ```python
        class Solution:
            def isPalindrome(self, x: int) -> bool:
                if x < 0:
                    return False
                s = str(x)
                start, end = 0, len(s)-1
                while start < end:
                    if s[start] == s[end]:
                        start += 1
                        end -= 1
                    else:
                        return False
                return True
        ```

        

## 算法与数据结构练习题

### 反转链表

**链表在面试中是一个高频考点**

* 如何反转一个单链表
* 能否用循环的方式实现吗？
* 能否用递归的方式实现吗？

## 面向对象基础及Python类常考问题

### 什么是面向对象编程

**Object Oriented Programming（OOP）**

* 把对象作为基本单元，把对象抽象成类(Class)，包含成员和方法
* 数据封装、继承、多态
* Python中使用类来实现。过程式编程(函数)，OOP(类)

### Python中如何创建类？

```python
class Person(object): # py3可以省略object直接写作 class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age 
        
    def print_name(self):
      print('my name is {}'.format(self.name))
```

### 组合与继承

**优先使用组合而非继承**

* 组合是使用其他的类实例作为自己的一个属性(Has-a 关系)
* 子类继承父类的属性和方法(Is a 关系)
* 优先使用组合保持代码简单

### 类变量和实例变量的区别

**区分类变量和实例变量**

* 类变量由所有实例共享
* 实例变量由实例单独享有，不同实例之间不影响
* 当我们需要一个类的不同实例之间共享变量的时候使用类变量

### classmethod和staticmethod区别

**classmethod vs staticmethod**

* 都可以通过Class.method()方式使用
* classmethod第一个参数是cls，可以引用类变量
* staticmethod使用起来和普通函数一样，只不过放在类里

### 什么是元类？使用场景

**元类（Meta Class）是创建类的类**

* 元类允许我们控制类的生成，比如修改类的属性等
* 使用type来定义元类
* 元类最常见的一个使用场景就是ORM框架

```python
# 元类继承自type
class LowercaseMeta(type):
    '''修改类的属性名称为小写的元类'''
    def __new__(mcs, name, bases, attrs):
        lower_attrs = {}
        for k, v in attrs.items():
            if not k.startswith('__'):
                lower_attrs[k.lower()] = v
            else:
                lower_attrs[k] = v
        return type.__new__(mcs, name, bases, lower_attrs)
     
class LowercaseClass(metaclass=LowercaseMeta):
    BAR = True
    
    def Hello(self):
        print('hello')
        
print(dir(LowercaseClass))
```

## Python装饰器常见问题

### Decorator

* Python中一切皆对象，函数也可以当做参数传递
* 装饰器是接受函数作为参数，添加功能后返回一个新函数的函数(类)
* Python中通过@使用装饰器

### 编写一个计算耗时的装饰器

```python
import time

def log_time(func):
    def wrapper(*args, **kwargs):
        start = time.time()
        res = func(*args, **kwargs)
        print('use time:{}'.format(time.time()-start))
        return 
    return wrapper
 
@log_time
def mysleep():
    time.sleep(1)
    
mysleep()
```

### 如何使用类编写装饰器？

```python
import time

class LogTime:
    def __call__(self, func):
        def wrapper(*args, **kwargs):
            start = time.time()
            res = func(*args, **kwargs)
            print('use time. {}'.format(time.time()-start))
            return res
        return wrapper
      
      
@LogTime()
def mysleep2():
    time.sleep(1)
    
mysleep2()
```

### 如何给装饰器增加参数？

**使用类装饰器比较方便实现装饰器参数**

```python
import time

class LogTimeParams:
  def __init__(self, use_int=False):
      self.use_int = use_int
      
  def __call__(self, func):
      def wrapper(*args, **kwargs):
          start = time.time()
          res = func(*args, **kwargs)
          if self.use_int:
              print('use time: {}'.format(int(time.time()-start)))
          else:
              print('use time: {}'.format(time.time()-start))
          return res
      return wrapper
    
@LogTimeParams(True)
def mysleep3():
    time.sleep(1)
    
mysleep3()
```

## Python设计模式之创建型模式

### 创建型设计模式常考题

**常见创建型设计模式**

* 工厂模式(Factory)：解决对象创建问题
* 构造模式(Builder)：控制复杂对象的创建
* 原型模式(Prototype)：通过原型的克隆创建新的实例
* 单例模式(Borg/Singleton)：一个类只能创建同一个对象
* 对象池模式(Pool)：预先分配同一类型的一组实例
* 惰性计算模式(Lazy Evaluation)：延迟计算(Python的property)

### 工厂模式

**什么是工厂模式(Factory)**

* 解决对象的创建问题
* 解耦对象的创建和使用
* 包括工厂方法和抽象工厂

```python
# 一个工厂方法的例子
class DogToy:
    def speak(self):
        print('wang wang')
        
class CatToy:
    def speak(self):
        print('miao miao')
        
def toy_factory(toy_type):
    if toy_type == 'dog':
        return DogToy()
    else:
        return CatToy()
```

### 构造模式

**什么是构造模式(Builder)**

* 用来控制复杂对象的构造
* 创建和表示分离。比如你要买电脑，工厂模式直接给你需要的电脑
* 但是构造模式允许你自己定义电脑的配置，组装完成后给你

```python
# 一个构造模式的例子
class Computer:
    def __init__(self, serial_number):
        self.serial = serial_number
        self.memory = None
        self.hdd = None
        self.gpu = None
        
    def __str__(self):
        info = ('Memory: {}GB'.format(self.memory),
               'Hard Disk: {}'.format(self.hdd),
               'Graphics Card: {}'.format(self.gpu))
        return '\n'.join(info)
      

class ComputerBuilder:
    def __init__(self):
        self.computer = Computer('Macbook Pro 2018')
        
    def configure_memory(self, amount):
        self.computer.memory = amount
    
    def configure_hdd(self, amount):
        self.computer.hdd = amount
        
    def configure_gpu(self, amount):
        self.computer.gpu = amount
        
        
class HardwareEngineer:
    def __init__(self):
        self.builder = None
        
    def construct_computer(self, memory, hdd, gpu):
        self.builder = ComputerBuilder()
        [step for step in (self.builder.configure_memory(memory),
                          self.builder.configure_hdd(hdd),
                          self.builder.configure_gpu(gpu))]
    
    @property
    def computer(self):
        return self.builder.computer
      
      
# 使用builder，可以创建多个builder类实现不同的组装方式
engineer = HardwareEngineer()
engineer.construct_computer(hdd=500, memory=8, gpu='GeForece GTX 650 Ti')
computer = engineer.computer
print(computer)
```

### 原型模式

**什么是原型模式(Prototype)**

* 通过克隆原型来创建新的实例
* 可以使用相同的原型，通过修改部分属性来创建新的实例
* 用途：对于一些创建实例开销比较高的地方可以用原型模式

### 单例模式

**单例模式的实现有多种方式**

* 单例模式：一个类创建出来的对象都是同一个
* Python的模块其实就是单例，只会导入一次
* 使用共享同一个实例的方式来创建单例模式

```python
# 单例模式
class Singleton:
    def __new__(cls, *args, **kwargs):
        if not hasattr(cls, '_instance'):
            _instance = super().__new__(cls, *args, **kwargs)
            cls._instance = _instance
        return cls._instance
      
class MyClass(Singleton):
    pass
  
c1 = MyClass()
c2 = MyClass()
assert c1 is c2 # 单例的，c1 c2是同一个实例
```

## Python设计模式之结构型模式

### 常见结构型设计模式

* 装饰器(Decorator)：无需子类化扩展对象功能
* 代理模式(Proxy)：把一个对象的操作代理到另一个对象
* 适配器模式(Adapter)：通过一个间接层适配统一接口
* 外观模式(Facede)：简化复杂对象的访问问题
* 享元模式(Flyweight)：通过对象复用(池)改善资源利用，比如连接池
* Model-View-Controller(MVC)：解耦展示逻辑和和业务逻辑

### 代理模式

**什么是代理模式(Proxy)**

* 把一个对象的操作代理到另一个对象
* 这里又要提到我们之前实现的Stack/Queue，把操作代理到deque
* 通常使用has-a组合关系

```python
from collections import deque

# 使用组合的例子
class Stack:
    
    def __init__(self):
    		self._deque = deque() # has a deque()
        
    def push(self, val):
        return self._deque.append(val)
    
    def pop(self):
        return self._deque.pop()
      
    def empty(self):
        return len(self._deque) == 0
  
```

### 适配器模式

**什么是适配器模式(Adapter)**

* 把不同对象的接口适配到同一个接口
* 想象一个多功能充电头，可以给不同的电器充电，充当了适配器
* 当我们需要给不同的对象统一接口的时候可以使用适配器模式

```python
# 适配器模式的例子
class Dog:
    def __init__(self):
        self.name = 'Dog'
        
    def bark(self):
        return 'woof!'
      
  
class Cat:
    def __init__(self):
        self.name = 'Cat'
        
    def meow(self):
        return 'meow'
    
    
class Adapter:
    def __init__(self, obj, **adapted_methods):
        '''
        We set the adapted methods in the object's dict
        '''
        self.obj = obj
        self.__dict__.update(adapted_methods)
        
    def __getattr__(self, attr):
        '''
        All non-adapted calls are passed to the object
        '''
        return getattr(self.obj, attr)
      
      
objects = []
dog = Dog()
objects.append(Adapter(dog, make_noise=dog.bark))
cat = Cat()
objects.append(Adapter(cat, make_noise=cat.meow))
for obj in objects:
    print('A {0} goes {1}'.format(obj.name, obj.make_noise()))
```

## Python设计模式之行为型模式

### 常见行为型设计模式

* 迭代器模式(Iterator)：通过统一的接口迭代对象
* 观察者模式(Observer)：对象发生改变的时候，观察者执行相应动作
* 策略模式(Strategy)：针对不同规模输入使用不同的策略

### 迭代器模式

**什么是迭代器模式(Iterator)**

* Python内置对迭代器模式的支持
* 比如我们可以用for遍历各种Iterable的数据类型
* Python里可以实现`__next__`和`__iter__`实现迭代器

```python
from collections import deque

# 使用组合的例子
class Stack:
    
    def __init__(self):
    		self._deque = deque() # has a deque()
        
    def push(self, val):
        return self._deque.append(val)
    
    def pop(self):
        return self._deque.pop()
      
    def empty(self):
        return len(self._deque) == 0

    def __iter__(self):
        res = []
        for i in self._deque:
            res.append(i)
        for i in reversed(res):
            yield i
            
            
s = Stack()
s.push(1)
s.push(2)
for i in s:
    print(i)
```

### 观察者模式

**什么是观察者模式(Observer)**

* 发布订阅是一种最常用的实现方式
* 发布订阅用于解耦逻辑
* 可以通过回调等方式实现，当发生事件时，调用相应的回调函数

```python
# 发布订阅模式

# 发布者
class Publisher:
    def __init__(self):
        # 观察者
        self.observers = []
        
    # 加入观察者
    def add(self, observer):
        if observer not in self.observers:
            self.observers.append(observer)
        else:
            print('Failed to add: {}'.format(observer))
     
    # 移除观察者
    def remove(self, observer):
        try:
            self.observers.remove(observer)
        except ValueError:
            print('Failed to remove: {}'.format(observer))
            
    # 调用观察者的回调
    def notify(self):
        [o.notify_by(self) for o in self.observers]
        

# 继承自发布者
class Formatter(Publisher):
    def __init__(self, name):
        super().__init__()
        self.name = name
        self._data = 0
       
    @property
    def data(self):
        return self._data
    
    @data.setter
    def data(self, new_value):
        self._data = int(new_value)
        # data在被合法赋值以后会执行notify
        self.notify()
        
        
class BinaryFormatter:
    '''订阅者'''
    
    def notify_by(self, publisher):
        print("{}: '{}' has now bin data = {}".format(
            type(self).__name__,
        	publisher.name,
        	bin(publisher.data))
        )
        
        
# 发布者
df = Formatter('formatter')
# 订阅者
bf = BinaryFormatter()
df.add(bf)
df.data = 3
```

### 策略模式

**什么是策略模式(Strategy)**

* 根据不同的输入采用不同的策略
* 比如买东西超过10个大八折，超过20个打七折
* 对外暴露统一的接口，内部采用不同的策略计算

```python
# 策略模式

class Order:
    def __init__(self, price, discount_strategy=None):
        self.price = price
        self.discount_strategy = discount_strategy
        
    def price_after_discount(self):
        if self.discount_strategy:
            discount = self.discount_strategy(self)
        else:
            discount = 0
        return self.price - discount
    
    def __repr__(self):
        fmt = '<Price: {}, price after discount: {}>'
        return fmt.format(self.price, self.price_after_discount())
    
def ten_percent_discount(order):
    return order.price * 0.10

def on_sale_discount(order):
    return order.price * 0.25 + 20

order0 = Order(100)
order1 = Order(100, discount_strategy=ten_percent_discount)
order2 = Order(1000, discount_strategy=on_sale_discount)
print(order0)
print(order1)
print(order2)
```

## Python函数式编程常考问题

### 函数式编程

**Python支持部分函数式编程特性**

* 把电脑的运算视作数学上的函数计算
* 高阶函数：map/reduce/filter
* 无副作用，相同的参数调用始终产生相同的结果

```python
list(map(lambda x: x*2, range(10)))

from functools import reduce
reduce(lambda x,y: x+y, range(1, 11))

list(filter(lambda x: x%2==0, range(10)))
```

### 什么是闭包

**Closure**

* 绑定了外部作用域的变量的函数
* 即使程序离开外部作用域，如果闭包仍然可见，绑定变量不会销毁
* 每次运行外部函数都会重新创建闭包

```python
from functools import wraps

# 装饰器
def cache(func):
    #外部变量
    store = {}
    
    @wraps(func)
    # 闭包函数
    def _(n):
        if n in store:
            return store[n]
        else:
            res = func(n)
            store[n] = res
            return res
        return _
    
# 斐波那契数列
@cache
def f(n):
    if n <= 1:
        return 1
    return f(n - 1) + f(n - 2)
```

## 编程范式与设计模式练习题

### 单例模式

**单例模式有多种方式来实现**

* 之前我们使用过`__new__`的方式实现了单例模式
* 你能使用类装饰器来完成单例模式吗？
* Tip：装饰器既可以接受一个函数，也可以是一个类(都是对象)

```python
def singleton(cls, *args, **kwargs):
    _instance = {}
    
    def _():
        if cls in _instance:
            return _instance[cls]
        else:
            _instance[cls] = cls(*args, **kwargs)
        return _instance[cls]
    return _
    

@singleton
class MyClass:
    pass
  
c1 = MyClass()
c2 = MyClass()
assert c1 is c2 # 单例的，c1 c2是同一个实例
```

## Linux常考命令

### 为什么要学Linux

**大部分企业应用跑在Linux server上**

* 熟练在Linux服务器上操作
* 了解Linux工作原理和常用工具
* 需要了解查看文件、进程、内存相关的一些命令，用来调试和排查

### 如何查询Linux命令的用法

**Linux命令众多，如何知道一个命令的用法**

* 使用man命令查询用法。但是man手册比较晦涩难懂
* 使用包管理工具自带的help，比如pip --help
* 这里介绍一个man的替代工具tldr。pip install tldr

### 文件/目录操作命令

**掌握常见的文件操作工具**

* chown/chmod/chgrp
* ls/rm/cd/cp/mv/touch/rename/ln(软连接和硬链接)等
* locate/find/grep 定位查找和搜索

### 文件查看

**文件或者日志查看工具**

* 编辑器 vi/nano
* cat/head/tail 查看文件
* more/less 交互式查看文件

### 进程操作命令

**掌握常见的进程操作工具**

* ps 查看进程
* kill 杀死进程 -9 -15
* top/htop 监控进程

### 内存操作命令

**掌握常见的内存操作工具**

* free 查看可用内存
* 了解每一列的具体含义
* 排查内存泄漏问题

### 网络操作命令

**掌握常见的网络工具**

* ifconfig 查看网卡信息
* lsof/netstat 查看端口信息
* ssh/scp 远程登录/复制 tcpdump抓包

### 用户/组操作命令

**掌握常见用户和组操作**

* useradd/usermod
* groupadd/groupmod

### 参考资料

**学习Linux命令**

* man命令可以查询用法 或者 cmd --help
* 《鸟哥的Linux私房菜》，学习简单的shell脚本知识
* 多用才能熟悉

## 操作系统进程和线程常考题

### 进程和线程的区别

**进程和线程对比**

* 进程是对运行时程序的封装，是系统资源调度和分配的基本单位
* 线程是进程的子任务，cpu调度和分配的基本单位，实现进程内并发
* 一个进程可以包含多个线程，线程依赖进程存在，并共享进程内存

### 什么是线程安全

**Python中那些操作是线程安全的？**

* 一个操作可以在多线程环境中安全使用，获取正确的结果
* 线程安全的操作好比线程是顺序执行而不是并发执行的(`i += 1`不是线程安全的)
* 一般如果涉及到写操作需要考虑如何让多个线程安全访问数据

### 线程同步的方式

**了解线程同步的方式，如何保证线程安全**

* 互斥量(锁)：通过互斥机制防止多个线程同时访问公共资源
* 信号量(Semphare)：控制同一时刻多个线程访问同一个资源的线程数
* 事件(信号)：通过通知的方式保持多个线程同步

### 进程间通信的方式

**Inter-Process Communication进程间传递信号或者数据**

* 管道/匿名管道/有名管道(pipe)
* 信号(Signal)：比如用户使用Ctrl+c产生SIGINT程序终止信号
* 消息队列(Message)
* 共享内存(share memory)
* 信号量(Semphare)
* 套接字(socket)：最常用的方式，我们的web应用都是这种方式

### Python中如何使用多线程

**threading模块**

* threading.Thread类用来创建线程
* start()方法启动线程
* 可以用join()等待线程结束

```python
import threading

lock = threading.Lock()

n = [0]

def foo():
    with lock:
        n[0] = n[0] + 1
        n[0] = n[0] + 1
        
threads = []
for i in range(500000):
    t = threading.Thread(target=foo)
    threads.append(t)
    
for t in threads:
    t.start()
    
print(n)
```

### Python中如何使用多进程

**Python有GIL，可以用多进程实现CPU密集程序**

* multiprocessing多进程模块
* Multiprocessing.Process类实现多进程
* 一般用在cpu密集程序，避免GIL的影响

```python
# 多进程
import multiprocessing

def fib(n):
    if n <=1
        return 1
    return fib(n-1) + fib(n-2)

jobs = []
for i in range(10, 20):
    p = multiprocessing.Process(tar=fib, args(i,))
    jobs.append(p)
    p.start()
   
```