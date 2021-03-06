---
title: numeric_limits 类
ms.date: 11/04/2016
f1_keywords:
- limits/std::numeric_limits
- limits/std::numeric_limits::denorm_min
- limits/std::numeric_limits::digits
- limits/std::numeric_limits::digits10
- limits/std::numeric_limits::epsilon
- limits/std::numeric_limits::has_denorm
- limits/std::numeric_limits::has_denorm_loss
- limits/std::numeric_limits::has_infinity
- limits/std::numeric_limits::has_quiet_NaN
- limits/std::numeric_limits::has_signaling_NaN
- limits/std::numeric_limits::infinity
- limits/std::numeric_limits::is_bounded
- limits/std::numeric_limits::is_exact
- limits/std::numeric_limits::is_iec559
- limits/std::numeric_limits::is_integer
- limits/std::numeric_limits::is_modulo
- limits/std::numeric_limits::is_signed
- limits/std::numeric_limits::is_specialized
- limits/std::numeric_limits::lowest
- limits/std::numeric_limits::max
- limits/std::numeric_limits::max_digits10
- limits/std::numeric_limits::max_exponent
- limits/std::numeric_limits::max_exponent10
- limits/std::numeric_limits::min
- limits/std::numeric_limits::min_exponent
- limits/std::numeric_limits::min_exponent10
- limits/std::numeric_limits::quiet_NaN
- limits/std::numeric_limits::radix
- limits/std::numeric_limits::round_error
- limits/std::numeric_limits::round_style
- limits/std::numeric_limits::signaling_NaN
- limits/std::numeric_limits::tinyness_before
- limits/std::numeric_limits::traps
helpviewer_keywords:
- std::numeric_limits [C++]
- std::numeric_limits [C++], denorm_min
- std::numeric_limits [C++], digits
- std::numeric_limits [C++], digits10
- std::numeric_limits [C++], epsilon
- std::numeric_limits [C++], has_denorm
- std::numeric_limits [C++], has_denorm_loss
- std::numeric_limits [C++], has_infinity
- std::numeric_limits [C++], has_quiet_NaN
- std::numeric_limits [C++], has_signaling_NaN
- std::numeric_limits [C++], infinity
- std::numeric_limits [C++], is_bounded
- std::numeric_limits [C++], is_exact
- std::numeric_limits [C++], is_iec559
- std::numeric_limits [C++], is_integer
- std::numeric_limits [C++], is_modulo
- std::numeric_limits [C++], is_signed
- std::numeric_limits [C++], is_specialized
- std::numeric_limits [C++], lowest
- std::numeric_limits [C++], max
- std::numeric_limits [C++], max_digits10
- std::numeric_limits [C++], max_exponent
- std::numeric_limits [C++], max_exponent10
- std::numeric_limits [C++], min
- std::numeric_limits [C++], min_exponent
- std::numeric_limits [C++], min_exponent10
- std::numeric_limits [C++], quiet_NaN
- std::numeric_limits [C++], radix
- std::numeric_limits [C++], round_error
- std::numeric_limits [C++], round_style
- std::numeric_limits [C++], signaling_NaN
- std::numeric_limits [C++], tinyness_before
- std::numeric_limits [C++], traps
ms.assetid: 9e817177-0e91-48e6-b680-0531c4b26625
ms.openlocfilehash: f0b33404f16df59e2cb73023f3539e87080734a1
ms.sourcegitcommit: f2a135d69a2a8ef1777da60c53d58fe06980c997
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/03/2020
ms.locfileid: "87520598"
---
# <a name="numeric_limits-class"></a>numeric_limits 类

类模板描述内置数值类型的算术属性。

## <a name="syntax"></a>语法

```cpp
template <class Type>
    class numeric_limits
```

### <a name="parameters"></a>parameters

*类别*\
正在测试、查询或设置其属性的基础元素数据类型。 *类型*还可以声明为 **`const`** 、 **`volatile`** 或 **`const volatile`** 。

## <a name="remarks"></a>备注

