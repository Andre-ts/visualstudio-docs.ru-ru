---
title: BP_UNBOUND_REASON | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BP_UNBOUND_REASON
helpviewer_keywords:
- BP_UNBOUND_REASON enumeration
ms.assetid: 939b6f9c-113b-471d-9f30-b03871af6285
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: b0ee695e1108bf9f1c6069084a0826ee23bf37d4
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "80737775"
---
# <a name="bp_unbound_reason"></a>BP_UNBOUND_REASON
Дает причину, по которой точка останова была непривязанной.

## <a name="syntax"></a>Синтаксис

```cpp
enum enum_BP_UNBOUND_REASON {
    BPUR_UNKNOWN           = 0x0000,
    BPUR_CODE_UNLOADED     = 0x0002,
    BPUR_BREAKPOINT_REBIND = 0x0003,
    BPUR_BREAKPOINT_ERROR  = 0x0004
};
typedef DWORD BP_UNBOUND_REASON;
```

```csharp
public enum enum_BP_UNBOUND_REASON {
    BPUR_UNKNOWN           = 0x0000,
    BPUR_CODE_UNLOADED     = 0x0002,
    BPUR_BREAKPOINT_REBIND = 0x0003,
    BPUR_BREAKPOINT_ERROR  = 0x0004
};
```

## <a name="fields"></a>Поля
`BPUR_UNKNOWN`\
Причина неизвестна.

`BPUR_CODE_UNLOADED`\
Код, содержащий точку останова, выгружен.

`BPUR_BREAKPOINT_REBIND`\
Точка останова была повторно привязана к другому расположению. Это может произойти после операций Edit и Continue при перемещении точки останова или при привязке точки останова к файлу с путем, который больше не является допустимым.

`BPUR_ BREAKPOINT_ERROR`\
Точка останова определяется как ошибка после привязки. Это происходит с управляемыми точками останова, условия которых больше не действительны.

## <a name="remarks"></a>Remarks
Возвращается методом [Reason](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getreason.md) .

## <a name="requirements"></a>Требования
Заголовок: мсдбг. h

Пространство имен: Microsoft. VisualStudio. Debugger. Interop

Сборка: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>См. также
- [Перечисления](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [GetReason](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getreason.md)
