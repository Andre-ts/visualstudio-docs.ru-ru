---
title: Настройка параметров запуска нагрузочного теста из командной строки
ms.date: 10/19/2016
ms.topic: how-to
helpviewer_keywords:
- load tests, command line
- load tests, run settings, selecting
ms.assetid: 175d1d58-f09a-4449-b132-a29a394a7c8e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 79f1cc833278a62e2871cdc725f5993b12bcdb60
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "85287562"
---
# <a name="how-to-select-a-load-test-run-setting-to-use-from-the-command-line"></a>Практическое руководство. Выбор параметров запуска нагрузочного теста из командной строки

Нагрузочный тест может содержать *параметры запуска*, которые представляют собой свойства, определяющие способ выполнения нагрузочного теста. Параметры запуска организованы по категориям в окне **Свойства**. При запуске нагрузочного теста используются те параметры запуска, которые указаны как активные.

Если нагрузочный тест содержит только один набор параметров запуска, этот узел всегда является активным. Если нагрузочный тест содержит несколько узлов параметров, при запуске любой из них можно выбрать с помощью командной строки. См. статью [Практическое руководство. Добавление дополнительных параметров запуска в нагрузочный тест](../test/how-to-add-additional-run-settings-to-a-load-test.md).

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

## <a name="to-change-the-run-setting-from-the-command-line"></a>Изменение параметров запуска из командной строки

1. Если требуется применять разные параметры запуска из командной строки, чтобы воспользоваться преимуществами стратегии использования контекстных параметров, выполните следующую команду:

    `Set Test.UseRunSetting= CorporateStagingWebServer`

2. Запуск нагрузочного теста с помощью программы mstest:

    `mstest /testcontainer:loadtest1.loadtest`

## <a name="see-also"></a>См. также раздел

- [Настройка параметров запуска нагрузочных тестов](../test/configure-load-test-run-settings.md)
- [Указание наборов счетчиков и правил порогов для компьютеров в нагрузочном тесте](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Практическое руководство. Добавление дополнительных параметров запуска в нагрузочный тест](../test/how-to-add-additional-run-settings-to-a-load-test.md)
- [Практическое руководство. Выбор активного параметра запуска для нагрузочного теста](../test/how-to-select-the-active-run-setting-for-a-load-test.md)
