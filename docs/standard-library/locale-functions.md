---
title: '&lt;locale&gt; 函数'
ms.date: 11/04/2016
f1_keywords:
- locale/std::has_facet
- locale/std::isalnum
- locale/std::isalpha
- locale/std::iscntrl
- locale/std::isdigit
- locale/std::isgraph
- locale/std::islower
- locale/std::isprint
- locale/std::ispunct
- locale/std::isspace
- locale/std::isupper
- locale/std::isxdigit
- locale/std::tolower
- locale/std::toupper
- locale/std::use_facet
ms.assetid: b06c1ceb-33a7-48d3-8d4b-2714bbb27f14
helpviewer_keywords:
- std::has_facet [C++]
- std::isalnum [C++]
- std::isalpha [C++]
- std::iscntrl [C++]
- std::isdigit [C++]
- std::isgraph [C++]
- std::islower [C++]
- std::isprint [C++]
- std::ispunct [C++]
- std::isspace [C++]
- std::isupper [C++]
- std::isxdigit [C++]
- std::tolower [C++]
- std::toupper [C++]
- std::use_facet [C++]
ms.openlocfilehash: a1e81fe28976e914f90a441ff97027f411b05738
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224807"
---
# <a name="ltlocalegt-functions"></a>&lt;locale&gt; 函数

