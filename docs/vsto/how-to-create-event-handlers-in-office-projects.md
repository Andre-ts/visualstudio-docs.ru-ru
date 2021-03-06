---
title: Как создавать обработчики событий в проектах Office
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visual Basic [Office development in Visual Studio], event handlers
- event handlers [Office development in Visual Studio]
- Visual C# [Office development in Visual Studio], event handlers
- events [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: ee85d89dcb990cebd595dadbd7b28add4a7b371a
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "85538311"
---
# <a name="how-to-create-event-handlers-in-office-projects"></a>Как создавать обработчики событий в проектах Office
  Существует несколько способов создания обработчиков событий в Visual Basic и C#. В режиме конструктора можно создать обработчики событий по умолчанию для элементов управления, дважды щелкнув элемент управления или воспользовавшись панелью события в окне **Свойства** для создания обработчиков для любого события в элементе управления. Однако если вы используете представление кода, переключиться на представление конструирования для создания обработчика событий может не потребоваться.

 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]

 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]

### <a name="to-create-an-event-handler-in-visual-basic"></a>Создание обработчика событий в Visual Basic

1. В раскрывающемся списке **имя класса** в верхней части редактора кода выберите объект, для которого требуется создать обработчик событий.

    > [!NOTE]
    > Если необходимо создать обработчики событий для `ThisDocument` или `ThisWorkbook` , необходимо выбрать **(события ThisDocument)** или **(события ThisWorkbook)** в раскрывающемся списке **имя класса** .

2. В раскрывающемся списке **имя метода** в верхней части редактора кода выберите событие.

     Visual Studio создает обработчик событий и перемещает точку вставки в созданный обработчик событий. Если обработчик событий уже существует, точка вставки переместится к существующему обработчику событий.

### <a name="to-create-an-event-handler-in-c"></a>Создание обработчика событий на языке C\#

1. Создайте делегат события в событии **Startup** класса, введя полное имя события, за которым следует пробел, а затем введите без **+=** пробела. Пример:

     `this.<object name>.<event name> +=`

2. В конце строки кода дважды нажмите клавишу TAB.

     Visual Studio автоматически завершает строку кода, создает обработчик событий и перемещает точку вставки в созданный обработчик событий.

## <a name="see-also"></a>См. также раздел
- [Написание кода в решениях Office](../vsto/writing-code-in-office-solutions.md)
- [Пошаговое руководство. Программирование событий элемента управления NamedRange](../vsto/walkthrough-programming-against-events-of-a-namedrange-control.md)
- [Создание решений Office](../vsto/building-office-solutions.md)
