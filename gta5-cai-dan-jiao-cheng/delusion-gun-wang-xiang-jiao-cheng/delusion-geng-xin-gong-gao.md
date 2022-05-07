---
description: 其他更新公告请移步售后群内公告查看，这里只是发送部分更新日志公告
---

# Delusion更新日志

## 2022.05.02 AntiGrind更新至 1.0.5 版本

{% hint style="info" %}
**更新日志：**&#x20;

**新增功能：**

* **添加 Lua API GetAllPeds --GetPedNearbyPeds 本机调用此方法，显然返回一个 lua 表而不是指向某个数组的指针。**
* **添加 Lua API GetAllObjects**
* **添加 Lua API GetAllVehicles --GetPedNearbyVehicles 调用它，显然返回一个 lua 表而不是指向某个数组的指针。**
* **添加 Lua API Faith.CreateSystemThread -- 创建一个真正的线程（与 Citizen.CreateThread 不同），将其用于 Lang.Translate 等繁重的任务以避免滞后游戏线程。**
* **添加 Lua API Faith.GetGameResolution() --返回 Vector2 屏幕分辨率 aka: 1920x1080 -> x=1920 y=1080**
* **完全修改了 Lua 脚本的工作方式，每个脚本现在都是独立的，并做了很多后端工作来支持一些好东西，以备后用，不会破坏这些。**
* **添加 Lua 隔离脚本常量 SCRIPT\_TITLE**
* **添加 Lua 隔离脚本常量 SCRIPT\_STARTUP\_TIME**
* **添加 Lua 隔离脚本常量 SCRIPT\_IS\_AUTORUN**
* **添加 Lua 隔离脚本常量 SCRIPT\_PATH**
* **添加大厅管理人，您可以在其中选择所需的大厅类型。**
* **添加 Lobby Matchmaker 区域（Mr. WorldWide、SA、NA、CN、RU、EU、US、JP）。**
* **添加大厅红娘退出多人游戏。**
* **改进的预览车辆现在默认启用。**
* **现在公民线程和信仰工作者是根据脚本创建的并且是隔离的。**
* **改进的反垃圾邮件，报告是否有误报。**
* **添加 Lua API GTA.SetMatchmakingRegion(region) & GTA.ResetMatchmakingRegion()。**
* **添加大厅媒人，您可以在其中选择所需的大厅类型。**
* **添加 Lobby Matchmaker 区域（Mr. WorldWide、SA、NA、CN、OC、EU、US、JP）。**
* **添加大厅红娘退出多人游戏。**
* **添加快速加入大厅的战局（测试版）。 <- 将改进，所以它更快。**
* **添加发送玩家到 Cayo Perico。**
* **添加 CEO BAN**
* **添加 CEO 踢**
* **添加 CEO 离职**
* **添加发送到恶劣天气。**
* **添加发送到半音轨**
* **添加了发送到夜鲨 AAT。**
* **添加发送到 APC 任务。**
* **添加发送到 MOC 任务。**
* **添加发送到坦帕任务。**
* **添加发送到 Opressor I 任务。**
* **添加发送到 Oppressor II 任务。**
* **在车辆生成器列表中添加了“花式车辆名称”，而不仅仅是使用模型名称。**
* **添加玩家加入/离开通知。**
* **添加战局主机通知。**
* **添加作弊者检测通知。**
* **添加导出到 Lua 到游戏主题编辑器，所以你可以保存它，你也可以将它保存为 autorun.lua 并让它在菜单启动时自动更改游戏的主题。**
* **添加一个切换以将所有日志保存到文件。**
* **添加阻止所有玩家通讯。**

**修复功能**

