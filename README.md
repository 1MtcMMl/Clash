# Clash

# 表示包含xxx.com域名后缀下的所有网站链接
DOMAIN-SUFFIX,xxx.com

# 表示包含这个xxxx域名关键词的所有网站链接
DOMAIN-KEYWORD,xxxx

# 以下代码是CFW默认自带的，不用特意再写，结合上图，按需设置策略组的选项
→ DIRECT: 直连 
→ REJECT: 该规则下不走网络活动，常用于广告拦截
→ .*: 表示加入你订阅中所有节点 
→ url-test: 表示有该代码下的节点会自动测速 

# 自动归类节点 - 以图片中香港节点策略组为例
→ (港|HK|Hong Kong)
代表具有"港"，"HK"，"HongKong"关键词的节点会归类到香港节点这个策略组中，
测速以 http://www.gstatic.com/generate_204`300,,50为准。

#举例 - 正则包含并排除的写法 - 香港节点不筛选5倍节点
custom_proxy_group=🇭🇰 香港节点`url-test`(?=.*(港|HK|Hong Kong|🇭🇰|HongKong))^((?!(5.0|5倍|5x)).)*$`http://www.gstatic.com/generate_204`300,,50

#优先度
规则按照配置文件里的顺序，按照从头到尾的顺序进行匹配。换句话说，第一条规则的优先级最高。
#  编辑规则
每一条规则由三部分组成：规则类型、匹配的流量（FINAL 规则没有这一项）以及所采取的策略。
即：TYPR,VALUE,POLICY。
比如：DOMAIN-SUFFIX,apple.com,DIRECT 
IP-CIDR,192.168.0.0/16,ProxyA。

#域名规则
有三种根据域名判断的规则
#DOMAIN
DOMAIN,www.apple.com,Proxy
规则会匹配与请求完全相同的地址
#DOMAIN-SUFFIX
DOMAIN-SUFFIX,apple.com,Proxy
规则会匹配与请求与主域名相同的地址
#DOMAIN-KEYWORD
DOMAIN-KEYWORD,google,Proxy
规则会匹配包含相应关键字的域名




