---
title: Практические руководства. Поддержка структурирования в языковой службе прежних версий | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], collapse to definitions command
- language services, supporting Collapse to Definitions command
- hidden text, Collapse to Definitions command
ms.assetid: bb6e74c3-93e4-4ef7-afc7-1c9b342f083b
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 28396d513c83ed83e2769e75a6020a98b10251b4
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "80707918"
---
# <a name="how-to-support-outlining-in-a-legacy-language-service"></a>Практические руководства. Поддержка структурирования в языковой службе прежних версий
Структурирование используется для разворачивания или сворачивания различных областей текста. Способ структурирования можно определить по-разному на разных языках. Дополнительные сведения см. в разделе [Структура](../../ide/outlining.md).

 Устаревшие языковые службы реализуются как часть VSPackage, но более новым способом реализации функций языковой службы является использование расширений MEF. Дополнительные сведения о новом способе реализации структуры см. в разделе [Пошаговое руководство. структурирование](../../extensibility/walkthrough-outlining.md).

> [!NOTE]
> Рекомендуется как можно скорее начать использовать новый API редактора. Это улучшит производительность языковой службы и позволит использовать новые функции редактора.

 Ниже показано, как обеспечить поддержку этой команды для языковой службы.

## <a name="to-support-outlining"></a>Поддержка структурирования

1. Реализуйте <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningCapableLanguage> для своего объекта языковой службы.

2. Вызовите <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession.AddOutlineRegions%2A> для текущего объекта сеанса структуризации, чтобы добавить новые области структуры.

## <a name="robust-programming"></a>Отказоустойчивость
 Когда пользователь выбирает пункт **Свернуть в определения** в меню **Структура** , интегрированная среда разработки обращается к <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningCapableLanguage.CollapseToDefinitions%2A> языковой службе.

 При вызове этого метода интегрированная среда разработки передает <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines> указатель (указатель на текстовый буфер) и <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession> (указатель на текущий сеанс структуры).

 Метод можно вызвать <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession.AddOutlineRegions%2A> для нескольких областей структуры, указав эти регионы в `rgOutlnReg` параметре. `rgOutlnReg`Параметр является <xref:Microsoft.VisualStudio.TextManager.Interop.NewOutlineRegion> структурой. Этот процесс позволяет задавать различные характеристики скрытой области, например, разворачивается или сворачивается определенный регион.

> [!NOTE]
> Будьте внимательны, скрывая символы новой строки. Скрытый текст должен находиться от начала первой строки до последнего символа последней строки в разделе, в результате чего отображается итоговый символ новой строки.

## <a name="see-also"></a>См. также раздел
- [Как обеспечить поддержку скрытого текста в языковой службе прежних версий](../../extensibility/internals/how-to-provide-hidden-text-support-in-a-legacy-language-service.md)
- [Руководство. Предоставление расширенной поддержки структурирования в языковой службе прежних версий](../../extensibility/internals/how-to-provide-expanded-outlining-support-in-a-legacy-language-service.md)