标头为类型、、、、、、、、、、、、、、、、和定义显式专用化 **`wchar_t`** **`bool`** **`char`** **`signed char`** **`unsigned char`** **`short`** **`unsigned short`** **`int`** **`unsigned int`** **`long`** **`unsigned long`** **`float`** **`double`** **`long double`** **`long long`** **`unsigned long long`** **`char16_t`** **`char32_t`** 。 对于这些显式专用化，成员[numeric_limits：： is_specialized](#is_specialized)为 **`true`** ，并且所有相关成员都具有有意义的值。 程序可提供额外的显式专用化。 类的大多数成员函数描述或测试的可能实现 **`float`** 。

对于任意专用化，所有成员均无有意义的值。 没有有意义的值的成员对象将存储零（或 **`false`** ），并且不返回有意义的值的成员函数将返回 `Type(0)` 。

## <a name="static-functions-and-constants"></a>静态函数和常数

|||
|-|-|
|[denorm_min](#denorm_min)|返回最小的非规范化非零值。|
|[位数](#digits)|返回类型可以表示而不会降低精度的基数数字的位数。|
|[digits10](#digits10)|返回类型可以表示而不会降低精度的十进制数字的位数。|
|[epsilon](#epsilon)|返回数据类型可以表示的 1 与大于 1 的最小值之间的差值。|
|[has_denorm](#has_denorm)|测试类型是否允许非规范化值。|
|[has_denorm_loss](#has_denorm_loss)|测试是否将准确度降低检测为非规范化损失，而不是不准确结果。|
|[has_infinity](#has_infinity)|测试某一类型是否能够表示正无穷。|
|[has_quiet_NaN](#has_quiet_nan)|测试某一类型是否具有 quiet （非信号）的表示形式。|
|[has_signaling_NaN](#has_signaling_nan)|测试某一类型是否能表示信号性沉寂非数值 (NAN)。|
|[无穷大](#infinity)|某一类型用于表示正无穷的值（若适用）。|
|[is_bounded](#is_bounded)|测试某一类型可表示的值设置是否为有限。|
|[is_exact](#is_exact)|测试针对某一类型进行的计算是否不产生舍入错误。|
|[is_iec559](#is_iec559)|测试某一类型是否符合 IEC 559 标准。|
|[is_integer](#is_integer)|测试某一类型是否具有具有整数表示形式。|
|[is_modulo](#is_modulo)|测试某一类型是否具有具有取模表示形式。|
|[is_signed](#is_signed)|测试某一类型是否具有带符号的表示形式。|
|[is_specialized](#is_specialized)|测试某一类型是否具有类模板中定义的显式专用化 `numeric_limits` 。|
|[层](#lowest)|返回最小的负有限值。|
|[max](#max)|返回某个类型的最大有限值。|
|[max_digits10](#max_digits10)|返回确保类型的两个非重复值具有不同的十进制表示形式所需的十进制数字的位数。|
|[max_exponent](#max_exponent)|返回最大正整数指数，当计算基数的该指数次幂时，浮点类型可将其表示为有限值。|
|[max_exponent10](#max_exponent10)|返回最大正整数指数，当计算 10 的该指数次幂时，浮点类型可将其表示为有限值。|
|[min](#min)|返回某个类型的最小规范化值。|
|[min_exponent](#min_exponent)|返回最大负整数指数，当计算基数的该指数次幂时，浮点类型可将其表示为有限值。|
|[min_exponent10](#min_exponent10)|返回最大负整数指数，当计算 10 的该指数次幂时，浮点类型可将其表示为有限值。|
|[quiet_NaN](#quiet_nan)|返回类型的静默非数值 (NAN) 表示形式。|
|[基数](#radix)|返回用于表示类型的整数底数（称为基数）。|
|[round_error](#round_error)|返回类型的最大舍入误差值。|
|[round_style](#round_style)|返回一个值，该值描述可供实现选择用于将浮点值舍入为整数值的各种方法。|
|[signaling_NaN](#signaling_nan)|返回类型的信令非数值 (NAN) 表示形式。|
|[tinyness_before](#tinyness_before)|测试某个类型是否可在舍入某个值之前确定该值太小而无法表示为规范化值。|
|[俘获](#traps)|测试是否为某个类型实现了报告算术异常的捕获。|

### <a name="denorm_min"></a><a name="denorm_min"></a>denorm_min

返回最小的非规范化非零值。

```cpp
static constexpr Type denorm_min() throw();
```

#### <a name="return-value"></a>返回值

最小的非规范化非零值。

#### <a name="remarks"></a>备注

**`long double`** 与 **`double`** c + + 编译器相同。

函数返回类型的最小值，如果[has_denorm](#has_denorm)不等于，则该函数与[min](#min)相同 `denorm_present` 。

#### <a name="example"></a>示例

```cpp
// numeric_limits_denorm_min.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The smallest nonzero denormalized value" << endl
        << "for float objects is: "
        << numeric_limits<float>::denorm_min( ) << endl;
   cout << "The smallest nonzero denormalized value" << endl
        << "for double objects is: "
        << numeric_limits<double>::denorm_min( ) << endl;
   cout << "The smallest nonzero denormalized value" << endl
        << "for long double objects is: "
        << numeric_limits<long double>::denorm_min( ) << endl;

   // A smaller value will round to zero
   cout << numeric_limits<float>::denorm_min( )/2 <<endl;
   cout << numeric_limits<double>::denorm_min( )/2 <<endl;
   cout << numeric_limits<long double>::denorm_min( )/2 <<endl;
}
```

```Output
The smallest nonzero denormalized value
for float objects is: 1.4013e-045
The smallest nonzero denormalized value
for double objects is: 4.94066e-324
The smallest nonzero denormalized value
for long double objects is: 4.94066e-324
0
0
0
```

### <a name="digits"></a><a name="digits"></a>阿拉伯数字

返回类型可以表示而不会降低精度的基数数字的位数。

```cpp
static constexpr int digits = 0;
```

#### <a name="return-value"></a>返回值

该类型可以表示且不会降低精度的基数数字的位数。

#### <a name="remarks"></a>备注

该成员存储该类型可以表示且无需更改的基数数字的位数，这是预定义的整数类型的任何符号位以外的比特数或预定义的浮点类型的尾数的位数。

#### <a name="example"></a>示例

```cpp
// numeric_limits_digits_min.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << numeric_limits<float>::digits <<endl;
   cout << numeric_limits<double>::digits <<endl;
   cout << numeric_limits<long double>::digits <<endl;
   cout << numeric_limits<int>::digits <<endl;
   cout << numeric_limits<__int64>::digits <<endl;
}
```

```Output
24
53
53
31
63
```

### <a name="digits10"></a><a name="digits10"></a>digits10

返回类型可以表示而不会降低精度的十进制数字的位数。

```cpp
static constexpr int digits10 = 0;
```

#### <a name="return-value"></a>返回值

该类型可以表示且不会降低精度的十进制数字的位数。

#### <a name="example"></a>示例

```cpp
// numeric_limits_digits10.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << numeric_limits<float>::digits10 <<endl;
   cout << numeric_limits<double>::digits10 <<endl;
   cout << numeric_limits<long double>::digits10 <<endl;
   cout << numeric_limits<int>::digits10 <<endl;
   cout << numeric_limits<__int64>::digits10 <<endl;
   float f = (float)99999999;
   cout.precision ( 10 );
   cout << "The float is; " << f << endl;
}
```

```Output
6
15
15
9
18
The float is; 100000000
```

### <a name="epsilon"></a><a name="epsilon"></a>epsilon

该函数返回数据类型可以表示的 1 与大于 1 的最小值之间的差值。

```cpp
static constexpr Type epsilon() throw();
```

#### <a name="return-value"></a>返回值

数据类型可以表示的 1 与大于 1 的最小值之间的差值。

#### <a name="remarks"></a>备注

值为类型 FLT_EPSILON **`float`** 。 `epsilon`类型是最小的正浮点数*n* ，因此*n*  +  `epsilon`  +  *n*可表示。

#### <a name="example"></a>示例

```cpp
// numeric_limits_epsilon.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The difference between 1 and the smallest "
        << "value greater than 1" << endl
        << "for float objects is: "
        << numeric_limits<float>::epsilon( ) << endl;
   cout << "The difference between 1 and the smallest "
        << "value greater than 1" << endl
        << "for double objects is: "
        << numeric_limits<double>::epsilon( ) << endl;
   cout << "The difference between 1 and the smallest "
        << "value greater than 1" << endl
        << "for long double objects is: "
        << numeric_limits<long double>::epsilon( ) << endl;
}
```

```Output
The difference between 1 and the smallest value greater than 1
for float objects is: 1.19209e-007
The difference between 1 and the smallest value greater than 1
for double objects is: 2.22045e-016
The difference between 1 and the smallest value greater than 1
for long double objects is: 2.22045e-016
```

### <a name="has_denorm"></a><a name="has_denorm"></a>has_denorm

测试类型是否允许非规范化值。

```cpp
static constexpr float_denorm_style has_denorm = denorm_absent;
```

#### <a name="return-value"></a>返回值

类型的枚举值 `const float_denorm_style` ，指示类型是否允许非规范化值。

#### <a name="remarks"></a>备注

`denorm_present`具有非规范化值的浮点类型的成员存储，实际上是可变数量的指数位。

#### <a name="example"></a>示例

```cpp
// numeric_limits_has_denorm.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects allow denormalized values: "
        << numeric_limits<float>::has_denorm
        << endl;
   cout << "Whether double objects allow denormalized values: "
        << numeric_limits<double>::has_denorm
        << endl;
   cout << "Whether long int objects allow denormalized values: "
        << numeric_limits<long int>::has_denorm
        << endl;
}
```

```Output
Whether float objects allow denormalized values: 1
Whether double objects allow denormalized values: 1
Whether long int objects allow denormalized values: 0
```

### <a name="has_denorm_loss"></a><a name="has_denorm_loss"></a>has_denorm_loss

测试是否将准确度降低检测为非规范化损失，而不是不准确结果。

```cpp
static constexpr bool has_denorm_loss = false;
```

#### <a name="return-value"></a>返回值

**`true`** 如果准确性损失被检测为非规范化损失，则为;**`false`** 否则为。

#### <a name="remarks"></a>备注

该成员将确定值是否已损失准确性的类型存储为 true，因为将该值作为非规范化结果传递（该值太小，从而无法表示为规范化的值）或者因为该值不精确（与不受指数范围和精度限制的结果不同），具有 IEC 559 浮点表示形式的选项可能会影响某些结果。

#### <a name="example"></a>示例

```cpp
// numeric_limits_has_denorm_loss.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects can detect denormalized loss: "
        << numeric_limits<float>::has_denorm_loss
        << endl;
   cout << "Whether double objects can detect denormalized loss: "
        << numeric_limits<double>::has_denorm_loss
        << endl;
   cout << "Whether long int objects can detect denormalized loss: "
        << numeric_limits<long int>::has_denorm_loss
        << endl;
}
```

```Output
Whether float objects can detect denormalized loss: 1
Whether double objects can detect denormalized loss: 1
Whether long int objects can detect denormalized loss: 0
```

### <a name="has_infinity"></a><a name="has_infinity"></a>has_infinity

测试某一类型是否能够表示正无穷。

```cpp
static constexpr bool has_infinity = false;
```

#### <a name="return-value"></a>返回值

**`true`** 如果该类型具有正无穷大的表示形式，则为; 否则为。**`false`** 否则为。

#### <a name="remarks"></a>备注

**`true`** 如果[is_iec559](#is_iec559)为，则成员返回 **`true`** 。

#### <a name="example"></a>示例

```cpp
// numeric_limits_has_infinity.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have infinity: "
        << numeric_limits<float>::has_infinity
        << endl;
   cout << "Whether double objects have infinity: "
        << numeric_limits<double>::has_infinity
        << endl;
   cout << "Whether long int objects have infinity: "
        << numeric_limits<long int>::has_infinity
        << endl;
}
```

```Output
Whether float objects have infinity: 1
Whether double objects have infinity: 1
Whether long int objects have infinity: 0
```

### <a name="has_quiet_nan"></a><a name="has_quiet_nan"></a>has_quiet_NaN

测试某一类型是否能表示非信号性沉寂非数值 (NAN)。

```cpp
static constexpr bool has_quiet_NaN = false;
```

#### <a name="return-value"></a>返回值

**`true`** 如果该**类型**具有 quiet NAN 的表示形式，则为; 否则为。**`false`** 否则为。

#### <a name="remarks"></a>备注

静默 NAN 为非数值的编码，不表示其在表达式中的存在。 **`true`** 如果[is_iec559](#is_iec559)为 true，则返回值为。

#### <a name="example"></a>示例

```cpp
// numeric_limits_has_quiet_nan.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have quiet_NaN: "
        << numeric_limits<float>::has_quiet_NaN
        << endl;
   cout << "Whether double objects have quiet_NaN: "
        << numeric_limits<double>::has_quiet_NaN
        << endl;
   cout << "Whether long int objects have quiet_NaN: "
        << numeric_limits<long int>::has_quiet_NaN
        << endl;
}
```

```Output
Whether float objects have quiet_NaN: 1
Whether double objects have quiet_NaN: 1
Whether long int objects have quiet_NaN: 0
```

### <a name="has_signaling_nan"></a><a name="has_signaling_nan"></a>has_signaling_NaN

测试某一类型是否能表示信号性沉寂非数值 (NAN)。

```cpp
static constexpr bool has_signaling_NaN = false;
```

#### <a name="return-value"></a>返回值

**`true`** 如果该类型具有信号 NAN 的表示形式，则为; 否则为。**`false`** 否则为。

#### <a name="remarks"></a>备注

信号 NAN为非数值的编码，表示其在表达式中的存在。 **`true`** 如果[is_iec559](#is_iec559)为 true，则返回值为。

#### <a name="example"></a>示例

```cpp
// numeric_limits_has_signaling_nan.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have a signaling_NaN: "
        << numeric_limits<float>::has_signaling_NaN
        << endl;
   cout << "Whether double objects have a signaling_NaN: "
        << numeric_limits<double>::has_signaling_NaN
        << endl;
   cout << "Whether long int objects have a signaling_NaN: "
        << numeric_limits<long int>::has_signaling_NaN
        << endl;
}
```

```Output
Whether float objects have a signaling_NaN: 1
Whether double objects have a signaling_NaN: 1
Whether long int objects have a signaling_NaN: 0
```

### <a name="infinity"></a><a name="infinity"></a>无穷大

用于表示某一类型的正无穷的值（若适用）。

```cpp
static constexpr Type infinity() throw();
```

#### <a name="return-value"></a>返回值

用于表示某一类型的正无穷的值（若适用）。

#### <a name="remarks"></a>备注

仅当[has_infinity](#has_infinity)为时，返回值才有意义 **`true`** 。

#### <a name="example"></a>示例

```cpp
// numeric_limits_infinity.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << numeric_limits<float>::has_infinity <<endl;
   cout << numeric_limits<double>::has_infinity<<endl;
   cout << numeric_limits<long double>::has_infinity <<endl;
   cout << numeric_limits<int>::has_infinity <<endl;
   cout << numeric_limits<__int64>::has_infinity <<endl;

   cout << "The representation of infinity for type float is: "
        << numeric_limits<float>::infinity( ) <<endl;
   cout << "The representation of infinity for type double is: "
        << numeric_limits<double>::infinity( ) <<endl;
   cout << "The representation of infinity for type long double is: "
        << numeric_limits<long double>::infinity( ) <<endl;
}
```

```Output
1
1
1
0
0
The representation of infinity for type float is: inf
The representation of infinity for type double is: inf
The representation of infinity for type long double is: inf
```

### <a name="is_bounded"></a><a name="is_bounded"></a>is_bounded

测试某一类型可表示的值设置是否为有限。

```cpp
static constexpr bool is_bounded = false;
```

#### <a name="return-value"></a>返回值

**`true`** 如果类型具有一组限定的可表示值，则为;**`false`** 否则为。

#### <a name="remarks"></a>备注

所有预定义类型都具有一组限定的可表示值并返回 **`true`** 。

#### <a name="example"></a>示例

```cpp
// numeric_limits_is_bounded.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have bounded set "
        << "of representable values: "
        << numeric_limits<float>::is_bounded
        << endl;
   cout << "Whether double objects have bounded set "
        << "of representable values: "
        << numeric_limits<double>::is_bounded
        << endl;
   cout << "Whether long int objects have bounded set "
        << "of representable values: "
        << numeric_limits<long int>::is_bounded
        << endl;
   cout << "Whether unsigned char objects have bounded set "
        << "of representable values: "
        << numeric_limits<unsigned char>::is_bounded
        << endl;
}
```

```Output
Whether float objects have bounded set of representable values: 1
Whether double objects have bounded set of representable values: 1
Whether long int objects have bounded set of representable values: 1
Whether unsigned char objects have bounded set of representable values: 1
```

### <a name="is_exact"></a><a name="is_exact"></a>is_exact

测试针对某一类型进行的计算是否不产生舍入错误。

```cpp
static constexpr bool is_exact = false;
```

#### <a name="return-value"></a>返回值

**`true`** 如果计算没有舍入误差，则为;**`false`** 否则为。

#### <a name="remarks"></a>备注

所有预定义的整数类型都具有其值的准确表示形式，并返回 **`false`** 。 定点的或合理的表示形式也被视为准确的表示形式，但浮点表示形式不是。

#### <a name="example"></a>示例

```cpp
// numeric_limits_is_exact.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have calculations "
        << "free of rounding errors: "
        << numeric_limits<float>::is_exact
        << endl;
   cout << "Whether double objects have calculations "
        << "free of rounding errors: "
        << numeric_limits<double>::is_exact
        << endl;
   cout << "Whether long int objects have calculations "
        << "free of rounding errors: "
        << numeric_limits<long int>::is_exact
        << endl;
   cout << "Whether unsigned char objects have calculations "
        << "free of rounding errors: "
        << numeric_limits<unsigned char>::is_exact
        << endl;
}
```

```Output
Whether float objects have calculations free of rounding errors: 0
Whether double objects have calculations free of rounding errors: 0
Whether long int objects have calculations free of rounding errors: 1
Whether unsigned char objects have calculations free of rounding errors: 1
```

### <a name="is_iec559"></a><a name="is_iec559"></a>is_iec559

测试某一类型是否符合 IEC 559 标准。

```cpp
static constexpr bool is_iec559 = false;
```

#### <a name="return-value"></a>返回值

**`true`** 如果类型符合 IEC 559 标准，则为;**`false`** 否则为。

#### <a name="remarks"></a>备注

IEC 559 是一个国际标准，用于表示浮点值，在美国也称为 IEEE 754。

#### <a name="example"></a>示例

```cpp
// numeric_limits_is_iec559.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects conform to iec559 standards: "
        << numeric_limits<float>::is_iec559
        << endl;
   cout << "Whether double objects conform to iec559 standards: "
        << numeric_limits<double>::is_iec559
        << endl;
   cout << "Whether int objects conform to iec559 standards: "
        << numeric_limits<int>::is_iec559
        << endl;
   cout << "Whether unsigned char objects conform to iec559 standards: "
        << numeric_limits<unsigned char>::is_iec559
        << endl;
}
```

```Output
Whether float objects conform to iec559 standards: 1
Whether double objects conform to iec559 standards: 1
Whether int objects conform to iec559 standards: 0
Whether unsigned char objects conform to iec559 standards: 0
```

### <a name="is_integer"></a><a name="is_integer"></a>is_integer

测试某一类型是否具有具有整数表示形式。

```cpp
static constexpr bool is_integer = false;
```

#### <a name="return-value"></a>返回值

**`true`** 如果该类型具有整数表示形式，则为; 否则为。**`false`** 否则为。

#### <a name="remarks"></a>备注

所有预定义的整数类型都有整数表示形式。

#### <a name="example"></a>示例

```cpp
// numeric_limits_is_integer.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have an integral representation: "
        << numeric_limits<float>::is_integer
        << endl;
   cout << "Whether double objects have an integral representation: "
        << numeric_limits<double>::is_integer
        << endl;
   cout << "Whether int objects have an integral representation: "
        << numeric_limits<int>::is_integer
        << endl;
   cout << "Whether unsigned char objects have an integral representation: "
        << numeric_limits<unsigned char>::is_integer
        << endl;
}
```

```Output
Whether float objects have an integral representation: 0
Whether double objects have an integral representation: 0
Whether int objects have an integral representation: 1
Whether unsigned char objects have an integral representation: 1
```

### <a name="is_modulo"></a><a name="is_modulo"></a>is_modulo

测试某一**类型**是否具有取模表示形式。

```cpp
static constexpr bool is_modulo = false;
```

#### <a name="return-value"></a>返回值

**`true`** 如果类型具有取模表示形式，则为; 否则为。**`false`** 否则为。

#### <a name="remarks"></a>备注

取模表示形式是一种将所有结果减去某些值的取模结果的表示形式。 所有预定义的无符号整数类型都有取模表示形式。

#### <a name="example"></a>示例

```cpp
// numeric_limits_is_modulo.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have a modulo representation: "
        << numeric_limits<float>::is_modulo
        << endl;
   cout << "Whether double objects have a modulo representation: "
        << numeric_limits<double>::is_modulo
        << endl;
   cout << "Whether signed char objects have a modulo representation: "
        << numeric_limits<signed char>::is_modulo
        << endl;
   cout << "Whether unsigned char objects have a modulo representation: "
        << numeric_limits<unsigned char>::is_modulo
        << endl;
}
```

```Output
Whether float objects have a modulo representation: 0
Whether double objects have a modulo representation: 0
Whether signed char objects have a modulo representation: 1
Whether unsigned char objects have a modulo representation: 1
```

### <a name="is_signed"></a><a name="is_signed"></a>is_signed

测试某一类型是否具有带符号的表示形式。

```cpp
static constexpr bool is_signed = false;
```

#### <a name="return-value"></a>返回值

**`true`** 如果类型具有有符号的表示形式，则为; 否则为。**`false`** 否则为。

#### <a name="remarks"></a>备注

该成员将具有带符号的表示形式的类型存储为 true，这种情况适用于所有预定义的浮点类型和带符号的整数类型。

#### <a name="example"></a>示例

```cpp
// numeric_limits_is_signaled.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have a signed representation: "
        << numeric_limits<float>::is_signed
        << endl;
   cout << "Whether double objects have a signed representation: "
        << numeric_limits<double>::is_signed
        << endl;
   cout << "Whether signed char objects have a signed representation: "
        << numeric_limits<signed char>::is_signed
        << endl;
   cout << "Whether unsigned char objects have a signed representation: "
        << numeric_limits<unsigned char>::is_signed
        << endl;
}
```

```Output
Whether float objects have a signed representation: 1
Whether double objects have a signed representation: 1
Whether signed char objects have a signed representation: 1
Whether unsigned char objects have a signed representation: 0
```

### <a name="is_specialized"></a><a name="is_specialized"></a>is_specialized

测试某一类型是否具有类模板中定义的显式专用化 `numeric_limits` 。

```cpp
static constexpr bool is_specialized = false;
```

#### <a name="return-value"></a>返回值

**`true`** 如果该类型具有在类模板中定义的显式专用化，则为; 否则为。**`false`** 否则为。

#### <a name="remarks"></a>备注

除指针之外的所有标量类型都具有为类模板定义的显式专用化 `numeric_limits` 。

#### <a name="example"></a>示例

```cpp
// numeric_limits_is_specialized.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have an explicit "
        << "specialization in the class: "
        << numeric_limits<float>::is_specialized
        << endl;
   cout << "Whether float* objects have an explicit "
        << "specialization in the class: "
        << numeric_limits<float*>::is_specialized
        << endl;
   cout << "Whether int objects have an explicit "
        << "specialization in the class: "
        << numeric_limits<int>::is_specialized
        << endl;
   cout << "Whether int* objects have an explicit "
        << "specialization in the class: "
        << numeric_limits<int*>::is_specialized
        << endl;
}
```

```Output
Whether float objects have an explicit specialization in the class: 1
Whether float* objects have an explicit specialization in the class: 0
Whether int objects have an explicit specialization in the class: 1
Whether int* objects have an explicit specialization in the class: 0
```

### <a name="lowest"></a><a name="lowest"></a>层

返回最小的负有限值。

```cpp
static constexpr Type lowest() throw();
```

#### <a name="return-value"></a>返回值

返回最小的负有限值。

#### <a name="remarks"></a>备注

返回此类型最小的有限值（通常，整数类型使用 `min()`，浮点类型使用 `-max()`）。 如果为，则返回值是有意义的 `is_bounded` **`true`** 。

### <a name="max"></a><a name="max"></a>数量

返回某个类型的最大有限值。

```cpp
static constexpr Type max() throw();
```

#### <a name="return-value"></a>返回值

某个类型的最大有限值。

#### <a name="remarks"></a>备注

类型类型和 FLT_MAX INT_MAX 的最大有限值 **`int`** **`float`** 。 如果[is_bounded](#is_bounded)为，则返回值是有意义的 **`true`** 。

#### <a name="example"></a>示例

```cpp
// numeric_limits_max.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main() {
   cout << "The maximum value for type float is:  "
        << numeric_limits<float>::max( )
        << endl;
   cout << "The maximum value for type double is:  "
        << numeric_limits<double>::max( )
        << endl;
   cout << "The maximum value for type int is:  "
        << numeric_limits<int>::max( )
        << endl;
   cout << "The maximum value for type short int is:  "
        << numeric_limits<short int>::max( )
        << endl;
}
```

### <a name="max_digits10"></a><a name="max_digits10"></a>max_digits10

返回所需的十进制数字的位数以确保类型的两个非重复值具有不同的十进制表示形式。

```cpp
static constexpr int max_digits10 = 0;
```

#### <a name="return-value"></a>返回值

返回所需的十进制数字的位数以确保类型的两个非重复值具有不同的十进制表示形式。

#### <a name="remarks"></a>备注

成员存储所需的十进制数字的位数以确保类型的两个非重复值具有不同的十进制表示形式。

### <a name="max_exponent"></a><a name="max_exponent"></a>max_exponent

返回最大正整数指数，当计算基数的该指数次幂时，浮点类型可将其表示为有限值。

```cpp
static constexpr int max_exponent = 0;
```

#### <a name="return-value"></a>返回值

可由该类型表示的以整型基数为底数的最大指数。

#### <a name="remarks"></a>备注

成员函数返回仅对浮点类型有意义。 `max_exponent`是类型 FLT_MAX_EXP 的值 **`float`** 。

#### <a name="example"></a>示例

```cpp
// numeric_limits_max_exponent.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The maximum radix-based exponent for type float is:  "
        << numeric_limits<float>::max_exponent
        << endl;
   cout << "The maximum radix-based exponent for type double is:  "
        << numeric_limits<double>::max_exponent
        << endl;
   cout << "The maximum radix-based exponent for type long double is:  "
        << numeric_limits<long double>::max_exponent
        << endl;
}
```

```Output
The maximum radix-based exponent for type float is:  128
The maximum radix-based exponent for type double is:  1024
The maximum radix-based exponent for type long double is:  1024
```

### <a name="max_exponent10"></a><a name="max_exponent10"></a>max_exponent10

返回最大正整数指数，当计算 10 的该指数次幂时，浮点类型可将其表示为有限值。

```cpp
static constexpr int max_exponent10 = 0;
```

#### <a name="return-value"></a>返回值

可由该类型表示的以整型基数 10 为底数的最大指数。

#### <a name="remarks"></a>备注

成员函数返回仅对浮点类型有意义。 `max_exponent`是类型 FLT_MAX_10 的值 **`float`** 。

#### <a name="example"></a>示例

```cpp
// numeric_limits_max_exponent10.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The maximum base 10 exponent for type float is:  "
           << numeric_limits<float>::max_exponent10
           << endl;
   cout << "The maximum base 10 exponent for type double is:  "
           << numeric_limits<double>::max_exponent10
           << endl;
   cout << "The maximum base 10 exponent for type long double is:  "
           << numeric_limits<long double>::max_exponent10
           << endl;
}
```

```Output
The maximum base 10 exponent for type float is:  38
The maximum base 10 exponent for type double is:  308
The maximum base 10 exponent for type long double is:  308
```

### <a name="min"></a><a name="min"></a> 分钟

返回某个类型的最小规范化值。

```cpp
static constexpr Type min() throw();
```

#### <a name="return-value"></a>返回值

该类型的最小规范化值。

#### <a name="remarks"></a>备注

最小标准化值为类型的类型 **`int`** 和 FLT_MIN INT_MIN **`float`** 。 如果[is_bounded](#is_bounded)为 **`true`** 或[is_signed](#is_signed)为，则返回值有意义 **`false`** 。

#### <a name="example"></a>示例

```cpp
// numeric_limits_min.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The minimum value for type float is:  "
        << numeric_limits<float>::min( )
        << endl;
   cout << "The minimum value for type double is:  "
        << numeric_limits<double>::min( )
        << endl;
   cout << "The minimum value for type int is:  "
        << numeric_limits<int>::min( )
        << endl;
   cout << "The minimum value for type short int is:  "
        << numeric_limits<short int>::min( )
        << endl;
}
```

```Output
The minimum value for type float is:  1.17549e-038
The minimum value for type double is:  2.22507e-308
The minimum value for type int is:  -2147483648
The minimum value for type short int is:  -32768
```

### <a name="min_exponent"></a><a name="min_exponent"></a>min_exponent

返回最大负整数指数，当计算基数的该指数次幂时，浮点类型可将其表示为有限值。

```cpp
static constexpr int min_exponent = 0;
```

#### <a name="return-value"></a>返回值

可由该类型表示的以整型基数为底数的最小指数。

#### <a name="remarks"></a>备注

成员函数仅对浮点类型有意义。 `min_exponent`是类型 FLT_MIN_EXP 的值 **`float`** 。

#### <a name="example"></a>示例

```cpp
// numeric_limits_min_exponent.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The minimum radix-based exponent for type float is:  "
        << numeric_limits<float>::min_exponent
        << endl;
   cout << "The minimum radix-based exponent for type double is:  "
        << numeric_limits<double>::min_exponent
        << endl;
   cout << "The minimum radix-based exponent for type long double is:  "
         << numeric_limits<long double>::min_exponent
        << endl;
}
```

```Output
The minimum radix-based exponent for type float is:  -125
The minimum radix-based exponent for type double is:  -1021
The minimum radix-based exponent for type long double is:  -1021
```

### <a name="min_exponent10"></a><a name="min_exponent10"></a>min_exponent10

返回最大负整数指数，当计算 10 的该指数次幂时，浮点类型可将其表示为有限值。

```cpp
static constexpr int min_exponent10 = 0;
```

#### <a name="return-value"></a>返回值

可由该类型表示的以整型基数 10 为底数的最小指数。

#### <a name="remarks"></a>备注

成员函数仅对浮点类型有意义。 `min_exponent10`是类型 FLT_MIN_10_EXP 的值 **`float`** 。

#### <a name="example"></a>示例

```cpp
// numeric_limits_min_exponent10.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The minimum base 10 exponent for type float is:  "
        << numeric_limits<float>::min_exponent10
        << endl;
   cout << "The minimum base 10 exponent for type double is:  "
        << numeric_limits<double>::min_exponent10
        << endl;
   cout << "The minimum base 10 exponent for type long double is:  "
        << numeric_limits<long double>::min_exponent10
        << endl;
}
```

```Output
The minimum base 10 exponent for type float is:  -37
The minimum base 10 exponent for type double is:  -307
The minimum base 10 exponent for type long double is:  -307
```

### <a name="quiet_nan"></a><a name="quiet_nan"></a>quiet_NaN

返回类型的静默非数值 (NAN) 表示形式。

```cpp
static constexpr Type quiet_NaN() throw();
```

#### <a name="return-value"></a>返回值

该类型的静默 NAN 的表示形式。

#### <a name="remarks"></a>备注

仅当[has_quiet_NaN](#has_quiet_nan)为时，返回值才有意义 **`true`** 。

#### <a name="example"></a>示例

```cpp
// numeric_limits_quiet_nan.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The quiet NaN for type float is:  "
        << numeric_limits<float>::quiet_NaN( )
        << endl;
   cout << "The quiet NaN for type int is:  "
        << numeric_limits<int>::quiet_NaN( )
        << endl;
   cout << "The quiet NaN for type long double is:  "
        << numeric_limits<long double>::quiet_NaN( )
        << endl;
}
```

```Output
The quiet NaN for type float is:  1.#QNAN
The quiet NaN for type int is:  0
The quiet NaN for type long double is:  1.#QNAN
```

### <a name="radix"></a><a name="radix"></a>基数

返回用于表示类型的整数底数（称为基数）。

```cpp
static constexpr int radix = 0;
```

#### <a name="return-value"></a>返回值

表示该类型的整型底数。

#### <a name="remarks"></a>备注

对于预定义的整数类型，底数为 2，并且计算了该底数的指数；对于预定义的浮点类型，则为 FLT_RADIX。

#### <a name="example"></a>示例

```cpp
// numeric_limits_radix.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The base for type float is:  "
        << numeric_limits<float>::radix
        << endl;
   cout << "The base for type int is:  "
        << numeric_limits<int>::radix
        << endl;
   cout << "The base for type long double is:  "
        << numeric_limits<long double>::radix
        << endl;
}
```

```Output
The base for type float is:  2
The base for type int is:  2
The base for type long double is:  2
```

### <a name="round_error"></a><a name="round_error"></a>round_error

返回类型的最大舍入误差值。

```cpp
static constexpr Type round_error() throw();
```

#### <a name="return-value"></a>返回值

该类型的最大舍入误差值。

#### <a name="example"></a>示例

```cpp
// numeric_limits_round_error.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The maximum rounding error for type float is:  "
        << numeric_limits<float>::round_error( )
        << endl;
   cout << "The maximum rounding error for type int is:  "
        << numeric_limits<int>::round_error( )
        << endl;
   cout << "The maximum rounding error for type long double is:  "
        << numeric_limits<long double>::round_error( )
        << endl;
}
```

```Output
The maximum rounding error for type float is:  0.5
The maximum rounding error for type int is:  0
The maximum rounding error for type long double is:  0.5
```

### <a name="round_style"></a><a name="round_style"></a>round_style

返回一个值，该值描述可供实现选择用于将浮点值舍入为整数值的各种方法。

```cpp
static constexpr float_round_style round_style = round_toward_zero;
```

#### <a name="return-value"></a>返回值

用于描述舍入样式的 `float_round_style` 枚举中的值。

#### <a name="remarks"></a>备注

该成员存储一个值，以描述可供实现选择用于将浮点值舍入为整数值的各种方法。

在此实现中对舍入样式进行硬编码，因此，即使通过不同的舍入模式启动该程序，也不会更改该值。

#### <a name="example"></a>示例

```cpp
// numeric_limits_round_style.cpp
// compile with: /EHsc
#include <iostream>
#include <float.h>
#include <limits>

using namespace std;

int main( )
{
   cout << "The rounding style for a double type is: "
        << numeric_limits<double>::round_style << endl;
   _controlfp_s(NULL,_RC_DOWN,_MCW_RC );
   cout << "The rounding style for a double type is now: "
        << numeric_limits<double>::round_style << endl;
   cout << "The rounding style for an int type is: "
        << numeric_limits<int>::round_style << endl;
}
```

```Output
The rounding style for a double type is: 1
The rounding style for a double type is now: 1
The rounding style for an int type is: 0
```

### <a name="signaling_nan"></a><a name="signaling_nan"></a>signaling_NaN

返回类型的信令非数值 (NAN) 表示形式。

```cpp
static constexpr Type signaling_NaN() throw();
```

#### <a name="return-value"></a>返回值

该类型的信号 NAN 的表示形式。

#### <a name="remarks"></a>备注

仅当[has_signaling_NaN](#has_signaling_nan)为时，返回值才有意义 **`true`** 。

#### <a name="example"></a>示例

```cpp
// numeric_limits_signaling_nan.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The signaling NaN for type float is:  "
        << numeric_limits<float>::signaling_NaN( )
        << endl;
   cout << "The signaling NaN for type int is:  "
        << numeric_limits<int>::signaling_NaN( )
        << endl;
   cout << "The signaling NaN for type long double is:  "
        << numeric_limits<long double>::signaling_NaN( )
        << endl;
}
```

### <a name="tinyness_before"></a><a name="tinyness_before"></a>tinyness_before

测试某个类型是否可在舍入某个值之前确定该值太小而无法表示为规范化值。

```cpp
static constexpr bool tinyness_before = false;
```

#### <a name="return-value"></a>返回值

**`true`** 如果该类型可以在舍入之前检测小值，则为;**`false`** 否则为。

#### <a name="remarks"></a>备注

将可以检测到微小值的类型包含为具有 IEC 559 浮点表示形式的选项，并且其实现可能会影响某些结果。

#### <a name="example"></a>示例

```cpp
// numeric_limits_tinyness_before.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float types can detect tinyness before rounding: "
        << numeric_limits<float>::tinyness_before
        << endl;
   cout << "Whether double types can detect tinyness before rounding: "
        << numeric_limits<double>::tinyness_before
        << endl;
   cout << "Whether long int types can detect tinyness before rounding: "
        << numeric_limits<long int>::tinyness_before
        << endl;
   cout << "Whether unsigned char types can detect tinyness before rounding: "
        << numeric_limits<unsigned char>::tinyness_before
        << endl;
}
```

```Output
Whether float types can detect tinyness before rounding: 1
Whether double types can detect tinyness before rounding: 1
Whether long int types can detect tinyness before rounding: 0
Whether unsigned char types can detect tinyness before rounding: 0
```

### <a name="traps"></a><a name="traps"></a>俘获

测试是否为某个类型实现了报告算术异常的捕获。

```cpp
static constexpr bool traps = false;
```

#### <a name="return-value"></a>返回值

**`true`** 如果为类型实现了陷印，则为; 否则为。**`false`** 否则为。

#### <a name="example"></a>示例

```cpp
// numeric_limits_traps.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float types have implemented trapping: "
        << numeric_limits<float>::traps
        << endl;
   cout << "Whether double types have implemented trapping: "
        << numeric_limits<double>::traps
        << endl;
   cout << "Whether long int types have implemented trapping: "
        << numeric_limits<long int>::traps
        << endl;
   cout << "Whether unsigned char types have implemented trapping: "
        << numeric_limits<unsigned char>::traps
        << endl;
}
```

```Output
Whether float types have implemented trapping: 1
Whether double types have implemented trapping: 1
Whether long int types have implemented trapping: 0
Whether unsigned char types have implemented trapping: 0
```
