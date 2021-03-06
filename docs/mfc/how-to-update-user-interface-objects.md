---
title: 如何：更新用户界面对象
ms.date: 11/04/2016
helpviewer_keywords:
- menus [MFC], updating as context changes
- user interface objects [MFC], updating
- user interface objects [MFC]
- update handlers [MFC]
- enabling UI elements [MFC]
- disabling menus [MFC]
- updating user-interface objects [MFC]
- disabling UI elements [MFC]
- commands [MFC], updating UI
- enabling menus [MFC]
ms.assetid: 82f09773-c978-427b-b321-05a6143b7369
ms.openlocfilehash: aec4067a7b5854ef872cfcef19a15db8438dd795
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626386"
---
# <a name="how-to-update-user-interface-objects"></a>如何：更新用户界面对象

通常，菜单项和工具栏按钮有多个状态。 例如，如果菜单项在当前上下文中不可用，则将灰显（变暗）。 菜单项还可处于选中或未选中状态。 工具栏如果不可用也可处于禁用状态，否则它可处于选中状态。

在逻辑上将这些项的状态更新为 "程序条件" 的用户，如果菜单项生成由处理的命令（例如文档），则使文档更新菜单项是有意义的。 文档可能包含更新所基于的信息。

如果命令具有多个用户界面对象（可能是一个菜单项和一个工具栏按钮），则这些对象将路由到同一处理程序函数。 这会将所有等效用户界面对象的用户界面更新代码封装在单个位置。

框架将为自动更新用户界面对象提供方便的界面。 您可以选择以某种其他方式进行更新，但提供的接口是高效且易于使用的。

下列主题介绍了更新处理程序的使用：

- [调用更新处理程序时](when-update-handlers-are-called.md)

- [ON_UPDATE_COMMAND_UI 宏](on-update-command-ui-macro.md)

- [CCmdUI 类](the-ccmdui-class.md)

## <a name="see-also"></a>另请参阅

[菜单](menus-mfc.md)
