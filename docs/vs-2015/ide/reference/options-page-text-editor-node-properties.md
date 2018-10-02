---
title: Страница "Параметры", свойства узла "Текстовый редактор" | Документы Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tools Options settings, Text Editor node properties
- automation [Visual Studio], controlling Tools Options
ms.assetid: 19438302-0677-4f4d-9720-5667e6a22ab2
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 945b1b41abf44c8525677bfb332afdf9f6f7788f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47564285"
---
# <a name="options-page-text-editor-node-properties"></a>Страница "Параметры"", свойства узла "Текстовый редактор"
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [страница "Параметры", свойства узла текстового редактора](https://docs.microsoft.com/visualstudio/ide/reference/options-page-text-editor-node-properties).  
  
  
В этом документе описываются некоторые из страниц (или коллекций свойств) диалогового окна **Параметры**, связанных с категорией **Текстовый редактор** — `DTE.Properties("TextEditor", <Property Page>)`. Заголовок каждого из подразделов представляет собой вызов, используемый для доступа к коллекции `Properties`, а таблицы содержат списки свойств в коллекции.  
  
 Макросы Visual Basic в разделе [Управление параметрами](http://msdn.microsoft.com/library/a09ed242-7494-4cde-bbd1-7a8ec617965d) демонстрируют, как отображать текущие параметры и их значения для каждой страницы диалогового окна **Параметры**.  
  
## <a name="general"></a>Общие  
 `DTE.Properties("TextEditor", "General")`  
  
|Имя элемента свойства|Значение|Описание|  
|------------------------|-----------|-----------------|  
|GoToAnchorAfterEscape|Get/Set (Boolean)|Если задано значение `True`, то при нажатии кнопки "escape" во время выделения точка вставки переместится туда, откуда началось выделение. При значении `False` точка вставки переместится в другой конец выделения.|  
|DragNDropTextEditing|Get/Set (Boolean)|Определяет, можно ли перетащить выбранный блок текста из одного места документа в другое для выполнения операций копирования, вставки или вырезания.|  
|HorizontalScrollBar|Get/Set (Boolean)|Определяет, будет ли отображаться горизонтальная полоса прокрутки окна редактора.|  
|VerticalScrollBar|Get/Set (Boolean)|Определяет, будет ли отображаться вертикальная полоса прокрутки окна редактора.|  
|SelectionMargin|Get/Set (Boolean)|Определяет, есть ли место слева от текстовой панели для выполнения специальных операций выбора, отображения значка точки останова и так далее.|  
|MarginIndicatorBar|Get/Set (Boolean)|Определяет, есть ли вертикальная полоса, разделяющая левую сторону текстовой панели от основной ее части.|  
|UndoCaretActions|Get/Set (Boolean)|Если `True`. операции отмены включают перемещение точки вставки, команды выбора и так далее в дополнение к действиям редактирования, меняющим содержимое буфера.|  
|AutoDelimiterHighlighting|Get/Set (Boolean)|Определяет, должен ли редактор выделять открывающий разделитель цветом, когда пользователь вводит соответствующий закрывающий разделитель. Независимо от значения этого свойства, открывающий разделитель всегда выделяется полужирным шрифтом.|  
|EditorEmulation|Get/Set (Enum)||  
|DetectUTF8WithoutSignature|Get/Set (Boolean)|Определяет, используется ли в файле кодировка UTF-8, когда у файла отсутствует сигнатура кодировки.|  
|TrackChanges|Get/Set (Boolean)||  
  
## <a name="plain-text"></a>Обычный текст  
 `DTE.Properties("TextEditor", "PlainText")`  
  
 Параметры редактора `PlainText` влияют на настройки редактора при редактировании текстовых файлов. Для каждого языка программирования и пакета [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] доступны определенные параметры **Текстового редактора**. Например, для просмотра или изменения параметров редактора [!INCLUDE[csprcs](../../includes/csprcs-md.md)] используйте `DTE.Properties("TextEditor", "CSharp") or DTE.Properties("TextEditor", "CSharp-Specific")`. Для параметров редактора **Скрипт SQL** используйте `DTE.Properties("TextEditor", "SQL ")`.  
  
|Имя элемента свойства|Значение|Описание|  
|------------------------|-----------|-----------------|  
|AutoListMembers|Get/Set (Boolean)|Определяет, должен ли автоматически открываться доступный список членов, когда пользователь вводит точку после ссылки на переменную.|  
|AutoListParams|Get/Set (Boolean)|Определяет, должно ли автоматически отображаться описание списка аргументов, когда пользователь вводит "(" после имени функции.|  
|HideAdvancedMembers|Get/Set (Boolean)|Определяет, должен ли оператор завершения выводить список всех членов или только часто используемых.|  
|VirtualSpace|Get/Set (Boolean)|Определяет, должны ли пробелы отображаться графически. Если этому свойству присвоить значение `true`, то элементу свойства `WordWrap` (в этом списке) будет присвоено значение `false`.|  
|WordWrap|Get/Set (Boolean)|Определяет, будут ли в представлении отображаться длинные строки с переносом на границах слов. Если этому свойству присвоить значение `true`, то элементу свойства `VirtualSpace` (в этом списке) будет присвоено значение `false`.|  
|WordWrapGlyphs|Get/Set (Boolean)|Отображает глиф в конце строки; это указывает, что строка переносится на следующую строку.|  
|EnableLeftClickForURLs|Get/Set (Boolean)|Определяет, должен ли редактор подчеркивать URL-адреса и позволять переходить по данному URL-адресу посредством щелчка левой кнопкой мыши, сделанного в зарегистрированном системном веб-браузере.|  
|IndentStyle|Get/Set (<xref:EnvDTE.vsIndentStyle>)|Определяет стиль отступов.: Default, Smart или None.|  
|TabSize|Get/Set (Long)|Представляет величину шага табуляции в знаках. Не допускается использовать целое число вне диапазона от 1 до 60 (включительно).|  
|InsertTabs|Get/Set (Boolean)|`True` означает использование знаков табуляции в отступах.|  
|IndentSize|Get/Set (Long)|Представляет величину одного уровня отступа в знаках. Не допускается использовать целочисленное значение вне диапазона от 1 до 60 (включительно).|  
|ShowLineNumbers|Get/Set (Boolean)|Определяет, должны ли отображаться номера строк вдоль левого поля.|  
|ShowNavigationBar|Get/Set (Boolean)|Определяет, появляются ли раскрывающиеся списки и кнопки вверху окон редактора.|  
|CutCopyBlankLines|Get/Set (Boolean)|Вырезает или копирует пустые строки при их выборе.|  
  
## <a name="see-also"></a>См. также  
 [Управление параметрами](http://msdn.microsoft.com/library/a09ed242-7494-4cde-bbd1-7a8ec617965d)   
 [Определение имен элементов свойств на страницах параметров](http://msdn.microsoft.com/library/d450422d-47c7-4eeb-9f9f-3286264bc5aa)   
 [Страница "Параметры", свойства узла "Среда"](../../ide/reference/options-page-environment-node-properties.md)   
 [Страница "Параметры", свойства узла "Шрифты и цвета"](../../ide/reference/options-page-fonts-and-colors-node-properties.md)


