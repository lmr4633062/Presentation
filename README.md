# Presentation
the presentation in Lab
## All Your DNS Records Point to Us-Understanding the Security Threats of Dangling DNS Records
2016 CCS
* 在 NDS 悬挂记录 (Dare) 里, DNS 记录指向的资源已经无效, 但记录本身尚未从 DNS 清除。
* 本文确定了攻击者可以利用 Dare 攻击的三个攻击向量: 1) 云平台随机分配 IP 地址, 这会导致基于概率的攻击; 2) 在第三方服务账户上声明(子)域名的所有权,攻击者可以声明和控制已经被遗弃的(子)域名; 3) 因为域名可以到期失效,第三种攻击途径就是在 DNS 记录的 data 域里寻找失效的域名。
* 测试中成功发现了 791 个可以确认的,5982 个潜在的 DNS 悬挂记录。令人担忧的是, 在 335 个影响程度较大的域名包括 edu,gov 和 Alexa top10000 中都发现了 DNS 悬挂记录的存在。
* 通过利用这些 DNS 悬挂记录，攻击者可以大量增加各种形式的欺骗活动(如发垃圾邮件、钓鱼以及 cookie 劫持),由于像 Let’s Encrypt 的自动免费的 CA 认证的出现，攻击者甚至可以签名认证被篡改的子域名以及设置一个“真正的” HTTPS 网站。

## On the Security and Performance of Proof of Work Blockchains
2016 SIGSAC
* 本文引入了一个定量框架来分析 PoW 区块链的各种共识和网络参数的安全性和性能影响。
* 基于提出的框架，本文制定了双重支付和自私挖掘的最佳应对策略，这个模型扩展了基于马尔可夫的决策过程 (MDP) 来寻找一个最佳策略。
* Ethereum 相比比特币有更小的块激励和更高的旧块率，Ethereum 需要至少 37 个确认才能达到 bitcoin 6 个区块确认的安全性，这 6 个确认能抵御有 30% 挖矿力的攻击者。而 Litecoin 要求 28 个，Dogecoin 要求 47 个。
* 不牺牲安全性的话，PoW 区块链最多能达到一分钟 60 个交易 (现在是一分钟 7 个)。
* 设计了一个比特币区块链模拟器 [Bitcoin blockchain simulator](http://arthurgervais.github.io/Bitcoin-Simulator/index.html) 来评估区块链的安全性和性能。
## Practical UC-Secure Delegatable Credentials with Attributes and Their Application to Blockchain
2017 SIGSAC
* 提出带属性的委托证书的理想功能 ℱdac。委托的任一级属性都是不同的。产生表达 token 时，每个属性都可以选择性披露。Token 可以用于签任意信息。仅在标记期间能保证隐私，在委托期间，被委托人知道委托给她的所有证书链。
* 从签名方案和零知识证明提出一个普适的 DAC 结构，并且证明在 [Universally Composable Security: A New Paradigm for Cryptographic Protocols](https://ieeexplore.ieee.org/abstract/document/959888/) 提出的 UC (通用可组合性)框架是安全的。本文的结构可用于安全构造区块，构造一个混合协议的高级系统，使得模块设计和简单的安全分析成为可能。
* 本文基于最近由 [Efficient Fully Structure-Preserving Signatures for Large Messages](https://link.springer.com/chapter/10.1007/978-3-662-48797-6_11) 提出的结构保护签名机制和 [schnorr 零知识证明](https://link.springer.com/chapter/10.1007/0-387-34805-0_22)，描述了一个 DAC 有效实例。
* 在满足隐私保护条件的环境下的许可区块链中呈现了本文方案的执行，并给出了执行图，证明了方案的可行性。比如用来自于委托证书 4 个未公开的属性产生了一个属性 token，就花了 50 毫秒，验证就花了 40 毫秒。
## Hawk: The Blockchain Model of Cryptography and Privacy-Preserving Smart Contracts
2016 S&P
本文提出 Hawk，一个建立隐私保护智能合约的框架。非专业开发人员也可以写 Hawk 程序而不用执行加密。这个 Hawk 编译器是编译用户和区块链之间的加密协议。Hawk 程序包含以下几个部分

* 私有部分 私有部分接收参与方的输入数据，比如“石头剪刀布”游戏中的选择、币值、拍卖中的竞价。私有部分保护参与者的数据和交易信息。
* 公有部分 公有部分不接触私有的数据和钱。

Hawk 编译器将把 Hawk 程序编译成以下部分，它们共同定义用户、管理员和 blockchain 之间的加密协议。
* 将由所有的共识节点执行的区块链程序
* 一个由用户的执行的程序
* 一个特殊的利益方也就是管理员执行的程序，它会被即时解释
