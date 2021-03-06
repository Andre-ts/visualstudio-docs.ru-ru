---
title: Создание операторов сравнения для типов, реализующих интерфейс IComparable
ms.date: 05/12/2020
ms.topic: reference
author: mikadumont
ms.author: midumont
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 31e33b562a5a11ff77c1d610fbce9e90506b036d
ms.sourcegitcommit: 1d4f6cc80ea343a667d16beec03220cfe1f43b8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85290909"
---
# <a name="generate-comparison-operators-for-types-that-implement-icomparable"></a>Создание операторов сравнения для типов, реализующих интерфейс IComparable

Область применения этого формирования кода:

- C#

**Что?** Теперь вы можете создавать операторы **сравнения** для типов, реализующих интерфейс IComparable.

**Когда?** Если у вас есть тип, реализующий интерфейс IComparable, операторы сравнения будут добавлены к нему автоматически.

**Зачем?** Если вы реализуете тип значения, рекомендуем переопределить метод **Equals**, чтобы повысить производительность по сравнению со стандартной реализацией метода Equals в ValueType.

## <a name="how-to"></a>Практические советы

1. Поместите курсор внутри класса или на ключевое слово IComparable.

2. Затем выполните одно из следующих действий:

   - Нажмите клавиши **CTRL**+ **.** чтобы открыть меню **Быстрые действия и рефакторинг**.

   - Щелкните правой кнопкой мыши и выберите меню **Быстрые действия и рефакторинг**.

   - Нажмите кнопку ![с отверткой](../media/screwdriver-icon.png) , которая отображается в левом поле.

   ![Создание операторов сравнения](media/generate-comparison-operators.png)

3. В раскрывающемся меню выберите **Создать "Equals(object)"** .

## <a name="see-also"></a>См. также

- [Создание кода](../code-generation-in-visual-studio.md)
- [Просмотр изменений](../../ide/preview-changes.md)
