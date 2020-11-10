# Python 基础

## 基本数据类型

1. 三引号 `''' '''` 支持字符串分行；
2. 浮点数 float 不准；
3. 布尔值的运算符是 `and or not`
4. 空值 `None`

## 编码问题

1. 保存 py 代码文件时确保使用 UTF-8 without BOM 编码；
2. 文件开头添加两行注释，让 Python 解释器按 UTF-8 编码读取源文件
    ```
    #!/usr/bin/env python3
    # -*- coding: utf-8 -*-
    ```
    第一行注释告诉 Linux/OSX 这是 python 可执行程序，Windows 会忽略；

## List
1. 列表的数据元素不一定要有一样的数据类型；
2. `name[0:2]` 取一个区间的元素；
3. 添加 `append` , `name.append('name11')`
4. 删除 `del` , `del name[2]`

## tuple
1. 不可变
2. 只有一个元素，`tuple=(123,)` 要在元素后加一个逗号
3. 小括号