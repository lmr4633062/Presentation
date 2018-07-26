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
