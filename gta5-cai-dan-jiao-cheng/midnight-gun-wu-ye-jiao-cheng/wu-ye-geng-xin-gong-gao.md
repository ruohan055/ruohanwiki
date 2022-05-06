---
description: 其他更新公告请移步售后群内公告查看，这里只是发送部分更新日志公告
---

# 午夜更新公告

## 午夜更新至 2022.04.27

{% hint style="info" %}
**更新日志:**

> **适配最新游戏版本 1.59**

**玩家列表：**

> **新增 \[T] 标识 (正在打字的玩家) 新增 \[P] 标识 (暂停玩家 如Esc键看地图) 新增 \[G] 标识 (被动模式玩家) 新增 \[O] 标识 (雷达隐匿玩家) 新增 \[$] 标识 (带悬赏金的玩家，鼠标悬停上方可查看赏金数值)**

**玩家列表 - 交互功能：**

> **新增友好选项 - 解锁物品 (将给予玩家一些奖章, RP 经验及一些金钱 (每人只可使用一次)) 新增友好选项 - 雷达隐匿 新增恶搞选项 - 踢出室内 新增恶搞选项 - 极致冻结 (另一种定身方式) 新增恶搞选项 - 滴滴轰炸 (带手机通知的声音轰炸) 新增恶搞选项 - 循环邀请 (通过你或 NPC 的方式邀请玩家(你可以对自己使用，看看效果如何)) 恶搞选项 - "显示小岛过场动画“ 重命名为 ”发送至过场动画“ 并重写，新增小岛与du场选择，小岛过场动画有几分钟长**

**新增子菜单 - 交互 - 传送：**

> **旧的 "传送到室内" 从恶搞选项中移到此处 旧的 "发送到小岛" 从恶搞选项中移到此处 新增 "小岛选项"，可选将玩家传送/派回小岛，可选是否使用启用过场动画，也可发给玩家无限加载屏幕 新增 "摩托帮选项"，可将玩家踢出摩托帮，可选将其放在摩托车上或发给玩家无限加载屏幕 新增 "海湾选项"，可将玩家发送到海湾 新增 "玩家室内"，可将玩家发送到另一个玩家的室内**

**战局玩家选项：**

> **新增 "间接性自由模式事件崩坏(不是崩溃游戏)"，这将破坏战局，向脚本主机发送大量脚本踢出事件并且破坏所有玩家的视角与角色控制 移除首选的 RID 加入战局方式 (因为被 R 星修补，旧方法仍可用，我们将尽快带入新方式)**

**自身选项 - 修改器：**

> **新增 "天基炮附体" (开启后凡是你杀死的玩家，不论何种方式，直接或是用菜单间接，都会显示被天基炮消灭并且目标玩家死后将在医院处复活) 新增 "禁用被动模式冷却"**

**错误修复：**

> **修复 "OnWeaponReceived" 脚本事件不工作的问题 修复 "传送到室内" 修复 "小丑枪" 修复从 "自定义" 之中无法生成载具的问题**

**防护改进：**

> **修补降落伞崩溃 (来自 Stand 650) 重写日志与崩溃转储(dump)，现在他们会被单独记录 鉴于游戏更新了部分内容，改进反作弊系统**

**其他改动：**

> **为一些脚本事件添加了缺失的筛选配置 为虚假的聊天信息发送者添加了显示真名功能 新增在更换战局时自动删除已生成载具 新增删除 "云载载具" 的二次确认 新增 "虚假聊天信息" 的作弊者标识 新增 "载具枪" 的力度设定 新增透视选项 - 特选模式，允许为特定玩家单独启用透视功能 武器选项中新增 "加入战局时给予所有武器" 与 "加入战局时给予所有武器附件" 武器选项中新增 "给予所有武器附件" 改进 Speedhack - 'Force' 载具 - 修改器中 "可被锁住" 重命名为 "禁用锁住" 并重写**

**新增 Lua 函数：**

> **script\_local(script\_name, index) -- same methods as for script\_global i2f(value) -- Convert int to IEEE 754 (float) s2i(value) -- Convert string to int s2f(value) -- Convert string to float native.get\_native\_name(hash) native.get\_native\_name\_full(hash) native.get\_native\_namespace(hash) script\_global.get\_string() script\_global.set\_string(string) player.outfit\_load(name) player.outfit\_save(ply, name)**
{% endhint %}

## 午夜更新至 2022.04.13

{% hint style="info" %}
**更新日志：**

* **修复日志文本切割**
* **修复在车辆载具内无法使用传送功能的问题**
* **修复将“最大速度”设置为“0”导致无法驾驶车辆的问题**
* **修复“游泳乘数”状态无法使用的问题**
* **修复使用午夜菜单时看不到战局聊天消息的问题**
* **修复脚本事件崩溃保护不启用**
* **修复“速度限制”恢复到540**
* **修复错误的附件崩溃**
* **修复错误的物体几何崩溃**
* **修复不正确的装备矩阵崩溃(任何无效的装备崩溃)**

**Lua API -**

* **- Events OnScriptSend and OnScriptEvent have been reworked:**&#x20;
* **--- \* Instead of LuaArray events now use native lua table that contains se args (not including the se)**&#x20;
* **--- \* Arg 'event' is the se by itself**&#x20;
* **--- \* Arg 'plys' is a table that contains se receivers indexes (player ids)**&#x20;
* **--- \* Arg 'ply' is a player that has sent you the se**
{% endhint %}

