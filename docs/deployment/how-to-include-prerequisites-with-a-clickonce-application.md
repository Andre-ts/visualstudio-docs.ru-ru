---
title: Включить необходимые компоненты (приложение ClickOnce)
description: Узнайте, как получить пакеты установщика для необходимых компонентов для распространения приложения ClickOnce для компьютера разработчика.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: how-to
ms.assetid: c66bf0a5-8c93-4e68-a224-3b29ac36fe4d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e9199bb720cb94bc949a04bd59d5d3b6527108ed
ms.sourcegitcommit: 75bfdaab9a8b23a097c1e8538ed1cde404305974
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94351197"
---
# <a name="how-to-include-prerequisites-with-a-clickonce-application"></a>Практическое руководство. Включение необходимых компонентов в дистрибутив приложения ClickOnce
Перед распространением программного обеспечения необходимых компонентов с приложением [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] следует загрузить на компьютер разработчика пакеты установщиков этих необходимых компонентов. Если в папке **Packages** пакеты установщиков отсутствуют, при публикации приложения и выборе команды **Загрузить необходимые компоненты с местоположения моего приложения** произойдет ошибка.

> [!NOTE]
> Чтобы добавить пакет установщика для .NET Framework, ознакомьтесь с [руководством по развертыванию .NET Framework для разработчиков](/dotnet/framework/deployment/deployment-guide-for-developers).

## <a name="to-add-an-installer-package-by-using-packagexml"></a><a name="Package"></a> Добавление пакета установщика с помощью файла Package.xml

1. В проводнике откройте папку **Packages**.

    По умолчанию путь имеет значение `%ProgramFiles(x86)%\Microsoft SDKs\ClickOnce Bootstrapper\Packages\` .

2. Откройте папку необходимого компонента, который требуется добавить, а затем папку языка для установленной версии [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] (например, **ru** для русского языка).

3. В блокноте откройте файл *Package.xml*.

4. Выберите элемент **Name** , содержащий `http://go.microsoft.com/fwlink` , и скопируйте URL-адрес. Включите часть **LinkID**.

   > [!NOTE]
   > Если элемент **Name** не содержит `http://go.microsoft.com/fwlink` , откройте файл **Product.xml** в корневой папке для необходимого компонента и перейдите к строке **fwlink** .

   > [!IMPORTANT]
   > Некоторые необходимые компоненты имеют несколько пакетов установщиков (например, для 32-разрядных или 64-разрядных систем). Если строка **fwlink** содержится в нескольких элементах **Имя** , оставшиеся действия следует выполнить для каждого из них.

5. Вставьте URL-адрес в адресную строку браузера, а затем, при получении запроса на выполнение или сохранение, нажмите кнопку **Сохранить**.

    На этом шаге файл установщика загружается на компьютер.

6. Скопируйте файл в корневую папку необходимого компонента.

    Например, для необходимого компонента установщик Windows 4,5 Скопируйте файл в папку *\паккажес\ WindowsInstaller4_5* .

    Теперь можно распространить пакет установщика с приложением.

## <a name="see-also"></a>См. также
- [Как установить необходимые компоненты с помощью приложения ClickOnce](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)
