---
title: IDebugPortEx2 | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPortEx2
helpviewer_keywords:
- IDebugPortEx2 interface
ms.assetid: 144724d0-38ee-4c9b-87ca-8a504371182b
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5789681b0da70f46dadac1e29d0d6bb9dc905d1a
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "80724995"
---
# <a name="idebugportex2"></a>IDebugPortEx2
Этот интерфейс позволяет диспетчеру отладки сеансов управлять программами и процессами, выполняемыми в порте.

## <a name="syntax"></a>Синтаксис

```
IDebugPortEx2 : IUnknown
```

## <a name="notes-for-implementers"></a>Примечания для разработчиков
 Пользовательский поставщик порта реализует этот интерфейс для того же объекта, который реализует [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md).

## <a name="notes-for-callers"></a>Примечания для вызывающих объектов
 Модель SDM вызывает [QueryInterface](/cpp/atl/queryinterface) на `IDebugPort2` интерфейсе для получения этого интерфейса.

## <a name="methods-in-vtable-order"></a>Методы в порядке таблицы Vtable
 В следующей таблице показаны методы `IDebugPortEx2` .

|Метод|Описание|
|------------|-----------------|
|[LaunchSuspended](../../../extensibility/debugger/reference/idebugportex2-launchsuspended.md)|Запускает исполняемый файл.|
|[ResumeProcess](../../../extensibility/debugger/reference/idebugportex2-resumeprocess.md)|Возобновляет выполнение процесса.|
|[CanTerminateProcess](../../../extensibility/debugger/reference/idebugportex2-canterminateprocess.md)|Определяет, можно ли завершить процесс.|
|[TerminateProcess](../../../extensibility/debugger/reference/idebugportex2-terminateprocess.md)|Завершает процесс.|
|[GetPortProcessId](../../../extensibility/debugger/reference/idebugportex2-getportprocessid.md)|Возвращает идентификатор процесса самого порта.|
|[GetProgram](../../../extensibility/debugger/reference/idebugportex2-getprogram.md)|Возвращает программу, связанную с узлом программы.|

## <a name="remarks"></a>Remarks
 Обычно этот интерфейс является частным между SDM и пользовательским поставщиком порта.

 При необходимости модуль отладки (DE) может найти этот интерфейс в интерфейсе [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) , переданном в [лаунчсуспендед](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md) , и использовать [лаунчсуспендед](../../../extensibility/debugger/reference/idebugportex2-launchsuspended.md) для запуска программы. Однако это не является обязательным требованием, а DE может выполнять любые действия, необходимые для запуска программы запроса.

## <a name="requirements"></a>Требования
 Заголовок: портприв. h

 Пространство имен: Microsoft. VisualStudio. Debugger. Interop

 Сборка: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>См. также раздел
- [Базовые интерфейсы](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)