```
// Example for OnScriptEvent:

function OnScriptEvent(ply, event, args)
  console.log("[Lua] Incoming script | From: " .. player.get_name(ply) .. ", Hash: " .. event .. ", Arg Count: " .. #args .. "\n")
  
  console.log("[Lua] Arguments:\n")
  for i, arg in ipairs(args) do
    console.log("[Lua] [" .. i .. "] " .. arg .. "\n")
  end  
  
  return true
end

Example for OnScriptSend:

function OnScriptSend(plys, event, args)
  console.log("[Lua] Sending script | Hash: " .. event .. ", Arg Count: " .. #args .. "\n")
  
  console.log("[Lua] Arguments:\n")
  for i, arg in ipairs(args) do
    console.log("[Lua] [" .. i .. "] " .. arg .. "\n")
  end  
  
  console.log("[Lua] Destination Players:\n")
  for i, name in ipairs(plys) do
    console.log("[Lua] [" .. i .. "] " .. name .. "\n")
  end  
end
```

## 午夜更新至 2022.04.08

{% hint style="info" %}
**更新日志：**&#x20;

**玩家列表 > 互动功能 的更改: 所有的踢出都已移至"踢出选项"，其中包括:**

* **非法混回音(Illlegal Dubstep Mixtape) (IDM) - 新的无法防护的踢出**
* **蛮力踢出 - 使用脚本事件旧的踢出，已过时**
* **踢出服务器(主机踢) - 如果你是主机 - 它会立即踢出玩家并且未被检测到，如果你不是，那么它将使用IDM踢 使用踢出服务器获得更快更好的效果**

**新增功能:**

* **新增作弊者标记反应 '防护 > 反应',能够选择多个反应**
* **新增'战局 > 战局加入 > 禁止超时踢出，让你可以更快地加入战局**
* **新增'防护 > 其他 > 拦截同步时间 (15秒,30秒,60秒,永久)**
* **新增'Gucci TP'提示工具**
* **新增新绘图方法'载具 > 车速表' - '角落边'**
* **新增'am\_launcher'脚本迁移通知 (脚本启动器)**
* **新增'自我 > 修改选项 > 彩虹头发'**
* **新增'骨骼','追踪器','旋转'到'视觉选项 -> 透视'**

**修复功能与改进保护:**

* **修复部分'玩家信息'未复制到剪贴板**
* **修复'拦截所有'拦截同步类型不起作用**
* **修复骨骼计算在'自瞄选项'**
* **修复骨骼计算在'杀死所有敌人'**
* **修复骨骼计算在'工具枪'**
* **修复'载具 > 门 > 行为'**
* **修复无效的内部崩溃**
* **次要改进保护**

**其他修复:**

* **更改昵称恶搞字符限制(20->16)**
* **重新排列恢复选项中的菜单控件**
* **改进虚假IP检测**
* **改进虚假名称检测**
* **改进'强制战局主机 > 静音'**
* **提高'战局 > 清除战局'的速度 - 现在可以立即使用**
* **更新翻译文件**

**LUA引擎:**

* **修复Natives在Lua中调用，这应该可以解决在光纤之外调用Natives的问题**

**新增LUA功能:**

* **kick\_idm(ply)**
* **crash\_izuku\_start(ply)**
* **crash\_izuku\_stop(ply)**
* **crash\_izuku\_active(ply) -> bool**
* **crash\_himiko\_start(ply)**
* **crash\_himiko\_stop(ply)**
* **crash\_himiko\_active(ply) -> bool**

**新增LUA事件:**

* **OnSyncBlocked(int player,string reason,int ban\_time)**
{% endhint %}

## **午夜更新至 2022.03.07**

{% hint style="info" %}
**更新日志：**

* **新增常驻状态事件防护'Moderation -> Copy Outfit'**
* &#x20;**新增强制拉进战局防护 'Griefing -> Block Passive'**
* **对某些无效的存在事件添加了保护**
* &#x20;**改进了脚本事件保护**
* &#x20;**修复了武器分配不正确的问题**
{% endhint %}

## **午夜更新至 2022.03.01**

{% hint style="info" %}
**更新日志：**

**任务:**

**我们进行了大量测试,找到了任务和抢劫无法正常游玩的问题。现在您可以流畅地完成它们。但是,我们提醒您,为了在任务/抢劫的时候防止出现问题,您应该:**

**- 关闭所有虚假信息 (RID/IP/名称) - 脚本可能会因此而中断**

**- 关闭所有防护 - 我们试图在正常游戏过程中尽量减少误报的可能,但是,在任务和抢劫期间你仍然可能遇到误报**

**- 不要使用任何可能破坏任务脚本的功能,例如:任务/抢劫中应该有警察,但您启用不被通缉**

**我们还尝试在启用防护的情况下完成抢劫,我们没有遇到任何问题。但是,如果您如上所述关闭它们会更好。**

**如果您在进行抢劫或任务时仍然遇到任何问题,请联系我们的支持团队并发送:**

**- 抢劫/任务的名称**

**- 您的配置(设置 -> 共享配置)**

**- 描述出现问题的地方,例如:NPC没有生成,载具没有生成,等等**

**- 如果可以,请附上问题的视频**

