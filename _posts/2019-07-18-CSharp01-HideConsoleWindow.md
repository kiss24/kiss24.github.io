---
layout:     post
title:      CSharp01-HideConsoleWindow
subtitle:   
date:       2019-07-18
author:     KS
header-img: img/home-bg-o.jpg
catalog: true
tags:
---

使用如下方式隐藏控制台窗口，可以在任务管理中找到进程

```CSharp
using System.Runtime.InteropServices;

[DllImport("kernel32.dll")]
static extern IntPtr GetConsoleWindow();

[DllImport("user32.dll")]
static extern bool ShowWindow(IntPtr hWnd, int nCmdShow);

const int SW_HIDE = 0;
const int SW_SHOW = 5;

var handle = GetConsoleWindow();

// Hide
ShowWindow(handle, SW_HIDE);

// Show
ShowWindow(handle, SW_SHOW);
```