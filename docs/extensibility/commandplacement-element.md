---
title: Элемент CommandPlacement | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- CommandPlacements element (VSCT XML schema)
- VSCT XML schema elements, CommandPlacements
ms.assetid: 2cbd7ac8-c55a-43d8-a26d-713b3d790016
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: dcf9f23b5e860b895baa4c2a7a783f2ee15fcc77
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "80739742"
---
# <a name="commandplacement-element"></a>CommandPlacement, элемент
Элемент CommandPlacement позволяет включать кнопки, группы и меню в более чем одну группу или меню. С помощью элемента CommandPlacement не нужно полностью переопределять эти элементы, чтобы изменить внешний вид пользовательского интерфейса.

 Дополнительные сведения см. в разделе [Создание многократно используемых групп кнопок](../extensibility/creating-reusable-groups-of-buttons.md).

## <a name="syntax"></a>Синтаксис

```
<CommandPlacement guid="guidMyCommandSet" id="MyCommand" priority="0x001" >
  <Parent>... </Parent>
</CommandPlacement>
```

## <a name="attributes-and-elements"></a>Элементы и атрибуты
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

|Атрибут|Описание|
|---------------|-----------------|
|guid|Обязательный. Идентификатор GUID набора команд, как определено в [элементе Symbols](../extensibility/symbols-element.md).|
|идентификатор|Обязательный. Идентификатор меню, группы или команды, которые необходимо разместить, как определено в `Symbols Element` .|
|priority|Обязательный. Определяет визуальную позицию элемента в его родительском элементе.|
|Условие|Необязательный элемент. См. раздел [Conditional ааттрибутес](../extensibility/vsct-xml-schema-conditional-attributes.md).|

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|Parent|Обязательный. Меню или группу, в которой размещен элемент, который необходимо разместить.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[CommandPlacements, элемент](../extensibility/commandplacements-element.md)|Задает группы элементов CommandPlacements и CommandPlacement.|

## <a name="example"></a>Пример

```
<CommandPlacements>
  <CommandPlacement guid="guidWidgetPackage" id="cmdidInsertOptions"
    priority="0x0300">
    <Parent guid="cmdGuidWidgetCommands" id="menuIDEditWidget"/>
  </CommandPlacement>
</CommandPlacements>
```

## <a name="see-also"></a>См. также раздел
- [CommandPlacements, элемент](../extensibility/commandplacements-element.md)
- [Файлы таблицы команд Visual Studio (. vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
