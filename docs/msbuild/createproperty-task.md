---
title: Задача CreateProperty | Документы Майкрософт
description: Используйте задачу CreateProperty MSBuild для заполнения свойств передаваемыми значениями, что позволяет копировать значения из одного свойства или строки в другое свойство или строку.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#CreateProperty
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- CreateProperty task [MSBuild]
- MSBuild, CreateProperty task
ms.assetid: fbc31a88-62d4-43d2-b739-68ef3fac38f5
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7d7dd8d7f5a50998832a8fac6f47bf66e9a6bbe9
ms.sourcegitcommit: bd9417123c6ef67aa2215307ba5eeec511e43e02
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2020
ms.locfileid: "92796191"
---
# <a name="createproperty-task"></a>CreateProperty - задача

Заполняет свойства переданными значениями. Это позволяет копировать значения из одного свойства или строки в другое свойство или строку.

## <a name="attributes"></a>Атрибуты

В следующей таблице приводятся параметры задачи `CreateProperty` .

| Параметр | Описание |
|------------------| - |
| `Value` | Необязательный выходной параметр `String`.<br /><br /> Указывает значение для копирования в новое свойство. |
| `ValueSetByTask` | Необязательный выходной параметр `String`.<br /><br /> Содержит то же значение, что и параметр `Value`. Используйте этот параметр только в том случае, если вы не хотите, чтобы MSBuild задавал выходное свойство при пропуске вложенного целевого объекта из-за актуальных выходных данных. |

## <a name="remarks"></a>Примечания

Помимо перечисленных выше параметров, эта задача наследует параметры от класса <xref:Microsoft.Build.Tasks.TaskExtension>, который, в свою очередь, наследует от класса <xref:Microsoft.Build.Utilities.Task>. Список этих дополнительных параметров и их описания см. в статье [Базовый класс TaskExtension](../msbuild/taskextension-base-class.md).

## <a name="example"></a>Пример

Следующий пример использует задачу `CreateProperty`, чтобы создать свойство `NewFile` с помощью сочетания значений свойств `SourceFilename` и `SourceFileExtension`.

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">

    <PropertyGroup>
        <SourceFilename>Module1</SourceFilename>
        <SourceFileExtension>vb</SourceFileExtension>
    </PropertyGroup>

    <Target Name="CreateProperties">

        <CreateProperty
            Value="$(SourceFilename).$(SourceFileExtension)">
            <Output
                TaskParameter="Value"
                PropertyName="NewFile" />
        </CreateProperty>

    </Target>

</Project>
```

После запуска проекта значение свойства `NewFile` равно *Module1.vb* .

## <a name="see-also"></a>См. также

- [Справочные сведения о задачах](../msbuild/msbuild-task-reference.md)
- [Задачи](../msbuild/msbuild-tasks.md)
