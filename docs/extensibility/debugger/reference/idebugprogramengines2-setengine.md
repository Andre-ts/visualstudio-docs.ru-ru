---
title: 'IDebugProgramEngines2:: Сетенгине | Документация Майкрософт'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgramEngines2::SetEngine
helpviewer_keywords:
- IDebugProgramEngines2::SetEngine
ms.assetid: c05857ee-89cf-455e-8f1e-300cce4a2eab
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 226f5bbf11627a3171641806a673eaa15b614572
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "80722406"
---
# <a name="idebugprogramengines2setengine"></a>IDebugProgramEngines2::SetEngine
Сообщает узлу программы или программы, какой модуль отладки (DE) следует использовать для отладки этой программы.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT SetEngine( 
   REFGUID guidEngine
);
```

```csharp
int SetEngine( 
   ref Guid guidEngine
);
```

## <a name="parameters"></a>Параметры
`guidEngine`\
окне Идентификатор GUID для DE.

## <a name="return-value"></a>Возвращаемое значение
 Возвращает значение `S_OK`, если выполнение прошло успешно; в противном случае возвращает код ошибки.

## <a name="see-also"></a>См. также раздел
- [IDebugProgramEngines2](../../../extensibility/debugger/reference/idebugprogramengines2.md)
