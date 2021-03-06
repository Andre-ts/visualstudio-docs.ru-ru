---
title: Как сообщить о проблеме с Visual Studio
description: Узнайте, как сообщить о проблеме с Visual Studio
ms.date: 03/11/2018
ms.topic: how-to
ms.assetid: bee01179-cde5-4419-9095-190ee0ba5902
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d8e0718eb01f422ad435492304e77d73c14b4dee
ms.sourcegitcommit: da7f093db52df5dcd67e0a030e616b307f0dc2a8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91211179"
---
# <a name="how-to-report-a-problem-with-visual-studio-or-visual-studio-installer"></a>Как сообщить о проблеме с Visual Studio или Visual Studio Installer

> [!NOTE]
> Информацию о Visual Studio для Mac см. в статье [Как сообщить о проблеме в Visual Studio для Mac](/visualstudio/mac/report-a-problem).

Вы можете сообщить о проблеме из Visual Studio или его установщика. Во встроенное средство обратной связи можно с легкостью добавлять диагностические сведения, которые помогают командам Visual Studio диагностировать проблемы и устранять их. Последовательность сообщения о проблеме.

1. **В Visual Studio** выберите значок обратной связи в правом верхнем углу и выберите "Сообщить о проблеме". Вы также можете получить доступ к средству обратной связи из меню **Help** > **Обратная связь** > **Сообщить о проблеме**.
![Сообщите о проблеме во всплывающем окне сообщества разработчиков Visual Studio](media/feedback-button.png). Или же сообщите о проблеме в **Visual Studio Installer**, если вы не можете установить Visual Studio или не можете получить доступ к средству обратной связи в Visual Studio.  В установщике выберите значок обратной связи в правом верхнем углу и выберите "Сообщить о проблеме".
![Всплывающее окно "Сообщить о проблеме" в сообществе разработчиков Visual Studio](media/installer.png)

1. При нажатии кнопки **Сообщить о проблеме** открывается ваш браузер по умолчанию и выполняется вход с той же учетной записью, которую вы использовали для входа в Visual Studio.

   ![Войти и сообщить о проблеме](../ide/media/feedback-browser-top.png)

1. Сначала введите описательный заголовок для вашего отчета об ошибках. Его длина должна быть не менее 25 знаков.

    ![Сообщите о проблеме](../ide/media/feedback-report.png)

1. По мере ввода заголовка под этим полем будут отображаться возможные дубликаты.

    ![Поиск дубликатов](../ide/media/feedback-search.png)

1. Выберите возможные дубликаты отчетов об ошибках, чтобы проверить их на соответствие вашей собственной проблеме. Если отчет, соответствующий вашей проблеме, обнаружится, проголосуйте за него вместо создания собственного билета.

    ![Голосование за дубликаты](../ide/media/feedback-duplicate.png)

2. Если дубликаты не были обнаружены, продолжайте и введите описание проблемы. Постарайтесь изложить все как можно более ясно, чтобы мы с большей вероятностью смогли воспроизвести ошибку. Обязательно включите четкие действия для воспроизведения.

3. Если для данного отчета об ошибке это имеет смысл, сделайте снимок экрана, установив флажок *Включить снимок экрана Visual Studio*.

    ![Создание снимка экрана](../ide/media/feedback-screenshot.png) *Этот снимок экрана могут видеть только инженеры Майкрософт*

    Вы можете даже обрезать снимок экрана непосредственно в браузере, чтобы удалить все конфиденциальные или ненужные части.

4. Один из лучших способов помочь команде разработчиков Visual Studio решить эту проблему — предоставить файлы дампа трассировки и кучи, чтобы специалисты могли просмотреть их. Сделать это легко — просто запишите шаги, которые привели к ошибке.

    ![Запишите свои действия](../ide/media/feedback-recording.png) *Эту запись могут просматривать только инженеры Майкрософт*

5. Проверьте вложенные файлы и добавьте дополнительные файлы, если считаете, что это поможет диагностировать проблему.

    ![Вложенные файлы](../ide/media/feedback-attachments.png) *Эти вложенные файлы могут просматривать только инженеры Майкрософт*

6. Последний шаг — нажать кнопку **Отправить**. Отчет будет отправлен непосредственно во внутреннюю систему отчетов об ошибках Visual Studio, где будет ожидать рассмотрения.

## <a name="when-further-information-is-needed"></a>Если требуются дополнительные сведения

Состояние **Нужны дополнительные сведения** указывает, что нам нужны от вас важные дополнительные сведения. Мы оставим комментарий о необходимых конкретных данных, а вы получите уведомление по электронной почте. Если информация не будет получена в течение семи дней, мы отправим вам напоминание. А через 14 дней бездействия запрос будет закрыт.

1. Нажмите ссылку в сообщении электронной почты, чтобы перейти к отчету о проблеме, или откройте страницу My Feedback (Мои отзывы), чтобы увидеть все отчеты в состоянии **Нужны дополнительные сведения**.

    ![Мои отзывы](../ide/media/feedback-my-feedback.png)

1. При нажатии ссылки Provide More Info (Предоставить дополнительные сведения) откроется новый экран. Здесь можно увидеть, какие сведения запрашиваются.

   ![Мои отзывы](../ide/media/feedback-need-more-info.png)

1. Вы можете предоставить дополнительные сведения, добавив комментарии, вложения и записи действий. Этот процесс похож на сообщение о новой проблеме или предоставлении дополнительных сведений при голосовании за проблему.

1. Запрашивающий специалист Майкрософт получает уведомление о поступлении дополнительной информации. Если этой информации будет достаточно, специалист изменит состояние проблемы. В противном случае будут запрошены дополнительные сведения.

Эти запросы, а также все ваши другие **проблемы** и **предложения** можно просмотреть на экране **Мои отзывы**.

## <a name="search-for-solutions-or-provide-feedback"></a>Поиск решений или предоставление отзыва

Если вы не хотите или не можете сообщить о проблеме с помощью Visual Studio, есть вероятность, что о ней уже сообщили, и решение опубликовано на странице [сообщества разработчиков Visual Studio](https://developercommunity.visualstudio.com/).

Если у вас нет проблем, о которых стоит сообщить, но вы хотели бы предложить какую-либо функцию, такая возможность тоже предусмотрена. Дополнительные сведения см. на странице [Предложить функцию](https://developercommunity.visualstudio.com/content/idea/post.html?space=8).

## <a name="see-also"></a>См. также

* [Рекомендации сообщества разработчиков](./developer-community-guidelines.md)
* [Параметры обратной связи Visual Studio](../ide/feedback-options.md)
* [Сообщение о проблеме в Visual Studio для Mac](/visualstudio/mac/report-a-problem)
* [Сообщение о проблеме в C++](/cpp/how-to-report-a-problem-with-the-visual-cpp-toolset)
* [Сообщество разработчиков Visual Studio](https://developercommunity.visualstudio.com/)
* [Конфиденциальность данных в сообществе разработчиков](developer-community-privacy.md)