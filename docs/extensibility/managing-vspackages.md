---
title: Управление пакетами VSPackage | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, autoloading
- VSPackages, delayed loading
- delay loading
- VSPackages, loading
ms.assetid: 386e0ce5-4107-4164-b0cd-1cf43eb5e7cf
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 60745d07679ae53b85d169473ed37ab314b67624
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "80702655"
---
# <a name="manage-vspackages"></a>Управление пакетами VSPackage
В большинстве случаев вам не нужно беспокоиться об управлении пакетами VSPackage, так как шаблоны проектов и элементов регистрируются и загружаются автоматически. Однако в некоторых случаях для управления пакетом может потребоваться несколько дополнительных изучений.

## <a name="use-the-experimental-instance"></a>Использование экспериментального экземпляра
 Чтобы узнать больше об экспериментальном экземпляре, см. [экспериментальный экземпляр](../extensibility/the-experimental-instance.md).

## <a name="register-and-unregister-vspackages"></a>Регистрация и Отмена регистрации пакетов VSPackage
 Сведения о регистрации и отмене регистрации пакетов VSPackage и других типов расширений см. в статье [Регистрация пакетов VSPackage](../extensibility/registering-and-unregistering-vspackages.md)и их отмена.

## <a name="load-a-vspackage"></a>Загрузка пакета VSPackage
 Пакеты VSPackage можно установить в значение автозагрузки, если включен определенный идентификатор GUID КМДУИКОНТЕКСТ. Дополнительные сведения см. в разделе [Load VSPackage](../extensibility/loading-vspackages.md).

## <a name="use-asyncpackage-to-load-vspackages-in-the-background"></a>Использование AsyncPackage для загрузки пакетов VSPackage в фоновом режиме
 `AsyncPackage`Класс включает загрузку пакетов в фоновом потоке для улучшения скорости реагирования пользовательского интерфейса в Visual Studio. Дополнительные сведения см. в разделе [как использовать AsyncPackage для загрузки пакетов VSPackage в фоновом режиме](../extensibility/how-to-use-asyncpackage-to-load-vspackages-in-the-background.md).

## <a name="rule-based-ui-context-for-extensions"></a>Контекст пользовательского интерфейса на основе правил для расширений
 Контексты пользовательского интерфейса на основе правил позволяют авторам расширений определять точные условия, при которых активируется контекст пользовательского интерфейса и загружаются связанные пакеты VSPackage. Дополнительные сведения см. [в разделе руководство. использование контекста пользовательского интерфейса на основе правил для расширений Visual Studio](../extensibility/how-to-use-rule-based-ui-context-for-visual-studio-extensions.md).

## <a name="diagnose-extension-performance"></a>Диагностика производительности расширения
Расширения могут повлиять на скорость запуска и загрузки решения. Узнайте, как вычисляется воздействие на расширение Visual Studio и как его можно анализировать локально, чтобы проверить, может ли расширение отображаться в качестве расширения, влияющего на производительность. Дополнительные сведения см. [в разделе как диагностировать производительность расширения](how-to-diagnose-extension-performance.md).

## <a name="troubleshoot-vspackages"></a>Устранение неполадок пакетов VSPackage
 Узнайте о методах устранения неполадок пакетов VSPackage, которые не загружаются или в которых возникают ошибки: [Устранение неполадок пакетов VSPackage](../extensibility/troubleshooting-vspackages.md)

## <a name="see-also"></a>См. также раздел
- [VSPackages](../extensibility/internals/vspackages.md)
