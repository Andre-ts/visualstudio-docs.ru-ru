---
title: 'IDebugCanStopEvent2:: Reason | Документация Майкрософт'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCanStopEvent2::GetReason
helpviewer_keywords:
- IDebugCanStopEvent2::GetReason
ms.assetid: f5de31ca-7b8d-4029-9cf9-ba860ac66af6
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 59e611c3ed69528f92a6085cf74aa44efed09144
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "80734520"
---
# <a name="idebugcanstopevent2getreason"></a>IDebugCanStopEvent2::GetReason
Возвращает причину, по которой подсистема отладки (DE) должна быть приостановлена.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetReason( 
   CANSTOP_REASON* pcr
);
```

```csharp
int GetReason( 
   out enum_CANSTOP_REASON pcr
);
```

## <a name="parameters"></a>Параметры
`pcr`\
заполняет Возвращает значение из перечисления [CANSTOP_REASON](../../../extensibility/debugger/reference/canstop-reason.md) , которое описывает причину для этого события.

## <a name="return-value"></a>Возвращаемое значение
 Возвращает значение `S_OK`, если выполнение прошло успешно; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Remarks
 Этот метод обычно вызывается перед методом [канстоп](../../../extensibility/debugger/reference/idebugcanstopevent2-canstop.md) , чтобы вызывающий объект мог определить, передавать ли метод ненулевое значение ( `TRUE` ) `IDebugCanStopEvent2::CanStop` .

 Причиной для остановки может быть либо, что означает, что `CANSTOP_ENTRYPOINT` de достиг точки входа, либо, что означает, что `CANSTOP_STEPIN` функция de пошагова в функцию.

## <a name="see-also"></a>См. также раздел
- [IDebugCanStopEvent2](../../../extensibility/debugger/reference/idebugcanstopevent2.md)
- [CANSTOP_REASON](../../../extensibility/debugger/reference/canstop-reason.md)
- [CanStop](../../../extensibility/debugger/reference/idebugcanstopevent2-canstop.md)
