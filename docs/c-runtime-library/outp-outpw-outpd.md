---
title: outp、outpw、_outp、_outpw _outpd
description: 描述 Microsoft C 运行时库（CRT）中过时和删除的 outp、outpw、_outp、_outpw 和 _outpd 函数。
ms.date: 12/09/2019
api_name:
- _outpd
- _outp
- _outpw
- outp
- outpw
api_location:
- msvcrt.dll
- msvcr100.dll
- msvcr120.dll
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _outpw
- _outpd
- _outp
- outp
- outpw
- outpd
helpviewer_keywords:
- outpw function
- words
- _outpd function
- outpd function
- outp function
- ports, writing bytes at
- bytes, writing to ports
- words, writing to ports
- double words
- double words, writing to ports
- _outpw function
- _outp function
ms.assetid: c200fe22-41f6-46fd-b0be-ebb805b35181
ms.openlocfilehash: ceaaefbbe6f9debfb5ac8e1e8f5f3d1bbb36c8a8
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "86404055"
---
# <a name="outp-outpw-_outp-_outpw-_outpd"></a>outp、outpw、_outp、_outpw _outpd

在端口、字节（ `outp` 、 `_outp` ）、字（ `outpw` 、 `_outpw` ）或双字（ `_outpd` ）输出。

> [!IMPORTANT]
> 这些函数已过时。 从 Visual Studio 2015 开始，它们在 CRT 中不可用。
> 此 API 不能用于在 Windows 运行时中执行的应用程序。 有关详细信息，请参阅[通用 Windows 平台应用中不支持的 CRT 函数](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)。

## <a name="syntax"></a>语法

```cpp
int _outp(
   unsigned short port,
   int data_byte
);
unsigned short _outpw(
   unsigned short port,
   unsigned short data_word
);
unsigned long _outpd(
   unsigned short port,
   unsigned long data_word
);
```

### <a name="parameters"></a>参数

*口*\
端口号。

*data_byte，data_word*\
输出值。

## <a name="return-value"></a>返回值

这些函数返回数据输出。 无错误返回。

## <a name="remarks"></a>备注

`_outp`、 `_outpw`和 `_outpd` 函数分别将字节、字和双字写入指定的输出端口。 *端口*参数可以是 0-65535 范围内的任何无符号整数。 *data_byte*可以是 0-255 范围内的任意整数。 *data_word*可以是整数范围内的任何值、无符号短整数和无符号长整数。

由于这些函数直接写入到 i/o 端口，因此不能在用户模式 Windows 代码中使用它们。

有关在 Windows 操作系统中使用 i/o 端口的信息，请参阅[串行通信](https://docs.microsoft.com/previous-versions/ff802693(v=msdn.10))。

`outp`和 `outpw` 名称是和函数的旧的、不推荐使用的名称 `_outp` `_outpw` 。 有关详细信息，请参阅[POSIX 函数名称](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names)。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|`_outp`|\<conio.h>|
|`_outpw`|\<conio.h>|
|`_outpd`|\<conio.h>|

有关兼容性的详细信息，请参阅[兼容性](../c-runtime-library/compatibility.md)。

## <a name="libraries"></a>库

[C 运行时库](../c-runtime-library/crt-library-features.md)的所有版本。

## <a name="see-also"></a>另请参阅

[控制台和端口 i/o](../c-runtime-library/console-and-port-i-o.md)\
[`inp`, `inpw`, `_inp`, `_inpw`, `_inpd`](../c-runtime-library/inp-inpw-inpd.md)
