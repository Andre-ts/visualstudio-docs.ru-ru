---
title: 'IDebugSymbolSearchEvent2:: Жетсимболсеарчинфо | Документация Майкрософт'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugSymbolSearchEvent2::GetSymbolSearchInfo
helpviewer_keywords:
- IDebugSymbolSearchEvent2::GetSymbolSearchInfo
ms.assetid: ae9eb72b-f2aa-43b8-87ca-da19d2e78d17
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: be498154a8141c61f114682893d0aaf8b841cf95
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "80718898"
---
# <a name="idebugsymbolsearchevent2getsymbolsearchinfo"></a>IDebugSymbolSearchEvent2::GetSymbolSearchInfo
Вызывается обработчиком событий для получения результатов о процессе загрузки символов.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetSymbolSearchInfo(
   IDebugModule3**    pModule,
   BSTR*              pbstrDebugMessage,
   MODULE_INFO_FLAGS* pdwModuleInfoFlags
);
```

```csharp
int GetSymbolSearchInfo(
   IDebugModule3              pModule,
   ref string                 pbstrDebugMessage,
   out enum_MODULE_INFO_FLAGS pdwModuleInfoFlags
);
```

## <a name="parameters"></a>Параметры
`pModule`\
заполняет Объект IDebugModule3, представляющий модуль, для которого были загружены символы.

`pbstrDebugMessage`\
[вход, выход] Возвращает строку, содержащую любые сообщения об ошибках из модуля. Если ошибка отсутствует, эта строка будет содержать только имя модуля, но не будет пустым.

> [!NOTE]
> [C++] `pbstrDebugMessage` параметр не может быть `NULL` и должен быть освобожден с помощью `SysFreeString` .

`pdwModuleInfoFlags`\
заполняет Сочетание флагов из перечисления [MODULE_INFO_FLAGS](../../../extensibility/debugger/reference/module-info-flags.md) , указывающее, загружены ли какие-либо символы.

## <a name="return-value"></a>Возвращаемое значение
 В случае успеха возвращает `S_OK` ; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Remarks
 Когда обработчик получает событие [IDebugSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugsymbolsearchevent2.md) после попытки загрузить символы отладки для модуля, обработчик может вызвать сисмесод, чтобы определить результаты этой нагрузки.

## <a name="see-also"></a>См. также раздел
- [IDebugModule3](../../../extensibility/debugger/reference/idebugmodule3.md)
- [MODULE_INFO_FLAGS](../../../extensibility/debugger/reference/module-info-flags.md)
- [IDebugSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugsymbolsearchevent2.md)