||||
|-|-|-|
|[has_facet](#has_facet)|[isalnum](#isalnum)|[isalpha](#isalpha)|
|[iscntrl](#iscntrl)|[isdigit](#isdigit)|[isgraph](#isgraph)|
|[islower](#islower)|[isprint](#isprint)|[ispunct](#ispunct)|
|[isspace](#isspace)|[isupper](#isupper)|[isxdigit](#isxdigit)|
|[tolower](#tolower)|[toupper](#toupper)|[use_facet](#use_facet)|

## <a name="has_facet"></a><a name="has_facet"></a>has_facet

测试某一特定 facet 是否存储在指定区域设置中。

```cpp
template <class Facet>
bool has_facet(const locale& Loc);
```

### <a name="parameters"></a>参数

*Loc*\
测试其中是否存在 facet 的区域设置。

### <a name="return-value"></a>返回值

**`true`** 如果区域设置测试了方面，则为;**`false`** 否则为。

### <a name="remarks"></a>备注

模板函数可用于检查在调用 `use_facet` 之前是否在区域设置中列出了非强制性 facet，以避免在不存在 facet 时将引发的异常。

### <a name="example"></a>示例

```cpp
// locale_has_facet.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   bool result = has_facet <ctype<char> > ( loc );
   cout << result << endl;
}
```

```Output
1
```

## <a name="isalnum"></a><a name="isalnum"></a>isalnum

测试区域设置中的某一元素是否是字母字符或数字字符。

```cpp
template <class CharType>
bool isalnum(CharType Ch, const locale& Loc)
```

### <a name="parameters"></a>参数

*48*\
要测试的字母数字元素。

*Loc*\
包含要测试的字母数字元素的区域设置。

### <a name="return-value"></a>返回值

**`true`** 如果测试的元素是字母数字，则为;**`false`** 否则为。

### <a name="example"></a>示例

```cpp
// locale_isalnum.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>

using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   bool result1 = isalnum ( 'L', loc);
   bool result2 = isalnum ( '@', loc);
   bool result3 = isalnum ( '3', loc);

   if ( result1 )
      cout << "The character 'L' in the locale is "
           << "alphanumeric." << endl;
   else
      cout << "The character 'L' in the locale is "
           << " not alphanumeric." << endl;

   if ( result2 )
      cout << "The character '@' in the locale is "
           << "alphanumeric." << endl;
   else
      cout << "The character '@' in the locale is "
           << " not alphanumeric." << endl;

   if ( result3 )
      cout << "The character '3' in the locale is "
           << "alphanumeric." << endl;
   else
      cout << "The character '3' in the locale is "
           << " not alphanumeric." << endl;
}
```

```Output
The character 'L' in the locale is alphanumeric.
The character '@' in the locale is  not alphanumeric.
The character '3' in the locale is alphanumeric.
```

## <a name="isalpha"></a><a name="isalpha"></a>isalpha

测试区域设置中的某一元素是否是字母字符。

```cpp
template <class CharType>
bool isalpha(CharType Ch, const locale& Loc)
```

### <a name="parameters"></a>参数

*48*\
要进行测试的元素。

*Loc*\
包含要测试的字母元素的区域设置。

### <a name="return-value"></a>返回值

**`true`** 如果测试的元素是字母，则为;**`false`** 否则为。

### <a name="remarks"></a>备注

模板函数返回[use_facet](../standard-library/locale-functions.md#use_facet) <  [ctype](../standard-library/ctype-class.md) \< **CharType**> > （ `Loc` ）。 [is](../standard-library/ctype-class.md#is)（ **ctype** \< **CharType**> ：： **alpha**， `Ch` ）。

### <a name="example"></a>示例

```cpp
// locale_isalpha.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>

using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   bool result1 = isalpha ( 'L', loc);
   bool result2 = isalpha ( '@', loc);
   bool result3 = isalpha ( '3', loc);

   if ( result1 )
      cout << "The character 'L' in the locale is "
           << "alphabetic." << endl;
   else
      cout << "The character 'L' in the locale is "
           << " not alphabetic." << endl;

   if ( result2 )
      cout << "The character '@' in the locale is "
           << "alphabetic." << endl;
   else
      cout << "The character '@' in the locale is "
           << " not alphabetic." << endl;

   if ( result3 )
      cout << "The character '3' in the locale is "
           << "alphabetic." << endl;
   else
      cout << "The character '3' in the locale is "
           << " not alphabetic." << endl;
}
```

## <a name="iscntrl"></a><a name="iscntrl"></a>iscntrl

测试区域设置中的某一元素是否是控制字符。

```cpp
template <class CharType>
bool iscntrl(CharType Ch, const locale& Loc)
```

### <a name="parameters"></a>参数

*48*\
要进行测试的元素。

*Loc*\
包含要测试的元素的区域设置。

### <a name="return-value"></a>返回值

**`true`** 如果测试的元素是控制字符，则为; 否则为。**`false`** 否则为。

### <a name="remarks"></a>备注

模板函数返回[use_facet](../standard-library/locale-functions.md#use_facet) <  [ctype](../standard-library/ctype-class.md) \< **CharType**> > （ `Loc` ）。 [is](../standard-library/ctype-class.md#is)（ **ctype** \< **CharType**> ：： **cntrl**， `Ch` ）。

### <a name="example"></a>示例

```cpp
// locale_iscntrl.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>

using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   bool result1 = iscntrl ( 'L', loc );
   bool result2 = iscntrl ( '\n', loc );
   bool result3 = iscntrl ( '\t', loc );

   if ( result1 )
      cout << "The character 'L' in the locale is "
           << "a control character." << endl;
   else
      cout << "The character 'L' in the locale is "
           << " not a control character." << endl;

   if ( result2 )
      cout << "The character-set 'backslash-n' in the locale\n is "
           << "a control character." << endl;
   else
      cout << "The character-set 'backslash-n' in the locale\n is "
           << " not a control character." << endl;

   if ( result3 )
      cout << "The character-set 'backslash-t' in the locale\n is "
           << "a control character." << endl;
   else
      cout << "The character-set 'backslash-n' in the locale \n is "
           << " not a control character." << endl;
}
```

## <a name="isdigit"></a><a name="isdigit"></a>isdigit

测试区域设置中的某一元素是否是数字字符。

```cpp
template <class CharType>
bool isdigit(CharType Ch, const locale& Loc)
```

### <a name="parameters"></a>参数

*48*\
要进行测试的元素。

*Loc*\
包含要测试的元素的区域设置。

### <a name="return-value"></a>返回值

**`true`** 如果测试的元素是数字字符，则为; 否则为。**`false`** 否则为。

### <a name="remarks"></a>备注

模板函数返回[use_facet](../standard-library/locale-functions.md#use_facet) <  [ctype](../standard-library/ctype-class.md) \< **CharType**> > （ `Loc` ）。 [is](../standard-library/ctype-class.md#is)（ **ctype** \< **CharType**> ：：**数字**， `Ch` ）。

### <a name="example"></a>示例

```cpp
// locale_is_digit.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>

using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   bool result1 = isdigit ( 'L', loc );
   bool result2 = isdigit ( '@', loc );
   bool result3 = isdigit ( '3', loc );

   if ( result1 )
      cout << "The character 'L' in the locale is "
           << "a numeric character." << endl;
   else
      cout << "The character 'L' in the locale is "
           << " not a numeric character." << endl;

   if ( result2 )
      cout << "The character '@' in the locale is "
           << "a numeric character." << endl;
   else
      cout << "The character '@' in the locale is "
           << " not a numeric character." << endl;

   if ( result3 )
      cout << "The character '3' in the locale is "
           << "a numeric character." << endl;
   else
      cout << "The character '3' in the locale is "
           << " not a numeric character." << endl;
}
```

## <a name="isgraph"></a><a name="isgraph"></a>isgraph

测试区域设置中的某一元素是否是字母数字字符或标点字符。

```cpp
template <class CharType>
bool isgraph(CharType Ch, const locale& Loc)
```

### <a name="parameters"></a>参数

*48*\
要进行测试的元素。

*Loc*\
包含要测试的元素的区域设置。

### <a name="return-value"></a>返回值

**`true`** 如果测试的元素是字母数字或标点字符，则为;**`false`** 否则为。

### <a name="remarks"></a>备注

模板函数返回[use_facet](../standard-library/locale-functions.md#use_facet) <  [ctype](../standard-library/ctype-class.md) \< **CharType**> > （ `Loc` ）。 [为](../standard-library/ctype-class.md#is)（ **ctype** \< **CharType**> ：： **graph**， `Ch` ）。

### <a name="example"></a>示例

```cpp
// locale_is_graph.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>

using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   bool result1 = isgraph ( 'L', loc );
   bool result2 = isgraph ( '\t', loc );
   bool result3 = isgraph ( '.', loc );

   if ( result1 )
      cout << "The character 'L' in the locale is\n "
           << "an alphanumeric or punctuation character." << endl;
   else
      cout << "The character 'L' in the locale is\n "
           << " not an alphanumeric or punctuation character." << endl;

   if ( result2 )
      cout << "The character 'backslash-t' in the locale is\n "
           << "an alphanumeric or punctuation character." << endl;
   else
      cout << "The character 'backslash-t' in the locale is\n "
           << "not an alphanumeric or punctuation character." << endl;

   if ( result3 )
      cout << "The character '.' in the locale is\n "
           << "an alphanumeric or punctuation character." << endl;
   else
      cout << "The character '.' in the locale is\n "
           << " not an alphanumeric or punctuation character." << endl;
}
```

## <a name="islower"></a><a name="islower"></a>islower

测试区域设置中的某一元素是否是小写。

```cpp
template <class CharType>
bool islower(CharType Ch, const locale& Loc)
```

### <a name="parameters"></a>参数

*48*\
要进行测试的元素。

*Loc*\
包含要测试的元素的区域设置。

### <a name="return-value"></a>返回值

**`true`** 如果测试的元素是小写字符，则为; 否则为。**`false`** 否则为。

### <a name="remarks"></a>备注

模板函数返回[use_facet](../standard-library/locale-functions.md#use_facet) <  [ctype](../standard-library/ctype-class.md) \< **CharType**> > （ `Loc` ）。 [is](../standard-library/ctype-class.md#is)（ **ctype** \< **CharType**> ：： **lower**， `Ch` ）。

### <a name="example"></a>示例

```cpp
// locale_islower.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>

using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   bool result1 = islower ( 'L', loc );
   bool result2 = islower ( 'n', loc );
   bool result3 = islower ( '3', loc );

   if ( result1 )
      cout << "The character 'L' in the locale is "
           << "a lowercase character." << endl;
   else
      cout << "The character 'L' in the locale is "
           << " not a lowercase character." << endl;

   if ( result2 )
      cout << "The character 'n' in the locale is "
           << "a lowercase character." << endl;
   else
      cout << "The character 'n' in the locale is "
           << " not a lowercase character." << endl;

   if ( result3 )
      cout << "The character '3' in the locale is "
           << "a lowercase character." << endl;
   else
      cout << "The character '3' in the locale is "
           << " not a lowercase character." << endl;
}
```

## <a name="isprint"></a><a name="isprint"></a>isprint

测试区域设置中的某一元素是否是可打印字符。

```cpp
template <class CharType>
bool isprint(CharType Ch, const locale& Loc)
```

### <a name="parameters"></a>参数

*48*\
要进行测试的元素。

*Loc*\
包含要测试的元素的区域设置。

### <a name="return-value"></a>返回值

**`true`** 如果测试的元素是可打印元素，则为;**`false`** 否则为。

### <a name="remarks"></a>备注

模板函数返回[use_facet](../standard-library/locale-functions.md#use_facet) <  [ctype](../standard-library/ctype-class.md) \< **CharType**> > （ `Loc` ）。 [is](../standard-library/ctype-class.md#is)（ **ctype** \< **CharType**> ：： **print**， `Ch` ）。

### <a name="example"></a>示例

```cpp
// locale_isprint.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc ( "German_Germany" );

   bool result1 = isprint ( 'L', loc );
   if ( result1 )
      cout << "The character 'L' in the locale is "
           << "a printable character." << endl;
   else
      cout << "The character 'L' in the locale is "
           << " not a printable character." << endl;

   bool result2 = isprint( '\t', loc );
   if ( result2 )
      cout << "The character 'backslash-t' in the locale is "
           << "a printable character." << endl;
   else
      cout << "The character 'backslash-t' in the locale is "
           << " not a printable character." << endl;

   bool result3 = isprint( '\n', loc );
   if ( result3 )
      cout << "The character 'backslash-n' in the locale is "
           << "a printable character." << endl;
   else
      cout << "The character 'backslash-n' in the locale is "
           << " not a printable character." << endl;
}
```

## <a name="ispunct"></a><a name="ispunct"></a>ispunct

测试区域设置中的某一元素是否是标点字符。

```cpp
template <class CharType>
bool ispunct(CharType Ch, const locale& Loc)
```

### <a name="parameters"></a>参数

*48*\
要进行测试的元素。

*Loc*\
包含要测试的元素的区域设置。

### <a name="return-value"></a>返回值

**`true`** 如果测试的元素是标点字符，则为; 否则为。**`false`** 否则为。

### <a name="remarks"></a>备注

模板函数返回[use_facet](../standard-library/locale-functions.md#use_facet) `<` [ctype](../standard-library/ctype-class.md) \< **CharType**> > （ `Loc` ）。 [is](../standard-library/ctype-class.md#is)（ **ctype** \< **CharType**> ：： **punct**， `Ch` ）。

### <a name="example"></a>示例

```cpp
// locale_ispunct.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>

using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   bool result1 = ispunct ( 'L', loc );
   bool result2 = ispunct ( ';', loc );
   bool result3 = ispunct ( '*', loc );

   if ( result1 )
      cout << "The character 'L' in the locale is "
           << "a punctuation character." << endl;
   else
      cout << "The character 'L' in the locale is "
           << " not a punctuation character." << endl;

   if ( result2 )
      cout << "The character ';' in the locale is "
           << "a punctuation character." << endl;
   else
      cout << "The character ';' in the locale is "
           << " not a punctuation character." << endl;

   if ( result3 )
      cout << "The character '*' in the locale is "
           << "a punctuation character." << endl;
   else
      cout << "The character '*' in the locale is "
           << " not a punctuation character." << endl;
}
```

## <a name="isspace"></a><a name="isspace"></a>isspace

测试区域设置中的某一元素是否是空白字符。

```cpp
template <class CharType>
bool isspace(CharType Ch, const locale& Loc)
```

### <a name="parameters"></a>参数

*48*\
要进行测试的元素。

*Loc*\
包含要测试的元素的区域设置。

### <a name="return-value"></a>返回值

**`true`** 如果测试的元素是空白字符，则为; 否则为。**`false`** 否则为。

### <a name="remarks"></a>备注

模板函数返回[use_facet](../standard-library/locale-functions.md#use_facet) <  [ctype](../standard-library/ctype-class.md) \< **CharType**> > （ `Loc` ）。 [is](../standard-library/ctype-class.md#is)（ **ctype** \< **CharType**> ：： **space**， `Ch` ）。

### <a name="example"></a>示例

```cpp
// locale_isspace.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>

using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   bool result1 = isspace ( 'L', loc );
   bool result2 = isspace ( '\n', loc );
   bool result3 = isspace ( ' ', loc );

   if ( result1 )
      cout << "The character 'L' in the locale is "
           << "a whitespace character." << endl;
   else
      cout << "The character 'L' in the locale is "
           << " not a whitespace character." << endl;

   if ( result2 )
      cout << "The character 'backslash-n' in the locale is "
           << "a whitespace character." << endl;
   else
      cout << "The character 'backslash-n' in the locale is "
           << " not a whitespace character." << endl;

   if ( result3 )
      cout << "The character ' ' in the locale is "
           << "a whitespace character." << endl;
   else
      cout << "The character ' ' in the locale is "
           << " not a whitespace character." << endl;
}
```

## <a name="isupper"></a><a name="isupper"></a>isupper

测试区域设置中的某一元素是否是大写。

```cpp
template <class CharType>
bool isupper(CharType Ch, const locale& Loc)
```

### <a name="parameters"></a>参数

*48*\
要进行测试的元素。

*Loc*\
包含要测试的元素的区域设置。

### <a name="return-value"></a>返回值

**`true`** 如果测试的元素是大写字符，则为; 否则为。**`false`** 否则为。

### <a name="remarks"></a>备注

模板函数返回[use_facet](../standard-library/locale-functions.md#use_facet) <  [ctype](../standard-library/ctype-class.md) \< **CharType**> > （ `Loc` ）。 [is](../standard-library/ctype-class.md#is)（ **ctype** \< **CharType**> ：： **upper**， `Ch` ）。

### <a name="example"></a>示例

```cpp
// locale_isupper.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>

using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   bool result1 = isupper ( 'L', loc );
   bool result2 = isupper ( 'n', loc );
   bool result3 = isupper ( '3', loc );

   if ( result1 )
      cout << "The character 'L' in the locale is "
           << "a uppercase character." << endl;
   else
      cout << "The character 'L' in the locale is "
           << " not a uppercase character." << endl;

   if ( result2 )
      cout << "The character 'n' in the locale is "
           << "a uppercase character." << endl;
   else
      cout << "The character 'n' in the locale is "
           << " not a uppercase character." << endl;

   if ( result3 )
      cout << "The character '3' in the locale is "
           << "a uppercase character." << endl;
   else
      cout << "The character '3' in the locale is "
           << " not a uppercase character." << endl;
}
```

## <a name="isxdigit"></a><a name="isxdigit"></a>isxdigit

测试区域设置中的某一元素是否是用于表示十六进制数字的字符。

```cpp
template <class CharType>
bool isxdigit(CharType Ch, const locale& Loc)
```

### <a name="parameters"></a>参数

*48*\
要进行测试的元素。

*Loc*\
包含要测试的元素的区域设置。

### <a name="return-value"></a>返回值

**`true`** 如果测试的元素是用于表示十六进制数字的字符，则为; 否则为。**`false`** 否则为。

### <a name="remarks"></a>备注

模板函数返回[use_facet](../standard-library/locale-functions.md#use_facet) <  [ctype](../standard-library/ctype-class.md) \< **CharType**> > （ `Loc` ）。 [is](../standard-library/ctype-class.md#is)（ **ctype** \< **CharType**> ：： **xdigit**， `Ch` ）。

十六进制数字以 16 为基数来表示数字，使用 0 到 9 的数字加上不区分大小写的 A 到 F 的字母来表示 0 到 15 的十进制数字。

### <a name="example"></a>示例

```cpp
// locale_isxdigit.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>

using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   bool result1 = isxdigit ( '5', loc );
   bool result2 = isxdigit ( 'd', loc );
   bool result3 = isxdigit ( 'q', loc );

   if ( result1 )
      cout << "The character '5' in the locale is "
           << "a hexidecimal digit-character." << endl;
   else
      cout << "The character '5' in the locale is "
           << " not a hexidecimal digit-character." << endl;

   if ( result2 )
      cout << "The character 'd' in the locale is "
           << "a hexidecimal digit-character." << endl;
   else
      cout << "The character 'd' in the locale is "
           << " not a hexidecimal digit-character." << endl;

   if ( result3 )
      cout << "The character 'q' in the locale is "
           << "a hexidecimal digit-character." << endl;
   else
      cout << "The character 'q' in the locale is "
           << " not a hexidecimal digit-character." << endl;
}
```

## <a name="tolower"></a><a name="tolower"></a>tolower

将字符转换为小写。

```cpp
template <class CharType>
CharType tolower(CharType Ch, const locale& Loc)
```

### <a name="parameters"></a>参数

*48*\
要转换为小写的字符。

*Loc*\
包含要转换的字符的区域设置。

### <a name="return-value"></a>返回值

被转换为小写的字符。

### <a name="remarks"></a>备注

模板函数返回[use_facet](../standard-library/locale-functions.md#use_facet) <  [ctype](../standard-library/ctype-class.md) \< **CharType**> > （ `Loc` ）。 [tolower](../standard-library/ctype-class.md#tolower)（ `Ch` ）。

### <a name="example"></a>示例

```cpp
// locale_tolower.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   char result1 = tolower ( 'H', loc );
   cout << "The lower case of 'H' in the locale is: "
        << result1 << "." << endl;
   char result2 = tolower ( 'h', loc );
   cout << "The lower case of 'h' in the locale is: "
        << result2 << "." << endl;
   char result3 = tolower ( '$', loc );
   cout << "The lower case of '$' in the locale is: "
        << result3 << "." << endl;
}
```

## <a name="toupper"></a><a name="toupper"></a>toupper

将字符转换为大写。

```cpp
template <class CharType>
CharType toupper(CharType Ch, const locale& Loc)
```

### <a name="parameters"></a>参数

*48*\
要转换为大写的字符。

*Loc*\
包含要转换的字符的区域设置。

### <a name="return-value"></a>返回值

转换为大写的字符。

### <a name="remarks"></a>备注

模板函数返回[use_facet](../standard-library/locale-functions.md#use_facet) <  [ctype](../standard-library/ctype-class.md) \< **CharType**> > （ `Loc` ）。 [toupper](../standard-library/ctype-class.md#toupper)（ `Ch` ）。

### <a name="example"></a>示例

```cpp
// locale_toupper.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   char result1 = toupper ( 'h', loc );
   cout << "The upper case of 'h' in the locale is: "
        << result1 << "." << endl;
   char result2 = toupper ( 'H', loc );
   cout << "The upper case of 'H' in the locale is: "
        << result2 << "." << endl;
   char result3 = toupper ( '$', loc );
   cout << "The upper case of '$' in the locale is: "
        << result3 << "." << endl;
}
```

## <a name="use_facet"></a><a name="use_facet"></a>use_facet

返回对区域设置中存储的某一指定类型 facet 的引用。

```cpp
template <class Facet>
const Facet& use_facet(const locale& Loc);
```

### <a name="parameters"></a>参数

*Loc*\
包含所引用的 facet 类型的 const 区域设置。

### <a name="return-value"></a>返回值

对 `Facet` 类的 facet 的引用包含在自变量区域设置中。

### <a name="remarks"></a>备注

只要存在包含区域设置的任何副本，则模板函数返回的对 facet 的引用保持有效。 如果自变量区域设置中没有列出 `Facet` 类的此类 facet 对象，则该函数将引发 `bad_cast` 异常。

### <a name="example"></a>示例

```cpp
// locale_use_facet.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc1 ( "German_Germany" ), loc2 ( "English_Australia" );
   bool result1 = use_facet<ctype<char> > ( loc1 ).is(
   ctype_base::alpha, 'a'
);
   bool result2 = use_facet<ctype<char> > ( loc2 ).is( ctype_base::alpha, '!'
   );

   if ( result1 )
      cout << "The character 'a' in locale loc1 is alphabetic."
           << endl;
   else
      cout << "The character 'a' in locale loc1 is not alphabetic."
           << endl;

   if ( result2 )
      cout << "The character '!' in locale loc2 is alphabetic."
           << endl;
   else
      cout << "The character '!' in locale loc2 is not alphabetic."
           << endl;
}
```

```Output
The character 'a' in locale loc1 is alphabetic.
The character '!' in locale loc2 is not alphabetic.
```

## <a name="see-also"></a>另请参阅

[\<locale>](../standard-library/locale.md)
