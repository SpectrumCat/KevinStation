---
title: Pytorch常用方法记录
published: 2024-04-17
description: "继续一些常用的pytorch函数方法"
image: "./pytorch_background.jpg"
tags: ["工具", "词典"]
category: 工具
draft: false
---

# Tensor操作

## permute

**作用**：交换维度

**使用例子**

> 从[0,1,2,3]交换为[3,1,2,0]

```python
import torch
x = torch.randn((10, 10, 10, 10))
x.permute(3,1,2,0)
```

## pad

**作用**：扩展（增广）数据

**使用例子**

> 目标维度的上下左右分别扩展10，20，30，40，扩展值为0
```python
import torch
torch.nn.functional.pad(x, (10, 20, 30, 40), mode='constant', value=0)
```

## roll

**作用**：将张量在维度上平移，超过边界的部分回到0点后继续平移

**使用例子**

>在维度(1,2)上移动(30,40)
```python
import torch
tensor = torch.randn((2,3,4))
shifted_tensor = torch.roll(input=tensor, shifts=(30,40), dims=(1,2))
```