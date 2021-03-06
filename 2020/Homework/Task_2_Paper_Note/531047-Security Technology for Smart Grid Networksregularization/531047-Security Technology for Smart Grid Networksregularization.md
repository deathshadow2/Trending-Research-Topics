- 笔记作者：SCU@A2u13


- 原文作者：Anthony R. Metke and Randy L. Ekl
- 原文题目：Security Technology for Smart Grid Networksregularization
- 原文来源：[IEEE TRANSACTIONS ON SMART GRID, VOL. 1, NO. 1, JUNE 2010](http://feihu.eng.ua.edu/NSF_CPS/year1/w12_3.pdf)



# 论文摘要

在过去的十年中，由于对旧技术的依赖导致系统效率低下，需要对电力网络进行升级和更新替换，要升级网格并运行改进的网格，将需要严重依赖于分布式智能和宽带通信能力，访问和通信功能需要用于大型，广域通信网络的最新安全技术。

本文讨论了智能网格系统的关键安全技术，包括公钥基础结构和可信计算、公钥基础结构（PKI），超级监控和数据采集（SCADA），安全，智能网格，可信计算等方面



# 论文研究

## 存在问题

智能电网系统和网络的新功能（例如分布式智能和宽带功能）可以大大提高效率和可靠性，但是如果不部署适当的安全控制措施，它们还可能会创建许多新的漏洞。

对于智能电网系统的防护要素如下：

- 智能电网系统的核心子系统之一是监督控制和数据采集（SCADA）解决方案。多家供应商提供了具有各种功能和安全机制的SCADA解决方案。尽管SCADA周围存在一些标准，但仍然需要使应用于SCADA部署的安全解决方案更加一致。

- 第二个组件是智能电网系统的关键，它是许多安全的，高度可用的无线网络。这些将包括广域，陆地移动无线电（LMR）系统以及诸如WLAN和WiMax之类的宽带网络。

- 第三个关键要素是全面的安全解决方案。本文提出了一种充分利用公钥的智能电网安全解决方案，包括基础架构（PKI）技术和可信计算技术。

## 解决方案— PKI

根据智能电网的安全要求以及系统的规模和所需的可用性，研究人员认为，在其他架构组件的支持下，利用公钥基础结构（PKI）技术以及受信任的计算元素是智能电网的最佳整体解决方案。

研究人员认为，保护智能电网最有效的密钥管理解决方案将基于PKI技术。

PKI不仅仅是系统中的硬件和软件，还包括描述设置，管理，更新，PKI的核心。

PKI通过使用数字证书将公用密钥与用户身份绑定。绑定是通过注册过程建立的，在此之后，注册机构（RA）保证。绑定的正确性是，证书颁发机构（CA）向用户颁发证书。用户或设备可以通过数字证书相互认证，建立对称的会话密钥，然后在彼此之间加密和解密消息。使用PKI的基本步骤如图所示。希望与安全资源[aka信赖方（RP）]进行通信的过程是从向RA发送证书签名请求（CSR）开始。RA执行审核功能，该功能确定所请求的绑定是否正确，是否分配CSR并将其转发给CA，然后由CA颁发证书。稍后，当证书主体希望访问安全资源时，它将证书发送给RP。RP通常通过向验证机构（VA）请求证书状态来对证书进行验证，如果证书有效，PVA允许建立信任链，其中第一个CA通过简单地颁发证书将信任扩展到第二个CA第二个CA的CA证书。这使得信任第一个CA的RP也可以信任带有第二个CA颁发的证书的子主题。当两个CA相互发出证书时，称为交叉签名。这样，一个组织的CA可以将信任扩展到其他组织的CA，从而实现跨域的安全互操作性。CA证书可以包含各种约束条件，以限制发布CA对主题CA扩展的信任。

![image-20200504225733676](https://a2u13-pic.oss-cn-chengdu.aliyuncs.com/pic/image-20200504225733676.png)

PKI主要包括四种技术元素：

- Smart Grid PKI Standards
- Trust Anchor Security
- Certificate Attributes
- Smart Grid PKI Tools

## 解决方案-可信计算

![image-20200504230538037](https://a2u13-pic.oss-cn-chengdu.aliyuncs.com/pic/image-20200504230538037.png)

<center>可信计算模型</center>

## 其他安全组件

A.  Overall Architecture

研究人员提供两种架构视图-高级概念模型和详细的逻辑模型。

高级概念模型：高级概念模型由NIST开发，并在智能电网和公用事业行业中得到应用。它仅显示了七个主要概念实体，以及它们之间的相互通信。图中的蓝色线是信息流，黄色的虚线是能量流。

![image-20200504224722985](https://a2u13-pic.oss-cn-chengdu.aliyuncs.com/pic/image-20200504224722985.png)

<center>智能电网概念模型</center>

详细的逻辑模型：详细的逻辑模型由几个关键要素组成：网络（无线和有线），功能子系统（例如SCADA），端点（例如后台计算机，受监视和/或可控制的变电站设备）和覆盖（例如分布式安全功能和元素）。下图显示了可能的内部互连示例。WANwireless网络作为整个系统的骨干网，是各种网络的子集。

![image-20200504230442820](https://a2u13-pic.oss-cn-chengdu.aliyuncs.com/pic/image-20200504230442820.png)

<center>智能电网详细的逻辑模型</center>

B.  Wireless Networks

智能电网网络需要不同的无线网络解决方案。

先进的计量基础设施（AMI）解决方案可以与本地覆盖或远程通信实现网格化或点对点。回程解决方案的选择包括光纤，无线宽带或超宽带。劳动力移动解决方案的可能性包括WiMax，WLAN，蜂窝和LMR，具体取决于公用事业需要的可靠性，吞吐量和覆盖范围。

C.  Incident Response Plan

![image-20200504230724725](https://a2u13-pic.oss-cn-chengdu.aliyuncs.com/pic/image-20200504230724725.png)

假设专用网络建立在硬件和软件的标准框架之上，则在发生安全事故时，专用公用事业网络可能会提供更好的事件响应计划一致性。响应速度随着参与方数量的增加而呈指数级下降。相反，理想情况下，专用网络将依赖于较少的参与者。

D.  Device’s Scope of Influence

首先，所有设备必须知道与谁通信以及应该与谁通信。

这可以通过相互认证技术（例如TLS或IPSec）来实现。

在相互身份验证期间，派生对称会话密钥，用于为后续流量提供消息的真实性和完整性。

其次，逻辑网络段必须隔离。必须在AMI网络内进行控制，以确保电表流量不能进入变电站或某个任意的网络地址。同样在变电站或控制中心中，还必须进行控制以确保仅从授权来源获得流量。

## 总结

- 作为关键的基础架构元素，智能电网需要最高级别的安全性，从一开始就需要内置安全性的全面体系结构。
- 智能电网安全解决方案需要整体方法，包括基于行业标准的PKI技术元素和可信计算元素。确保电网安全将需要使用基于标准的最新安全协议、PKI技术元素，例如证书生命周期管理工具，信任锚安全性和属性证书PKI解决方案支持受信任的计算元素，包括设备认证。

- 要实现本文提出的愿景，需要采取许多步骤。其中最主要的是需要一套有针对性的智能电网安全性要求和标准。

# 创新点

- 利用公钥基础结构（PKI）技术以及受信任的计算元素是智能电网的最佳整体解决方案，对于防范针对智能电网的超大范围攻击是很有作用的
- 在大型的智能电网的网络使用公钥基础设施的公钥系统将比私钥系统来的高效的多
- 使用可信计算技术能进一步确保智能电网在软件到硬件层面的安全性

# 不足点

- PKI体系对于超大型公司集团而言，部署较为困难，需要结合公司实际情况来进行合理化部署
- 如果私钥保存不当会对所有的重要设施造成毁灭性打击
- 如果公钥在部署后产生问题需要撤销，会产生一定的延迟性问题，这个过程可能会产生一些安全问题
- 文章对于详细技术细节讲解不够，大部分内容在阐述理论，缺乏实验以及数据支持

# 改进

- KPI体系需要集团公司结合自身实际情况部署，针对自身的系统特点选择正确的防护方案
- 对于私钥的保存一定要确保无法被任何第三方窃取，若被窃取要及时撤销证书和发布声明，防止产生安全性问题
- 文章应该着重于KPI体系在实际工业界中的应用场景与面临的困难，将理论与实际相结合才能确保论文中提到的技术能够对智能电网的安全提供有效解决方案