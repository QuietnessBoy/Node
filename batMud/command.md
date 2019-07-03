## batmud命令（持续更新）

###  方向
  > n:北方  s:南方  w:西方  e:东方
  > nw:西北   ne:东北   sw:西南   se:东南
  > d：下  o:上  enter: 进去   out:出去

### 自定义命令
  > command 查询自定义的命令列表
  > command+自定义字符+想要完成的一系列游戏内建命令 创建自己的命令，举个例子：command abc use bladed fury at 这句话表示使用abc三个字符输入 代替每次释放bladed fury的技能，后面的表示指定的目标，在打怪时可以直接abc bunny，来代替原来的use bladed fury at bunny这么一长串的输入内容。当然也可以同时输入多个命令，用分号;来做分隔。
  > uncommand+自定义字符 取消这句自创命令，因为总共也只能存250条command，有限的位子要好好利用

###  移动
  > num 方向 :向某方向移动num步
  > travel 方向 num : 适用于高速通道，不消耗体力

###  组队
  > party create name : 创建队伍
  > party invite name : 邀请队员

###  战斗
  > kill :战斗
  > gid grave :埋葬（杀死怪物需要埋葬，不然会出现超级恐怖的亡灵，伤害极高）
  > get name : 拾取物品
  > force :推动
  > use+技能名称 释放技能（skill），对于有目标的释放需要使用at，语法如：use 技能名称 at 目标
  > cast+咒语名称 释放咒语、魔法（spell）,使用方式同use
  > zz 停止释放技能或魔法，一般移动一步也会打断施法


### 场景互动
  > open : 打开
  > pull :推
  > look at : 查看某物信息
  > l : 查看周围信息
  > search :搜索，不是很常用，但是可以发现一些场景中特殊的东西，search要加搜索位置，例如search desk
  > read :读书看报，或者场景中需要你read的说明之类
  > sleep睡觉，可以回复HP\SP\EP，但是有时间限制，睡觉的时候什么都不能做。
  > view 注意商品前面都有序号，使用view+序号，可以了解对应商品的详细说明
  > turn 转动（个体）
  > touch post(传送某个场景，修道院大石柱说明)
  > row : 划

### 信息查询
  > i 查看身上携带的道具或没有穿上的装备，查看身上带了多少零钱，同时能看到自己的当前负重
  > eq 查看已经上身的装备，或握住的武器，查看装备对玩家的保护效果如何
  > eq check 查看身上穿的、包里放的装备道具的条件是否良好，有快坏了的装备要早点修哦
  > slots 查看身上哪些地方穿了装备，哪些地方还有空地儿
  > show skills/spells 查看自己已学会的技能或魔法
  > score 查看玩家自己的基本信息，包括存款、经验值、所属house、当前状态等等非常有用并且常用的命令
  > show experience 查看当前花费在自己身上的经验明细和总量
  > consider :查看怪物信息是否与你当前能力匹配
  > whereami : 查看自己身处何地
  >  whereismyparty : 查看自己的队伍在何处

### 玩家互动类命令
  > say 说话，这种相当于当面说话，要和其他玩家在一起才可以
  > tell 这种相当于发送游戏内信息啦，隔多远都能收到，其他的还有些表情之类，我也不熟悉 也不是必须的就不说了
  > finger 查看某个玩家的信息，finger+玩家名称


###  日常
  > map : 查看周围地图
  > light : 点亮（需要照明物品）
  > wear : 穿装备
  > wield :拿武器
  > drop : 丢东西
  > remove : 移除身上的装备
  > advance level : 升级


###  银行
  >  :存钱	deposit
  >  :取钱

###  商店
  > list : 查看商店商品
  > buy : 购买商品
  > sell : 贩卖商品
