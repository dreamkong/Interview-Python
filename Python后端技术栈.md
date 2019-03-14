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
  flist{l} #[0, 0]
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