* **更新本地人名单。 （将来会对此做一些事情，所以你不必依赖我们添加游戏添加的新本地人）**
* **大大提高了 lua DrawApi 性能？也许？**
* **修复了 DrawApi 订单不会更新的问题。如果您有一个问题，您的文本将被绘制在您绘制的正方形下，这可以解决它。**
* **修复了 DrawApiPictureEx，对此感到抱歉。**
* **Vector2 和 Vector4 的小内存使用优化**
* **修复了标记为修改器的错误。**
* **修复了由于微软导致的 lua 执行器崩溃。**
* **修复了在 lua 编辑器中按 WASD 时角色会移动的错误（糟糕，抱歉）**
* **在我们招致一些人所说的技术债务之前，清理/整理和改进了很多后端代码。 （这个清理非常深入，可能会导致崩溃/问题，但是当测试一切都很好时，实际上东西效果更好，只是一个小警告）**
* **修复了一个错误，我他妈的把 PushNotification 的参数按错误的顺序排列...我制作了那个 API...**
* **修正了阻止玩家的所有同步。**
* **QOL：当玩家离开时，您为他们（在玩家列表中）切换的东西将被重置。**
*

    **Changelog : --- Added Stuff ---**

    * **Added Lua API GetAllPeds --GetPedNearbyPeds native calls this instead nd obviously returns a lua table instead of a pointer to some array.**
    * **Added Lua API GetAllObjects**
    * **Added Lua API GetAllVehicles --GetPedNearbyVehicles calls this instead and obviously returns a lua table instead of a pointer to some array.**
    * **Added Lua API Faith.CreateSystemThread --Creates a REAL thread (unlike Citizen.CreateThread), use this for heavy tasks such as Lang.Translate to avoid lagging the game thread.**
    * **Added Lua API Faith.GetGameResolution() --Returns Vector2 with the screen's resolution aka: 1920x1080 -> x=1920 y=1080**
    * **Completely revamped how Lua Scripts work, each script is now isolated and did a lot of backend work to support some goodies for later, won't spoil those.**
    * **Added Lua Isolated Script Constant SCRIPT\_TITLE**
    * **Added Lua Isolated Script Constant SCRIPT\_STARTUP\_TIME**
    * **Added Lua Isolated Script Constant SCRIPT\_IS\_AUTORUN**
    * **Added Lua Isolated Script Constant SCRIPT\_PATH**
    * **Added Lobby Matchmaker where you can pick the type of lobby you want.**
    * **Added Lobby Matchmaker region (Mr. WorldWide, SA, NA, CN, RU, EU, US, JP).**
    * **Added Lobby Matchmaker quit multiplayer.**
    * **Improved Preview Vehicle also it's now enabled by default.**
    * **Now Citizen Threads & Faith Workers are created per script and are isolated.**
    * **Improved Anti Spam, report if there are any false positives.**
    * **Added Lua API GTA.SetMatchmakingRegion(region) & GTA.ResetMatchmakingRegion().**
    * **Added Lobby Matchmaker where you can pick the type of lobby you want.**
    * **Added Lobby Matchmaker region (Mr. WorldWide, SA, NA, CN, OC, EU, US, JP).**
    * **Added Lobby Matchmaker quit multiplayer.**
    * **Added Lobby Join Sessions Fast (BETA). <- Will be improved upon so it's faster.**
    * **Added Send Player to Cayo Perico.**
    * **Added Ceo BAN**
    * **Added CEO Kick**
    * **Added CEO Termination**
    * **Added Send to Severe Weather.**
    * **Added Send to Half Track**
    * **Added Send to Night Shark AAT.**
    * **Added Send to APC Mission.**
    * **Added Send to MOC Mission.**
    * **Added Send to Tampa Mission.**
    * **Added Send to Opressor I Mission.**
    * **Added Send to Oppressor II Mission.**
    * **Added "Fancy Vehicle Names" to the vehicle spawner list, instead of just using model names.**
    * **Added Player Join/Leave Notifications.**
    * **Added Session Host Notifications.**
    * **Added Modder Detection Notifications.**
    * **Added Export to Lua to Game Theme editor, so you can save it, you may also save it as autorun.lua and have it automatically change the game's theme on menu boot.**
    * **Added a Toggle to save ALL logs to file.**
    * **Added Block All Player Comms.**

    **--- Fixed Stuff ---**

    * **Updates natives list. (Will do something about this in the future, so you don't have to rely on us on adding the new natives the game adds)**
    * **Greatly improved lua DrawApi performance? Maybe?**
    * **Fixed a bug where DrawApi order wouldn't be updated. If you had an issue where your text would be drawn under a square you drew, this fixes it.**
    * **Fixed DrawApiPictureEx, sorry for this one.**
    * **Minor memory usage optimizations for Vector2 & Vector4**
    * **Fixed a bug with marking as modder.**
    * **Fixed a crash in the lua executor caused thanks to microsoft.**
    * **Fixed a bug where the character would move if you pressed WASD in the lua editor (oops sorry)**
    * **Cleaned up/tidied and improved a lot of backend code, before we incur what some people call a technical debt. (Was quite deep this cleanup, could cause crashes/issues but when testing all been good in fact stuff works better, just a lil warning)**
    * **Fixed a bug where i fucking put PushNotification's parameters in the wrong order... I made that API...**
    * **Fixed block all Syncs from player.**
    * **QOL: When a player leaves, the things you toggled for them (on the playerlist) will be reset.**
{% endhint %}

## 2022.04.18 AntiGrind更新至 1.0.4 版本

{% hint style="info" %}
**更新日志：**

**新增功能：**

* **添加发送玩家到 佩里科岛。**
* **添加 Lua API GetAllPeds --GetPedNearbyPeds 本机调用此方法，显然返回一个 lua 表而不是指向某个数组的指针。**
* **添加 Lua API GetAllObjects**
* **添加 Lua API GetAllVehicles --GetPedNearbyVehicles 调用它，显然返回一个 lua 表而不是指向某个数组的指针。**
* **添加 Lua API Faith.CreateSystemThread -- 创建一个真正的线程（与 Citizen.CreateThread 不同），将其用于 Lang.Translate 等繁重的任务以避免滞后游戏线程。**
* **添加 Lua API Faith.GetGameResolution() --返回 Vector2 屏幕分辨率 aka: 1920x1080 -> x=1920 y=1080**
* **完全修改了 Lua 脚本的工作方式，每个脚本现在都是独立的，并做了很多后端工作来支持一些好东西，以备后用，不会破坏这些。**
* **添加 Lua 隔离脚本常量 SCRIPT\_TITLE**
* **添加 Lua 隔离脚本常量 SCRIPT\_STARTUP\_TIME**
* **添加 Lua 隔离脚本常量 SCRIPT\_IS\_AUTORUN**
* **改进的预览车辆现在默认启用。**
* **脚本与线程现在每个脚本都是隔离的，将添加一些让您很快利用这一点的东西**

**修复功能：**

* **大大提高了 lua DrawApi 性能**
* **修复了 DrawApi 订单不会更新的问题。如果您有一个问题，您的文本将被绘制在您绘制的正方形下，这可以解决它。**
* **修复了 DrawApiPictureEx，对此感到抱歉。**
* **Vector2 和 Vector4 的小内存使用优化**
* **修复了一些奇怪的崩溃**

**原文：**

**Antigrind 1.0.4**&#x20;

**--- Added Stuff ---**

* **Added Send Player to Cayo Perico.**
* **Added Lua API GetAllPeds --GetPedNearbyPeds native calls this instead nd obviously returns a lua table instead of a pointer to some array.**
* **Added Lua API GetAllObjects**
* **Added Lua API GetAllVehicles --GetPedNearbyVehicles calls this instead and obviously returns a lua table instead of a pointer to some array.**
* **Added Lua API Faith.CreateSystemThread --Creates a REAL thread (unlike Citizen.CreateThread), use this for heavy tasks such as Lang.Translate to avoid lagging the game thread.**
* **Added Lua API Faith.GetGameResolution() --Returns Vector2 with the screen's resolution aka: 1920x1080 -> x=1920 y=1080**
* **Completely revamped how Lua Scripts work, each script is now isolated and did a lot of backend work to support some goodies for later, won't spoil those.**
* **Added Lua Isolated Script Constant SCRIPT\_TITLE**
* **Added Lua Isolated Script Constant SCRIPT\_STARTUP\_TIME**
* **Added Lua Isolated Script Constant SCRIPT\_IS\_AUTORUN**
* **Improved Preview Vehicle also it's now enabled by default.**
* **Faith Workers & Citizen Threads are now isolated per script, will add something that will let you take advantage of this soon**

**--- Fixed Stuff ---**

* **Greatly improved lua DrawApi performance? Maybe?**
* **Fixed a bug where DrawApi order wouldn't be updated. If you had an issue where your text would be drawn under a square you drew, this fixes it.**
* **Fixed DrawApiPictureEx, sorry for this one.**
* **Minor memory usage optimizations for Vector2 & Vector4**
* **Fixed some weird crash**
{% endhint %}

## 2022.04.13 AntiGrind更新至 1.0.3 版本

{% hint style="info" %}
**更新日志：**

**-新增2个新的UI元素。**

**-新增Config/Game Theme下添加了游戏主题编辑器（可以更改游戏UI的颜色）**

**-新增在调整中添加了自定义颜色的车身涂料。**

**-新增在调谐中添加了自定义颜色霓虹灯。**

**-新增在调整中添加了自定义颜色的轮胎烟雾。**

**-新增增加了水上驾驶。**

****

**新增LuaAPI矢量2、3和4操作“+”**

**新增LuaAPI矢量2、3和4操作“-”**

**新增Lua API矢量2、3和4操作“\*”**

**新增Lua API矢量2、3和4操作“/”**

**新增Lua API矢量2、3和4操作“^”**

**新增LuaAPI矢量2、3和4操作“=”**

**新增LuaAPI矢量2、3和4操作“\~=”**

**新增Lua API矢量2、3和4操作“<”**

**新增Lua API矢量2、3和4操作“>”**

**新增Lua API矢量2、3和4操作“>=”**

**新增Lua API矢量2、3和4操作“<=”**

**新增Lua API矢量2、3和4操作“-v”（倒置）**

**新增LuaAPI矢量2、3和4操作“tostring（v）”**

**新增Lua API Vector3 ez teleport“v（PlayerMedia（））”**

**新增Lua API CreateVehicle\&amp;CreatePed\&amp;CreateObject\&amp;CreateObjectNoOffset\&amp;其他；MP生成管理。**

**新增表格解压对Vector2、3和4的支持。**

**新增规范化向量添加了Lua API范数（向量\[2,3,4]v）。你也可以做向量。norm（）来规范化所述向量。**

**简言之，在FiveM的vectors上添加了完全支持，并在上面添加了更多内容。**

****

**-新增Lua API rot2dir（Vector3 v）将旋转向量转换为方向向量。**

**-完全改进了云浏览器的外观和功能，现在你可以喜欢和喜欢一个脚本。**

****

**-新增Lua加密的错误处理**

**-新增Faith PushNotification API**

**-修复一些后端清理。**

**-修复轮胎烟雾不起作用。**

**-修复在框中输入数据时角色移动的问题。**

**-修复云选择框与随机字母散播**

**-修复云未将脚本加载到lua executor的问题**

**-修复云刷新按钮图标**

**-修复lua中固有的DoesEntityExist。**

**-修复lua natives 的一些错误。**

**-修复lua的许多其他 natives 需要char\*作为参数的问题。**
{% endhint %}

## 2022.04.06 AntiGrind更新至 1.0 版本

{% hint style="info" %}
**更新日志：**

**添加：**

**+添加了游戏网络事件挂钩API。（以一种智能的方式，在不破坏游戏的情况下，像其他的菜单那样，制作自己的游戏网络事件保护）。**

**下面是一个例子。**

**+添加并反转了“爆炸事件”游戏NetEvent挂钩。**

**+添加和反转\*“火灾事件”游戏NetEvent挂钩。**

**+添加和反转\*“网络清除任务事件”游戏NetEvent挂钩。**

**+添加并反转\*“武器伤害事件”游戏NetEvent挂钩。**

**+添加并反转\*“开始事件”游戏NetEvent挂钩。**

**+添加并反转\*“报告\现金\生成\事件”游戏NetEvent挂钩。**

**+添加并反转\*“重生玩家事件”游戏NetEvent挂钩。**

**+添加并反转\*“网络事件”游戏NetEvent挂钩。**

**+添加和反转\*“给予武器事件”游戏NetEvent挂钩。**

**+添加并反转\*“移除武器事件”游戏NetEvent挂钩。**

**+添加并反转\*“移除所有武器事件”游戏NetEvent挂钩。**

**+添加并反转\*“报告\现金\生成\事件”游戏NetEvent挂钩。**

**+添加并反转\*“车辆组件控制事件”游戏NetEvent挂钩。**

**+在未反转的事件中添加了游戏NetEvent挂钩**

**+添加了游戏事件（不同于你所知道的网络事件）挂钩API。（这些基本上都是未经修改的，但一些FiveM资源已经在使用它们，并具备一些基本的编程知识，你应该能够将它们的代码与我们的代码一起使用）。**

**+增加了防爆保护，但没有完全禁止爆炸。**

**+添加了重定向加入我的人（通常情况下，当有人用RID加入者跟踪你时，你会使用此功能，它也会对朋友起作用。它会将他们重定向到一个特殊的人的位置 如果此人在线，则进行重定向）**

**+为无效/断开的网络事件添加了被动崩溃保护。**

**+增加了Ped冷冻/该死的保护。**

**+增加了“OnGameEvent”事件。**

**+增加了“OnSessionEnd”事件。**

**+添加了ScriptEvent Lua挂钩API。（您现在可以通过lua制作自己的脚本事件保护）**

**+添加了一个完整的XML生成程序（具有menyoo文件兼容性）（很快就会有一个完整的菜单生成器）**

**+添加了本地XML浏览器**

**+添加了本地Lua脚本浏览器**

**+添加了从文件中打开Lua**

**+在文件中添加了Save Lua**

**+添加了Lua API GTA。塞特通缉犯**

**+添加了Lua API GTA。GetPlayerInfo包含关于玩家的所有已知信息的列表。**

**+添加了Lua API FS。移除文件。**

**+添加了自动游戏聊天翻译。（请查看游戏聊天日志部分）。**

**+增加了对108种语言的支持。**

**+添加了Lua API Lang.Translate（借助argos翻译库，使用机器学习翻译字符串并自动检测语言）**

**+添加了反游戏聊天垃圾信息（目前很简单，但完成任务后，它只会屏蔽大量垃圾信息，不会扫描信息）。**

**+升级到fontawesome pro（适用于lua，所以现在你有了更多字体）。**

**+彻底检查菜单图标/图形。**

**+彻底改进了字体渲染。**

**+经过彻底改造的DirectX渲染，现在速度更快、更平滑，甚至可能更安全一点。**

**+为Faith添加了字体大小支持。在最后一个参数上绘制文本。**

**+加上Lua Draw API Faith。FontSizePush（在调用FontSizePop之前，它会更改字体大小）**

**+加上Lua Draw API Faith。FontSizePop。**

**+加上Lua API Faith。LoadPictureFromUrl。**

**+添加了Lua API GTA。加载图片emugshot。**

**+增加了覆盖时间，小时，分钟，秒。**

**+为SP上的MP车辆添加了检测。**

**+添加了加密您的Lua脚本，人们现在可以在通过菜单加密的同时执行您的Lua脚本。你可以给它自己的密钥\&amp;iv，让它被解密。如果愿意，还可以允许用户解密脚本。**

**+添加了执行加密的Luas**

**+添加了DrawapRect Rounding和Border thickness的参数，这两个参数都是可选的，默认情况下不需要填写0和1。**

**+添加了DrawApiRectFilled取整的参数，它是可选参数，默认情况下不需要填写0。**

**+添加了请求API**

**+Lua编辑器错误UI修复。**

**+在Lua编辑器中添加了“大模式”，这样可以使Lua编辑器更大。**

**修复：**

**-修复Rockstar Anticheat检测（来自其他玩家）不会被记录的错误。**

**-修复OnScriptEvent和OnGameEvent lua事件无法工作的错误。**

**-修复一些文件系统API错误。**

**-修复Lua错误记录器未显示哪些错误的问题**

**-修复Lua编辑器未注册所有输入的问题**

**-给按钮一个鼠标悬停和点击操作**

**-修复车辆在生成后被摧毁的问题**

**-修复他妈的一大堆内部的东西。**

**-修复OnTeamChat和OnPublicChat事件错误触发的问题。**

**-修复DrawApiPicture**

**-修复Lua executor上的“保存到云”图标不工作的问题**

**\*此处反转意味着这些事件将被记录，我们知道参数，因此您不必自己反转它们。**

**目前您自己无法访问未反转的事件参数，我们将在将来的更新中添加该参数。**
{% endhint %}

例子：

```
Hook.GameNetEvent("EXPLOSION_EVENT", function(handle, type, damageScale, audible, invisible, position, netId)
 print(GetPlayerName(handle), " has done a explosion of type ", type)

 if damage > 1000.f then
     return false --Block Explosion
 end

 return true --Don't block explosion
 end)
```

```
// Solocal response = Faith.Request(
    {
        Url = "https://google.com",  -- This website
        Method = "GET",
        Headers = {
            ["Content-Type"] = "application/json"  -- Content-Type
        },
        Body = "" --Optional table
    }
)

if response["StatusCode" == 200 then
    print("Success: " .. response["Results"])
else 
    print("Failed: " .. response["Error"])
end
```

{% hint style="success" %}
在使用钩子之前，请阅读Lua文档，因为这是一个高级API。
{% endhint %}

## 2022.03.20 AntiGrind更新至 0.5.1 版本

{% hint style="info" %}
**更新日志：**\
**添加:**\
**+ 添加了细调玩家载具参数选项**\
**+ 添加了Lua API GTA.GetModderInfractions()（返回其他作弊者的违规行为，像这样："Rockstar AntiCheat I", "Host Token Manipulation", "Rockstar ID Manipulation"）**\
**+ 添加了载具黑色漆面选项**\
**+ 添加了复制玩家外观选项**\
**+ 添加了超人模式**\
**+ 添加了无障碍选项**\
**+ 添加了六星通缉选项**\
**+ 添加了力场模式选项**\
**+ 添加了人物变小选项**\
**+ 添加了显示被标记玩家选项**\
**+ 添加了延长水下时间选项**\
**+ 添加了逮捕自己选项**\
**+ 添加了跳伞选项**\
**+ 添加了清理玩家选项**\
**+ 添加了吞药自杀选项**\
**+ 添加了远程爆胎选项**\
**+ 添加了远程载具告警选项**\
**+ 添加了远程锁定载具车门选项**\
**+ 添加了远程解锁载具车门选项**\
**+ 添加了远程关闭载具引擎选项**\
****\
**修复:**\
**- 重构了整个载具参数调整部分（提高性能，对QOL进行改进，并修复了一些错误）**\
**- 重构了作弊者检测系统（能够看到所有的违规行为）**\
**- 修复了一些作弊者检测的错误**\
**- 重构了玩家列表中的用户界面**\
**- 修复了有关观看玩家功能的小错误**\
**- 修复了卸载LUA脚本的问题**\
**- 修复了LUA API创建子菜单时的间距问题**\
**- 修复了LUA API的开关、按钮等元素不出现在右侧的子菜单内或多个子菜单内的问题**
{% endhint %}

## 2022.03.18 AntiGrind 0.5.0 更新内容

{% hint style="info" %}
**更新日志：**

**--- 添加的东西 ---**

* **添加了对自定义字体的支持（进入Documents/AntiGrind目录，用TTF字体文件替换即可）**
* **添加了GTA.GetTransitionStatus() - ret:string (以漂亮的字符串返回游戏当前状态)**
* **添加了FS.ExecuteFromFile( path)**
* **添加了显示游戏状态（位于屏幕左上方）**
* **添加了让其他玩家的载具控制反转选项（玩家向右，载具就向左，玩家加速，载具就刹车等等...）**
* **添加了让其他玩家的载具减少牵引力的选项**
* **添加了克隆创建防护**
* **添加了克隆同步提示防护**
* **添加了克隆创建提示保护**
* **添加了克隆删除提示保护**
* **添加了克隆组合防护**
* **添加了克隆同步防护**
* **添加了克隆删除防护**
* **添加了阻止所有来自特定玩家或所有玩家的克隆请求选项**
* **添加了让载具打开所有车门选项**
* **添加了让载具关闭所有 车门选项**
* **添加了让载具阴影漆黑一片的选项**

**--- 修复的东西 ---**

* **重构了字体绘制（文字显示更加清晰）**
* **改善了菜单加载时间**
* **修复了LUA界面叠加的错误（稍稍向左偏移）**
* **重构了LUA API编辑器的高亮显示**
* **重构了对所有错误屏幕的防护选项（显示按回车键以继续或同意以继续）**
* **修复了给予载具无敌选项的小错误**
* **重构了部分用户界面的翻译支持**
* **重构了单选按钮（点击任意位置以切换）**
* **修复了注入时产生的崩溃**
{% endhint %}

## 2022.03.14 AG更新至 0.4.7 版本&#x20;

{% hint style="info" %}
**更新日志：**\
**--- 添加的东西 ---**\
**+ 启用了LUA引擎的基础安全配置**\
**+ 添加了作弊者检测-玩家/Ped模型的更改**\
**+ 添加了作弊者检测-Frame Flag Manipulation**\
**+ 添加了Lua API**\
**GTA.GetPlayerIp(Player handle) ret: string.**\
**+ 增加了Lua API。GTA.GetPlayerRID(Player handle) ret: string, string.**\
**+ 增加了Lua API**\
**GTA.IsPlayerScriptHost(Player handle) ret: bool.**\
**+ 增加了Lua API**\
**GTA.IsPlayerHost(Player handle) ret: bool.**\
**+ 增加了Lua API**\
**GTA.RemoveFromGame(Player handle) ret: void**\
**+ 添加了Lua HTTP库（文档即将上线）例子：**\
&#x20; ****  \
**Request.SendRequest({ Url = "https://antigrind.net",** \
&#x20;       **Method = "POST",**\
&#x20;       **Headers = {**\
&#x20;           **\["Content-Type"] = "application/json",**\
&#x20;           **\["User-Agent"] = "User"**\
&#x20;       **},**\
&#x20;       **Body = ""**\
**});**\
****\
**+ 为创建配置文件添加了Lua Json支持**\
****\
**--- 修复的东西 ---**\
**- 做了一些平常的后端工作**
{% endhint %}

## AG更新至 0.4.6 版本&#x20;

{% hint style="info" %}
**更新日志：**

**+ 添加 Lua API Crypt.DecodeBase64 -> args (string str)**\
**+ 添加 Lua API Crypt.EncodeString -> args (string str, string charsetName, string encoding)**\
**+ 添加 Lua API Crypt.DecodeString -> args (string str, string charsetName, string encoding)**\
**+ 添加 Lua API Crypt.EncodeInt -> args (int value, int numBytes, bool littleEndian, string encoding)**\
**+ 添加 Lua API Crypt.DecodeInt -> args (string str, string encoding)**\
**+ 添加 Lua API Crypt.HashString -> args (string str)**\
**+ 添加 Lua API Crypt.HashString -> args (string str, string hashAlgo, string charset, string encoding)**\
**+ 添加 Lua API Crypt.RandomString -> args (int size)**\
**+ 添加Lua API Crypt.RandomIntString -> args (int size)**\
**关于新的Lua APIs的更多细节，请访问文档**\
**https://docs.antigrind.net**\
**--- 修复 ---**\
**- 修复了半无敌**\
**- 修复了通知显示顺序错误的问题**\
**- 删除了Lua API打印中的日志文件记录**\
**- 改进了MarkAsModder API。**\
**- 修复了远程最大出车**\
**- 改进了电磁脉冲（EMP）功能**\
**- 修复了菜单中的输入和GTAV中的其他输入冲突的问题**\
**- 修复了一些中文导航栏不工作的问题​**
{% endhint %}
