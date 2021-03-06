---
title: IEnumDebugBoundBreakpoints2 | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugBoundBreakpoints2
helpviewer_keywords:
- IEnumDebugBoundBreakpoints2
ms.assetid: ea03e7e1-28d6-40b7-8097-bbb61d3b7caa
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 421d46efbef189fd6ffc86812d2bfdd28f5da5ff
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "80717439"
---
# <a name="ienumdebugboundbreakpoints2"></a>IEnumDebugBoundBreakpoints2
Этот интерфейс перечисляет привязанные точки останова, связанные с отложенной точкой останова или событием, привязанным к точке останова.

## <a name="syntax"></a>Синтаксис

```
IEnumDebugBoundBreakpoints2 : IUnknown
```

## <a name="notes-for-implementers"></a>Примечания для разработчиков
 Модуль отладки (DE) реализует этот интерфейс в рамках поддержки точек останова. Этот интерфейс должен быть реализован, если поддерживаются точки останова.

## <a name="notes-for-callers"></a>Примечания для вызывающих объектов
 Вызовы Visual Studio:

- [Енумбреакпоинтс](../../../extensibility/debugger/reference/idebugbreakpointevent2-enumbreakpoints.md) для получения этого интерфейса, представляющего список всех запущенных точек останова.

- [Енумбаундбреакпоинтс](../../../extensibility/debugger/reference/idebugbreakpointboundevent2-enumboundbreakpoints.md) для получения этого интерфейса, представляющего список всех привязанных точек останова.

- [Енумбаундбреакпоинтс](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumboundbreakpoints.md) для получения этого интерфейса, представляющего список всех точек останова, привязанных к этой ожидающей точке останова.

## <a name="methods-in-vtable-order"></a>Методы в порядке таблицы Vtable
 В следующей таблице показаны методы `IEnumDebugBoundBreakpoints2` .

|Метод|Описание|
|------------|-----------------|
|[Вперед](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2-next.md)|Извлекает указанное число связанных точек останова в последовательности перечисления.|
|[Skip](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2-skip.md)|Пропускает указанное число связанных точек останова в последовательности перечисления.|
|[Сброс](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2-reset.md)|Сбрасывает последовательность перечислений в начало.|
|[Клонировать](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2-clone.md)|Создает перечислитель, который содержит то же состояние перечисления, что и текущий перечислитель.|
|[GetCount](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2-getcount.md)|Возвращает количество связанных точек останова в перечислителе.|

## <a name="remarks"></a>Remarks
 Visual Studio использует привязанные точки останова, представленные этим интерфейсом, для обновления отображения точек останова в интегрированной среде разработки.

## <a name="requirements"></a>Требования
 Заголовок: мсдбг. h

 Пространство имен: Microsoft. VisualStudio. Debugger. Interop

 Сборка: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>См. также раздел
- [Базовые интерфейсы](../../../extensibility/debugger/reference/core-interfaces.md)
- [EnumBoundBreakpoints](../../../extensibility/debugger/reference/idebugbreakpointboundevent2-enumboundbreakpoints.md)
- [EnumBoundBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumboundbreakpoints.md)
- [EnumBoundBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumboundbreakpoints.md)
