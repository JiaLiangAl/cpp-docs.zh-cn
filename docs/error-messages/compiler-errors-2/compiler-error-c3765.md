---
title: 编译器错误 C3765
ms.date: 11/04/2016
f1_keywords:
- C3765
helpviewer_keywords:
- C3765
ms.assetid: feadee7a-fcfb-402c-af2f-0e656f814a13
ms.openlocfilehash: 8a12bdfaf0931fb0a94dafc289f9ae39aef61f23
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757225"
---
# <a name="compiler-error-c3765"></a>编译器错误 C3765

"event"：不能在标记为 event_receiver 的类/结构 "type" 中定义事件

如果用[event_receiver](../../windows/event-receiver.md)特性标记了类，则该类不能包含[__event](../../cpp/event.md)声明。

下面的示例生成 C3765：

```cpp
// C3765.cpp
[event_receiver(native)]
struct ER2 {
   __event void f();   // C3765
   __event void b(int);   // C3765
};
```
