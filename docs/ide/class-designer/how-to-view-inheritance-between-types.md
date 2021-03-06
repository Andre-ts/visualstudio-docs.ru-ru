---
title: Практическое руководство. Просмотр отношения наследования между типами (конструктор классов)
ms.date: 11/04/2016
ms.topic: how-to
f1_keywords:
- vs.classdesigner.AssociationTypeNotFoundError
helpviewer_keywords:
- types [Visual Studio], inheritance
- types [Visual Studio], base
- types [Visual Studio], derived
ms.assetid: ea3f0ada-f53b-4fb1-9fb5-908286f5ec3e
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d5c35279421ad17e62afe707d62dbc879d03b384
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "85769905"
---
# <a name="how-to-view-inheritance-between-types-in-class-designer"></a>Практическое руководство. Просмотр наследования между типами в конструкторе классов

Отношение наследования (если оно существует) между базовым типом и его производными типами можно найти на диаграмме классов в **конструкторе классов**. Сведения о создании отношения наследования между двумя типами (если оно отсутствует) см. в статье [Практическое руководство. Создание наследования между типами](how-to-create-inheritance-between-types.md).

## <a name="to-find-the-base-type"></a>Поиск базового типа

1. На диаграмме классов щелкните тип, базовый класс или интерфейс которого следует показать.

2. В меню **Диаграмма классов** выберите пункт **Показать базовый класс** или **Показать базовые интерфейсы**.

     Базовый класс или интерфейс типа появится на диаграмме. Теперь будут показаны любые скрытые линии наследования между двумя фигурами.

Вы также можете щелкнуть правой кнопкой тип, базовый тип которого необходимо показать, и выбрать команду **Показать базовый класс** или **Показать базовые интерфейсы**.

## <a name="to-find-the-derived-types"></a>Поиск производных типов

1. На диаграмме классов щелкните тип, производные классы или интерфейсы которого следует показать.

2. В меню **Диаграмма классов** выберите пункт **Показать производные классы** или **Показать производные интерфейсы**.

     На диаграмме появятся производные классы или интерфейсы типа. Теперь будут показаны любые скрытые линии наследования между фигурами.

Вы также можете щелкнуть правой кнопкой тип, производные типы которого необходимо показать, и выбрать команду **Показать производные классы** или **Показать производные интерфейсы**.

## <a name="see-also"></a>См. также раздел

- [Практическое руководство. Создание ассоциаций между типами](how-to-create-associations-between-types.md)
- [Просмотр типов и отношений](designing-and-viewing-classes-and-types.md)
