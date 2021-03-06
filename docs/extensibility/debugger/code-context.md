---
title: Контекст кода | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], contexts
ms.assetid: 65e4d37a-086b-426e-9394-a3534967fd59
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6424c1182f30b1bbfe6c166209b94afb7ec45549
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "80739152"
---
# <a name="code-context"></a>Контекст кода
При [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] отладке — **контекст кода**:

- Предоставляет абстракцию места в коде, известное модулю отладки (DE). В настоящее время для большинства архитектур времени выполнения контекст кода можно рассматривать как адрес в потоке инструкций программы. Для нетрадиционных языков, где код может не быть представлен инструкциями, контекст кода может быть представлен другими средствами.

- Описывает текущую точку в потоке выполнения отлаживаемой программы.

- Существует только в том случае, если программа остановлена в точке останова.

- Имеет связанный контекст документа.

- Реализуется с помощью интерфейса [IDebugCodeContext2](../../extensibility/debugger/reference/idebugcodecontext2.md) .

## <a name="see-also"></a>См. также раздел
- [Контекст документа](../../extensibility/debugger/document-context.md)
- [Контексты отладчика](../../extensibility/debugger/debugger-contexts.md)
