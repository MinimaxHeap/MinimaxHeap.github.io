---
title: iOS 提交审核 Invalid Swift Support, SwiftSupport folder is empty
date: 2020-05-13 11:56:03
author: Kevin Feng
tags:
- iOS
---
## 问题描述
iOS提交给app store connect审核被退回,显示如下内容:
> Dear Developer,
> 
> We identified one or more issues with a recent delivery for your app, "". Please correct the following issues, then upload again.
> 
> __ITMS-90424: Invalid Swift Support__ - The SwiftSupport folder is empty. Rebuild your app using the current public (GM) version of Xcode and resubmit it.
> 
> Best regards,
> 
> The App Store Team

## 最新解决办法
2020开始 XCode使用了新的build system. 所以会不产生这个文件夹.

在菜单栏中,XCode或File列找到workspace settings, 点击之后选择legacy build system. 上下都选. 
### 验证是否修复

重新archive. distribute app中选择export而不是upload. 在导出的路径中将ipa文件重命名为zip文件,解压zip看到出现SwiftSupport文件夹即可.