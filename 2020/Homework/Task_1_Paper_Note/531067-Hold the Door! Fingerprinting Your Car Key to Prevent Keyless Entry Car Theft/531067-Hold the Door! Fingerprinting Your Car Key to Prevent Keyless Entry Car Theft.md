-   笔记作者：2017141531067 刘浩
-   原文作者： Kyungho Joo, Wonsuk Choi and Dong Hoon Lee
-   原文题目：Hold the Door! Fingerprinting Your Car Key to Prevent 
Keyless Entry Car Theft
-   原文来源：NDSS Symposium 2020: Network Defenses

传统的钥匙解锁车门方式逐渐被无钥匙进入系统取代，这对车主来说更加方便。然而，这缺面临着信号中继攻击，尽管汽车制造商已经采取了预防措施以保护无钥匙进入系统的安全，但仍然易受一系列攻击。针对此类漏洞，本文提出了一种RF指纹方法，即HODOR，这是在汽车行业首次利用RF指纹技术的尝试。本文介绍了HODOR在检测无钥匙进入系统的攻击方面的评估，实验结果表明，HODOR能够精确地测出多种类型的攻击尝试。

### 1、研究内容

系统架构：整个系统框架图如下所示，车辆应验证密钥卡发出的UHF频段信号。 因此，HODOR应该配备RF接收器并安装到车辆上，并与汽车的车身控制模块（BCM）集成在一起，该模块控制车身中的各种电子配件。 BCM的一种典型功能是通过诸如CAN或LIN的车载网络通信来发送锁定/解锁命令包。 在检测到攻击的情况下，HODOR会发出攻击检测警报，并且BCM不会发送包含解锁命令的CAN数据包。

![](https://graph.baidu.com/resource/121f326b60ca0ddbbb04301586831753.jpg)
图1 系统框架图

HODOR架构：整个框架图如下所示，由两个阶段组成，训练阶段和攻击阶段。在训练阶段，HODOR基于仅包含合法信号的训练数据集创建分类器。 通过预处理和特征提取，可以获得每个RF信号的一组特征，并对分类器进行训练。 此外，还计算了在“攻击检测”阶段中用于输出归一化的归一化参数。
训练完分类器后，在“攻击检测”阶段，HODOR现在可以检测到我们在第III-B节的攻击模型中定义的任何攻击。 在攻击检测阶段，HODOR会收到一个新的RF信号，其中包含一个门解锁请求。 然后，如训练阶段所述，HODOR对这个新接收到的RF信号进行预处理和特征提取。

![](https://graph.baidu.com/resource/121f295daae1b0222772d01586830897.jpg)
图2 HODOR框架图

评估结果：

HODOR执行时间表。
![](https://graph.baidu.com/resource/121e6d98e9c25331c66b601586832089.jpg)

人类无法轻易识别出小于500毫秒的延迟，因此HODOR将有效地作为对现有无钥匙进入系统的支持机制，而不会在用户端造成明显的延迟。

### 2、创新点

本文的主要创新点如下：

-   这是首次在汽车领域使用RF指纹技术的尝试
-   可直接用于现有系统，无需任何硬件修改
-   从密钥和中继攻击的角度来解释了漏洞

### 3、论文评论

这篇文章题材新颖，切合生活实际，具有很高的实用价值。但仍然存在一些不足之处，文章对相关硬件方面解释的不是很全面，较为简单并没有深入分析；HODOR系统需要新增一个设备来采集UHFband RF信号并进行分析，但这个设备在文中并没有很好的进行分析评价，存在安全风险；此外，环境差异对系统工作有一定影响，在极端的环境下可能会造成重大隐患。