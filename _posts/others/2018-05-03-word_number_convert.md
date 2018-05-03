---
layout: default
title: word中标题编号转换为纯文本 
tag: others
---
# Word 编号转纯文本
1. Alt+F11 打开VB编辑器
2. 双击This Document 进入该文档编辑界面
3. 输入如下代码
```
Sub ListConverter()
		ActiveDocument.Content.ListFormat.ConvertNumbersToText
End Sub
```
4. 运行，OK