---
title: Команда Symbol Path
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- debug.symbolpath
helpviewer_keywords:
- symbol path command
- Debug.SymbolPath command
- SymbolPath command
ms.assetid: b697ef2d-3f5d-40df-b113-7068a5bec0d4
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 83acc551c778fdb245b3bacec164a7544253d55f
ms.sourcegitcommit: 566144d59c376474c09bbb55164c01d70f4b621c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2020
ms.locfileid: "90808695"
---
# <a name="symbol-path-command"></a>Команда Symbol Path
Задает список каталогов для поиска символов отладчиком.

## <a name="syntax"></a>Синтаксис

```
Debug.SymbolPath pathname1;pathname2;... pathnameN
```

## <a name="arguments"></a>Аргументы
`pathname`

Необязательный параметр. Список путей, разделенных точкой с запятой, для поиска символов отладчиком.

## <a name="remarks"></a>Remarks
Если `pathname` не указан, эта команда выводит список текущих путей к символам.

## <a name="example-1"></a>Пример 1
Этот пример добавляет два пути в список каталогов символов.

```
Debug.SymbolPath C:\Symbol Path 1;C:\Symbol Path 2
```

## <a name="example-2"></a>Пример 2
Этот пример отображает список текущих путей к символам, разделенных точкой с запятой.

```
Debug.SymbolPath
```

## <a name="see-also"></a>См. также раздел

- [Окно команд](../../ide/reference/command-window.md)
- [Команды Visual Studio](../../ide/reference/visual-studio-commands.md)
