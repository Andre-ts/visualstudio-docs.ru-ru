---
title: Идебугаддресс | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugAddress
helpviewer_keywords:
- IDebugAddress interface
ms.assetid: bc709ff7-4966-4f36-9af2-690efe2cea1d
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1f281ceb1f305c5774fedbf725f2e6a9481d073d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "80736590"
---
# <a name="idebugaddress"></a>IDebugAddress
Этот интерфейс представляет адрес элемента. Он возвращается обработчиком символов.

## <a name="syntax"></a>Синтаксис

```
IDebugAddress : IUnknown
```

## <a name="notes-for-implementers"></a>Примечания для разработчиков
 Поставщик символов реализует этот интерфейс для представления адреса объекта.

## <a name="notes-for-callers"></a>Примечания для вызывающих объектов
 Многие методы на многих интерфейсах возвращают этот интерфейс.

## <a name="methods-in-vtable-order"></a>Методы в порядке таблицы Vtable
 Этот интерфейс реализует следующий метод:

|Метод|Описание|
|------------|-----------------|
|[GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)|Возвращает структуру [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) , описывающую объект и его расположение.|

## <a name="remarks"></a>Remarks
 Поставщик символов возвращает этот интерфейс для представления объекта и его расположения в определенной области (например, функции, метода или класса). Этот интерфейс возвращается из и передается различным методам поставщика символов и средства оценки выражений. Как правило, поставщик символов является единственной сущностью, которой необходимо интерпретировать содержимое этого интерфейса.

## <a name="requirements"></a>Требования
 Заголовок: sh. h

 Пространство имен: Microsoft. VisualStudio. Debugger. Interop

 Сборка: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>См. также раздел
- [Интерфейсы поставщика символов](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)
- [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)
