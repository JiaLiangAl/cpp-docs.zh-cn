---
title: 编译器错误 C3106
ms.date: 11/04/2016
f1_keywords:
- C3106
helpviewer_keywords:
- C3106
ms.assetid: 39d97a32-0905-4702-87d3-7f8ce473fb93
ms.openlocfilehash: 85aef1937ccbdbbbc335e4166fab11aa982b1839
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755832"
---
# <a name="compiler-error-c3106"></a>编译器错误 C3106

"attribute"：未命名参数必须在命名参数之前

未命名参数必须在命名参数之前传递到特性。

有关更多信息，请参见 [User-Defined Attributes](../../extensions/user-defined-attributes-cpp-component-extensions.md)。

## <a name="example"></a>示例

下面的示例生成 C3106。

```cpp
// C3106.cpp
// compile with: /c
[module(name="MyLib", dll)];   // C3106
[module(dll, name="MyLib")];   // OK
```
