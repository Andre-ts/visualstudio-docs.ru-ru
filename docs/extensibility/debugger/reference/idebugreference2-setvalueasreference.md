---
title: 'IDebugReference2:: Сетвалуеасреференце | Документация Майкрософт'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugReference2::SetValueAsReference
helpviewer_keywords:
- IDebugReference2::SetValueAsReference
ms.assetid: 94a545d2-16b9-45e9-b2e7-4e49ff90aad0
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: f4767dbe08e716d64ea03c18a1c4a6f7d6690a7b
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "80720305"
---
# <a name="idebugreference2setvalueasreference"></a>IDebugReference2::SetValueAsReference
Задает значение ссылки из другой ссылки. Зарезервировано для будущего использования.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT SetValueAsReference ( 
   IDebugReference2** rgpArgs,
   DWORD              dwArgCount,
   IDebugReference2*  pValue,
   DWORD              dwTimeout
);
```

```cpp
int SetValueAsReference ( 
   IDebugReference2[] rgpArgs,
   uint               dwArgCount,
   IDebugReference2   pValue,
   uint               dwTimeout
);
```

## <a name="parameters"></a>Параметры
`rgpArgs`\
окне Массив объектов [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) , используемый для определения способа установки эталонного значения.

`dwArgCount`\
окне Число ссылок в массиве.

`pValue`\
окне Объект [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) , из которого задается значение свойства.

`dwTimeout`\
окне Максимальное время ожидания (в миллисекундах) перед возвратом из этого метода. Используйте `INFINITE` для бесконечного ожидания.

## <a name="return-value"></a>Возвращаемое значение
 Всегда возвращает значение `E_NOTIMPL`.

## <a name="see-also"></a>См. также раздел
- [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)
