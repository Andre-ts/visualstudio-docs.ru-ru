---
title: Изменение языка публикации для приложения ClickOnce
description: Узнайте, как указать язык и региональные параметры для локализации приложения в ClickOnce, а не по умолчанию для языка и региональных параметров компьютера разработчика.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: how-to
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Publish language property
- ClickOnce deployment, changing publish language
- publishing, ClickOnce
ms.assetid: ef5024c4-cda1-4970-bc75-32a2a10c92c3
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7fed8c137b5bce225d8a231bb5a263b87c2bf361
ms.sourcegitcommit: 75bfdaab9a8b23a097c1e8538ed1cde404305974
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94350170"
---
# <a name="how-to-change-the-publish-language-for-a-clickonce-application"></a>Практическое руководство. Изменение языка публикации для приложения ClickOnce

При публикации [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] приложения пользовательский интерфейс, отображаемый во время установки, по умолчанию имеет язык и региональные параметры компьютера разработчика. При публикации локализованного приложения необходимо указать язык и региональные параметры, которые будут соответствовать локализованной версии. Это определяется `Publish language` свойством проекта.

`Publish language`Свойство можно задать в диалоговом окне **Параметры публикации** , доступном на странице **Публикация** в **конструкторе проектов**.

> [!NOTE]
> Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в разделе [Сброс параметров](../ide/environment-settings.md#reset-settings).

## <a name="to-change-the-publish-language"></a>Изменение языка публикации

1. Выберите проект в **обозревателе решений** , а затем в меню **Проект** щелкните **Свойства**.

2. Перейдите на вкладку **Публикация**.

3. Нажмите кнопку " **Параметры** ", чтобы открыть диалоговое окно " **Параметры публикации** ".

4. Щелкните **Описание**.

5. В диалоговом окне **Параметры публикации** выберите язык и региональные параметры из раскрывающегося списка **язык публикации** , а затем нажмите кнопку **ОК**.

## <a name="see-also"></a>См. также

- [Публикация приложений ClickOnce](../deployment/publishing-clickonce-applications.md)
- [Инструкции. Публикация приложения ClickOnce с помощью мастера публикации](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)