**我们将尽快修复所有问题!**

**新增功能:**

**- 新增同步拦截"无效坐标",这可能会让战局主机的游戏崩溃**

**- 新增第一人称、第三人称和载具的视野更换(自我 -> 视野)**

**- 新增"恢复 -> 修改创建日期",允许您修改角色创建日期(将其设置为8年)**

**- 新增"恢复 -> 清除作弊统计", 删除您帐户中的一些可疑行为**

**- 新增"战局锁定"的不同模式 -"无需主机"和"智能",其中"无需主机"不需要您成为战局主机,"智能"会自动选择适当的方法**

**- 新增缺失的"检查Tree低级"检查"受限的实体生成"**

**- 新增"速踢" 到"互动 -> 恶搞 -> 踢出战局", 其中有一个设置,告诉玩家应该在战局中主机序列**

**- 新增"循环悬赏" 到"互动 -> 友好", 您可以使用此功能向战局中的任何一位玩家获得钱(包括获得玩家赏金的排名和成就)**

**- 新增"锁定所有玩家" 与"解锁所有门" 到"载具 -> 门"**

**- 新增"K/D","击杀","死亡","现金","银行存款","经验","等级","使用RC遥控车", 到"互动 -> 监管 -> 玩家信息"**

**移除功能:**

**- 移除"自我 -> 视野 -> 晃动视野" (替换成视野更换)**

**- 移除"恢复"里的"循环赏金" - 现在在"互动 -> 友好"**

**- 移除布娃娃恶搞、附加、杀死被动模式,因为它们已在最新更新中被R星修复(我们可能会在未来使用其他方式实现将它们添加回来)**

**保护和稳定性:**

**- 提高菜单的整体稳定性,现在您应该体验到更少的自我崩溃**

**- 改进同步Tree防护**

**- 修补武器池溢出崩溃**

**- 其他一些崩溃防护改进**

**其他的更新:**

**- 修复"载具 -> 升级", 现在它们应该更好的运作**

**-"载具 -> 引擎 -> 涡轮" 现在的最大值为25(以前为 5)**

**-"载具 -> 加速 -> 力量" 对于"精确"模式，现在最大值为1000(以前为 300)**

**- 修复"反挂机视角"，现在它也可以在载具上使用**

**一些透视：**

****![](<../../.gitbook/assets/image (294).png>)****![](<../../.gitbook/assets/image (198).png>)****
{% endhint %}

## **午夜更新至 2022.02.06**

{% hint style="info" %}
**更新日志:**

**- 添加新的(Izuku)崩溃到玩家互动选项**

**- 添加赏金循环到恢复选项里,自动添加指定数量(从1到1万)的金钱**

**- 添加玩家-模型-模型名称输入hash切换模型的功能**

**- 添加忽略在室内的玩家到EPS透视里**

**- 添加可锁定到载具修改里**

**- 添加稳定直升机气流到载具修改里**

**- 添加稳定飞机气流到载具修改里**

**- 添加Players.get\_network\_handle(ply)函数到Lua API里**

**防护:**

**- 修复导致图形命令池溢出并导致崩溃的漏洞**

**- 修复一个允许行人池溢出并导致崩溃的漏洞**

**- 修复一个因声音攻击而导致崩溃的漏洞**

**- 添加限制实体创建到防护选项里**

**- 添加限制行人渲染到防护选项里**

**- 添加拦截网络声音到防护选项里**

**Bug修复:**

**- 修复导致周围玩家崩溃的错误**

**- 修复如果没有为玩家刷新模型,可能会出现防护误报的错误**

**- 为原来的NETWORK\_GET\_PARTICIPANT\_INDEX添加额外的代码执行检查**

**其他调整:**

**- 改进在战局中获取玩家信息方式,现在可以更快获取信息了**

**- 防护选项中删除阻止太多相同的实体对象选项**

**- 载具爬墙功能现在忽略飞行载具和船只**

**解释限制实体创建如何工作:**

**限制实体创建防护是阻止太多相同实体对象防护的改进版,它在验证方法和阻止方法上有所不同.**

**新方法不能给出导致同步阻塞的误报,因为该方法的工作原理是在超出指定限制时限制游戏世界中任何玩家创建任何对象.**

**这样的限制可以防止任何基于实体池溢出原理的攻击,但是在实测中,您可能看不到周围玩家的实体.**

**这种情况是不可避免的,如果您更喜欢和信任的人一起玩,建议在防护->其他中启用不拦截好友选项.**

**建议将此选项与限制行人渲染器选项结合使用.**

**解释限制行人渲染器如何工作:**

**有针对游戏渲染的攻击.**

**此类攻击利用渲染器命令列表的溢出,并且您受到此类漏洞攻击的常见迹象之一是无声关闭游戏而没有任何错误和日志,并且在某些情况下可能会出现延迟.**

**此类攻击是通过创建大量行人来实现的,该模型在您旁边有很多细节.**

**此选项在渲染器中引入了限制,可防止命令列表达到临界大小,从而防止游戏崩溃.**

**启用此选项后,游戏在受到攻击时不会崩溃,但在您离开攻击区域之前,环境会以部分或完全透明的形式出现一些行人或玩家的变形.**

**建议将此选项与限制实体创建选项结合使用.**
{% endhint %}

## 午夜更新至 2022.01.24

