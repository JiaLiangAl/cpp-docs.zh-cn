---
title: for 语句（c + +）
description: 对 Microsoft Visual Studio c + + 中的语句的标准 c + + 的引用。
f1_keywords:
- for_cpp
ms.date: 07/31/2020
helpviewer_keywords:
- for keyword [C++]
ms.assetid: 6c7d01b3-c4c1-4c6a-aa58-e2d198f33d4a
ms.openlocfilehash: b32a50e376113f9f9d550d4984d05fc8c675f14d
ms.sourcegitcommit: f2a135d69a2a8ef1777da60c53d58fe06980c997
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/03/2020
ms.locfileid: "87520844"
---
# <a name="for-statement-c"></a>`for`语句（c + +）

重复执行语句，直到条件变为 false。 有关基于范围的语句的信息 **`for`** ，请参阅[基于范围的 `for` 语句（c + +）](../cpp/range-based-for-statement-cpp.md)。

## <a name="syntax"></a>语法

> **`for (`** *`init-expression`* **`;`** *`cond-expression`* **`;`** *`loop-expression`* **`)`**\
> &emsp;*`statement`*

## <a name="remarks"></a>备注

使用 **`for`** 语句构造必须执行指定次数的循环。

**`for`** 语句由三个可选部分组成，如下表所示。

### <a name="for-loop-elements"></a>for 循环元素

| 语法名称 | 执行时间 | 说明 |
|--|--|--|
| *`init-expression`* | 在语句的任何其他元素之前 **`for`** *`init-expression`* 执行一次。 然后，控制将传递到 *`cond-expression`* 。 | 通常用来初始化循环索引。 它可以包含表达式或声明。 |
| *`cond-expression`* | 在执行的每次迭代之前 *`statement`* ，包括第一次迭代。 *`statement`* 仅当 *`cond-expression`* 计算结果为 true （非零）时才执行。 | 计算结果为整数型或明确转换为整数型的类类型的表达式。 通常用于测试循环终止条件。 |
| *`loop-expression`* | 在每次迭代结束时 *`statement`* 。 *`loop-expression`* 执行后， *`cond-expression`* 计算。 | 通常用于循环索引递增。 |

下面的示例演示了使用语句的不同方式 **`for`** 。

```cpp
#include <iostream>
using namespace std;

int main() {
    // The counter variable can be declared in the init-expression.
    for (int i = 0; i < 2; i++ ){
       cout << i;
    }
    // Output: 01
    // The counter variable can be declared outside the for loop.
    int i;
    for (i = 0; i < 2; i++){
        cout << i;
    }
    // Output: 01
    // These for loops are the equivalent of a while loop.
    i = 0;
    while (i < 2){
        cout << i++;
    }
    // Output: 01
}
```

*`init-expression`* 和 *`loop-expression`* 可以包含用逗号分隔的多个语句。 例如：

```cpp
#include <iostream>
using namespace std;

int main(){
    int i, j;
    for ( i = 5, j = 10 ; i + j < 20; i++, j++ ) {
        cout << "i + j = " << (i + j) << '\n';
    }
}
    // Output:
    i + j = 15
    i + j = 17
    i + j = 19
```

*`loop-expression`* 可以增加或减少，也可以通过其他方式进行修改。

```cpp
#include <iostream>
using namespace std;

int main(){
for (int i = 10; i > 0; i--) {
        cout << i << ' ';
    }
    // Output: 10 9 8 7 6 5 4 3 2 1
    for (int i = 10; i < 20; i = i+2) {
        cout << i << ' ';
    }
    // Output: 10 12 14 16 18
```

**`for`** [`break`](../cpp/break-statement-cpp.md) 执行中的、 [return](../cpp/return-statement-cpp.md)或 [`goto`](../cpp/goto-statement-cpp.md) （到循环外的标记语句）时，循环将终止 **`for`** *`statement`* 。 [`continue`](../cpp/continue-statement-cpp.md)循环中的语句 **`for`** 仅终止当前迭代。

如果 *`cond-expression`* 省略，则认为它是 **`true`** ，并且 **`for`** **`break`** 在中没有、或的情况下，循环不会终止 **`return`** **`goto`** *`statement`* 。

尽管语句的三个字段 **`for`** 通常用于初始化、测试终止和递增，但并不局限于这些字段的使用。 例如，下面的代码将打印数字 0 至 4。 在这种情况下， *`statement`* 为 null 语句：

```cpp
#include <iostream>
using namespace std;

int main()
{
    int i;
    for( i = 0; i < 5; cout << i << '\n', i++){
        ;
    }
}
```

## <a name="for-loops-and-the-c-standard"></a>`for`循环和 c + + 标准

C + + 标准表明循环结束后，在循环中声明的变量 **`for`** 应超出范围 **`for`** 。 例如：

```cpp
for (int i = 0 ; i < 5 ; i++) {
   // do something
}
// i is now out of scope under /Za or /Zc:forScope
```

默认情况下，在[/ze](../build/reference/za-ze-disable-language-extensions.md)下，在循环 **`for`** **`for`** 的封闭范围结束之前，在循环中声明的变量将保留在范围内。

[/Zc： forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)启用 for 循环中声明的变量的标准行为，无需指定 `/Za` 。

还可以使用循环的作用域差异 **`for`** 来重新声明下的变量， `/Ze` 如下所示：

```cpp
// for_statement5.cpp
int main(){
   int i = 0;   // hidden by var with same name declared in for loop
   for ( int i = 0 ; i < 3; i++ ) {}

   for ( int i = 0 ; i < 3; i++ ) {}
}
```

此行为更严格地模拟循环中声明的变量的标准行为 **`for`** ，这要求循环中声明的变量在 **`for`** 循环完成之后超出范围。 当在循环中声明变量时 **`for`** ，编译器会在内部将其升级为 **`for`** 循环封闭范围内的局部变量。 即使已经存在具有相同名称的本地变量，也会升级它。

## <a name="see-also"></a>请参阅

[迭代语句](../cpp/iteration-statements-cpp.md)<br/>
[关键字](../cpp/keywords-cpp.md)<br/>
[while 语句（c + +）](../cpp/while-statement-cpp.md)<br/>
[while 语句（c + +）](../cpp/do-while-statement-cpp.md)<br/>
[基于范围的 for 语句（c + +）](../cpp/range-based-for-statement-cpp.md)
