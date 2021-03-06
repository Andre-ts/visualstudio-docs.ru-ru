---
title: Руководство. Программное открытие текстовых файлов в виде книг
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, opening text files as
- text [Office development in Visual Studio], text files
- text files, opening as workbooks
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 7a0f1b384aafb491183a750f17653ab55f2003e2
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "85519837"
---
# <a name="how-to-programmatically-open-text-files-as-workbooks"></a>Руководство. Программное открытие текстовых файлов в виде книг
  Можно открыть текстовый файл в виде книги. Необходимо передать имя текстового файла, который необходимо открыть. Можно указать несколько необязательных параметров, например номер строки для начала синтаксического анализа и формат столбцов данных в файле.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="example"></a>Пример
 [!code-csharp[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#80)]
 [!code-vb[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#80)]

## <a name="compile-the-code"></a>Компиляция кода
 Для этого примера требуются следующие компоненты:

- Текстовый файл с разделителями-запятыми `Test.txt` , содержащий по крайней мере три строки текста.

- Текстовый файл `Test.txt` , который будет сохранен на диске C.

## <a name="see-also"></a>См. также раздел
- [Работа с книгами](../vsto/working-with-workbooks.md)
- [Руководство. Программное открытие книг](../vsto/how-to-programmatically-open-workbooks.md)
- [Как создать новые книги программным способом](../vsto/how-to-programmatically-create-new-workbooks.md)
- [Как программно сохранять книги](../vsto/how-to-programmatically-save-workbooks.md)
- [Руководство. программное закрытие книг](../vsto/how-to-programmatically-close-workbooks.md)
- [Необязательные параметры в решениях Office](../vsto/optional-parameters-in-office-solutions.md)
