---
title: Время обработки пользовательского интерфейса | Документы Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.uiprocessing
helpviewer_keywords:
- Concurrency Visualizer, UI Processing Time
ms.assetid: 0ddb05a3-8c6b-448b-8488-2751c1e5abcc
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 391b4582d03e32e738f0eade823326e72a662a43
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/18/2020
ms.locfileid: "63004443"
---
# <a name="ui-processing-time"></a>Время обработки пользовательского интерфейса
Эти сегменты на временной шкале связаны с периодами блокирования, отнесенными к категории "Обработка UI". Это означает, что поток переносит сообщения Windows или выполняет другие операции пользовательского интерфейса. В это время поток был заблокирован в интерфейсе API, который визуализатор параллелизма интерпретирует как обработку пользовательского интерфейса. К этой группе относятся такие интерфейсы API, как `GetMessage()` и `MsgWaitForMultipleObjects()`.

 Если предварительно заданные блокирующие интерфейсы API отсутствуют, просмотрите стеки вызовов и отчеты профилирования, чтобы определить изначальную причину задержки.

 Категория "Обработка UI" помогает понять скорость отклика приложений с графическим пользовательским интерфейсом и желательна для приложений, зависящих от скорости отклика пользовательского интерфейса. Например, если поток пользовательского интерфейса приложения 100 % времени находился в состоянии "Обработка UI", скорость его отклика, по всей вероятности, высока. Если значительная часть времени выполнения потока пользовательского интерфейса была затрачена на операции иных категорий, нужно искать корневые причины и рассмотреть возможности сокращения в этом потоке числа операций, не относящихся к категории пользовательского интерфейса.

## <a name="see-also"></a>См. также раздел
- [Представление "Потоки"](../profiling/threads-view-parallel-performance.md)