---
title: LAUNCH_FLAGS | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- LAUNCH_FLAGS
helpviewer_keywords:
- LAUNCH_FLAGS enumeration
ms.assetid: f51aab02-d257-4302-bb79-b7d8ba9ac4e5
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: f18fb850641391f451f5eedb08b7130566dd4de3
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "80714717"
---
# <a name="launch_flags"></a>LAUNCH_FLAGS
Задает флаги запуска отладки.

## <a name="syntax"></a>Синтаксис

```cpp
enum enum_LAUNCH_FLAGS {
    LAUNCH_DEBUG      = 0x0000,
    LAUNCH_NODEBUG    = 0x0001,
    LAUNCH_ENABLE_ENC = 0x0002,
    LAUNCH_MERGE_ENV  = 0x0004
};
typedef DWORD LAUNCH_FLAGS;
```

```csharp
public enum enum_LAUNCH_FLAGS {
    LAUNCH_DEBUG      = 0x0000,
    LAUNCH_NODEBUG    = 0x0001,
    LAUNCH_ENABLE_ENC = 0x0002,
    LAUNCH_MERGE_ENV  = 0x0004
};
```

## <a name="fields"></a>Поля
`LAUNCH_DEBUG`\
Запускает процесс для отладки.

`LAUNCH_NODEBUG`\
Запускает процесс без его отладки.

`LAUNCH_ENABLE_ENC`\
НЕ РЕКОМЕНДУЕТСЯ, НЕ ИСПОЛЬЗУЙТЕ.

`LAUNCH_MERGE_ENV`\
Запускает процесс и выполняет слияние среды с запускающим узлом.

## <a name="remarks"></a>Remarks
Эти значения передаются в качестве аргумента в метод [лаунчсуспендед](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md) .

Эти флаги можно сочетать с помощью побитовой операции `OR` .

## <a name="requirements"></a>Требования
Заголовок: мсдбг. h

Пространство имен: Microsoft. VisualStudio. Debugger. Interop

Сборка: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>См. также
- [Перечисления](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)
