---
title: 使用 CString
ms.date: 06/18/2018
helpviewer_keywords:
- CString objects, C++ string manipulation
- CString objects, reference counting
- CString class (Visual C++)
ms.assetid: ed018aaf-8b10-46f9-828c-f9c092dc7609
ms.openlocfilehash: 8ebf3441c7d8856fe412e2efed4c717b01ced362
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219009"
---
# <a name="using-cstring"></a>使用 CString

本部分中的主题介绍如何使用 `CString` 进行编程。 有关类的参考文档 `CString` ，请参阅[CStringT](../atl-mfc-shared/reference/cstringt-class.md)的文档。

若要使用 `CString`，请包含 `atlstr.h` 标头。

`CString`、 `CStringA` 和 `CStringW` 类是一个名为[CStringT](../atl-mfc-shared/reference/cstringt-class.md)的类模板的专用化，它基于其支持的字符数据类型。

`CStringW`对象包含 **`wchar_t`** 类型并支持 Unicode 字符串。 `CStringA`对象包含 **`char`** 类型，并支持单字节和多字节（MBCS）字符串。 `CString`对象支持 **`char`** 类型或 **`wchar_t`** 类型，具体取决于是否在编译时定义 MBCS 符号或 UNICODE 符号。

`CString` 对象在 `CStringData` 对象中保留字符数据。 `CString`接受以 NULL 结尾的 C 样式字符串。 `CString`跟踪字符串长度以提高性能，但它还在存储的字符数据中保留空字符，以支持转换为 LPCWSTR。 `CString`导出 C 样式字符串时包含 null 终止符。 可以在中的其他位置插入 NULL `CString` ，但可能会产生意外的结果。

以下一组字符串类可在未链接 MFC 库的情况下使用，无论是否有 CRT 支持：`CAtlString`、`CAtlStringA` 和 `CAtlStringW`。

`CString` 在本机项目中使用。 对于托管代码 (C++/CLI) 项目，请使用 `System::String`。

若要添加多于 `CString`、`CStringA` 或 `CStringW` 当前所能提供的功能，你应该创建包含其他功能的 `CStringT` 的子类。

以下代码显示如何创建 `CString` 并将其打印到标准输出中：

```cpp
#include <atlstr.h>

int main() {
    CString aCString = CString(_T("A string"));
    _tprintf(_T("%s"), (LPCTSTR) aCString);
}
```

## <a name="in-this-section"></a>本节内容

[基本 CString 操作](../atl-mfc-shared/basic-cstring-operations.md)<br/>
介绍基本 `CString` 操作，包括从 C 文本字符串创建对象、访问 `CString` 中的单个字符、串联两个对象以及比较 `CString` 对象。

[字符串数据管理](../atl-mfc-shared/string-data-management.md)<br/>
讨论将 Unicode 和 MBCS 和 `CString` 一起使用。

[CString 语义](../atl-mfc-shared/cstring-semantics.md)<br/>
说明如何使用 `CString` 对象。

[与 C 样式字符串相关的 CString 操作](../atl-mfc-shared/cstring-operations-relating-to-c-style-strings.md)<br/>
介绍操作 `CString` 对象的内容，像 C 样式 null 结尾的字符串一样。

[为 BSTR 分配和释放内存](../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md)<br/>
讨论使用内存作为 BSTR 和 COM 对象。

[CString 异常清理](../atl-mfc-shared/cstring-exception-cleanup.md)<br/>
说明 MFC 3.0 和更高版本中的显式清理不再是必需的。

[CString 参数传递](../atl-mfc-shared/cstring-argument-passing.md)<br/>
说明如何将 CString 对象传递到函数以及如何从函数返回 `CString` 对象。

[Unicode 和多字节字符集（MBCS）支持](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)<br/>
讨论如何为 Unicode 和 MBCS 支持启用 MFC。

## <a name="reference"></a>参考

[CStringT](../atl-mfc-shared/reference/cstringt-class.md)<br/>
提供有关 `CStringT` 类的参考信息。

[CSimpleStringT 类](../atl-mfc-shared/reference/csimplestringt-class.md)<br/>
提供有关 `CSimpleStringT` 类的参考信息。

## <a name="related-sections"></a>相关章节

[字符串（ATL/MFC）](../atl-mfc-shared/strings-atl-mfc.md)<br/>
包含指向介绍管理字符串数据的多种方法的主题的链接。

[字符串（ATL/MFC）](../atl-mfc-shared/strings-atl-mfc.md)
