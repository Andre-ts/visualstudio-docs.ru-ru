---
title: Безопасное развертывание
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- deploying applications [Office development in Visual Studio], security
- Office development in Visual Studio, security
- Office applications [Office development in Visual Studio], security
- ClickOnce deployment [Office development in Visual Studio], security
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: c838eddea5b3118c28fb33411a8c58a19d7b4a2d
ms.sourcegitcommit: 566144d59c376474c09bbb55164c01d70f4b621c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2020
ms.locfileid: "90810958"
---
# <a name="secure-deployment"></a>Безопасное развертывание
  При создании решения Office компьютер разработчика обновляется автоматически, чтобы разрешить выполнение кода в проекте. Однако при развертывании решения необходимо предоставить свидетельство, на основе которого будет основано решение о доверии, подписывая решение с помощью сертификата или используя [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] ключ запроса доверия. Дополнительные сведения см. [в статье предоставление доверия для решений Office](../vsto/granting-trust-to-office-solutions.md).

 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]

 Для настроек на уровне документа при развертывании документа в сетевом расположении необходимо также добавить расположение документа в список надежных расположений в центре управления безопасностью приложения Office. Дополнительные сведения о настройке разрешений для документов на компьютерах конечных пользователей см. в разделе [Предоставление доверия](../vsto/granting-trust-to-documents.md)документам.

## <a name="prevent-office-solutions-from-running-code"></a>Запретить выполнение кода в решениях Office
 Администраторы могут использовать реестр для предотвращения запуска всех решений Office на компьютере. При открытии решения Office с расширениями управляемого кода Инструменты Visual Studio для среды выполнения Office проверяет, существует ли запись с именем `Disabled` в одном из следующих разделов реестра на компьютере:

- **HKEY_CURRENT_USER \Софтваре\микрософт\всто**

- **HKEY_LOCAL_MACHINE \Софтваре\микрософт\всто**

  Чтобы предотвратить выполнение кода в решениях Office, создайте `Disabled` запись в одном или обоих разделах реестра и укажите один из следующих типов данных и значений для `Disabled` :

- REG_SZ или REG_EXPAND_SZ, для которого задана любая строка, отличная от "0" (ноль).

- REG_DWORD, для которого задано любое значение, отличное от 0 (ноль).

  Чтобы разрешить решениям Office выполнять код, установите `Disabled` для обоих записей значение 0 (ноль) или удалите записи реестра.

## <a name="see-also"></a>См. также раздел
- [Развертывание решения Office](../vsto/deploying-an-office-solution.md)
- [Подготовка компьютеров для запуска или размещения решений Office](/previous-versions/bb772092(v=vs.110))
- [Безопасные решения Office](../vsto/securing-office-solutions.md)