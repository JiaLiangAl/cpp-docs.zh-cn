---
title: 编译器错误 C3066
ms.date: 03/28/2017
f1_keywords:
- C3066
helpviewer_keywords:
- C3066
ms.assetid: 226f6de5-c4c5-41e2-b31a-2e30a37fbbeb
ms.openlocfilehash: 80468f4e35ffd9d09706b8bb8fc2fdc6eb8e679e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738849"
---
# <a name="compiler-error-c3066"></a>编译器错误 C3066

有多种方法可使用这些参数调用此类型的对象

编译器检测到涉及代理项的不明确的函数调用。

下面的示例生成 C3066：

```cpp
// C3066.cpp
template <class T, class U> void func(T*, U*){}

typedef void (*PF)(const int*, const char*);
typedef void (*PF1)(const int*, volatile char*);

struct A {
   operator PF() const {
      return func;
   }

   operator PF1() {
      return func;
   }

   operator PF1() const  {
      return func;
   }

};

int main() {
   A a;
   int i;
   char c;

   a(&i, &c);   // C3066
   a(&i, (const char *) &c);   // OK
}
```

## <a name="copy-list-initialization"></a>复制列表初始化

在 Visual Studio 2015 中，编译器以与常规复制初始化相同的方式错误地处理复制列表初始化；它只考虑将转换构造函数用于重载决策。 在以下示例中，Visual Studio 2015 选择 MyInt(23)，但 Visual Studio 2017 正确引发错误。

```
// From http://www.open-std.org/jtc1/sc22/wg21/docs/cwg_closed.html#1228
struct MyList {
       explicit MyStore(int initialCapacity);
};

struct MyInt {
       MyInt(int i);
};

struct Printer {
       void operator()(MyStore const& s);
       void operator()(MyInt const& i);
};

void f() {
       Printer p;
       p({ 23 }); // C3066: there are multiple ways that an object of this type can be called with these arguments
}
```