{% hint style="info" %}
**更新日志：**

**崩溃保护：**\
**- 修复了由于状态不正确导致崩溃的漏洞**\
**- 修复了由于混合头数据不正确导致崩溃的漏洞**\
**- 修复了由于访问不正确的矩阵而导致崩溃的漏洞**\
**- 修复了由于PED变异数据结构中的纹理值不正确而导致崩溃的漏洞**\
**- 修复漏洞导致Synctree损坏因缓冲区过度读取**

****\
**Bug修复：**\
**- 修复了由于无法获得哪些对象坐标而导致的错误**\
**- 修复了收到的坐标可能是违规行为所致的错误**\
**- 修正了未显示某些车辆预览的错误**\
**- 修正了警察自行车被认为是侵权对象的错误**\
****\
**改进：**\
**- 改进汽车维修，现在此功能考虑到破车鞋垫**\
**- 改进了传送 - >目标自我，现在只有汽车中的玩家将在这个地方显示**\
**- 改进了传送 - >目标到自我，现在它的工作要好得多，不需要窥探员工后面**\
**- 改进的车辆 - > Wallride ，现在它只能应用在汽车底部的地面/物体附近**\
**- 改进的车辆 - > Carjump**\
**- 改进的车辆 - >加速**\
****\
**玩家的新功能 - >互动：**\
**- 添加了管理器交互选择菜单管理器中的新项目 - >交互 - >车辆**\
**- 添加交互 - >车辆 - > Boostveh，推动播放器的车向前**\
**- 添加互动 - >车辆 - > carjump让玩家的汽车跳跃**\
**- 添加交互 - >车辆 - > ModifyVelocity，允许您将播放器的汽车推向任何指定的方向**\
**- 添加交互 - >车辆 - > upgradeveh，允许您按5按钮施加车辆升级预设，如车辆的车辆选项卡**\
****\
**其他新功能：**\
**- add der detect - 超级跳转**\
**- 添加了MODDER检测 - 畸形盔甲**\
**- 返回后车 - >加速 - >合法，让您更精确地定制加速度**\
****\
**其他：**\
**- 由于无用和不便，删除了noclip方法 - >世界**\
**- 删除了NT系统保留消息的日志记录**\
**- 更新了本地化文件**
{% endhint %}

## 午夜更新至 2022.01.13

{% hint style="info" %}
**更新日志:**

**引擎：现在你在游戏内聊天内使用 Ctrl+V (粘贴)**\
**玩家：新增玩家列表中的铭牌 "下个战局主机" (\[N])**\
**防护：新增针对使用网络踢出到线下的拓展防护**\
**交互：新增在 "发送短信" 功能上使用虚假名称**\
**交互：新增在 "发送短信" 时应用到所有玩家**\
**载具：改进 "载具跳跃"**\
**载具：新增动作 "传送进个人载具"**\
**通用：新增 "下个战局主机已更改" 事件的控制台通知**\
**通用：更新本地化文件**\
****

**LUA:**

**- 添加“建议”里的功能**

**- 添加当新文件被添加到“Lua”文件夹/从“Lua”文件夹中添加/删除时，Lua列表自动刷新**

**- 修复检查文件路径正确性功能检查相对路径时会提出异常的问题**

**- 修复使用相对路径访问游戏文件夹而不是菜单文件夹时的错误**

**- 修复了Fs.file\_append重写整个文件时的问题**

**- 为Player.send\_sms添加了重新加载，允许虚假发件人名称（Players.send\_sms(dest, src, text)）**

**- 玩家: 添加新的功能:**

**-- Player.is\_next\_host(ply)**

**-- Player.get\_host\_priority(ply)**

**-- Player.get\_hosts\_queue()**

**-- Player.teleport\_to\_island(ply, is\_invite)**

**-- Player.teleport\_to\_interior(ply, interior\_id)**

**-- Player.teleport\_to\_mission(ply)**

**-- Player.teleport\_to\_cutscene(ply)**

**-- Player.ceo\_kick(ply)**

**-- Player.ceo\_ban(ply)**

**-- Player.Vehicle\_destroy(ply)**

**-- Player.Vehicle\_kick(ply)**

**-- Player.Vehicle\_disown(ply)**

**-- Player.Vehicle\_emp(ply)**

**-- Player.clear\_wanted\_level(ply)**

**-- Player.cops\_blind\_eye(ply)**

**-- Player.off\_the\_radar(ply)**

**-- Player.set\_bounty(ply, bounty, is\_anon)**

**-- Player.force\_cam(ply)**

**-- Player.kick(ply)**

**-- Player.kick\_brute(ply)**
{% endhint %}

## 午夜更新至 2021.12.17

