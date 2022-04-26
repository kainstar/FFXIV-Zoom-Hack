> 参考 [MYuuuuuu/FFXIV-Zoom-Hack](https://github.com/MYuuuuuu/FFXIV-Zoom-Hack) 的 README 翻译

# FFXIV-Zoom-Hack

允许调整游戏摄像机距离超过游戏内允许的最大距离。

仅在 DX11 版本下可用。

你可以使用源码或点击该地址获取最新的软件版本：https://github.com/kainstar/FFXIV-Zoom-Hack/releases

# 在版本更新后提交新的偏移地址

CE 软件在此处下载: http://www.cheatengine.org/downloads.php
本指南使用的版本为 6.5: http://www.cheatengine.org/download/CheatEngine65NoSetup.rar
该指南适用于任何软件版本，但设置上可能有不同的命名

## 图片指南: https://jayotterbein.com/2016/03/13/hacking-ffxiv-zoom/

## 如果你熟悉 CE 软件的话，可以使用以下简洁指南

1. 在 CE: File - Open process. 打开 ffxiv_dx11.exe（最终幻想 XIV）
2. 在游戏: 拉到最远视角，确保没有碰上障碍物
3. 在 CE: 在软件右侧，更改 Value Type 为 Float，查找 Value 值 20.0
4. 在游戏: 不使用第一人称模式，拉到最近视角
5. 在 CE: 更改 Value 值为 1.5, 按下键盘上的"enter" 或点击软件上的 "Next Scan"
6. 重复步骤 2-5 直到左边的窗口出现了有意义的值，你能过看到这个值随着游戏视角距离的变化而变化。
7. 在 CE: 右键列表中小数位只有一位的选项，点击"find what writes to this address"
8.
9. 在游戏: 拉进拉远视角一会, 在 CE 的新窗口中能看到一条指令代码的出现
10. 在 CE:
11. 选择该条指令
12. 在下方的文本框中查找以'<<' 结尾的指令
13. 查找寄存器与偏移量, 你可以看到一些如 mov [r9+00000128] 的代码(r9:寄存器 00000128：偏移量)
14. 在寄存器中查找地址 在下方可以发现如 R9=0000019E9BC70AC0 的地址. 把这个地址保存到剪贴板或记事本
15. 返回 CE 的主窗口
16. 在 CE: 点击 "New Scan", Value Type 设置为 DX11: 8 Bytes, 勾选 "Hex"，开始查找
17. 在 CE: 顶部的列表可能会出现多个值, 点击表里绿色的值:
18. 双击顶部的地址
19. 双击在出现在底部列表里项目的"Address"值
20. 复制新窗口中"Address"框里的内容,内容为 DX9: ffxiv.exe+offset, DX11: ffxiv_dx11.exe+offset
21. ffxiv_dx11.exe+offset 中的 offset 地址即为所寻找的地址

你已经找到了偏移地址，可以着手修改 Offset.xml 文件, 偏移地址为 mxl 文件里的 DX11 标签内的 StructureAddress 值
