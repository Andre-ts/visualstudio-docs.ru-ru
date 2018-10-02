---
title: 'Пошаговое руководство: Запись графических сведений | Документация Майкрософт'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48f12f6e-57b4-48ec-a145-89fa71a42424
caps.latest.revision: 22
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: de553729d37bb82d1b30c6a142f7e65c983bb1c1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47559517"
---
# <a name="walkthrough-capturing-graphics-information"></a>Пошаговое руководство. Запись графических сведений
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [Пошаговое руководство: захват графической информации](https://docs.microsoft.com/visualstudio/debugger/graphics/walkthrough-capturing-graphics-information).  
  
В этом пошаговом руководстве демонстрируется использование [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] диагностики графики вручную захватывать графические данные из приложения Direct3D.  
  
 В данном пошаговом руководстве рассмотрены следующие задачи:  
  
-   Перенаправление диагностики графики в приложение  
  
-   Захват графической информации  
  
## <a name="capturing-graphics-information"></a>Захват графической информации  
 Чтобы использовать средства диагностики графики, сначала нужно захватить графические данные для него. Чтобы включить захват, используйте команду **Начать диагностику** для перенаправления диагностики графики в приложение при его запуске.  
  
#### <a name="to-enable-the-capture-of-graphics-information-after-a-project-or-solution-is-loaded"></a>Включение захвата графических данных после загрузки проекта или решения  
  
1.  В [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], загрузить приложение, которое требуется захватывать графические данные из файла проекта или решения.  
  
2.  На панели инструментов "Диагностика графики" нажмите кнопку **Начать диагностику**.  
  
#### <a name="to-enable-the-capture-of-graphics-information-without-loading-a-project-or-solution"></a>Включение захвата графических данных без загрузки проекта или решения  
  
1.  В строке меню выберите **Файл**, **Открыть**, **Проект/Решение**. Откроется диалоговое окно **Открыть проект** .  
  
2.  Вместо файла проекта или решения укажите исполняемый файл для приложения, из которого требуется захватывать графические данные, а затем нажмите кнопку **Открыть**.  
  
3.  В строке меню выберите **Отладка**, **Графика**, **Начать диагностику**.  
  
 После запуска приложения – когда оно начало отрисовывать кадры — можно захватывать данные графики.  
  
#### <a name="to-capture-graphics-information"></a>Захват графических данных  
  
-   На панели инструментов "Диагностика графики" нажмите кнопку **Захват** . ![Значок кнопки захвата графики](../debugger/media/debuggingdirectxgraphics.png "DebuggingDirectXGraphics")  
  
     - или -  
  
     Поместив фокус на приложение, нажмите клавишу **PRINT SCREEN**.  
  
 Каждый раз при захвате данных о кадре диагностика графики записывает события Direct3D и связанное состояние и добавляет эти данные в журнал графики. Новый журнал графики создается для каждого сеанса диагностики графики. Сведения о журналах графики см. в разделе [Обзор](../debugger/overview-of-visual-studio-graphics-diagnostics.md).  
  
## <a name="next-steps"></a>Следующие шаги  
 В этом пошаговом руководстве было продемонстрировано, как захватывать графические данные вручную. Далее можно перейти к рассмотрению следующего этапа.  
  
-   Узнайте, как анализировать захваченные графические данные с помощью средств диагностики графики. См. в разделе [Обзор](../debugger/overview-of-visual-studio-graphics-diagnostics.md).  
  
## <a name="see-also"></a>См. также  
 [Захват графической информации](../debugger/capturing-graphics-information.md)


