---
title: Решения по проектированию системы управления версиями | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], design decisions
ms.assetid: 5f60ec1a-5a74-4362-8293-817a4dd73872
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9c36bb2b50a72a52aeaeb7712f4ed711845b5e6d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "80705245"
---
# <a name="source-control-design-decisions"></a>Проектные решения для системы управления версиями
При реализации системы управления версиями следует рассматривать следующие решения по проектированию.

## <a name="will-information-be-shared-or-private"></a>Будут ли сведения общими или частными?
 Наиболее важным решением при проектировании является то, какие данные можно совместно использовать и что является частным. Например, список файлов для проекта является общим, но в этом списке файлов некоторым пользователям может потребоваться использовать частные файлы. Параметры компилятора являются общими, но начальный проект обычно является частным. Параметры либо полностью являются общими, либо общими с переопределением, либо исключительно частными. Закрытые элементы, например файлы пользовательских параметров решения (SUO), не возвращаются в [!INCLUDE[vsvss](../../extensibility/includes/vsvss_md.md)] . Не забудьте сохранить личные сведения в закрытых файлах, таких как suo-файл или конкретный закрытый файл, например файл csproj. User для Visual C# или файл. vbproj. User для Visual Basic.

 Это решение является неинклюзивным и может быть принято для каждого элемента.

## <a name="will-the-project-include-special-files"></a>Будет ли проект включать специальные файлы?
 Еще одним важным решением при проектировании является то, использует ли структура проекта специальные файлы. Специальные файлы — это скрытые файлы, которые лежат в основе файлов, видимых в обозреватель решений и в диалоговых окнах возврата и извлечения. При использовании специальных файлов следуйте приведенным ниже рекомендациям.

1. Не связывайте специальные файлы с корневым узлом проекта, т. е. с самим файлом проекта. Файл проекта должен быть одним файлом.

2. При добавлении, удалении или переименовании специальных файлов в проекте <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2> должны запускаться соответствующие события с установленным флагом, указывающим, что файлы являются специальными файлами. Эти события вызываются средой в ответ на проект, вызывающий соответствующие <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2> методы.

3. Когда проект или редактор вызывает <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> файл, Специальные файлы, связанные с этим файлом, не изменяются автоматически. Передайте специальные файлы вместе с родительским файлом. Среда обнаружит связь между всеми передаваемыми файлами и соответствующим образом скрывает специальные файлы в пользовательском интерфейсе извлечения.

## <a name="see-also"></a>См. также раздел
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>
- [Поддержка системы управления версиями](../../extensibility/internals/supporting-source-control.md)
