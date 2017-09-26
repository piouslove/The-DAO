# 关于DAO的相关调研
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