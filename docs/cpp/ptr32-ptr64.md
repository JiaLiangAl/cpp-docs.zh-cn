---
title: __ptr32、__ptr64
ms.date: 10/09/2018
f1_keywords:
- __ptr32_cpp
- __ptr64_cpp
- __ptr32
- __ptr64
- _ptr32
- _ptr64
helpviewer_keywords:
- __ptr64 keyword [C++]
- _ptr32 keyword [C++]
- ptr32 keyword [C++]
- ptr64 keyword [C++]
- _ptr64 keyword [C++]
- __ptr32 keyword [C++]
ms.assetid: afb563d8-7458-4fe7-9c30-bd4b5385a59f
ms.openlocfilehash: 5ff2fa22c8a466252cfaf8b80dc8d56774aff58e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227148"
---
# <a name="__ptr32-__ptr64"></a>__ptr32、__ptr64

**Microsoft 专用**

**`__ptr32`** 表示32位系统中的本机指针，而 **`__ptr64`** 表示64位系统上的本机指针。

以下示例演示如何声明所有这些指针类型：

```cpp
int * __ptr32 p32;
int * __ptr64 p64;
```

在32位系统中，使用声明的指针被 **`__ptr64`** 截断为32位指针。 在64位系统中，使用声明的指针 **`__ptr32`** 被强制转换为64位指针。

> [!NOTE]
> 使用 **`__ptr32`** **`__ptr64`** **/clr： pure**进行编译时，不能使用或。 否则，将生成编译器错误 C2472。 **/Clr： pure**和 **/clr： safe**编译器选项在 visual studio 2015 中已弃用，在 visual studio 2017 中不受支持。

为了与早期版本兼容， **_ptr32**和 **_ptr64**是指定的同义词， **`__ptr32`** **`__ptr64`** 除非指定编译器选项[/za \( 禁用语言扩展）](../build/reference/za-ze-disable-language-extensions.md) 。

## <a name="example"></a>示例

下面的示例演示如何用和关键字声明和分配指针 **`__ptr32`** **`__ptr64`** 。

```cpp
#include <cstdlib>
#include <iostream>

int main()
{
    using namespace std;

    int * __ptr32 p32;
    int * __ptr64 p64;

    p32 = (int * __ptr32)malloc(4);
    *p32 = 32;
    cout << *p32 << endl;

    p64 = (int * __ptr64)malloc(4);
    *p64 = 64;
    cout << *p64 << endl;
}
```

```Output
32
64
```

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[内置类型](../cpp/fundamental-types-cpp.md)
