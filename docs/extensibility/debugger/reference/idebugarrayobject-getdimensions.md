---
title: 'Идебугаррайобжект:: Dimension | Документация Майкрософт'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugArrayObject::GetDimensions
helpviewer_keywords:
- IDebugArrayObject::GetDimensions method
ms.assetid: 113e0aff-9028-49d6-b104-9fe7be4772d7
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 527f79724aeac0de58d0ae63c9c2408ed2eca9ec
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "80736162"
---
# <a name="idebugarrayobjectgetdimensions"></a>IDebugArrayObject::GetDimensions
Возвращает размеры массива.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetDimensions( 
   DWORD dwCount,
   DWORD dwDimensions[]
);
```

```csharp
int GetDimensions(
   [In] uint    dwCount,
   [Out] uint[] dwDimensions
);
```

## <a name="parameters"></a>Параметры
`dwCount`\
окне Число извлекаемых измерений.

`dwDimensions`\
[вход, выход] Массив, который заполняется размерами каждого измерения. `dwCount` Задает максимальный размер `dwDimensions` массива.

## <a name="return-value"></a>Возвращаемое значение
 В случае успеха возвращает S_OK; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Remarks
 Многомерный массив может иметь разные размеры для каждого измерения. Например, при наличии трехмерного массива `myarray[3][2][6]` этот метод возвращает 3, 2 и 6 в `dwDimensions` параметре в указанном порядке.

## <a name="see-also"></a>См. также раздел
- [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)
