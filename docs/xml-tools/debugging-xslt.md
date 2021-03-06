---
title: Способы отладки кода XSLT
ms.date: 03/05/2019
ms.topic: overview
author: TerryGLee
ms.author: tglee
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: d8e3885aa895cec5ed080b7a8b4d22522d2e9edf
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "85815621"
---
# <a name="debugging-xslt"></a>Отладка XSLT

В Visual Studio можно выполнять отладку кода XSLT. Отладчик XSLT поддерживает задание точек останова, просмотр состояний выполнения XSLT и т. д. Его можно использовать для отладки таблицы стилей XSLT или приложений XSLT.

Код можно выполнять по одной строке, делая шаг с входом, шаг с пропуском или шаг с выходом. Команды для использования возможностей пошагового прохождения кода аналогичны в отладчике XSLT и в других отладчиках Visual Studio.

При запуске отладки отладчик XSLT открывает окна, в которых отображается входной документ и выход XSLT.

> [!NOTE]
> Отладчик XSLT доступен только в выпусках Visual Studio Professional и Enterprise.

## <a name="debug-from-the-xml-editor"></a>Отладка из редактора XML

Отладчик можно запустить при наличии таблицы стилей или входного XML-файла, открытого в редакторе. Это позволяет выполнять отладку по мере создания таблицы стилей.

1. Откройте таблицу стилей или XML-файл в Visual Studio.

1. Выберите **Начать отладку XSLT** из меню **XML** или нажмите клавиши **ALT**+**F5**.

## <a name="debug-from-an-app-that-uses-xslt"></a>Отладка из приложения, использующего XSLT

При отладке приложения можно сделать шаг с входом в код XSLT. Если нажать клавишу **F11** при вызове <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A?displayProperty=fullName>, отладчик может войти в код XSLT.

> [!NOTE]
> Выполнение шага со входом в код XSLT из класса <xref:System.Xml.Xsl.XslTransform> не поддерживается. Класс <xref:System.Xml.Xsl.XslCompiledTransform> является единственным обработчиком XSLT, поддерживающим вход в код XSLT при отладке.

### <a name="to-start-debugging-an-xslt-application"></a>Начало отладки приложения XSLT

1. При создании объекта <xref:System.Xml.Xsl.XslCompiledTransform> устанавливайте в своем коде параметр `enableDebug` в значение `true`. Это заставляет обработчик XSLT создавать отладочные данные при компиляции кода.

1. Нажмите клавишу **F11**, чтобы войти в код XSLT.

   Таблица стилей XSLT загружается в новое окно документа и запускается XSLT-отладчик.

   Можно также добавить точку останова в таблицу стилей и запустить приложение.

### <a name="example"></a>Пример

Ниже приведен пример программы C# XSLT. Он показывает, как включить отладку XSLT.

```csharp
using System;
using System.IO;
using System.Xml;
using System.Xml.Xsl;

namespace ConsoleApplication
{
  class Program
  {
    private const string sourceFile = @"c:\data\xsl_files\books.xml";
    private const string stylesheet = @"c:\data\xsl_files\below-average.xsl";
    private const string outputFile = @"c:\data\xsl_files\output.xml";

    static void Main(string[] args)
    {
      // Enable XSLT debugging.
      XslCompiledTransform xslt = new XslCompiledTransform(true);

      // Compile the style sheet.
      xslt.Load(stylesheet);

      // Execute the XSLT transform.
      FileStream outputStream = new FileStream(outputFile, FileMode.Append);
      xslt.Transform(sourceFile, null, outputStream);
    }
  }
}
```

## <a name="xslt-profiler"></a>Профилировщик XSLT

[Профилировщик XSLT](../xml-tools/xslt-profiler.md) — это средство, которое позволяет разработчикам измерять, оценивать и устранять в XSLT-коде проблемы, связанные с производительностью, посредством создания подробных отчетов о производительности XSLT. Дополнительные сведения см. в статье о [профилировщике XSLT](../xml-tools/xslt-profiler.md).

## <a name="see-also"></a>См. также

- [Пошаговое руководство: Отладка таблицы стилей XSLT](../xml-tools/walkthrough-debug-an-xslt-style-sheet.md)
- [Знакомство с отладчиком Visual Studio](../debugger/debugger-feature-tour.md)
- [Общие сведения об отладке: точки останова](../debugger/using-breakpoints.md)
