---
title: Практическое руководство. Открытие нескольких решений
description: Узнайте, как открыть несколько решений в Visual Studio для Mac и несколько экземпляров приложения.
author: heiligerdankgesang
ms.author: dominicn
ms.date: 04/02/2019
ms.assetid: 592BA4E3-8DEF-4FCD-8BA0-519A4CEEE03E
ms.custom: video
ms.topic: how-to
ms.openlocfilehash: d90a2a92e2902633e5667e71c5692faa8fa161e1
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "85950052"
---
# <a name="open-multiple-solutions-or-instances-of-visual-studio-for-mac"></a>Открытие нескольких решений или экземпляров Visual Studio для Mac

По умолчанию все приложения на компьютерах Mac, включая Visual Studio для Mac, имеют _один экземпляр_. Это значит, что если приложение уже открыто (на что указывает точка под значком приложения на панели закрепления), то при повторном выборе его значка откроется уже запущенный экземпляр, а не новый. Если требуются дополнительные экземпляры приложения, можно указать необходимость их открытия, как описано в [следующем разделе](#open-a-second-instance-of-visual-studio-for-mac).

Кроме того, при открытии решения оно по умолчанию открывается в новой рабочей области, а текущая рабочая область закрывается (если необходимо). Это поведение по умолчанию можно переопределить так, чтобы текущая рабочая область оставалась открытой, как описано в разделе [Открытие еще одного решения](#open-a-second-solution-inside-a-single-instance).

## <a name="open-a-second-instance-of-visual-studio-for-mac"></a>Открытие еще одного экземпляра Visual Studio для Mac

Чтобы открыть второй экземпляр интегрированной среде разработки (IDE), щелкните правой кнопкой мыши значок Visual Studio в закрепленном элементе или папке **Приложения** и выберите **Новый экземпляр**.

![Снимок экрана: пункт меню "Новый экземпляр" при щелчке правой кнопкой мыши на значке Visual Studio](media/open-new-instance.png)

## <a name="open-a-second-solution-inside-a-single-instance"></a>Открытие еще одного решения в одном экземпляре

Чтобы открыть еще одно решение, не закрывая первое, выполните указанные ниже действия.

1. Когда первое решение уже открыто, выберите **Файл** > **Открыть**.
2. Найдите существующее решение в файловой системе.
3. Выберите файл с расширением **SLN**, затем выберите **Параметры**:

    ![Снимок экрана Visual Studio для Mac с SLN-файлом и выделенной кнопкой "Параметры"](media/open-multiple-solutions-image3.png)

4. Снимите флажок **Закрыть текущую рабочую область**:

    ![Снимок экрана диалогового окна "Параметры" со снятым флажком "Закрыть текущую рабочую область"](media/open-multiple-solutions-image1.png)

5. На Панели решения выберите **Открыть**, чтобы открыть еще одно решение.

Кроме того, если решение открывалось недавно, можно выполнить указанные ниже действия.

1. Выберите **File (Файл)**  > **Recent Solutions (Последние решения)** .

    ![Снимок экрана меню Recent Solutions (Последние решения)](media/open-multiple-solutions-image2.png)

1. Удерживайте клавишу **CTRL** и выберите решение. В результате на Панели решения откроется еще одно решение.

## <a name="related-video"></a>Связанные видео

> [!Video https://channel9.msdn.com/Shows/Visual-Studio-Toolbox/Visual-Studio-for-Mac-Work-With-Multiple-Solutions/player]
