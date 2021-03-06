---
title: 'Идебугпроцесскуерипропертиес:: Куерипропертиес | Документация Майкрософт'
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugProcessQueryProperties::QueryProperties
ms.assetid: 976a9962-b689-45bb-afb6-16b2c5dbc3b8
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 4daac369485febe38e3366d413985bda90b30f05
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "80723315"
---
# <a name="idebugprocessquerypropertiesqueryproperties"></a>IDebugProcessQueryProperties::QueryProperties
Этот метод запрашивает заданные значения свойств процесса отладки.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT QueryProperties(
   ULONG                  celt,
   PROCESS_PROPERTY_TYPE *rgdwPropTypes,
   VARIANT               *rgtPropValues);
```

```csharp
int QueryProperties(
   uint                       celt,
   enum_PROCESS_PROPERTY_TYPE rgdwPropTypes,
   out object[ ]              rgtPropValues);
```

## <a name="parameters"></a>Параметры
`celt`\
окне Размер массивов, содержащих определения свойств и значения свойств.

`dwPropType`\
окне Массив, содержащий определения запрашиваемых свойств. Допустимые значения:

- PROCESS_PROPERTY_COMMAND_LINE = 1

- PROCESS_PROPERTY_CURRENT_DIRECTORY = 2

- PROCESS_PROPERTY_ENVIRONMENT_VARIABLES = 3

`pvarPropValue`\
заполняет Массив, содержащий значения свойств.

## <a name="return-value"></a>Возвращаемое значение
 Возвращает значение `S_OK`, если выполнение прошло успешно; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Remarks
 Этот метод редко используется.

## <a name="see-also"></a>См. также раздел
- [IDebugProcessQueryProperties](../../../extensibility/debugger/reference/idebugprocessqueryproperties.md)
