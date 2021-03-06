---
title: Подписки Visual Studio в MPSA | Документация Майкрософт
author: evanwindom
ms.author: v-evwin
manager: cabuschl
ms.assetid: b331c837-3524-42b7-820e-b4fdd5e12793
ms.date: 09/03/2020
ms.topic: conceptual
description: Узнайте об управлении подписками Visual Studio в рамках соглашения о продуктах и службах Майкрософт (MPSA)
ms.openlocfilehash: f0e894272f13b08af20f36579aea807cba7a882a
ms.sourcegitcommit: 09d1f5cef5360cdc1cdfd4b22a1a426b38079618
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "91006089"
---
# <a name="visual-studio-subscriptions-in-a-microsoft-products-and-services-agreement-mpsa"></a>Подписки Visual Studio в соглашении о продуктах и службах Майкрософт (MPSA)
Если вы приобрели подписки Visual Studio по программе MPSA, то существуют несколько моментов, которые следует учесть перед тем, как вы сможете стать администратором подписок Visual Studio и назначать подписки своим пользователям. Если вы уже назначены в качестве администратора, то можете перейти непосредственно на [портал администрирования подписок Visual Studio](https://manage.visualstudio.com/).

Пользователи с соглашением MPSA могут управлять ресурсами, приобретенными через MPSA, на портале [Business Center](https://businessaccount.microsoft.com/Customer), который поддерживает возможности, предоставляемые Volume Licensing Service Center (VLSC). К ним относятся просмотр сводных данных о ваших лицензиях, заказов, файлов для загрузки, ключей, пользователей и т. д. Однако действие подписок Visual Studio в MPSA больше сходно с облачными службами. Портал Business Center также использует рабочие учетные записи для входа, а не учетные записи Майкрософт (MSA). Если ваша организация использует облачные службы, такие как Office 365 или Azure Active Directory, и ваш адрес электронной почты является частью одной из этих служб, этот адрес уже является рабочей учетной записью. Это позволяет вам регистрироваться на портале Business Center при помощи существующего пароля. Если ваша организация не использует облачные службы и ваш адрес электронной почты не является рабочей учетной записью, вы можете использовать его для регистрации на портале Business Center.

Кроме того, когда вы становитесь администратором подписок Visual Studio, на [портале администрирования](https://manage.visualstudio.com/) подписок Visual Studio вы можете назначать подписки подписчикам. В соглашении MPSA подписки Visual Studio необходимо подготовить для соответствующего портала управления, которым является портал администрирования подписок Visual Studio. Для этого необходимо связать учетную запись покупателя с клиентом (например, contoso.onmicrosoft.com).

Обратите внимание на то, что существует два типа клиентов: управляемые и неуправляемые. Управляемый клиент — клиент, который уже управляется администраторами в организации.

Неуправляемый клиент — это клиент, у которого нет собственных администраторов и который не может использоваться для веб-служб, таких как Office 365. Неуправляемые клиенты также создаются при регистрации на портале Business Center с использованием адреса электронной почты, который не связан с рабочей учетной записью. Если при регистрации в Business Center вам было предложено создать пароль, это означает, что ваш адрес электронной почты не связан с рабочей учетной записью и что был создан неуправляемый клиент.

Прежде, чем установить связь с клиентом, необходимо выполнить некоторые действия, чтобы стать администратором Подписок Visual Studio. Эти действия описаны ниже.

## <a name="pre-tenant-association-managed-tenant"></a>Перед установлением связи с клиентом (управляемый клиент)
- Необходимо зарегистрироваться на портале Business Center.
- Необходимо быть администратором пользователей (как минимум) или глобальным администратором в рамках своего клиента. (В случае, если ваша компания уже использует облачные службы.) Указанные роли требуются для того, чтобы стать администратором подписок Visual Studio.
- Необходимо быть глобальным администратором в своем клиенте, чтобы иметь возможность связать вашу учетную запись покупателя с клиентом.
- Необходимо быть администратором учетных записей или диспетчером учетных записей на портале Business Center.
- В вашем профиле пользователя (и любого другого пользователя) поле "Страна или регион" на портале [Azure](https://portal.azure.com/) должно быть заполнено в соответствии с вашим регионом (т. е. США, Калифорния и т. д.). 

> [!NOTE]
> Все пользователи, которых нужно сделать администраторами подписок Visual Studio, необязательно должны быть пользователями портала Business Center, они должны удовлетворять только условиям номер 2 и 5.

Когда соблюдены условия, описанные выше, можно продолжить установление связи учетной записи покупателя с клиентом с помощью следующих действий.
1. Войдите на портал [Business Center](https://businessaccount.microsoft.com/Customer).
2. Щелкните вкладку **Учетная запись** и выберите **Связать домены**.
3. Выберите необходимую **учетную запись покупателя** (если у вас их больше одной).
4. Выберите **клиент** (т. е. contoso.onmicrosoft.com).
5. Нажмите кнопку **Связать домен**.

Обычно при установлении связи процесс подготовки пользователей, соответствующих критериям, в качестве администраторов подписок Visual Studio занимает считаные минуты. Однако в некоторых случаях процесс может занимать до 24 часов. После завершения подготовки клиента вы получите доступ к порталу администрирования подписок Visual Studio. Если процесс продолжается более 24 часов, обратитесь в службу поддержки MPSA, следуя инструкциям:
1. Подключитесь к <https://www.microsoft.com/licensing/mpsa/default>.
2. Нажмите на вкладку **Дополнительно** в верхней части страницы. 
3. Выберите **Поддержка**.
4. Выберите **Поддержка по лицензированию**.
5. Выберите вариант поддержки, который лучше всего соответствует вашим потребностям. 

> [!NOTE]
> При наличии новых пользователей, соответствующих условиям номер 2 и 5 (после установления связи), вам необходимо обратиться в службу поддержки MPSA. Поддержка MPSA будет оказывать помощь новым администраторам подписок Visual Studio.

## <a name="tenant-association-unmanaged"></a>Установление связи с клиентом (неуправляемый клиент)
Если вы зарегистрировались на портале Business Center с помощью адреса электронной почты, который не является рабочей учетной записью (не зарегистрирован в Azure Active Directory (Azure AD)), как описано выше, то процесс установления связи с клиентом будет немного отличаться. Вам необходимо будет выполнить так называемый "перехват домена". Во время этого процесса вы назначите себя глобальным администратором, и ваш неуправляемый клиент станет управляемым.

Более подробное описание этого процесса вы можете найти в [кратких руководствах](https://www.microsoft.com/Licensing/existing-customer/business-center-training-and-resources.aspx). Загрузите руководство под названием *"Настройка и использование веб-служб"* , в котором описывается процедура перехвата домена. После выполнения этого действия ваша учетная запись покупателя будет связана с клиентом.

> [!NOTE]
> После завершения процесса перехвата домена вы станете удовлетворять пяти условиям из раздела "Перед установлением связи с клиентом (управляемый клиент)". После выполнения всех условий останется только связаться со службой поддержки MPSA для подготовки дополнительных администраторов подписок Visual Studio.

## <a name="see-also"></a>См. также
- [Документация по Visual Studio](/visualstudio/)
- [Документация по Azure DevOps](/azure/devops/)
- [Документация по Azure](/azure/)
- [Документация по Microsoft 365](/microsoft-365/)

## <a name="next-steps"></a>Следующие шаги
Узнайте больше об управлении подписками Visual Studio.
- [Назначение отдельных подписок](assign-license.md)
- [Назначение нескольких подписок](assign-license-bulk.md)
- [Изменение подписок](edit-license.md)
- [Удаление подписок](delete-license.md)
- [Определение максимального использования](maximum-usage.md)