{% hint style="info" %}
**更新日志:**\
**- 适配最新游戏版本 1.58**\
**- 新增新版本载具**\
**- 新增新版本武器**\
**- 新增 "自动瞄准 - 自动扳机"**\
**- 新增功能 "自身选项 - 修改 - 快速落地"**\
**- 新增崩溃 "战局选项 - 修改 - BNHA 崩溃"**\
**- 新增崩溃 "战局选项 - 修改 - 崩溃战局主机"**\
**- 在 "玩家列表 - 互动 - 调节 - 玩家信息" 中为玩家加入新游戏客户端检测**\
**- 新增交互功能 "玩家列表 - 交互 - 恶搞 - 载具控制"**\
**- 新增交互功能 "玩家列表 - 交互 - 恶搞 - 强制重置视角"**\
**- 新增交互功能 "玩家列表 - 交互 - 恶搞 - 爆炸"**\
**- 新增交互功能 "玩家列表 - 交互 - 恶搞 - 毁坏被动模式"**\
**- 新增交互功能 "玩家列表 - 交互 - 恶搞 - 设置悬赏金"**\
**- 新增交互功能 "玩家列表 - 交互 - 恶搞 - 掉帧攻击"**\
**- 新增交互功能 "玩家列表 - 交互 - 恶搞 - 显示du场过场动画"**\
**- 新增崩溃 "玩家列表 - 交互 - 崩溃 - 脚本主机崩溃"**\
**- 新增崩溃 "玩家列表 - 交互 - 崩溃 - 帝国(Imperium)崩溃"**\
**- 新增即时功能 "玩家列表 - 交互 - 恶搞 - 空袭玩家"**\
**- 为可能出现在战局中的 R\* 管理员添加新的检测**\
**- 新增新类型的 "强制战局主机" - "避开战局主机" (你将是战局最后一个成为战局主机的，这对使用 BNHA 崩溃更好)**\
**- 新增工具枪 "重力枪"**\
**- 修复交互功能 "玩家列表 - 交互 - 友好 - 移除附加物" 会试图重复删除附件的问题**\
**- 修复行为 "载具选项 - 动作 - 清理" 无法在本地正常工作的问题**\
**- 修复玩家长距离驾驶载具时获取坐标的问题**\
**- 修复笼子生成在地下的问题**\
**- 修复禁用虚假信息后未及时复原的问题**\
**- 修复调用 Lua 函数 'Lobby.change\_session' 后导致游戏卡住的问题**\
**- 修复当一名玩家离开战局后，对此玩家列表位的操作可对到来的新玩家生效的问题**\
**- 修复使用 "玩家列表 - 交互 - 调节 - 玩家信息" 会改变玩家的问题**\
**- 修复 "解锁所有研究项" 不起作用的问题**\
**- 修复玩家应用新服饰后使玩家离开所在载具的问题**\
**- 修复服饰组件数值不归位的问题**\
**- 修复 "其他功能 - 流星雨" 在某些情形下失效的问题**\
**- 交互功能"玩家列表 - 交互 - 恶搞 - 交易错误" 现在具有"可选"种类了**\
**- 崩溃选项"战局选项 - 行动 - 崩溃所有玩家" 移到了 "战局选项 - 修改 - 无 Thots 崩溃"**\
**- 工具枪现在可在任何武器上使用**\
**- 工具枪 "信息工具" 在物体未被同步时只会显示实体 ID 和哈希值**\
**- 改进偷偷改为战局主机的检测**\
**- 改进恶搞功能检测**\
**- 改进更多崩溃类型防护**\
**- 改进菜单初始化速度**\
**- 修复当多开时签名搜索冲突的问题**\
**- 新增遗漏的云端变量**\
**- 改进本地化文件**\
**- 召回旧版 RID 追战局功能**\
**- 拓展恢复选项卡**\
**- 其他改进**

**LUA 更新日志**

**- 活动 -**

\- **添加了一个新事件 OnSessionJoin() -**

**- 添加了一个新事件 OnSessionLeft() -**

**- 添加了一个新事件 OnSpawn(is\_online) -**

**- 添加了一个新事件 OnMetric(class\_name, name) -**

**- 添加了一个新事件 OnWarningScreen(script\_thread, entryHeader, entryLine1, entryLine2,instructionalKey)**

**- 玩家 -**

**- 增加了一个新函数players.get\_client(ply)**

**- 实用程序 -**

\- **添加了一个新函数 utils.change\_ped\_model(hash/string)**

**- 画 -- Пространсто имён полностью переработано, добавлены новые функции и исправлены некоторые яцкоторые ялекоторые ялекоторыж -**

**- 名称空间已完全重新设计。添加了新功能并修复了一些错误（文档将在稍后更新）**

**- 为函数 entity.spawn\_ped、entity.spawn.veh、entity.spawn\_obj 添加了参数“name”作为字符串的重载 - 修正了一个错误，该错误导致实体无法使用 entity.spawn\_ped 和 entity.spawn\_obj 函数生成**

**- 修复了导致事件 OnKeyPressed 在打开菜单时不起作用的错误**

**- 现在池类型返回类型表的功能**
{% endhint %}

## 午夜更新至 2021.11.20

{% hint style="info" %}
**更新日志：**

**改进了崩溃保护**

**- 改进了对其他玩家报告的保护，现在会有带类型指示的报告/建议通知。**

**- 修正了一些错误处理程序**

**- 修正了不正确的射击参数**

**- 修复了突发事件**

**- 修正了 "互动->不在雷达上"。**

**- 修正了 "互动->交易错误"**

**- 修正了在菜单打开时执行汽车跳跃的情况**

**- 修复了盔甲的ESP**

**- 改进了 "战局->RID战局追踪"**

**-- 增加了以旁观者身份进入战局的功能**

**-- 增加了进入单人封闭战局的能力**

**-- 修复了必须要有 "朋友 "才能连接的问题**

**-- 减少了连接初始化的时间**

