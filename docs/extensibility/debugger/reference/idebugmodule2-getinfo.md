---
title: IDebugModule2::/info | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugModule2::GetInfo
helpviewer_keywords:
- GetInfo method
- IDebugModule2::GetInfo method
ms.assetid: de337e66-294f-4ac9-b21e-71fac7418e36
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: c68c583702d7def5a7bff3ee40a9b8b2c537bb31
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "80726961"
---
# <a name="idebugmodule2getinfo"></a>IDebugModule2::GetInfo
Получает сведения об этом модуле.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetInfo( 
   MODULE_INFO_FIELDS dwFields,
   MODULE_INFO*       pInfo
);
```

```cpp
int GetInfo( 
   enum_MODULE_INFO_FIELDS dwFields,
   MODULE_INFO[]           pInfo
);
```

## <a name="parameters"></a>Параметры
`dwFields`\
окне Сочетание флагов из перечисления [MODULE_INFO_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md) , определяющих поля, которые должны `pInfo` быть заполнены.

`pInfo`\
[вход, выход] Структура [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md) , которая заполняется описанием модуля.

## <a name="return-value"></a>Возвращаемое значение
 Возвращает значение `S_OK`, если выполнение прошло успешно; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Remarks
 Структура [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md) содержит имя модуля, отображаемого в окне **модули** .

## <a name="see-also"></a>См. также раздел
- [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)
- [MODULE_INFO_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md)
- [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md)
