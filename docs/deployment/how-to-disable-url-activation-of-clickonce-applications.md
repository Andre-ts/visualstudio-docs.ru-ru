---
title: Отключить активацию URL-адресов для приложений ClickOnce
description: Узнайте, как отключить автоматический запуск при установке для приложения ClickOnce, если вы хотите, чтобы пользователи запускали приложение из меню "Пуск".
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: how-to
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- disallowUrlActivation
- URL activation, ClickOnce applications
- ClickOnce deployment, URL activation
ms.assetid: db31a16b-960f-4264-91d7-c7c40f876068
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 46e46278f5465de029aa9536744f51843397d743
ms.sourcegitcommit: 75bfdaab9a8b23a097c1e8538ed1cde404305974
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94351236"
---
# <a name="how-to-disable-url-activation-of-clickonce-applications"></a>Как отключить активацию по URL-адресу приложений ClickOnce

Как правило, приложение [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] запускается автоматически сразу после установки с веб-сервера. По соображениям безопасности можно отключить это поведение и сообщить пользователям, что запускать приложение нужно из меню **Пуск**. Следующая процедура описывает процесс отключения активации через URL.

Такой подход можно использовать только для приложений [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)], установленных на компьютере пользователя с веб-сервера. Этот метод нельзя использовать для приложений, предназначенных только для использования в Интернете, запустить которые можно только с помощью URL. Дополнительные сведения о различиях между приложениями для использования только в Интернете и установленными приложениями см. в разделе [Выбор стратегии развертывания ClickOnce](../deployment/choosing-a-clickonce-deployment-strategy.md).

В этой процедуре используется средство пакета средств разработки программного обеспечения (SDK) для Windows MageUI.exe. Дополнительные сведения об этом средстве см. в разделе [MageUI.exe (инструмент создания и изменения манифестов, графический клиент)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client). Эту процедуру также можно выполнить с помощью Visual Studio.

## <a name="procedure"></a>Процедура

### <a name="to-disable-url-activation-for-your-application"></a>Отключение активации приложения с помощью URL

1. Откройте манифест развертывания в MageUI.exe. Если вы еще не создали его, выполните действия, описанные в [разделе Пошаговое руководство. Развертывание приложения ClickOnce вручную](../deployment/walkthrough-manually-deploying-a-clickonce-application.md).

2. Перейдите на вкладку **Параметры развертывания**.

3. Снимите флажок **Автоматически запускать приложение после установки**.

4. Сохраните и подпишите манифест.

## <a name="see-also"></a>См. также

- [Публикация приложений ClickOnce](../deployment/publishing-clickonce-applications.md)