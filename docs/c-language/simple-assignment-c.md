---
title: 简单赋值 (C)
ms.date: 11/04/2016
helpviewer_keywords:
- type conversion [C++], simple assignment
- data type conversion [C++], simple assignment
- operators [C], simple assignment
- assignment operators [C++], simple
- simple assignment operator
- equal sign
ms.assetid: e7140a0a-7104-4b3a-b293-7adcc1fdd52b
ms.openlocfilehash: 64112a54828a9a6626e78e556e8fe6dc52a3300f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229540"
---
# <a name="simple-assignment-c"></a>简单赋值 (C)

简单赋值运算符可将其右操作数赋给其左操作数。 右操作数的值将转换为赋值表达式的类型，并替换存储在左侧操作数指定的对象中的值。 用于赋值的转换规则适用（请参阅[赋值转换](../c-language/assignment-conversions.md)）。

```
double x;
int y;

x = y;
```

在此示例中，`y` 的值被转换为类型 `double` 并赋给 `x`。

## <a name="see-also"></a>请参阅

[C 赋值运算符](../c-language/c-assignment-operators.md)
