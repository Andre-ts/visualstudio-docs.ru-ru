---
title: Поиск процесса в представлении процессов | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: how-to
helpviewer_keywords:
- Processes view
- processes, searching for
ms.assetid: 7cb97b37-4a95-4f1b-9eee-4910aa9c115b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3b94a052f7cb50df676140b45a43f49b92283903
ms.sourcegitcommit: 062615c058d2ff44751e8d0c704ccfa3c5543469
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90852000"
---
# <a name="how-to-search-for-a-process-in-processes-view"></a>Практическое руководство. поиск процесса в представлении процессов
Вы можете найти конкретный процесс в представлении процессов, используя идентификатор процесса или строку модуля в качестве условия поиска. Вы также можете указать начальное направление поиска. Поля в диалоговом окне будут содержать атрибуты процесса, выбранного в дереве процессов.

### <a name="to-search-for-a-process-in-processes-view"></a>Поиск процесса в представлении процессов

1. Расположите окна таким образом, чтобы были видны окно Spy++ и активное окно [представления процессов](../debugger/processes-view.md).

2. В меню **Поиск** выберите **Найти процесс**.

    Откроется диалоговое окно [Поиск процесса](../debugger/process-search-dialog-box.md).

3. В качестве условия поиска введите идентификатор процесса или строку модуля.

4. Очистите все поля, в которых не нужно указывать значения.

   > [!TIP]
   > Чтобы найти все процессы, принадлежащие модулю, снимите флажок **Процесс** и введите имя модуля в поле **Модуль**. Затем используйте элемент **Найти далее**, чтобы продолжить поиск процессов.

5. Нажимайте кнопки **Вверх** или **Вниз**, чтобы выбрать начальное направление поиска.

6. Нажмите кнопку **ОК**.

   Если соответствующий процесс найден, он выделяется в окне **Processes View** (Представление процессов).