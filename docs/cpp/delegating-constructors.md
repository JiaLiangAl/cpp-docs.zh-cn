---
title: 委派构造函数 （C++）
description: 在C++中使用委派构造函数来调用其他构造函数并减少代码重复。
ms.date: 11/19/2019
ms.openlocfilehash: f26a013aa3c081d900ffc3eb32649acc77505db0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2020
ms.locfileid: "81316674"
---
# <a name="delegating-constructors"></a>委托构造函数

许多类具有执行类似操作（例如，验证参数）的多个构造函数：

```cpp
class class_c {
public:
    int max;
    int min;
    int middle;

    class_c() {}
    class_c(int my_max) {
        max = my_max > 0 ? my_max : 10;
    }
    class_c(int my_max, int my_min) {
        max = my_max > 0 ? my_max : 10;
        min = my_min > 0 && my_min < max ? my_min : 1;
    }
    class_c(int my_max, int my_min, int my_middle) {
        max = my_max > 0 ? my_max : 10;
        min = my_min > 0 && my_min < max ? my_min : 1;
        middle = my_middle < max && my_middle > min ? my_middle : 5;
    }
};
```

你可以通过添加一个执行所有验证的函数来减少重复的代码，但是如果一个构造函数可以将部分工作委托给其他构造函数，则 `class_c` 的代码更易于了解和维护。 若要添加委托构造函数，请使用 `constructor (. . .) : constructor (. . .)` 语法：

```cpp
class class_c {
public:
    int max;
    int min;
    int middle;

    class_c(int my_max) {
        max = my_max > 0 ? my_max : 10;
    }
    class_c(int my_max, int my_min) : class_c(my_max) {
        min = my_min > 0 && my_min < max ? my_min : 1;
    }
    class_c(int my_max, int my_min, int my_middle) : class_c (my_max, my_min){
        middle = my_middle < max && my_middle > min ? my_middle : 5;
}
};
int main() {

    class_c c1{ 1, 3, 2 };
}
```

当您单步调试上一示例时，请注意，构造函数 `class_c(int, int, int)` 首先调用构造函数 `class_c(int, int)`，该构造函数反过来调用 `class_c(int)`。 每个构造函数将仅执行其他构造函数不会执行的工作。

调用的第一个构造函数将初始化对象，以便此时初始化其所有成员。 您不能在委托给其他构造函数的构造函数中执行成员初始化，如下所示：

```cpp
class class_a {
public:
    class_a() {}
    // member initialization here, no delegate
    class_a(string str) : m_string{ str } {}

    //can’t do member initialization here
    // error C3511: a call to a delegating constructor shall be the only member-initializer
    class_a(string str, double dbl) : class_a(str) , m_double{ dbl } {}

    // only member assignment
    class_a(string str, double dbl) : class_a(str) { m_double = dbl; }
    double m_double{ 1.0 };
    string m_string;
};
```

下一示例演示非静态数据成员初始值设定项的使用。 请注意，如果构造函数还将初始化给定数据成员，则将重写成员初始值设定项：

```cpp
class class_a {
public:
    class_a() {}
    class_a(string str) : m_string{ str } {}
    class_a(string str, double dbl) : class_a(str) { m_double = dbl; }
    double m_double{ 1.0 };
    string m_string{ m_double < 10.0 ? "alpha" : "beta" };
};

int main() {
    class_a a{ "hello", 2.0 };  //expect a.m_double == 2.0, a.m_string == "hello"
    int y = 4;
}
```

构造函数委托语法不会阻止意外创建构造函数递归 - Constructor1 将调用 Constructor2（其调用 Constructor1），在出现堆栈溢出之前不会出错。 您应当避免循环。

```cpp
class class_f{
public:
    int max;
    int min;

    // don't do this
    class_f() : class_f(6, 3){ }
    class_f(int my_max, int my_min) : class_f() { }
};
```
