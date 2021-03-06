---
title: Реализация обработки команд для вложенных проектов | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- nested projects, implementing command handling
ms.assetid: 48a9d66e-d51c-4376-a95a-15796643a9f2
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2092fc8033d5a5cc53b12bd63a945bd9865ca30e
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "80707598"
---
# <a name="implementing-command-handling-for-nested-projects"></a>Реализация обработки команд для вложенных проектов
Интегрированная среда разработки может передавать команды, передаваемые через <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> интерфейс и в <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> вложенные проекты, или же родительские проекты могут фильтровать или переопределять команды.

> [!NOTE]
> Фильтровать можно только команды, обычно обрабатываемые родительским проектом. Такие команды, как **Сборка** и **развертывание** , обрабатываемые интегрированной средой разработки, не могут быть отфильтрованы.

 Следующие шаги описывают процесс реализации обработки команд.

## <a name="procedures"></a>Процедуры

#### <a name="to-implement-command-handling"></a>Реализация обработки команд

1. Когда пользователь выбирает вложенный проект или узел во вложенном проекте:

   1. Интегрированная среда разработки вызывает <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> метод.

      Или...

   2. Если команда была создана в окне иерархии, например в команде контекстного меню в обозреватель решений, интегрированная среда разработки вызывает <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A> метод для родителя проекта.

2. Родительский проект может проверять параметры, передаваемые в `QueryStatus` , например `pguidCmdGroup` и `prgCmds` , чтобы определить, должен ли родительский проект фильтровать команды. Если родительский проект реализуется для фильтрации команд, он должен задать:

   ```
   prgCmds[0].cmdf = OLECMDF_SUPPORTED;
   // make sure it is disabled
   prgCmds[0].cmdf &= ~MSOCMDF_ENABLED;
   ```

    Затем родительский проект должен вернуть значение `S_OK` .

    Если родительский проект не фильтрует команду, он должен просто возвращать `S_OK` . В этом случае интегрированная среда разработки автоматически направляет команду в дочерний проект.

    Родительский проект не должен маршрутизировать команду в дочерний проект. Интегрированная среда разработки выполняет эту задачу.

## <a name="see-also"></a>См. также раздел
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>
- [Команды, меню и панели инструментов](../../extensibility/internals/commands-menus-and-toolbars.md)
- [Проекты вложения](../../extensibility/internals/nesting-projects.md)
