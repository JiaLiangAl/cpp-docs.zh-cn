---
title: EVENT_ID枚举
description: C++生成见解 SDK EVENT_ID枚举引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EVENT_ID
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: bcc0bea145a835342c89ad344a0585960fcf0cb3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325570"
---
# <a name="event_id-enum"></a>EVENT_ID枚举

::: moniker range="<=vs-2015"

C++构建见解 SDK 与 Visual Studio 2017 及以上版本兼容。 要查看这些版本的文档，请将本文的 Visual Studio**版本**选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面的目录顶部。

::: moniker-end
::: moniker range=">=vs-2017"

枚`EVENT_ID`举。

## <a name="members"></a>成员

| “属性” | “值” | 事件详细信息 URL |
|--|--|--|
| `EVENT_ID_BACK_END_PASS` | 1 (0x00000001) | [BACK_END_PASS](../event-table.md#back-end-pass) |
| `EVENT_ID_BOTTOM_UP` | 2 （0x0000002） | [BOTTOM_UP](../event-table.md#bottom-up) |
| `EVENT_ID_C1_DLL` | 3 （0x0000003） | [C1_DLL](../event-table.md#c1-dll) |
| `EVENT_ID_C2_DLL` | 4 （0x0000004） | [C2_DLL](../event-table.md#c2-dll) |
| `EVENT_ID_CODE_GENERATION` | 5 （0x0000005） | [CODE_GENERATION](../event-table.md#code-generation) |
| `EVENT_ID_COMMAND_LINE` | 6 （0x0000006） | [COMMAND_LINE](../event-table.md#command-line) |
| `EVENT_ID_COMPILER` | 7 （0x0000007） | [编译 器](../event-table.md#compiler) |
| `EVENT_ID_ENVIRONMENT_VARIABLE` | 8 （0x0000008） | [ENVIRONMENT_VARIABLE](../event-table.md#environment-variable) |
| `EVENT_ID_EXECUTABLE_IMAGE_OUTPUT` | 9 （0x0000009） | [EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output) |
| `EVENT_ID_EXP_OUTPUT` | 10 （0x000000A） | [EXP_OUTPUT](../event-table.md#exp-output) |
| `EVENT_ID_FILE_INPUT` | 11 （0x000000B） | [FILE_INPUT](../event-table.md#file-input) |
| `EVENT_ID_FORCE_INLINEE` | 12 （0x000000C） | [FORCE_INLINEE](../event-table.md#force-inlinee) |
| `EVENT_ID_FRONT_END_FILE` | 13 （0x00000D） | [FRONT_END_FILE](../event-table.md#front-end-file) |
| `EVENT_ID_FRONT_END_PASS` | 14 （0x000000E） | [FRONT_END_PASS](../event-table.md#front-end-pass) |
| `EVENT_ID_FUNCTION` | 15 （0x000000F） | [功能](../event-table.md#function) |
| `EVENT_ID_IMP_LIB_OUTPUT` | 16 （0x0000010） | [IMP_LIB_OUTPUT](../event-table.md#imp-lib-output) |
| `EVENT_ID_LIB_OUTPUT` | 17 （0x00000011） | [LIB_OUTPUT](../event-table.md#lib-output) |
| `EVENT_ID_LINKER` | 18 （0x00000012） | [连接](../event-table.md#linker) |
| `EVENT_ID_LTCG` | 19 （0x00000013） | [LTCG](../event-table.md#ltcg) |
| `EVENT_ID_OBJ_OUTPUT` | 20 （0x00000014） | [OBJ_OUTPUT](../event-table.md#obj-output) |
| `EVENT_ID_OPT_ICF` | 21 （0x00000015） | [OPT_ICF](../event-table.md#opt-icf) |
| `EVENT_ID_OPT_LBR` | 22 （0x00000016） | [OPT_LBR](../event-table.md#opt-lbr) |
| `EVENT_ID_OPT_REF` | 23 （0x00000017） | [OPT_REF](../event-table.md#opt-ref) |
| `EVENT_ID_PASS1` | 24 （0x00000018） | [通过1](../event-table.md#pass1) |
| `EVENT_ID_PASS2` | 25 （0x00000019） | [PASS2](../event-table.md#pass2) |
| `EVENT_ID_PRE_LTCG_OPT_REF` | 26 （0x000001A） | [PRE_LTCG_OPT_REF](../event-table.md#pre-ltcg-opt-ref) |
| `EVENT_ID_SYMBOL_NAME` | 27 （0x000001B） | [SYMBOL_NAME](../event-table.md#symbol-name) |
| `EVENT_ID_TEMPLATE_INSTANTIATION` | 28 （0x000001C） | [TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) |
| `EVENT_ID_THREAD` | 29 （0x000001D） | [线程](../event-table.md#thread) |
| `EVENT_ID_TOP_DOWN` | 30 （0x0000001E） | [TOP_DOWN](../event-table.md#top-down) |
| `EVENT_ID_WHOLE_PROGRAM_ANALYSIS` | 31 （0x0000001F） | [WHOLE_PROGRAM_ANALYSIS](../event-table.md#whole-program-analysis) |

## <a name="remarks"></a>备注

这些值与 C SDK 函数一起使用。

::: moniker-end
