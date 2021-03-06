---
title: 'IDebugErrorEvent2:: Жетеррормессаже | Документация Майкрософт'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugErrorEvent2::GetErrorMessage
helpviewer_keywords:
- IDebugErrorEvent2::GetErrorMessage
ms.assetid: 9e3b0d74-a2dd-4eaa-bd95-21b2f9c79409
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 1ff1da2f2a2d24b958a613e6fe5cb58c0081ed3e
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "80730040"
---
# <a name="idebugerrorevent2geterrormessage"></a>IDebugErrorEvent2::GetErrorMessage
Возвращает сведения, позволяющие создавать удобное для восприятия сообщение об ошибке.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetErrorMessage(
   MESSAGETYPE* pMessageType,
   BSTR*        pbstrErrorFormat,
   HRESULT*     hrErrorReason,
   DWORD*       pdwType,
   BSTR*        pbstrHelpFileName,
   DWORD*       pdwHelpId
);
```

```csharp
int GetErrorMessage(
   out enum_MESSAGETYPE   pMessageType,
   out string             pbstrErrorFormat,
   out int                phrErrorReason,
   out uint               pdwType,
   out string             pbstrHelpFileName,
   out uint               pdwHelpId
);
```

## <a name="parameters"></a>Параметры
`pMessageType`\
заполняет Возвращает значение из перечисления [MESSAGETYPE](../../../extensibility/debugger/reference/messagetype.md) , описывающее тип сообщения.

`pbstrErrorFormat`\
заполняет Формат последнего сообщения для пользователя (Дополнительные сведения см. в разделе "Примечания").

`hrErrorReason`\
заполняет Код ошибки, о которой подается сообщение.

`pdwType`\
заполняет Серьезность ошибки (Используйте константы MB_XXX для, например `MessageBox` `MB_EXCLAMATION` или `MB_WARNING` ).

`pbstrHelpFileName`\
заполняет Путь к файлу справки (значение null, если файл справки отсутствует).

`pdwHelpId`\
заполняет Идентификатор отображаемого раздела справки (значение 0, если раздел справки отсутствует).

## <a name="return-value"></a>Возвращаемое значение
 Возвращает значение `S_OK`, если выполнение прошло успешно; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Remarks
 Сообщение об ошибке должно быть отформатировано по строкам `"What I was doing.  %1"` . `"%1"`Затем объект будет заменен вызывающим объектом с сообщением об ошибке, полученным на основе кода ошибки (возвращаемого в `hrErrorReason` ). `pMessageType`Параметр указывает вызывающему объекту, как должно отображаться окончательное сообщение об ошибке.

## <a name="see-also"></a>См. также раздел
- [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md)
- [MESSAGETYPE](../../../extensibility/debugger/reference/messagetype.md)