**- 增加了 "在车辆中 "的标志**

**- 增加了为战局选择区域的功能**

**- 增加了修改者标志 "畸形的昵称"。**

**- 现在，日志文件不会被封锁，可以在你登录时打开。 (已编辑)**

**LUA**

**增加了一个库utf8**

**修复了卸载或加载脚本时的崩溃**

**修复了在使用OnDirectXPresent和OnRirectXResizeBuffers事件时的崩溃**

**修复了使用entity.request\_control函数时的崩溃**

**增加了一个事件OnFrame(每次在产品中使用绘制函数时调用)**

**增加了为玩家列表创建自定义标志的能力**

**现在任何地方都可以叫native**

**你应该记住，由于实现的差异，本机SYSTEM::WAIT仍然需要在光纤池中使用**

**下发简单来说就是完善LUA**

**-- Updated namespace entity（更新的名称空间实体）**

**--- Added function entity.spawn\_ped**

**--- Added function entity.spawn\_veh**

**--- Added function entity.spawn\_cloud\_veh**

**--- Added function entity.spawn\_obj**

**--- Added function entity.delete**

**--- Added function entity.is\_controlled**

**--- Added function entity.request\_control**

**--- Removed function entity.get\_all\_vehicles**

**--- Removed function entity.get\_all\_peds**

**--- Removed function entity.get\_all\_objects**

**--- Removed function entity.get\_all\_ents**

**-- Added namespace fs（添加了命名空间 fs）**

**--- Added function fs.file\_load\_bin**

**--- Added function fs.file\_load\_txt**

**--- Added function fs.file\_write**

**--- Added function fs.file\_append**

**--- Added function fs.file\_free**

**--- Added function fs.exists**

**--- Added function fs.file\_exists**

**--- Added function fs.directory\_exists**

**--- Added function fs.create\_dir**

**--- Added function fs.is\_file**

**--- Added function fs.is\_dir**

**--- Added function fs.delete**

**--- Added function fs.get\_dir\_appdata**

**--- Added function fs.get\_dir\_product**

**--- Added function fs.get\_dir\_log**

**--- Added function fs.get\_dir\_script**

**--- Added function fs.get\_dir\_windows**

**--- Added function fs.get\_dir\_game**

**--- Added function fs.get\_size**

**--- Added function fs.get\_files**

**--- Added function fs.get\_directories**

**--- Added function fs.get\_all**

**-- Updated namespace menu（更新了命名空间菜单）**

**--- Added function menu.is\_menu\_opened**

**--- Added function menu.get\_main\_menu\_size**

**--- Added function menu.get\_main\_menu\_size\_x**

**--- Added function menu.get\_main\_menu\_size\_y**

**--- Added function menu.get\_main\_menu\_pos**

**--- Added function menu.get\_main\_menu\_pos\_x**

**--- Added function menu.get\_main\_menu\_pos\_y**

**-- Updated namespace player（更新了命名空间播放器）**

**--- Added function player.get\_script\_host**

**--- Added function player.get\_session\_host**

**--- Added function player.set\_modder\_flag**

**--- Added function player.remove\_modder\_flag**

**--- Added function player.get\_rid**

**--- Added function player.send\_sms**

**--- Added function player.is\_spectating**

**--- Added function player.get\_spectating**

**--- Added function player.is\_god**

**--- Added function player.is\_script\_host**

**--- Added function player.is\_session\_host**

**--- Added function player.is\_in\_interior**

**--- Added function player.is\_in\_vehicle**

**--- Added function player.flags.create**

**--- Added function player.flags.delete**

**--- Added function player.flags.set\_color**

**--- Added function player.flags.set\_caption**

**--- Added function player.flags.set\_description**

**--- Added function player.flags.set\_callback**

**-- Added namespace pools**

**--- Added function pools.get\_all\_vehicles**

**--- Added function pools.get\_all\_peds**

**--- Added function pools.get\_all\_objects**

**--- Added function pools.get\_all\_ents**

**--- Added function pools.get\_all\_pickups**

**-- Added namespace draw（增加了命名空间draw）**

**--- Added function draw.get\_window\_width**

**--- Added function draw.get\_window\_height**

**--- Added function draw.get\_screen\_width**

**--- Added function draw.get\_screen\_height**

**--- Added function draw.create\_texture\_from\_file**

**--- Added function draw.create\_texture\_from\_memory**

**--- Added function draw.release\_texture**

**--- Added function draw.texture**

**--- Added function draw.line**

**--- Added function draw.text**

**--- Added function draw.rect**

**--- Added function draw.rect\_filled**

**--- Added function draw.rect\_filled\_multi\_color**

**--- Added function draw.quad**

**--- Added function draw.quad\_filled**

**--- Added function draw.triangle**

**--- Added function draw.triangle\_filled**

**--- Added function draw.circle**

**--- Added function draw.circle\_filled**

**--- Added function draw.ngon**

**--- Added function draw.ngon\_filled**

**-- Added namespace social（添加了命名空间社交）**

**--- Added function social.is\_ready**

**--- Added function social.get\_username**

**--- Added function social.get\_mail**

**--- Added function social.get\_rid**

**-- Added namespace http（添加命名空间http）**

**--- Added function http.get**

**-- Updated namespace utils（更新的命名空间实用程序）**

