# 自动化赛马娘



## 小栗帽（脚本）


### 简介
本脚本可以实现**半自主化**刷金币，从第一年的首日，到第三年的有马纪念，全程只需要暂停四次手动加技能点。目前本脚本已稳定通过10次育成测试。

### 配置要求
1. PC端和模拟器端均需要下载按键精灵手机助手才能使用脚本
2. 模拟器使用雷电模拟器，设置中开root，机型设置为**华为p30p**，授予按键精灵超级权限，并**调整至1080×1920的分辨率**
3. 小栗帽必须觉醒3（解锁大胃王金回），推荐先行跑法
   * 除非支援卡稳定给金回，否则十分容易翻车
4. 一定要关掉育成中所有可以被关闭的弹窗提示（治疗、外出、休息、出道站比赛），并二倍速且跳过设置为第二个选项

按键精灵（安卓版）下载地址：
http://res.91anjian.com/Mobile/apk/MobileAnJian3.3.8.apk

按键精灵手机助手下载地址：
http://res.91anjian.com/Mobile/exe/MobileAnjian3.6.5.exe


### 使用说明

1. 分别再PC端和模拟器端安装好按键精灵手机助手和按键精灵（安卓版）
2. 打开赛马娘，选好种马（推荐堆耐力）和S卡
   * 推荐3速1力1智1耐，强烈建议带上**小海湾或伏特加**
   * 所选S卡尽量带比赛奖励（レースボーナス）加成的特点
   * 本脚本不识别友人卡和根性卡，不推荐带根性卡，**禁止带友人卡**（否则会出现程序错误）
3. 赛马娘调整至首日，打开小栗帽 ver1.0文件，将 time_code 修改为101后，点击调试按钮，之后可放手干其他事情
   * 操作示范见：小栗帽_脚本操作示范_起始
4. 在第二年5月前（NHK）、第二年12月后（有马）、第三年4月后（天皇赏春）、第三年12月后（有马）这四个节点脚本会中止，需要手动操作加技能点
   * 第一次技能加点必点大胃王，增加初期胜率
   * 第三次技能加点必点其他金回，若没有请点击至少一个，最好两个白回，好拿天皇赏春的牌子
5. 加完技能点后，将 time_code 分别修改为209、224、308、324后，再点击调试按钮，之后可放手干其他事情
   * 以上两步操作示范见：小栗帽_脚本操作示范_中止
6. 打完第三年的有马纪念后，育成生涯赛结束，这时候需要手动操作将剩余的比赛打完

### 报错处理

1. 程序停止运行一般有以下几种原因：
   * 上述需要手操的情形
   * 比赛没过遇到闹钟
   * 外出遇到抓娃娃机
   * 赛马娘游戏停止响应
   * 网络连接错误且点击重连无效（脚本可以自动点击重连）
2. 若你遇到了上述以外的情况，请截图并和我联系（于discussion版块留言），十分感谢！
3. 发生错误也不用着急，将赛马娘手动调整到育成主界面，然后于 time_code 处输入当日日期后再点击调试，脚本即可继续运行
   * 日期代码首数字为年数，后二数字为半月数。例如：第二年5月前-209；第二年12月后-224；第三年4月后-308

### 算法原理

1. 比赛：
   * 日期已经按照最优日程安排（两战一休，接生涯赛三战一修，赛程包括大多数G1和少数G2）被设计好，而非动态规划
   * 第二年夏日合宿前若速度达到580，则不进行休息和训练，而是选择参加第三年的宝冢纪念以及合宿期间的两场G2比赛
2. 训练：
   * 第一年遵循“哪里人多点哪里”的训练方式增加羁绊
   * 第二年训练只点速度，保证速度能保底B评分
   * 如果速度达到B，之后的训练会只点力量
3. 其他：
   * 若马娘生病，则无论当日是否有比赛，都进行治疗
   * 若马娘心情为普通及以下，比赛日依旧出去比赛，非比赛日则优先选择外出
   * 在非比赛日，低体力（保守向，设定为40%以下）则选择休息，否则选择训练
   * 合宿前一天更倾向于回体而不是比赛或训练

### 成果展示

![Screenshot_20210402-231546](https://user-images.githubusercontent.com/81814988/113432592-3dabf800-9410-11eb-978b-039ba32810e5.png)

一般来说，小栗帽强悍的实力和友好的赛程能极大概率无闹钟一直打到第三年的有马纪念。对于闹钟的使用，我的建议是，如果是非第三年的有马纪念翻车（一般在第二年的有马纪念有几率会演），必用闹钟；如果是第三年的有马纪念翻车，一般来说粉丝数也已经到达了50w水平，可以不用闹钟；甚至在第三年的天皇秋翻车（本人几乎没见到过），由于粉丝人数已经高于32w，也可以不用闹钟。

总的来说，小栗帽历战一把能有28（第三年夏日合宿前属性未达标，且未通过最后的有马纪念）~36（第三年夏日合宿前属性达标，且通过URA决赛）场比赛，实测金币稳定在1.6w-1.8w一把，顺带刷鞋刷牌子（特别是天皇赏春的牌子，长距离马觉醒短板），还能刷因子（速度稳定上B，力量大概率上B，耐力小概率上B）。而本脚本在一定程度上节约了历战流打法费时分心的时间成本。

### 下一步计划

之所以没有把脚本做的很完善（指连续性方面），很重要的原因是按键精灵软件自身的图片识别命令无法识别划动后的图像，这导致选技能操作无法被自动解决。因此之后下一步的计划是使用python把脚本重写一遍，并实现自动打jjc的功能，最后满足0手操的要求。（这一步预计两周内实现，在此立个Flag）

在之后的想法是在此基础上写一个能适用所有马娘的脚本，只需要使用者输入要求打的比赛，脚本就能做到所有马娘刷因子的功能。这个有前面的基础的话，就是改几个参数的事，不难实现。

当然最终的目标是写一个能够自动养出高评分的马娘的脚本，要实现这个需要把马娘资料站的信息都载入到脚本里面去，是一项比较大的工程，已经接近商业脚本的范畴了（淘宝上卖的就是这种）。不过我个人出于喜爱和共享的精神，之后写的脚本也都会上传到这里，供大家免费下载。

最后，毕竟不是商业脚本（其实就是一个自用脚本），所以请别太苛求于我！但是欢迎来讨论区（discussion版块）分享改进的建议，十分感谢！
