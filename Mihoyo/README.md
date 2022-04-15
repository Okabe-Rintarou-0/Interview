# 面经

## 一面

时间：2022/3/16

形式：视频面试

持续时间：约1小时

## 过程

上来先自我介绍，然后讲了讲自己的项目和lab。（面试官说Raft和LSMT这种偏实验室了，不愧是游戏公司。。。）

对我两个项目比较感兴趣，聊着聊着说到UDP。

### UDP

+ 什么方式可以判断玩家网络情况
  + 我回答用ping的方式，然后像检测心跳一样，判断丢包率。
  + 但是应该有更好的方案，但我一个本科生没怎么接触过啊QAQ
+ 网络衡量指标
  + RTT
  + Jitter 提到Jitter面试官虎躯一震？？？
  + 丢包率
+ UDP好在哪？

### 做题

#### Singleton 单例模式

第一题写个单例模式。面试前在写JUnit，上来private Singleton *，面试官汗颜，急忙道歉说我之前在写Java写串了。。。。

标准写法，以前写的都是单线程版本，面试官提示下写了如下版本，注意到**volatile**关键字，就知道会考这个。。。

```c++
class Singleton {
private:
    static volatile Singleton *instance;
    static mutex mtx;

    Singleton() = default;

public:
    static Singleton *getInstance() {
        if (instance == nullptr) {
            mtx.lock();
            if (instance == nullptr) {
                instance = new Singleton;
            }
            mtx.unlock();
        }
        return instance;
    }
};

Singleton *Singleton::instance = nullptr
```

#### Atoi 字符串转整数

leetcode原题：https://leetcode-cn.com/problems/string-to-integer-atoi/

### 提问环节

“送不送原石？”

“不送”

So sad.

## 结果

简历不匹配寄了，呜呜。

来世再做米卫兵！