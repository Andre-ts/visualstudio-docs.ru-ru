---
title: 'IDebugObject2:: Жетбаккингфиелдфорпроперти | Документация Майкрософт'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugObject2::GetBackingFieldForProperty
helpviewer_keywords:
- IDebugObject2::GetBackingFieldForProperty method
ms.assetid: e72c6338-5573-4fad-8075-f3ade3435424
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: b5b9fed9b071f34c119c8e4a5af12c1df7990f4c
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "80726243"
---
# <a name="idebugobject2getbackingfieldforproperty"></a>IDebugObject2::GetBackingFieldForProperty
Возвращает поле или переменную (если есть), которые могут быть резервными копиями свойства, представленного этим объектом.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetBackingFieldForProperty(
   IDebugObject2** ppObject
);
```

```csharp
int GetBackingFieldForProperty(
   out IDebugObject2 ppObject
);
```

## <a name="parameters"></a>Параметры
`ppObject`\
заполняет Объект [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md) , описывающий резервное поле.

## <a name="return-value"></a>Возвращаемое значение
 В случае успеха возвращает S_OK; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Remarks
 Объект [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md) представляет свойство класса управляемого кода, то есть метод с методом доступа get и/или Set. Для таких свойств обычно требуется, чтобы переменная содержала значение, управляемое свойством. Эта переменная называется резервным полем. Если для объекта нет резервного поля, убедитесь, что возвращено значение NULL: некоторые вызывающие объекты могут не обратить внимание на возвращаемое значение, но вместо этого будет проверять, было ли возвращено значение NULL в `ppObject` .

## <a name="see-also"></a>См. также раздел
- [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)
