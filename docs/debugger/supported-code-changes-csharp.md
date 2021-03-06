---
title: Поддерживаемые изменения кода (C# и Visual Basic) | Документация Майкрософт
ms.date: 10/11/2018
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Edit and Continue [C#], supported code changes
- Edit and Continue [Visual Basic], supported code changes
ms.assetid: c7a48ea9-5a7f-4328-a9d7-f0e76fac399d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: c480fad064cad602ea3fd19153d53f0276815d30
ms.sourcegitcommit: 5caad925ca0b5d136416144a279e984836d8f28c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2020
ms.locfileid: "89509423"
---
# <a name="supported-code-changes-c-and-visual-basic"></a>Поддерживаемые изменения кода (C# и Visual Basic)
Операция "Изменить и продолжить" обрабатывает большинство типов изменений, вносимых в код внутри тела метода. Однако большинство изменений за пределами тела метода и некоторые изменения в теле метода во время отладки применены быть не могут. Чтобы такие неподдерживаемые изменения вступили в силу, необходимо остановить отладку и заново запустить ее для обновленной версии кода.

## <a name="supported-changes-to-code"></a>Поддерживаемые изменения в коде

В следующей таблице показаны изменения, которые можно вносить в код на C# и Visual Basic во время сеанса отладки без его перезапуска.

|Элемент или компонент языка|Поддерживаемые операции редактирования|Ограничения|
|-|-|-|
|Типы|Добавление методов, полей, конструкторов, и т. п.|[Да](https://github.com/dotnet/roslyn/blob/master/docs/wiki/EnC-Supported-Edits.md)|
|Iterators|Добавить или изменить|Нет|
|Выражения async и await|Добавить или изменить|[Да](https://github.com/dotnet/roslyn/blob/master/docs/wiki/EnC-Supported-Edits.md)|
|Динамические объекты|Добавить или изменить|Нет|
|лямбда-выражения|Добавить или изменить|[Да](https://github.com/dotnet/roslyn/blob/master/docs/wiki/EnC-Supported-Edits.md)|
|Выражения LINQ|Добавить или изменить|[Аналогично лямбда-выражениям](https://github.com/dotnet/roslyn/blob/master/docs/wiki/EnC-Supported-Edits.md)|

> [!NOTE]
> Новые функции языка, например интерполяция строк и условные операторы со значением NULL, обычно поддерживаются в режиме "Изменить и продолжить". См. актуальные сведения о [правках, поддерживаемых в режиме "Изменить и продолжить"](https://github.com/dotnet/roslyn/blob/master/docs/wiki/EnC-Supported-Edits.md).

## <a name="unsupported-changes-to-code"></a>Неподдерживаемые изменения в коде
 Следующие изменения в коде C# и Visual Basic нельзя применять во время сеанса отладки.

- Изменения в текущем или любом другом активном операторе.

     К активным операторам относятся любые операторы внутри функций из стека вызовов, которые были вызваны для перехода к текущему оператору.

     Текущий оператор выделяется в окне исходного кода желтым фоном. Остальные активные операторы выделяются затенением и доступны только для чтения. Эти используемые по умолчанию цвета можно изменить в диалоговом окне **Параметры**.

- Неподдерживаемые изменения в коде для каждого элемента языка представлены в следующей таблице.

|Элемент или компонент языка|Неподдерживаемые операции редактирования|
|-|-|
|Все элементы кода|Переименование|
|Пространства имен|Add|
|Пространства имен, типы, члены|Удаление|
|Универсальные шаблоны|Добавить или изменить|
|Интерфейсы|Изменить|
|Типы|Добавление абстрактного или виртуального члена, добавление переопределения (см. [здесь](https://github.com/dotnet/roslyn/blob/master/docs/wiki/EnC-Supported-Edits.md))|
|Типы|Добавить деструктор|
|Участники|Изменение члена, ссылающегося на внедренный тип взаимодействия|
|Участники|Изменение статического члена после того, как к нему выполнено обращение из выполняемого кода|
|Члены (Visual Basic)|Изменение члена с помощью оператора On Error или Resume|
|Члены (Visual Basic)|Изменение члена, содержащего одно из следующих предложений запроса LINQ: Aggregate, Group By, Simple Join или Group Join|
|Методы|Изменение сигнатур|
|Методы|Преобразование абстрактного метода в неабстрактный путем добавления тела метода|
|Методы|Удаление тела метода|
|Атрибуты|Добавить или изменить|
|Свойства или события|Изменение параметра типа, базового типа, типа делегата или возвращаемого типа |
|Операторы или индексаторы|Изменение параметра типа, базового типа, типа делегата или возвращаемого типа |
|catch - блоки|Изменение, когда блок содержит активный оператор|
|Блоки try-catch-finally|Изменение, когда блок содержит активный оператор|
|использование операторов|Add|
|Асинхронные методы или лямбда-выражения|Изменение асинхронного метода или лямбда-выражения в проекте, предназначенном для .NET Framework 4 или более ранней версии (см. [здесь](https://github.com/dotnet/roslyn/blob/master/docs/wiki/EnC-Supported-Edits.md))|
|Iterators|Изменение итератора в проекте, предназначенном для .NET Framework 4 или более ранней версии (см. [здесь](https://github.com/dotnet/roslyn/blob/master/docs/wiki/EnC-Supported-Edits.md))|

## <a name="unsafe-code"></a>Небезопасный код
 В отношении изменений небезопасного кода действуют те же ограничения, что и для безопасного кода, а также следующее дополнительное ограничение: Режим "Изменить и продолжить" не поддерживает изменения в небезопасном коде, в котором осуществляется выход из метода, содержащего оператор `stackalloc`.

## <a name="unsupported-app-scenarios"></a>Неподдерживаемые сценарии в приложениях

К неподдерживаемым относятся платформы ASP.NET 5, Silverlight 5, Windows 8.1 и приложения для них.

> [!NOTE]
> Поддерживаются приложения UWP для Windows 10, а также приложения для архитектур x86 и x64, предназначенные для .NET Framework 4.6 или более поздних версий (.NET Framework поддерживается только для классических приложений).

## <a name="unsupported-scenarios"></a>Неподдерживаемые сценарии
 Режим "Изменить и продолжить" не доступен при следующих скриптах отладки:

- отладка в смешанном режиме (машинный код/управляемый код);

- отладка SQL;

- отладка дампа Dr. Watson;

- отладка вложенного приложения времени выполнения;

- отладка приложения, для которого была выполнена команда присоединения к процессу (**Отладка > Подключиться к процессу**) вместо запуска приложения с помощью команды **Пуск** в меню **Отладка**;

- отладка оптимизированного кода;

- отладка старой версии кода после того, как новую версию не удалось собрать из-за ошибок сборки.

## <a name="see-also"></a>См. также
- [Режим "Изменить и продолжить" (Visual C#)](../debugger/edit-and-continue-visual-csharp.md)
- [Практическое руководство. Использование режима "Изменить и продолжить" (C#)](../debugger/how-to-use-edit-and-continue-csharp.md)