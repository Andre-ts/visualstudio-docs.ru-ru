---
title: Использование элементов управления Windows Forms на листах Excel
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Windows Forms controls [Office development in Visual Studio], Excel
- Excel [Office development in Visual Studio], Windows Forms controls
- controls [Office development in Visual Studio], Window Forms controls
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 032ee551ff04590ccdb8744c1274b137dec0b756
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "62982319"
---
# <a name="use-windows-forms-controls-on-excel-worksheets"></a>Использование элементов управления Windows Forms на листах Excel
  Вы можете добавлять Windows Forms элементы управления в книги Microsoft Office Excel так же, как и элементы управления, добавляемые в Windows Forms. Общие сведения о работе с элементами управления в документах см. [в разделе Windows Forms элементы управления в документах Office](../vsto/windows-forms-controls-on-office-documents-overview.md).

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="control-considerations-for-excel"></a>Рекомендации по управлению для Excel
 Существует несколько аспектов, характерных для Excel.

### <a name="match-control-size-to-cell-size"></a>Соответствие размера элемента управления размеру ячейки
 Вы можете задать автоматическое изменение размера элемента управления при изменении размера его родительской ячейки. Дополнительные сведения см. [в разделе Практические руководства. изменение размеров элементов управления в ячейках листа](../vsto/how-to-resize-controls-within-worksheet-cells.md).

### <a name="add-components-that-are-shared-by-all-worksheets"></a>Добавление компонентов, совместно используемых всеми листами
 Вы можете добавлять компоненты, которые будут совместно использоваться всеми листами, такие как <xref:System.Data.DataSet>, не в сами листы, а в конструктор книги. Такой компонент будет отображаться в области компонентов.

### <a name="formula-for-embedding-controls"></a>Формула для внедрения элементов управления
 При выборе элемента управления в Excel вы увидите **=EMBED("WinForms.Control.Host","")** в **строке формул**. Этот текст обязательный, его не следует удалять.

## <a name="see-also"></a>См. также раздел
- [Руководство. изменение размеров элементов управления в ячейках листа](../vsto/how-to-resize-controls-within-worksheet-cells.md)
- [Как скрыть элементы управления на листах при печати](../vsto/how-to-hide-controls-on-worksheets-when-printing.md)
- [Пошаговое руководство. изменение форматирования листа с помощью элементов управления CheckBox](../vsto/walkthrough-changing-worksheet-formatting-using-checkbox-controls.md)
- [Пошаговое руководство. Отображение текста в текстовом поле листа с помощью кнопки](../vsto/walkthrough-displaying-text-in-a-text-box-in-a-worksheet-using-a-button.md)
- [Пошаговое руководство. Обновление диаграммы на листе с помощью переключателей](../vsto/walkthrough-updating-a-chart-in-a-worksheet-using-radio-buttons.md)
