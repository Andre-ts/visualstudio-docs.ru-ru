---
title: Реализация и регистрация поставщика портов | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], registering port suppliers
- port suppliers, registering
ms.assetid: fb057052-ee16-4272-8e16-a4da5dda0ad4
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: efa9cdd8740648b66fe7190177b5fe769c4b2539
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "80738529"
---
# <a name="implement-and-register-a-port-supplier"></a>Реализация и регистрация поставщика портов
Роль поставщика порта заключается в отслеживании и предоставлении портов, которые, в свою очередь, управляют процессами. Когда необходимо создать порт, создается экземпляр поставщика порта с помощью команды Create с идентификатором GUID поставщика порта (диспетчер отладки сеанса [SDM] будет использовать поставщика порта, выбранного пользователем, или поставщика порта, указанного в системе проекта). Затем SDM вызывает [канаддпорт](../../extensibility/debugger/reference/idebugportsupplier2-canaddport.md) , чтобы узнать, можно ли добавить какие либо порты. Если порт можно добавить, запрашивается новый порт путем вызова [аддпорт](../../extensibility/debugger/reference/idebugportsupplier2-addport.md) и передачи ему [IDebugPortRequest2](../../extensibility/debugger/reference/idebugportrequest2.md) , описывающего порт. `AddPort` Возвращает новый порт, представленный интерфейсом [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md) .

## <a name="discussion"></a>Разговор
 Порт создается поставщиком порта, связанным с компьютером или сервером отладки. Сервер перечисляет поставщиков портов с помощью метода[енумпортсупплиерс](../../extensibility/debugger/reference/idebugcoreserver2-enumportsuppliers.md) , а поставщик порта перечисляет его порты с помощью метода [енумпортс](../../extensibility/debugger/reference/idebugportsupplier2-enumports.md) .

 Помимо обычной регистрации COM, поставщик порта должен зарегистрироваться в Visual Studio, поместив его CLSID и имя в определенные расположения реестра. Вспомогательная функция SDK отладки с именем `SetMetric` обрабатывает эту работу: она вызывается один раз для каждого регистрируемого элемента, таким образом:

```cpp
SetMetric(metrictypePortSupplier,
          <GUID of your port supplier>,
          metricCLSID,
          <CLSID of your port supplier>,
          false,
          NULL)
SetMetric(metrictypePortSupplier,
          <GUID of your port supplier>,
          metricName,
          <name of your port supplier>,
          false,
          NULL);
```

 Поставщик портов отменяет регистрацию самостоятельно путем вызова `RemoveMetric` (другой вспомогательной функции SDK отладки) для каждого зарегистрированного элемента, таким образом:

```cpp
RemoveMetric(metrictypePortSupplier,
             <GUID of your port supplier>,
             metricCLSID,
             NULL);
RemoveMetric(metrictypePortSupplier,
             <GUID of your port supplier>,
             metricName,
             NULL);
```

> [!NOTE]
> [Вспомогательные функции SDK для отладки](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md) `SetMetric` и `RemoveMetric` являются статическими функциями, определенными в *дбгметрик. h* и скомпилированными в *ad2de. lib*. `metrictypePortSupplier` `metricCLSID` Вспомогательные методы, и `metricName` также определяются в *дбгметрик. h*.

 Поставщик порта может предоставить свое имя и идентификатор GUID с помощью методов [жетпортсупплиернаме](../../extensibility/debugger/reference/idebugportsupplier2-getportsuppliername.md) и [жетпортсупплиерид](../../extensibility/debugger/reference/idebugportsupplier2-getportsupplierid.md)соответственно.

## <a name="see-also"></a>См. также раздел
- [Реализация поставщика порта](../../extensibility/debugger/implementing-a-port-supplier.md)
- [Вспомогательные методы SDK для отладки](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)
- [Поставщики портов](../../extensibility/debugger/port-suppliers.md)