**--- Added function utils.set\_mouse\_pos**

**--- Added function utils.get\_mouse\_pos**

**--- Added function utils.set\_clipboard**

**--- Added function utils.vector\_to\_angle**

**--- Added function utils.world\_to\_screen**

**--- Added function utils.send\_chat**

**-- Updated namespace vehicle（更新的命名空间车辆）**

**--- Removed function vehicle.spawn**

**--- Removed function vehicle.spawn\_cloud**
{% endhint %}

## 午夜更新至 2021.10.16

{% hint style="info" %}
**更新日志:**

**- 添加了 Lua**

**- 增加了对 RID 0 崩溃的保护**

**- 增加了对混音器崩溃的保护**

**- 添加了丢失的 Cloud Config 参数**

**- 添加交互 -> Griefing -> Desync Kick（不能应用于主机，在这种情况下你会被踢）**

**- 添加交互 -> 审核 -> 显示个人资料**

**- 添加了全局武器修改器（适用于每种武器）**

**- 添加车辆 -> 修改器 -> Wallride 能够配置功率属性和绑定支持（切换，按键时）**

**- 为车辆增加了加速和减速绑定 -> 加速**

**- 新增传送 -> Blips（可配置必要的地图点）**

**- 添加传送 -> 自动航点传送**

**- 为 ESP 添加了玩家标记（它与玩家列表中的标记相同）**

**- 为车辆的 Spawn 修改器添加了即时爆炸**

**- 添加了杀死行人的能力，并能够在通知消息中显示您的名字（其他 -> Blip Funcs -> 杀死所有敌人（此时您必须使用任何枪））**

**- 添加修饰符播放器 -> 修饰符 -> 无限 BST（牛鲨睾酮）**

**- 添加了修改器播放器 -> 修改器 -> 移动收音机**

**- 添加了修改器大厅 -> 修改器 -> 锁定会话（需要主机）**

**- 添加了视觉效果 -> 禁用 HUD**

**- 添加了对玩家的搜索 -> 互动**

**- 添加了在 World -> Clouds 中配置云密度的功能**

**- 添加强制会话主机方法（默认 - 经典强制主机方法；静音 - 其他菜单不易检测，但如果有其他具有强制会话主机功能的玩家，则不保证主机传输给您；硬保证强制主机方法，但可以导致游戏错误，在某些情况下，您可能会被踢出会话）**

**- 添加了世界 -> 水**

**- 添加了大厅 -> 大厅名称欺骗器（所有连接的玩家的名称都将更改）；所有连接的玩家都会看到你的假昵称，但你将无法看到它**

**- 修复了强制会话主机错误，导致聊天中断和无法在会话中连接到其他午夜用户（可能还有其他菜单）**

**- 修复了导致任务中断的脚本过滤器错误**

**- 修正了 DropRP 和金钱，现在可以被其他玩家看到**

**- 固定世界 -> 时间 -> 锁定时间**

**- 固定世界 -> 时间 -> 当地时间**

**- 固定 Noclip 透明**

**- 修复了引擎回调调用的 FPS 下降**

**- 修复了禁用自我报告系统启用时 FPS 下降的问题**

**- 修复了罕见的签名搜索崩溃**

**- 修复了使用交互功能时崩溃的问题**

**- 固定车辆 -> 动作 -> 快速停止**

**- 修复了某些“行人”的错误“模型不匹配”阳性**

**- 修复了菜单控制台中的颜色混合**

**- 固定 ESP 盒粘在屏幕的角落**

**- 修复了导致无法显示多个修改器原因的修改器检测错误**

**- 固定的传送工具会破坏玩家所在的车辆传送**

**- 改进无效任务保护**

**- 改进无效节点保护**

**- 禁用自我报告系统从现在开始总是启用**

**- Kick Brute 交互现在在 Kick Brute 和 Script Sender 上分开**

**- 紧急按钮（保护）现在没有默认设置（如果您不需要使用该功能，请删除绑定并保存配置）**

**- 更新本地化文件**

**脚本发件人：**

