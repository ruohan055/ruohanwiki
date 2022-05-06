# 2Take1自定义字体

## **1.创建字体** <a href="#uf2nh" id="uf2nh"></a>

**为了使用 2Take1 中的字体，您需要使用 Microsoft 的 MakeSpriteFont 工具将其转换为spritefont文件。**

[**点此下载MakeSpriteFont**](https://github.com/microsoft/DirectXTK/releases/download/jul2020/MakeSpriteFont.exe)

**下载后，在所在目录打开CMD窗口，运行以下命令：**

```
// .\MakeSpriteFont "<font>" <file> /FontSize:<size> /NoPremultiply /Sharp /defaultcharacter:0x2592 /characterregion:0x0-0xFF /characterregion:0x25A0 /characterregion:0x192 /characterregion:0x393 /characterregion:0x398 /characterregion:0x3A3 /characterregion:0x3A6 /characterregion:0x3A9 /characterregion:0x3B1 /characterregion:0x3B4-0x3B5 /characterregion:0x3C0 /characterregion:0x3C3-0x3C6 /characterregion:0x207F /characterregion:0x20A7 /characterregion:0x2219 /characterregion:0x221A /characterregion:0x221E /characterregion:0x2229 /characterregion:0x2248 /characterregion:0x2261 /characterregion:0x2264-0x2265 /characterregion:0x2310 /characterregion:0x2320 /characterregion:0x2321 /characterregion:0x2500 /characterregion:0x2502 /characterregion:0x250C /characterregion:0x2510 /characterregion:0x2514 /characterregion:0x2518 /characterregion:0x251C /characterregion:0x2524 /characterregion:0x252C /characterregion:0x2534 /characterregion:0x253C /characterregion:0x2550-0x256C /characterregion:0x2580 /characterregion:0x2584 /characterregion:0x2588 /characterregion:0x258C /characterregion:0x2590-0x2593 /characterregion:0x4E00-0x9FFF /fastpack
```



* <mark style="background-color:blue;">**\<font>**</mark>**– 字体名称。它必须已经安装在您的 PC 上。**
* <mark style="background-color:blue;">**\<file>**</mark>**– 将创建的 spritefont 文件的名称。确保它有.spritefont扩展名。**
* <mark style="background-color:blue;">**\<size>**</mark>** – 字体大小（以像素为单位）。**

**您可以使用相同的字体但不同的大小创建不同的字体文件。**

**例如微软雅黑24号：**

```
// .\MakeSpriteFont "Microsoft YaHei UI" yahei_24.spritefont /FontSize:24 /NoPremultiply /Sharp /defaultcharacter:0x2592 /characterregion:0x0-0xFF /characterregion:0x25A0 /characterregion:0x192 /characterregion:0x393 /characterregion:0x398 /characterregion:0x3A3 /characterregion:0x3A6 /characterregion:0x3A9 /characterregion:0x3B1 /characterregion:0x3B4-0x3B5 /characterregion:0x3C0 /characterregion:0x3C3-0x3C6 /characterregion:0x207F /characterregion:0x20A7 /characterregion:0x2219 /characterregion:0x221A /characterregion:0x221E /characterregion:0x2229 /characterregion:0x2248 /characterregion:0x2261 /characterregion:0x2264-0x2265 /characterregion:0x2310 /characterregion:0x2320 /characterregion:0x2321 /characterregion:0x2500 /characterregion:0x2502 /characterregion:0x250C /characterregion:0x2510 /characterregion:0x2514 /characterregion:0x2518 /characterregion:0x251C /characterregion:0x2524 /characterregion:0x252C /characterregion:0x2534 /characterregion:0x253C /characterregion:0x2550-0x256C /characterregion:0x2580 /characterregion:0x2584 /characterregion:0x2588 /characterregion:0x258C /characterregion:0x2590-0x2593 /characterregion:0x4E00-0x9FFF /fastpack
```

## **2.导入字体** <a href="#dstxb" id="dstxb"></a>

**确保文件具有.spritefont扩展名，并将其复制到以下目录。请记住，您必须先取消注入菜单（长按F12）,再重新注入才能看到新字体。**

```
// %appdata%\PopstarDevs\2Take1Menu\ui\fonts
```

**之后，你将能够为菜单 UI 的每个元素使用新字体。**
