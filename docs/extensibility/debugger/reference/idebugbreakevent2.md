---
title: IDebugBreakEvent2 | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugBreakEvent2
helpviewer_keywords:
- IDebugBreakEvent2 interface
ms.assetid: 57dfdbc2-4e68-4dbf-9579-006cd6fb1c62
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1af6ce13de529fef5e16b3bc1be7053f0e1347b6
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "80735403"
---
# <a name="idebugbreakevent2"></a>IDebugBreakEvent2
Этот интерфейс сообщает диспетчеру отладки сеансов (SDM), что асинхронный останов был успешно выполнен.

## <a name="syntax"></a>Синтаксис

```
IDebugBreakEvent2 : IUnknown
```

## <a name="notes-for-implementers"></a>Примечания для разработчиков
 Метод DE реализует этот интерфейс для поддержки прерываний пользователей в программе. Интерфейс [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) должен быть реализован на том же объекте, что и этот интерфейс (модель SDM использует [QueryInterface](/cpp/atl/queryinterface) для доступа к `IDebugEvent2` интерфейсу).

## <a name="notes-for-callers"></a>Примечания для вызывающих объектов
 Модель SDM вызывает [каусебреак](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md) , когда пользователь запрашивает приостановку отлаживаемой программы. Когда программа успешно приостановлена, команда DE отправляет `IDebugBreakEvent2` событие. Это событие отправляется с помощью функции обратного вызова [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) , предоставляемой SDM при присоединении к отлаживаемой программе.

## <a name="remarks"></a>Remarks
 Например, пользователь может выбрать команду **прервать все** в меню **Отладка** , чтобы выйти из программы, выполняющей бесконечный цикл. Модель SDM сообщает программе о необходимости ее завершения путем вызова [каусебреак](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md). Значение DE отправляется `IDebugBreakEvent2` при остановке программы.

## <a name="requirements"></a>Требования
 Заголовок: мсдбг. h

 Пространство имен: Microsoft. VisualStudio. Debugger. Interop

 Сборка: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>См. также раздел
- [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)
- [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)
- [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)