**可以在此处找到有关此功能如何工作的简短说明：**[**https://midnight.im/threads/3177/**](https://midnight.im/threads/3177/)****

**路亚：**

**文档可以在这里找到：**[**https://docs.midnight.im/midnight-gta5/lua**](https://docs.midnight.im/midnight-gta5/lua)****

**LUA API 本身的文档仍在开发中，API 集将在未来的更新中扩展。请继续关注后续更新。**

**如果您对扩展功能有任何建议或愿望 - 写到适当的主题：**[**https://midnight.im/forums/59/**](https://midnight.im/forums/59/)****

**LUA 示例：**

**各种功能的示例可以在文档或 GTA 5 部分的论坛中找到，链接如下：**[**https://midnight.im/forums/59/**](https://midnight.im/forums/59/)****

**LUA VSCode 扩展：**

**扩展可以直接从 VSCode 的适当部分添加，只需在搜索栏中插入“0x800080.midnight-lua-api-snippets”。您将看到带有 Midnight 徽标的所需扩展名。**

**附注**

**任务/抢劫的所有问题都已修复（在测试期间发现的问题。）。但是，如果由于某种原因某些东西对您不起作用，请联系支持人员并提供所出现问题的完整描述并报告任务/抢劫的名称**
{% endhint %}

## 午夜更新至 2021.08.26

{% hint style="info" %}
**更新日志:**

**- 为会话中的玩家添加了聊天命令（大厅选项卡）**

**- 添加了汽车预览**

**- 为汽车添加了油漆编辑器（Chrome、Metallic 等）**

**- 增加了小猪骑**

**- 在玩家列表中添加了新标签（\[A] - Rockstar dev，\[C] - Cheater）**

**- 添加了互动“善良 - >清除附件”**

**- 添加修饰符“自我 -> 修饰符 -> 无限氧气”**

**- 在武器部分增加了汽车射击**

**- 增加玩家车内关门功能玩家-> 悲伤- 将 ForceAsDriver 添加到武器 -> JumpInVehicle 和玩家 -> 审核 -> JumpInVehicle**

**-为车辆升级添加了珠光和车轮颜色- 为车辆升级添加了 WindowTint / TyreSmoke 颜色- 增加了打开/关闭汽车门（引擎盖和后备箱）的功能**

**- 生成时通过门向玩家添加车辆的旋转- 添加了从游戏中获取汽车名称的功能**

**- 在内部添加了 noclip 速度设置- 将当地雪添加到“世界 - > 天气”- 修正了瞄准机器人的工作，现在它应该正常命中，不管什么**

**- 修复了使用 Negotium 崩溃时罕见的游戏崩溃- 修复了加载配置时通知样式参数的切换**

**- 修正了模组标签可以设置在自己身上的情况**

**- 修复了在错误转储期间检查不正确的内存区域时崩溃的问题**

**- 修复了“彩虹车”选项在“车辆”选项卡打开时会出现意外结果的问题**

**- 修复了在启用“允许角色控制”选项时打开菜单时切换武器和无线电台的问题**

**- 修复了“霓虹灯”中文本的剪辑**

**- 修复了颜色编辑器“霓虹色”的工作**

**- 扩展通知设置**

**- 扩展了会话中有关模组的通知**

**-** **有关脚本中异常情况的扩展信息**

**- 增加了攻击“大厅->动作->全部崩溃”的持续时间，以增加玩家被击倒的机会**

**- 现在选择第一个项目后“霓虹灯”不会关闭**

**- 选项“生成后进入车辆”现在在生成车辆列表时不起作用并且适用于云车辆**

**- 更新了本地化文件**
{% endhint %}

## 午夜更新至 2021.08.06

{% hint style="info" %}
**更新日志：**

* **增加了”传送到内部"的互动**
* **修正:了车辆颜色与其他玩家同步的问题**
* **修正:了在游戏菜单中生成车辆时的崩溃问题**
* **增加了“恢复->杂项\~>绕过教程"选项**
* **增加了将当前会话的玩家列表保存到玩家文件夹中的文件，该文件将在启动器附近创建(大厅->行动->收集玩家)。**
* **按钮“杂项->剪辑\~>跳过剪辑“现在总是可用的。**
* **增加了“大厅->行动->离开会议"选项。**
* **-增加了显示“玩家信息“窗口时的崩溃错误的快速修复。**
* **. 改进了崩溃保护**
* **-增加了高级保护配置**
* **日志文件现在被保存在“日志"文件夹中**
* **绕过观众检测“选项现在默认启用**
* **增加了显示观战玩家的名字**
* **-为“玩家信息"互动添加了"复制到剪贴板“按钮**
* **增加了“世界>修改器->禁用雾"选项**
* **修正了使用'Negotium'时的崩溃问题**
* **增加了武器>修改器->彩虹枪。**
* **增加了武器>修改器>小丑枪。**
* **-添加了错过的轮子类型**
* **-添加了视觉\~>杂项>显示FPS'。**
* **添加了保护->杂项->不阻挡朋友"选项.**
* **-为保护->杂项添加了绑定，允许你配置恐慌键来立即启用所有保护选项。-增加了保护>事件>爆炸事件' -增加了"传送到内部互动**
* **. 修正了与其他玩家同步的车辆颜色**
* **修正了在游戏菜单中生成车辆时的崩溃问题**
* **增加了“恢复->杂项->绕过教程"选项**
* **. 增加了将当前会话玩家列表保存到玩家文件夹中的文件，该文件将在启动器附近创建(大厅->行动>收集玩家)。**
* **. 按钮“杂项->剪辑\~>跳过剪辑“现在总是可用的。**
* **增加了“大厅\~>行动->离开会议“选项。**
* **增加了显示“玩家信息“窗时的崩溃错误的快速修复。**
* **.改进了崩溃保护**
* **增加了高级保护配置**
* **日志文件现在被保存在“日志“文件夹中**
* **绕过观众检测“选项现在默认启用**
* **增加:了显示观战玩家的名字**
* **-为“玩家信息"互动添加了"复制到剪贴板“按钮**
* **增加了“世界->修改器->禁用雾"选项**
* **修正:了使用'Negotium'时的崩溃问题**
* **增加了武器>修改器->彩虹枪。**
* **增加了武器>修改器->小丑枪。**
* **-添加了错过的轮子类型"**
* **添加了视觉>杂项->显示FPS'。**
* **-添加了“保护->杂项->不阻挡朋友选项**
* **-为保护->杂项添加了绑定，允许你配置恐慌键来立即启用所有保护选项。. 增加了保护->事件->爆炸事件"。\* -**
{% endhint %}
