---
title: Конструктор действий с конструктор рабочих процессов блок-схемой
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Flowchart.UI
- System.Activities.Statements.FlowStep.UI
- System.Activities.Core.Presentation.FlowStart.UI
ms.assetid: d5af2276-5215-4138-880a-cf2b90bbf3a0
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d786e9acfa99d2b106b72822a0106e2161724790
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "75597039"
---
# <a name="flowchart-activity-designer"></a>Конструктор действия блок-схемы

Действие <xref:System.Activities.Statements.Flowchart> служит для создания рабочих процессов, в которых определяются и поддерживаются сложные элементы управления потоком. <xref:System.Activities.Statements.Flowchart>Можно создать либо в коде, либо с помощью Конструктор рабочих процессов. В этом разделе документируется конструктор рабочих процессов интерфейс. Конструктор действий конструктор рабочих процессов рабочего процесса позволяет разработчикам создавать рабочие процессы естественным образом.

## <a name="the-flowchart-activity"></a>Действие Flowchart

<xref:System.Activities.Statements.Flowchart> определяет уникальный <xref:System.Activities.Statements.Flowchart.StartNode%2A>, который выполняется при запуске рабочего процесса и использует сеть связанных <xref:System.Activities.Statements.Flowchart.Nodes%2A> для создания произвольных циклов или отклонения потока выполнения в любое место рабочего процесса в любой момент времени.

### <a name="using-the-flowchart-activity-designer"></a>Использование конструктора действия Flowchart

Конструктор операций с **блок-схемой** можно найти в категории " **схема** " **панели элементов**, щелкнув вкладку **область элементов** на конструктор рабочих процессов. Кроме того, можно выбрать **область элементов** в меню **вид** или нажать клавиши **CTRL** + **ALT** + **X**.

Конструктор действий **блок-схемы** можно перетащить из **панели элементов** в конструктор рабочих процессовную поверхность, где обычно размещаются конструкторы действий: как корневое действие или как дочерний элемент другой операции потока управления. Если конструктор действий **блок-схемы** перемещается на пустую конструктор рабочих процессов поверхность, он создает <xref:System.Activities.Statements.Flowchart> действие, которое по умолчанию представляет собой в развернутом представлении, в котором начальный узел, инициирующий выполнение, представляется зеленым шариком. Если конструктор действий **блок-схемы** перемещается в другую операцию потока управления, он представляется в режиме сворачивания, который можно расширить, дважды щелкнув конструктор действий **блок-схемы** . Любое действие на **панели элементов** можно перетащить непосредственно в конструктор действий **блок-схемы** , включая другие действия потока управления.

После перетаскивания различных конструкторов действий на холст конструктор рабочих процессов <xref:System.Activities.Activity> объекты, которые они представляют, можно связать друг с другом, чтобы указать порядок выполнения. Чтобы создать ссылку между исходным и целевым действием, поместите мышь над конструктором исходного действия, после чего на каждой его стороне появятся квадратные маркеры. Щелкните один из них и, удерживая нажатой кнопку мыши, перетащите его к одному из маркеров, которые аналогичным образом появляются на целевом действии при наведении мыши. Отпустите кнопку мыши, чтобы создать связь между этими двумя действиями, которая будет отмечена стрелкой от исходного к целевому конструктору.

### <a name="flowchart-activity-properties"></a>Свойства действия Flowchart

В следующей таблице показаны свойства <xref:System.Activities.Statements.Flowchart> и описано их использование в конструкторе. Эти свойства можно изменить в таблице свойств или в области конструктора.

|Имя свойства|Обязательно|Использование|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|Неверно|Указывает отображаемое имя конструктора действия в заголовке. По умолчанию используется Flowchart. Значение можно изменить в окне **Свойства** или непосредственно в заголовке конструктора действий.<br /><br /> Несмотря на то что свойство <xref:System.Activities.Activity.DisplayName%2A> не является обязательным, его все же рекомендуется использовать.|
|<xref:System.Activities.Statements.Flowchart.Variables%2A>|Неверно|Коллекция переменных, доступных в этом <xref:System.Activities.Statements.Flowchart> для общего доступа к состоянию для вложенных действий.|
|<xref:System.Activities.Statements.Flowchart.StartNode%2A>|Неверно|<xref:System.Activities.Statements.FlowNode>, который выполняется при запуске <xref:System.Activities.Statements.Flowchart>.|
|<xref:System.Activities.Statements.Flowchart.Nodes%2A>|Неверно|Содержит коллекцию объектов <xref:System.Activities.Statements.FlowNode> в <xref:System.Activities.Statements.Flowchart>.|

## <a name="see-also"></a>См. также раздел

- [Блок-схема](../workflow-designer/flowchart-activity-designers.md)
- [FlowDecision](../workflow-designer/flowdecision-activity-designer.md)
- [FlowSwitch\<T>](../workflow-designer/flowswitch-t-activity-designer.md)
