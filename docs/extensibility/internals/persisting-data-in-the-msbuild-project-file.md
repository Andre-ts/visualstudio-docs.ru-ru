---
title: Сохранение данных в файле проекта MSBuild | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- project files, persisting data in
ms.assetid: 6a920cb7-453d-4ffd-af1c-6f3084bd03f7
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e83526007f676ae94ddce57936b627bcb4308c2a
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "80706698"
---
# <a name="persisting-data-in-the-msbuild-project-file"></a>Сохранение данных в файле проекта MSBuild
Подтипу проекта может потребоваться сохранить данные подтипа в файле проекта для последующего использования. Подтип проекта использует сохранение файлов проекта для удовлетворения следующих требований:

1. Сохранение данных, используемых в процессе сборки проекта. (Дополнительные сведения о Microsoft Build Engine см. в разделе [MSBuild](../../msbuild/msbuild.md).) Сведения, относящиеся к сборке, могут быть:

    1. Независимые от конфигурации данные. То есть данные, хранящиеся в элементах MSBuild с пустыми или отсутствующими условиями.

    2. Зависящие от конфигурации данные. То есть данные, хранящиеся в элементах MSBuild, которые были условы для конкретной конфигурации проекта. Например:

        ```
        <PropertyGroup Condition=" '$(Configuration)' == 'Debug' ">
        ```

2. Сохранение данных, не относящихся к сборке. Эти данные могут быть выражены в формате XML произвольной формы, который не проверяется на соответствие схеме XML.

    1. Независимые от конфигурации данные.

    2. Зависящие от конфигурации данные.

## <a name="persisting-build-related-information"></a>Сохранение информации, связанной с построением
 Сохранение данных, полезных для сборки проекта, осуществляется с помощью MSBuild. Система MSBuild хранит главную таблицу сведений, связанных с построением. Подтипы проектов отвечают за доступ к этим данным для получения и задания значений свойств. Подтипы проектов также могут дополнять таблицу данных, связанную с сборкой, путем добавления дополнительных свойств для сохранения и удаления свойств, чтобы они не сохранялись.

 Чтобы изменить данные MSBuild, подтип проекта отвечает за извлечение объекта свойства MSBuild из базовой системы проектов с помощью <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage> . <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage> — Это интерфейс, реализованный в основной системе проектов и выполняющий статистическую обработку запросов подтипов проекта, выполняя `QueryInterface` .

 В следующей процедуре описаны действия по удалению свойства с помощью <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage> .

#### <a name="to-remove-a-property-from-an-msbuild-project-file"></a>Удаление свойства из файла проекта MSBuild

1. Вызов `QueryInterface` для <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage> подтипа проекта.

2. Вызовите метод с параметром, <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.RemoveProperty%2A> указав `pszPropName` свойство, которое необходимо удалить.

### <a name="persisting-non-build-related-information"></a>Сохранение сведений, не связанных с построением
 Сохранение данных в файлах проекта, не имеющих значения для сборки, осуществляется с помощью <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment> .

 Можно реализовать <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment> для основного `project subtype aggregator` объекта, `project subtype project configuration` объекта или и того и другого.

 В следующих точках представлены основные понятия, связанные с сохранением информации, не связанной с построением.

- Базовый проект вызывает метод основного подтипа проекта (то есть самый внешний подтип проекта) для загрузки и сохранения независимых от конфигурации данных, а также вызывает объекты конфигурации проекта подтипа проекта для загрузки или сохранения зависящих от конфигурации данных.

- Базовый проект вызывает методы <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment> несколько раз для каждого уровня статистической обработки подтипа проекта и передает идентификатор GUID для каждого уровня.

- Базовый проект передает или получает фрагмент XML, выделенный для конкретного подтипа проекта, и использует этот механизм как способ сохранения состояния между уровнями статистической обработки.

- Базовый проект вызывает реализацию реализации самого внешнего подтипа проекта, <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment> передавая идентификатор GUID. Если идентификатор GUID принадлежит самому внешнему подтипу проекта, он обрабатывает сам вызов. в противном случае он делегирует вызов внутреннему подтипу проекта и т. д., пока не будет найден подтип проекта, соответствующий этому идентификатору GUID.

- Подтип проекта также может изменить фрагмент XML до или после того, как он делегирует вызов внутреннему подтипу проекта. В следующем примере показан фрагмент из файла проекта, где имя файла, содержащего свойства, относящиеся к подтипу проекта, передается в этот подтип проекта.

    ```
    <ProjectExtensions>
        <VisualStudio>
          <FlavorProperties GUID="{<FlavorGUID>}">
            <FlavorProject TestFileFolder="TestFile" />
          </FlavorProperties>
        </VisualStudio>
      </ProjectExtensions>
    ```

## <a name="see-also"></a>См. также раздел
- [Подтипы проектов](../../extensibility/internals/project-subtypes.md)
