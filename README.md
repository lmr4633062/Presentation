# Presentation
the presentation in Lab
## All Your DNS Records Point to Us-Understanding the Security Threats of Dangling DNS Records
2016 CCS
* 在 NDS 悬挂记录 (Dare) 里,DNS 记录指向的资源已经无效，但记录本身尚未从 DNS 清除。
* 本文确定了攻击者可以利用 Dare 攻击的三个攻击向量：1) 云平台随机分配 IP 地址，这会导致基于概率的攻击;2) 在第三方服务账户上声明(子)域名的所有权,攻击者可以声明和控制已经被遗弃的(子)域名;3) 因为域名可以到期失效,第三种攻击途径就是在 DNS 记录的 data 域里寻找失效的域名。
* 测试中成功发现了 791 个可以确认的,5982 个潜在的 DNS 悬挂记录。令人担忧的是,在 335 个影响程度较大的域名包括 edu,gov 和 Alexa top10000 中都发现了 DNS 悬挂记录的存在。
* 通过利用这些 DNS 悬挂记录，攻击者可以大量增加各种形式的欺骗活动(如发垃圾邮件、钓鱼以及 cookie 劫持),由于像 Let’s Encrypt 的自动免费的 CA 认证的出现，攻击者甚至可以签名认证被篡改的子域名以及设置一个“真正的” HTTPS 网站。
