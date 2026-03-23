1.首先会给出一个公司名（使用爱企查： aiqicha.com），此以`乐视`为例（www.le.com）
<img width="2460" height="1603" alt="image" src="https://github.com/user-attachments/assets/3985d55b-5439-4e33-aa44-37e82857b189" />


2. 查到公司的域名之后，进入网络空间搜索

| 公司             | 产品                          | 网址                                      |
|------------------|-------------------------------|-------------------------------------------|
| 白帽汇-华顺信安   | FOFA（大学生免费会员）         | https://fofa.info/                        |
| 知道创宇          | 钟馗之眼                      | https://www.zoomeye.org/                  |
| 奇安信            | 鹰图                          | https://hunter.qianxin.com/               |
| 360              | 夸克                          | https://quake.360.net/                    |
| 安恒              | SUMAP                         | https://sumap.dbappsecurity.com.cn/       |
| 盛邦安全          | daydaymap                     | https://www.daydaymap.com/home            |
|                  | 知风-工控、物联网搜索           | https://zhifeng.io/web/new/               |
|                  | shodan                        | https://www.shodan.io/                    |
|                  | censys                        | https://censys.io/                        |
|                  | onyphe                        | https://www.onyphe.io/                    |

使用hunter https://hunter.qianxin.com/ 来查一下
<img width="2519" height="1551" alt="image" src="https://github.com/user-attachments/assets/e48af47f-d1b7-4e05-b541-8e216ae7c406" />
<img width="2519" height="1488" alt="image" src="https://github.com/user-attachments/assets/f961f038-4cd1-4aa0-aa80-24eb5dda6c21" />

使用企业名字来查域名：`icp.name=="乐视网信息技术（北京）股份有限公司"`
<img width="2461" height="1492" alt="image" src="https://github.com/user-attachments/assets/f6bebb92-57f3-4973-adb1-1e563598af35" />

通过企业的logo来搜索资产：web.icon=="f9b2ac37c01f8a1c86b3d791647f3303"
<img width="2452" height="1492" alt="image" src="https://github.com/user-attachments/assets/1efb48f9-a04f-4bd0-9fde-dc319f045647" />

如何查看该公司的子公司：在爱企查里面点击股权穿透图即可：
<img width="2519" height="1543" alt="image" src="https://github.com/user-attachments/assets/9889ed2f-f248-4364-982c-0ab6d50d241a" />

如何搜索小程序资产：直接去微信里面搜索即可
<img width="1699" height="1268" alt="image" src="https://github.com/user-attachments/assets/b164bbb9-022a-47b8-931c-4d5b05550d02" />

什么情况会使用fofa:搜索ip的时候
如何使用fofa搜索c段：ip="xx.xx.xx.xx/24"
什么情况使用hunter:搜索子域名的时候

工具推荐：
1.https://github.com/shmilylty/oneforall

2.https://github.com/adysec/ARL

3.https://github.com/euphrat1ca/LayerDomainFinder

4.https://github.com/TideSec/TideFinger

敏感信息收集
1.github搜索
比如： edu.cn 密码
<img width="2519" height="1553" alt="image" src="https://github.com/user-attachments/assets/d21d992d-72ad-4d96-995a-34f4f043438a" />
如果绕过github搜索的代码页面限制：https://www.jianshu.com/p/ec98d49d4cd8

2.网盘搜索
https://www.lingfengyun.com/

3.语雀搜索
https://www.yuque.com/dashboard

4.短视频搜索






3.使用网络资产搜索引擎搜索资产(fofa: domin=" *** "),可选备案企业（icp="京ICP证030173号"）,通过网站图标的hash值进行查询	(icon_hash="-247388890"),搜ip的话可以用fofa,搜子域名的话可以用hunter
4.站长工具(https://www.aizhan.com/,https://tool.chinaz.com/)
5.fofa查c段 ： ip="xx.xx.xx.xx/24"

### 知识补充
#### 1.C段
在计算机网络中，“C段”通常是指IP地址中的 C类地址段（Class C network segment），它是IPv4地址分类体系中的一个概念。虽然现代网络更多使用无类别域间路由（CIDR）来分配IP地址，但“C段”这个说法仍然被广泛沿用，特别是在运维、安全和网络管理领域。

一、传统IP地址分类中的C类地址

在早期的IPv4地址分类体系中，IP地址被分为A、B、C、D、E五类：

- C类地址：
  - 第一个字节范围：192 – 223
  - 默认子网掩码：255.255.255.0（即 /24）
  - 可用主机数量：254台（因为全0和全1的主机号保留）
  - 网络位：前24位（即前三个字节）
  - 主机位：后8位（最后一个字节）

例如：
- 192.168.1.0/24 是一个典型的C类网段
- 其中可用IP地址范围是 192.168.1.1 到 192.168.1.254

二、现代语境下的“C段”

现在虽然不再严格按A/B/C类划分（因为使用了CIDR），但人们仍习惯把 一个/24的子网 称为“一个C段”。

比如：
- 当说“扫描某个C段”，通常指扫描如 x.x.x.0/24 这个范围内的所有IP（共256个地址）。
- 在渗透测试或网络安全中，“同C段”常意味着这些IP属于同一个局域网或同一组织，可能有相似的安全策略或拓扑结构。

三、举例说明

假设你有一个IP地址：203.0.113.45

- 它所在的“C段”就是 203.0.113.0/24
- 包含的IP范围是：203.0.113.0 ~ 203.0.113.255
- 实际可用主机IP：203.0.113.1 ~ 203.0.113.254

四、为什么“C段”重要？

1. 网络规划：/24网段大小适中，适合中小型网络。
2. 安全分析：攻击者或安全人员常以C段为单位进行资产发现。
3. 日志关联：如果多个可疑IP处于同一C段，可能来自同一攻击源或同一服务商。

