---
title: Проверка подтипов проекта во время выполнения | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- project subtypes
- check subtypes
ms.assetid: b87780ec-36a3-4e9a-9ee2-7abdc26db739
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f0d739a9f8734dd8941e3254d03364cbf4c77350
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "80698174"
---
# <a name="verify-subtypes-of-a-project-at-run-time"></a>Проверка подтипов проекта во время выполнения
Пакет VSPackage, зависящий от настраиваемого подтипа проекта, должен включать логику для поиска этого подтипа, чтобы он мог корректно завершить работу при отсутствии подтипа. В следующей процедуре показано, как проверить наличие указанного подтипа.

### <a name="to-verify-the-presence-of-a-subtype"></a>Проверка наличия подтипа

1. Получите иерархию проекта из объектов проекта и решения в виде <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> объекта, добавив следующий код в VSPackage.

    ```csharp
    EnvDTE.DTE dte;
    dte = (EnvDTE.DTE)Package.GetGlobalService(typeof(EnvDTE.DTE));

    EnvDTE.Project project;
    project = dte.Solution.Projects.Item(1);

    IVsSolution solution;
    solution = (IVsSolution)Package.GetGlobalService(typeof(SVsSolution));

    IVsHierarchy hierarchy;
    hierarchy = solution.GetProjectOfUniqueName(project.UniqueName);

    ```

2. Приведите иерархию к <xref:Microsoft.VisualStudio.Shell.Flavor.IVsAggregatableProjectCorrected> интерфейсу.

    ```csharp
    IVsAggregatableProjectCorrected AP;
    AP = hierarchy as IVsAggregatableProjectCorrected;

    ```

3. Получите список идентификаторов GUID типа проекта, вызвав <xref:Microsoft.VisualStudio.Shell.Flavor.IVsAggregatableProjectCorrected.GetAggregateProjectTypeGuids%2A> .

    ```csharp
    string projTypeGuids = AP.GetAggregateProjectTypeGuids().ToUpper();

    ```

4. Проверьте список идентификаторов GUID указанного подтипа.

    ```csharp
    // Replace the string "MyGUID" with the GUID of the subtype.
    string guidMySubtype = "MyGUID";
    if (projTypeGuids.IndexOf(guidMySubtype) > 0)
    {
        // The specified subtype is present.
    }
    ```

## <a name="see-also"></a>См. также раздел
- [Подтипы проектов](../extensibility/internals/project-subtypes.md)
- [Проект подтипов проекта](../extensibility/internals/project-subtypes-design.md)
- [Свойства и методы, расширенные по подтипам проектов](../extensibility/internals/properties-and-methods-extended-by-project-subtypes.md)
