---
title: Необязательные параметры в решениях Office
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office applications [Office development in Visual Studio], optional parameters
- Visual C# [Office development in Visual Studio], optional parameters
- Visual Basic [Office development in Visual Studio], optional parameters
- application development [Office development in Visual Studio], optional parameters
- missing field [Office development in Visual Studio]
- optional parameters [Office development in Visual Studio]
- parameters [Office development in Visual Studio], optional
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: e8684ad4b9429a5499660ef4ad6fdd8133dccaa5
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "90843001"
---
# <a name="optional-parameters-in-office-solutions"></a>Необязательные параметры в решениях Office
  Многие методы в объектных моделях приложений Microsoft Office принимают необязательные параметры. При использовании Visual Basic для разработки решения Office в Visual Studio значение для необязательных параметров передавать не нужно, так как для каждого отсутствующего параметра автоматически используется значение по умолчанию. В большинстве случаев в проектах Visual C# также можно опускать необязательные параметры. Однако нельзя опустить необязательные параметры **ref** `ThisDocument` класса в проектах уровня документа Word.

 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]

 Дополнительные сведения о работе с необязательными параметрами в проектах Visual C# и Visual Basic см. в разделе [именованные и необязательные аргументы &#40;руководство по программированию C&#35;&#41;](/dotnet/csharp/programming-guide/classes-and-structs/named-and-optional-arguments) и [необязательные параметры &#40;](/dotnet/visual-basic/programming-guide/language-features/procedures/optional-parameters)Visual Basic&#41;.

> [!NOTE]
> В более ранних версиях Visual Studio в проектах Visual C# необходимо было передавать значение для каждого необязательного параметра. Для удобства эти проекты содержат глобальную переменную с именем `missing`, которую можно передавать в необязательный параметр, если для него нужно использовать значение по умолчанию. Проекты Visual C# для Office в Visual Studio по-прежнему содержат `missing` переменную, но обычно ее не нужно использовать при разработке решений Office в [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)] , за исключением случаев, когда вызываются методы с необязательными параметрами **ref** в `ThisDocument` классе в проектах уровня документа для Word.

## <a name="example-in-excel"></a>Пример в Excel
 Метод <xref:Microsoft.Office.Tools.Excel.Worksheet.CheckSpelling%2A> имеет много необязательных параметров. Как показано в следующем примере кода, для одних параметров можно указать значения, а для других — принять значение по умолчанию. В этом примере требуется проект на уровне документа с классом листа под именем `Sheet1`.

 [!code-csharp[Trin_VstrefGeneralExcel#1](../vsto/codesnippet/CSharp/excelworkbook1/Sheet1.cs#1)]
 [!code-vb[Trin_VstrefGeneralExcel#1](../vsto/codesnippet/VisualBasic/excelworkbook1/Sheet1.vb#1)]

## <a name="example-in-word"></a>Пример в Word
 Метод <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> имеет много необязательных параметров. Как показано в следующем примере кода, для одних параметров можно указать значения, а для других — принять значение по умолчанию.

 [!code-vb[Trin_VstrefGeneralWord#1](../vsto/codesnippet/VisualBasic/worddocument1/ThisDocument.vb#1)]
 [!code-csharp[Trin_VstrefGeneralWord#1](../vsto/codesnippet/CSharp/worddocument1/ThisDocument.cs#1)]

## <a name="use-optional-parameters-of-methods-in-the-thisdocument-class-in-visual-c-document-level-projects-for-word"></a>Использование необязательных параметров методов в классе ThisDocument в проектах уровня документа Visual C# для Word
 Объектная модель Word содержит множество методов с необязательными параметрами **ref** , которые принимают <xref:System.Object> значения. Однако нельзя опустить необязательные параметры **ref** методов созданного `ThisDocument` класса в проектах уровня документа Visual C# для Word. Visual C# позволяет опускать необязательные параметры **ref** только для методов интерфейсов, а не классов. Например, следующий пример кода не компилируется, так как нельзя опустить необязательные параметры **ref** <xref:Microsoft.Office.Tools.Word.DocumentBase.CheckSpelling%2A> метода `ThisDocument` класса.

 [!code-csharp[Trin_VstrefGeneralWord#3](../vsto/codesnippet/CSharp/worddocument1/ThisDocument.cs#3)]

 При вызове методов класса `ThisDocument` следуйте приведенным ниже рекомендациям:

- Чтобы принять значение по умолчанию для необязательного параметра **ref** , передайте `missing` переменную в параметр. Переменная `missing` автоматически определяется в проектах Visual C# для Office, и ей назначается значение <xref:System.Type.Missing> в созданном коде проекта.

- Чтобы указать собственное значение для необязательного параметра **ref** , объявите объект, назначенный значению, которое необходимо указать, а затем передайте объект в параметр.

  В следующем примере кода показано, как вызвать <xref:Microsoft.Office.Tools.Word.DocumentBase.CheckSpelling%2A> метод, указав значение для параметра *игнореупперкасе* и приняв значение по умолчанию для других параметров.

  [!code-csharp[Trin_VstrefGeneralWord#4](../vsto/codesnippet/CSharp/worddocument1/ThisDocument.cs#4)]

  Если вы хотите написать код, который опускает необязательные параметры **ref** метода в `ThisDocument` классе, можно также вызвать тот же метод для <xref:Microsoft.Office.Interop.Word.Document> объекта, возвращаемого <xref:Microsoft.Office.Tools.Word.Document.InnerObject%2A> свойством, и опустить параметры из этого метода. Это можно сделать, так как <xref:Microsoft.Office.Interop.Word.Document> — интерфейс, а не класс.

  [!code-csharp[Trin_VstrefGeneralWord#5](../vsto/codesnippet/CSharp/worddocument1/ThisDocument.cs#5)]

  Дополнительные сведения о параметрах типа Value и Reference см. в статьях [Передача аргументов по значению и по ссылке &#40;Visual Basic&#41;](/dotnet/visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference) (для Visual Basic) и [Передача параметров &#40;&#35; руководство по программированию с ](/dotnet/csharp/programming-guide/classes-and-structs/passing-parameters)&#41;.

## <a name="see-also"></a>См. также
- [Разработка решений Office](../vsto/developing-office-solutions.md)
- [Написание кода в решениях Office](../vsto/writing-code-in-office-solutions.md)
