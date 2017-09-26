# 关于DAO的相关调研
## Ethereum官方设计的The DAO
### 概述
在以太坊上，智能合约帐户拥有和个人账户近乎一样的功能。  
根据这个特点，我们可以建立一种独立于区块链，分权民主化的去中心化自立组织DAO。  
这个特殊民主组织的工作方式是拥有一个像管理人，CEO或总统这样的Owner。Owner可以向组织添加（或删除）投票成员。任何成员都有权提出一个提案，这种提案是以一个发送以太币或调用一些智能合约的以太坊交易形式而提出的，其他成员可以投票支持或反对该提案。一旦到达预定时间或者有足够数量的成员投票，就可以执行提案：由智能合约计票，如果有足够的投票将执行给定的交易。
### 区块链会议
参考[The Blockchain Congress](https://www.ethereum.org/dao#the-blockchain-congress)。
### 股东联盟
参考[The Shareholder Association](https://www.ethereum.org/dao#the-shareholder-association)。
### 流动民主
参考[Liquid democracy](https://www.ethereum.org/dao#liquid-democracy)。
### 时间锁多重签名
参考[Time-Locked Multisig](https://www.ethereum.org/dao#time-locked-multisig)。
## Slock设计的DAO
[简要论述](https://blog.slock.it/a-primer-to-the-decentralized-autonomous-organization-dao-69fb125bd3cd)
### 背景
智能合约适合于创建企业或法人实体之间的书面协议。  
智能合约创建自立组织尤其适合于众筹场景，可以很好地保护小额投资者的权益。  
### 目的
实现一个分散式自立组织(DAO)，参与者直接实时地控制自己的贡献资金，并且DAO用软件形式化、自动化、强制化组织协议。  
关于现实法律层面的讨论：  
A word of caution, at the outset: the legal status of
DAOs remains the subject of active and vigorous debate
and discussion. Not everyone shares the same defenition.
Some have said that they are autonomous code and can
operate independently of legal systems; others have said
that they must be owned or operate by humans or hu-
man created entities. There will be many uses cases, and
the DAO code will develop over time. Ultimately, how a
DAO functions and its legal status will depend on many
factors, including how DAO code is used, where it is used,
and who uses it. This paper does not speculate about
the legal status of DAOs worldwide. This paper is not
intended to offer legal advice or conclusions. Anyone who
uses DAO code will do so at their own risk.
### 定义DAO概念
DAO是被部署在以太坊上由Solidity编写的智能合约代码。首先，它需要以太币来支持它在以太坊上的行为，它可以创建代币来向参与者换取以太币。
它会提前设定最低筹集目标值和最长筹集时间，在指定时间后若未达到最低目标，则会原路退回所有的以太币。
每个DAO都会有一个承包商作为链下事务的负责人，每个参与者都有资格成为承包商。承包商由参与者的提案经过投票后选出，并且可以通过提案转让。
每个参与者都有投票权和提案权，投票作用由每个人所控制的DAO代币数量加权决定。
### 多数抢劫少数攻击(Majority robs minority attack)
由于根据代币持有量加权投票作用的规定，代币持有量较少的人的权利很容易被持有量较多的人攻击。这个问题在目前实体公司中也比较常见。
为了解决这个问题，代码中加入了DAO分离机制和监护人(Curator)机制。
### 其他
代币价格、代币激励以及智能合约细节请参考[白皮书](https://download.slock.it/public/DAO/WhitePaper.pdf)。

# 数字身份结合DAO的思考
组织是由个人构成的，个人身份的一部分意义必然是由组织赋予或背书的。区块链数字身份的生态系统中理应存在DAO的概念，重点是组织协议记录在区块链这种公共账本上。将DAO概念抽象为代码模型，并编写成智能合约之后部署在区块链上可以提升透明性并严格保护组织成员的权利。
## 应用场景
众筹，slock对此已有论述和良好的抽象模型；慈善，DAO透明性的特点结合OpenPDS完美契合。其余场景待思考......
## 目的与意义
规范化个人在区块链世界中的权利与义务。
## 抽象模型(需讨论、思考、补充)
### 投票权
投票权利不能仅仅依靠代币持有量加权来恒定，应该为组织创建者和参与者提供更多投票类型以供选择。多签投票是保证民主自治化的重要保障。
### 提案权
除非组织协议由明确规定，否则每个参与者都应该由提案权。为了防止滥用提案权，提案的同时应该提供足够的保证金。
### 代币发行与激励
代币可能具有激励组织发展、链下锚定价值等作用。每个DAO组织都应该享有发行代币的权利，代币作用、代币管理取决于组织参与者共识，并且组织参与者应该为代币使用负责。
### 链下锚定
如若组织需要与链下世界锚定价值，Slock设计的承包商的是一个很好的例子。这一点应该取决于组织成员的共识意愿。
## DAO启发的数字身份扩展
数字身份生态系统中的组织概念不应该仅仅包括去中心化自立组织DAO，链下的社会共识(包括以后逐渐形成的新共识)都有机会抽象成智能合约模型来提升透明性和安全性，比如说众筹和慈善等。链上组织的形成对于数字身份意味着不再是将现实身份区块链化、数字化，而是创建一种从无到有、从0到1的区块链数字身份，也意味着这种数字身份在区块链世界中有它特有的价值。