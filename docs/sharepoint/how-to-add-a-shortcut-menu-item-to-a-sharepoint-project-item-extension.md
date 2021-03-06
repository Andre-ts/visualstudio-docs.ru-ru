---
title: Добавить пункт контекстного меню в расширение элемента проекта SharePoint
titleSuffix: ''
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- project items [SharePoint development in Visual Studio], extending
- SharePoint project items, extending
- SharePoint development in Visual Studio, extending project items
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: d3c0627849df12b98ddc16f54317faf952cb41f6
ms.sourcegitcommit: 9d2829dc30b6917e89762d602022915f1ca49089
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2020
ms.locfileid: "91585866"
---
# <a name="how-to-add-a-shortcut-menu-item-to-a-sharepoint-project-item-extension"></a>Как добавить пункт контекстного меню в расширение элемента проекта SharePoint
  Элемент контекстного меню можно добавить в существующий элемент проекта SharePoint с помощью расширения элемента проекта. Этот пункт меню появляется, когда пользователь щелкает правой кнопкой мыши элемент проекта в **Обозреватель решений**.

 В следующих шагах предполагается, что вы уже создали расширение элемента проекта. Дополнительные сведения см. [в разделе инструкции. Создание расширения элемента проекта SharePoint](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md).

### <a name="to-add-a-shortcut-menu-item-in-a-project-item-extension"></a>Добавление пункта контекстного меню в расширение элемента проекта

1. В <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension.Initialize%2A> методе <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> реализации обработайте <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemMenuItemsRequested> событие параметра *прожектитемтипе* .

2. В обработчике событий для <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemMenuItemsRequested> события добавьте новый <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> объект в <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemMenuItemsRequestedEventArgs.ViewMenuItems%2A> <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemMenuItemsRequestedEventArgs.AddMenuItems%2A> коллекцию или параметра аргументов события.

3. В <xref:Microsoft.VisualStudio.SharePoint.IMenuItem.Click> обработчике событий для нового <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> объекта выполните задачи, которые необходимо выполнить, когда пользователь щелкнет нужный пункт контекстного меню.

## <a name="example"></a>Пример
 В следующем примере кода показано, как добавить пункт контекстного меню в элемент проекта приемника событий. Когда пользователь щелкает правой кнопкой мыши элемент проекта в **Обозреватель решений** и щелкает пункт меню **запись сообщения в окно вывода** , Visual Studio отображает сообщение в окне **вывод** .

 [!code-vb[SPExtensibility.ProjectItemExtension.MenuAndProperty#1](../sharepoint/codesnippet/VisualBasic/projectitemmenuandproperty/extension/projectitemextensionmenu.vb#1)]
 [!code-csharp[SPExtensibility.ProjectItemExtension.MenuAndProperty#1](../sharepoint/codesnippet/CSharp/projectitemmenuandproperty/extension/projectitemextensionmenu.cs#1)]

 В этом примере используется служба проекта SharePoint для записи сообщения в окно **вывода** . Дополнительные сведения см. [в статье Использование службы проектов SharePoint](../sharepoint/using-the-sharepoint-project-service.md).

## <a name="compile-the-code"></a>Компиляция кода
 Для этого примера требуется проект библиотеки классов со ссылками на следующие сборки:

- Microsoft. VisualStudio. SharePoint

- System.ComponentModel.Composition

## <a name="deploy-the-extension"></a>Развертывание расширения
 Чтобы развернуть расширение, создайте [!include[vsprvs](../sharepoint/includes/vsprvs-md.md)] пакет расширения (VSIX) для сборки и всех остальных файлов, которые требуется распространить с расширением. Дополнительные сведения см. [в статье Развертывание расширений для инструментов SharePoint в Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).

## <a name="see-also"></a>См. также
- [Как создать расширение элемента проекта SharePoint](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)
- [Как добавить свойство в расширение элемента проекта SharePoint](../sharepoint/how-to-add-a-property-to-a-sharepoint-project-item-extension.md)
- [Расширение элементов проектов SharePoint](../sharepoint/extending-sharepoint-project-items.md)
- [Пошаговое руководство. расширение типа элемента проекта SharePoint](../sharepoint/walkthrough-extending-a-sharepoint-project-item-type.md)
