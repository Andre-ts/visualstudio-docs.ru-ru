---
title: ПОПДИРЛИСТФУНК | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- POPLISTFUNC
helpviewer_keywords:
- POPDIRLISTFUNC callback function
ms.assetid: 0ee90fd2-5467-4154-ab4c-7eb02ac3a14c
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 52a0c16af0e142bda8527c5244a22e0830ced9e0
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "80702081"
---
# <a name="popdirlistfunc"></a>POPDIRLISTFUNC
Это функция обратного вызова, предоставляемая функции [сккпопулатедирлист](../extensibility/sccpopulatedirlist-function.md) для обновления коллекции каталогов и (необязательно) имен файлов, которые следует найти в системе управления версиями.

 `POPDIRLISTFUNC`Обратный вызов должен вызываться только для тех каталогов и имен файлов (в списке, заданном для `SccPopulateDirList` функции), которые фактически находятся в системе управления версиями.

## <a name="signature"></a>Подпись

```cpp
typedef BOOL (*POPDIRLISTFUNC)(
   LPVOID pvCallerData,
   BOOL bFolder,
   LPCSTR lpDirectoryOrFileName
);
```

## <a name="parameters"></a>Параметры
 пвкаллердата

окне Значение пользователя, заданное в [сккпопулатедирлист](../extensibility/sccpopulatedirlist-function.md).

 бфолдер

[входные] `TRUE` значение, если имя в `lpDirectoryOrFileName` папке является каталогом; в противном случае — имя файла.

 лпдиректорйорфиленаме

окне Полный локальный путь к каталогу или имени файла в системе управления исходным кодом.

## <a name="return-value"></a>Возвращаемое значение
 Интегрированная среда разработки возвращает соответствующий код ошибки:

|Значение|Описание|
|-----------|-----------------|
|SCC_OK|Продолжайте обработку.|
|SCC_I_OPERATIONCANCELED|Останавливает обработку.|
|SCC_E_xxx|Любая соответствующая ошибка системы управления версиями должна прерывать обработку.|

## <a name="remarks"></a>Remarks
 Если `fOptions` параметр `SccPopulateDirList` функции содержит `SCC_PDL_INCLUDEFILES` флаг, то список может содержать имена файлов, а также имена каталогов.

## <a name="see-also"></a>См. также раздел
- [Функции обратного вызова, реализованные интегрированной средой разработки](../extensibility/callback-functions-implemented-by-the-ide.md)
- [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md)
- [Коды ошибок](../extensibility/error-codes.md)
