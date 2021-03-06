---
title: Упаковка сведений о развертывании & в элементах проекта
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.Project.SafeControlEntries
- VS.SharePointTools.Project.ProjectOutputReference
- VS.SharePointTools.Project.FeatureProperties
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, safe controls
- project output references [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, feature properties
- SharePoint development in Visual Studio, project output references
- SharePoint development in Visual Studio, advanced packaging tools
- feature properties [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, feature receiver
- feature receiver [SharePoint development in Visual Studio]
- safe controls [SharePoint development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: db805c308fd245554824997b24236eb2e2d80e62
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "72984206"
---
# <a name="provide-packaging-and-deployment-information-in-project-items"></a>Предоставление сведений об упаковке и развертывании в элементах проекта
  Все элементы проектов SharePoint в [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] имеют свойства, которые можно использовать для предоставления дополнительных данных при развертывании проекта в SharePoint. Список содержит следующие свойства.

- Свойства функций

- Приемники компонентов

- Выходные ссылки проекта

- Записи безопасных элементов управления

  Эти свойства отображаются в окне **Свойства** .

## <a name="feature-properties"></a>Свойства функций
 Используйте свойство **Свойства компонента** , чтобы указать данные, используемые компонентом. Данные свойств компонентов — это набор значений (хранимых в виде пар "ключ-значение"), который входит в состав функции при развертывании в SharePoint. После развертывания функции значения свойств можно использовать в коде.

 При добавлении значения свойства компонента в элемент проекта это значение добавляется в манифест компонента элемента в виде элемента. Например, в проекте модели подключения к бизнес-данным (BDC) свойство компонента Моделфиленаме выглядит следующим образом:

```xml
<Property Key="ModelFileName" Value="BdcModel1\BdcModel1.bdcm" />
```

 После установки значения свойства компонента оно добавляется как элемент Феатурепроперти в файл *данных проекта.* Сведения о доступе к свойствам в SharePoint см. в разделе [класс спфеатурепропертиколлектион](/previous-versions/office/sharepoint-server/ms461895(v=office.15)).

 Одинаковые значения свойств функций из всех элементов проекта объединяются в манифесте компонента. Однако если два разных элемента проекта задают один и тот же ключ свойства компонента с несовпадающими значениями, возникает ошибка проверки.

 Чтобы добавить свойства функции непосредственно в файл компонента (*Feature*), вызовите [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] метод объектной модели SharePoint <xref:Microsoft.VisualStudio.SharePoint.Features.IPropertyCollection.Add%2A> . При использовании этого метода следует иметь в виду, что то же самое правило, относящееся к добавлению идентичных значений свойств компонента в свойствах функций, также применяется к свойствам, добавленным непосредственно в файл компонента.

## <a name="feature-receiver"></a>Приемник компонента
 Приемники компонентов — это код, который выполняется при возникновении определенных событий в функции, содержащей элемент проекта. Например, можно определить Приемники компонентов, которые выполняются при установке, активации или обновлении компонента. Одним из способов добавления приемника компонента является добавление его непосредственно в компонент, как описано в разделе [Пошаговое руководство. Добавление приемников событий компонентов](../sharepoint/walkthrough-add-feature-event-receivers.md). Другой способ — сослаться на имя класса приемника компонента и сборку в свойстве **приемника компонента** .

### <a name="direct-method"></a>Прямой метод
 При добавлении приемника компонента непосредственно в компонент файл кода помещается в узел **компонента** в Обозреватель решений. При построении решения SharePoint код компилируется в сборку и развертывается в SharePoint. По умолчанию классы **Assembly** и **получатель** свойств компонентов ссылаются на имя класса и сборку.

### <a name="reference-method"></a>Reference - метод
 Другим способом добавления приемника компонента является использование свойства **приемника компонента** элемента проекта для ссылки на сборку приемника компонента. Значение свойства приемника компонента имеет два вложенных свойства: **Assembly** и **имя класса**. Сборка должна использовать полное, строгое имя, а имя класса должно быть полным именем типа. Подробнее см. в статье [Сборки со строгими именами](/previous-versions/dotnet/netframework-4.0/wd40t7ad(v=vs.100)). После развертывания решения в SharePoint Эта функция использует приемник компонентов, на который указывает ссылка, для управления событиями функций.

 Во время сборки решения значения свойств приемника функций в компоненте и его проектах объединяются для задания атрибутов Рецеиверассембли и Рецеиверкласс элемента Feature в манифесте компонента в файле решения SharePoint (*. wsp*). Таким образом, если одновременно указаны значения свойств сборки и класса для элемента проекта и компонента, то значения элемента проекта и свойства компонента должны совпадать. Если значения не совпадают, вы получите ошибку проверки. Если требуется, чтобы элемент проекта ссылался на сборку приемника компонента, отличную от используемой ее функцией, переместите ее в другую функцию.

 При ссылке на сборку приемника компонента, которая еще не находится на сервере, необходимо также включить в пакет сам файл сборки. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] не добавляет его для вас. При развертывании компонента файл сборки копируется в систему [!INCLUDE[TLA#tla_gac](../sharepoint/includes/tlasharptla-gac-md.md)] или в папку Bin в физическом каталоге SharePoint. Дополнительные сведения см. в разделе инструкции. [Добавление и удаление дополнительных сборок](../sharepoint/how-to-add-and-remove-additional-assemblies.md).

 Дополнительные сведения о приемниках компонентов см. в статье [приемник событий](/previous-versions/office/developer/sharepoint-2007/bb862634(v=office.12)) компонентов и [события компонентов](/previous-versions/office/developer/sharepoint-2010/ms469501(v=office.14)).

## <a name="project-output-references"></a>Выходные ссылки проекта
 Свойство Выходные ссылки проекта определяет зависимость, например сборку, которую должен выполнить элемент проекта. Например, предположим, что решение содержит проект BDC и проект класса. Если проект BDC зависит от сборки, выводимой проектом класса, можно сослаться на сборку в свойстве выходных ссылок проекта проекта BDC. При упаковке проекта BDC зависимая сборка включается в пакет.

 Выходными ссылками проекта обычно являются сборки, но в некоторых случаях (например, проекты Silverlight) могут быть файлы других типов.

 Дополнительные сведения см. [в разделе инструкции. Добавление выходной ссылки на проект](../sharepoint/how-to-add-a-project-output-reference.md).

## <a name="safe-control-entries"></a>Записи безопасного контроля
 SharePoint предоставляет механизм безопасности, называемый записями безнадежных элементов управления, чтобы ограничить доступ недоверенных пользователей к определенным элементам управления. SharePoint позволяет недоверенным пользователям отправлять и создавать страницы ASPX на сервере SharePoint. Чтобы запретить этим пользователям добавлять ненадежный код на страницы ASPX, SharePoint ограничивает доступ к *защищенным элементам управления*. Безопасные элементы управления — это элементы управления ASPX и веб-части, которые обозначены как безопасные и могут использоваться любым пользователем на сайте. Дополнительные сведения см. в разделе [Шаг 4. Добавление веб-части в список безнадежных элементов управления](/previous-versions/office/developer/sharepoint-2007/ms581321(v=office.12)).

 Каждый элемент проекта SharePoint в [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] имеет свойство, называемое **записями безэлементного управления** , которое имеет два логических вложенных свойства: **Безопасность** и **безопасность в скрипте**. Свойство "Безопасно" определяет, возможен ли доступ к элементу управления для недоверенных пользователей. Свойство "безопасность в отношении скриптов" указывает, могут ли недоверенные пользователи просматривать и изменять свойства элемента управления.

 Ссылки на защищенные элементы управления указываются на основе сборки. Записи безэлементного управления добавляются в сборку проекта путем ввода их в свойстве **записей безопасного управления** элемента проекта. Однако можно также добавить записи безэлементного управления в сборку проекта на вкладке **Дополнительно** в **конструкторе пакетов** при добавлении в пакет дополнительной сборки. Дополнительные сведения см. [в разделе как пометить элементы управления как защищенные](../sharepoint/how-to-mark-controls-as-safe-controls.md) или [зарегистрировать сборку веб-части в качестве безопасного элемента управления](/previous-versions/office/developer/sharepoint2003/dd587360(v=office.11)).

### <a name="xml-entries-for-safe-controls"></a>Записи XML для безнадежных элементов управления
 При добавлении записи безопасного элемента управления в элемент проекта или сборку проекта ссылка записывается в манифест пакета в следующем формате:

```xml
<Assemblies>
    <Assembly Location="<assembly name>.dll"
      DeploymentTarget="<'GlobalAssemblyCache' or 'WebApplication'">>
        <SafeControls>
            <SafeControl Assembly="<assembly name>.dll" Namespace=
              "<SharePoint project name>" Safe="<true/false>"
                TypeName="<control name>"
                SafeAgainstScript="<true/false>" />
        </SafeControls>
    </Assembly>
</Assemblies>
```

## <a name="see-also"></a>См. также раздел
- [Упаковка и развертывание решений SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)
- [Использование модулей для включения файлов в решение](../sharepoint/using-modules-to-include-files-in-the-solution.md)
- [Расширение упаковки и развертывания SharePoint](../sharepoint/extending-sharepoint-packaging-and-deployment.md)
