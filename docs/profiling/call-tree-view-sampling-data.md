---
title: Представление "Дерево вызовов" — данные выборки | Документы Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- sampling profiling method,Call Tree view
- Call Tree view
ms.assetid: 5c4e8ec3-d0d3-485a-93bd-9060df4eb739
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 558cef408ceca48a55563ae31f2399da0e951b8e
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/18/2020
ms.locfileid: "74779757"
---
# <a name="call-tree-view---sampling-data"></a>Представление "Дерево вызовов" — данные выборки
В преставлении "Дерево вызовов" отображаются пути выполнения функции, пересеченные в профилируемом приложении.

> [!NOTE]
> Возможности расширенной безопасности в Windows 8 и Windows Server 2012 требовали значительных изменений в способе, которым профилировщик Visual Studio собирает данные на этих платформах. Для приложений универсальной платформы Windows также требуются новые методы сбора. См. раздел [Средства производительности в приложениях Windows 8 и Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).

 Корнем дерева является точка входа в приложение или компонент. В каждом узле функции перечислены все вызванные в нем функции и содержатся данные о производительности, связанные с этими вызовами функций.

 Значения в представлении "Дерево вызовов" приведены для экземпляров функций, вызванных родительской функцией в дереве вызовов. Процентные значения вычисляются путем сравнения значения экземпляров функции с общим количеством образцов в сеансе профилирования.

## <a name="highlight-the-execution-hot-path"></a>Выделение критического пути выполнения
 Можно развернуть представление "Дерево вызовов" и выделить путь выполнения процесса или функции, который встречается в выборке наиболее часто. Чтобы отобразить самый активный путь, щелкните процесс или функцию правой кнопкой мыши и выберите команду **Развернуть критический путь**.

## <a name="set-the-call-tree-root-node"></a>Задание корневого узла дерева вызовов
 Каждый процесс в сеансе профилирования отображается как корневой узел. Чтобы задать начальный узел представления "Дерево вызовов", щелкните правой кнопкой мыши узел, который необходимо задать в качестве начального, и выберите команду **Задать корень**.

 После задании корневого узла из представления удаляются все записи, кроме поддеревьев выбранного узла. Чтобы восстановить исходное состояние корневого узла, щелкните правой кнопкой мыши в окне представления "Дерево вызовов" и выберите **Сбросить корень**.

|Столбец|Описание|
|------------|-----------------|
|**Идентификатор процесса**|Идентификатор процесса (PID) сеанса профилирования.|
|**Имя процесса**|Имя процесса.|
|**Имя модуля**|Имя модуля, содержащего функцию.|
|**Путь к модулю**|Путь к модулю, содержащему функцию.|
|**Исходный файл**|Исходный файл, содержащий определение данной функции.|
|**Имя функции**|Полное имя функции.|
|**Номер строки функции**|Номер строки, на которой эта функция начинается в исходном файле.|
|**Адрес функции**|Адрес функции.|
|**Уровень**|Глубина функции в дереве вызовов. Только в отчетах командной строки [VSPerfReport](../profiling/vsperfreport.md).|
|**Эксклюзивные выборки**|Число выборок, собранных в этой функции при вызове ее родительской функцией в дереве вызовов. Это значение не включает выборки, собранные в функциях, которые были вызваны этой функцией.|
|**% эксклюзивных выборок**|Процент всех выборок в сеансе профилирования, которые оказались эксклюзивными для данной функции при вызове ее родительской функцией в дереве вызовов.|
|**Инклюзивные выборки**|Число выборок, собранных в этой функции при вызове ее родительской функцией в дереве вызовов. Это значение включает выборки, собранные в функциях, которые были вызваны этой функцией.|
|**Включающие выборки %**|Процент всех выборок в сеансе профилирования, которые оказались инклюзивными для данной функции при вызове ее родительской функцией в дереве вызовов.|

## <a name="see-also"></a>См. также
- [Практическое руководство. Настройка столбцов представлений отчета](../profiling/how-to-customize-report-view-columns.md)
- [Представление в виде дерева вызовов — данные выборки профилировщика](../profiling/call-Tree-view-sampling-data.md)
- [Представление "Дерево вызовов" — выборка](../profiling/call-tree-view-dotnet-memory-sampling-data.md)
- [Представление "Дерево вызовов" — инструментирование](../profiling/call-tree-view-dotnet-memory-instrumentation-data.md)
- [Представление "Дерево вызовов"](../profiling/call-tree-view-instrumentation-data.md)
