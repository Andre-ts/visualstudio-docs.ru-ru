---
title: Изменение данных в наборах данных
ms.date: 11/04/2016
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- datasets [Visual Basic], editing data
- data [Visual Studio], editing in datasets
ms.assetid: 50d5c580-fbf7-408f-be70-e63ac4f4d0eb
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: fe59b30e9af7ee1d98c0aba65339af1d53cba8fb
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "85282466"
---
# <a name="edit-data-in-datasets"></a>Изменение данных в наборах данных
Изменение данных в таблицах данных аналогично изменению данных в таблице в любой базе данных. Процесс может включать в себя вставку, обновление и удаление записей в таблице. В форме с привязкой к данным можно указать, какие поля доступны для изменения пользователем. В таких случаях инфраструктура привязки данных обрабатывает все отслеживание изменений, чтобы изменения можно было отправить обратно в базу данных позже. Если вы собираетесь вносить изменения в данные программными средствами и планируете их отправить обратно в базу данных, необходимо использовать объекты и методы, которые выполняют отслеживание изменений.

Помимо изменения фактических данных, можно также выполнить запрос к, <xref:System.Data.DataTable> чтобы получить определенные строки данных. Например, можно запрашивать отдельные строки, отдельные версии строк (исходные и предложенные), строки, которые были изменены, или строки с ошибками.

## <a name="to-edit-rows-in-a-dataset"></a>Изменение строк в наборе данных
Чтобы изменить существующую строку в, необходимо <xref:System.Data.DataTable> выбрать расположение, которое <xref:System.Data.DataRow> нужно изменить, а затем присвоить обновленные значения нужным столбцам.

Если вы не знакомы с индексом строки, которую нужно изменить, используйте `FindBy` метод для поиска по первичному ключу:

[!code-csharp[VbRaddataEditing#3](../data-tools/codesnippet/CSharp/edit-data-in-datasets_1.cs)]
[!code-vb[VbRaddataEditing#3](../data-tools/codesnippet/VisualBasic/edit-data-in-datasets_1.vb)]

Если вы знакомы с индексом строки, можно получить доступ к строкам и отредактировать ее следующим образом:

[!code-csharp[VbRaddataEditing#5](../data-tools/codesnippet/CSharp/edit-data-in-datasets_2.cs)]
[!code-vb[VbRaddataEditing#5](../data-tools/codesnippet/VisualBasic/edit-data-in-datasets_2.vb)]

## <a name="to-insert-new-rows-into-a-dataset"></a>Вставка новых строк в набор данных
Приложения, использующие привязанные к данным элементы управления, обычно добавляют новые записи с помощью кнопки **Добавить новую** в [элементе управления BindingNavigator](/dotnet/framework/winforms/controls/bindingnavigator-control-windows-forms).

Чтобы вручную добавить новые записи в набор данных, создайте новую строку данных, вызвав метод для DataTable. Затем добавьте строку в <xref:System.Data.DataRow> коллекцию ( <xref:System.Data.DataTable.Rows%2A> ) объекта <xref:System.Data.DataTable> :

[!code-csharp[VbRaddataEditing#1](../data-tools/codesnippet/CSharp/edit-data-in-datasets_3.cs)]
[!code-vb[VbRaddataEditing#1](../data-tools/codesnippet/VisualBasic/edit-data-in-datasets_3.vb)]

Чтобы хранить сведения, необходимые набору данных для отправки обновлений в источник данных, используйте <xref:System.Data.DataRow.Delete%2A> метод для удаления строк из таблицы данных. Например, если приложение использует TableAdapter (или <xref:System.Data.Common.DataAdapter> ), `Update` метод TableAdapter удаляет строки в базе данных, которые имеют значение <xref:System.Data.DataRow.RowState%2A> <xref:System.Data.DataRowState.Deleted> .

Если приложению не требуется отсылать обновления обратно в источник данных, можно удалить записи путем прямого доступа к коллекции строк данных ( <xref:System.Data.DataRowCollection.Remove%2A> ).

#### <a name="to-delete-records-from-a-data-table"></a>Удаление записей из таблицы данных

- Вызовите <xref:System.Data.DataRow.Delete%2A> метод объекта <xref:System.Data.DataRow> .

     Этот метод не удаляет запись физически. Вместо этого он помечает запись для удаления.

    > [!NOTE]
    > Если вы получаете свойство Count объекта <xref:System.Data.DataRowCollection> , результирующее число включает записи, которые были помечены для удаления. Чтобы получить точное число записей, которые не отмечены для удаления, можно выполнить цикл по коллекции, просмотрев <xref:System.Data.DataRow.RowState%2A> свойство каждой записи. (Записи, отмеченные для удаления, имеют значение <xref:System.Data.DataRow.RowState%2A> <xref:System.Data.DataRowState.Deleted> .) Кроме того, можно создать представление данных для набора данных, которое фильтруется на основе состояния строки и получает из него свойство Count.

В следующем примере показано, как вызвать <xref:System.Data.DataRow.Delete%2A> метод, чтобы пометить первую строку в `Customers` таблице как удаленную:

[!code-csharp[VbRaddataEditing#8](../data-tools/codesnippet/CSharp/edit-data-in-datasets_4.cs)]
[!code-vb[VbRaddataEditing#8](../data-tools/codesnippet/VisualBasic/edit-data-in-datasets_4.vb)]

## <a name="determine-if-there-are-changed-rows"></a>Определение наличия измененных строк
При внесении изменений в записи в наборе данных сведения об этих изменениях сохраняются до их фиксации. Изменения фиксируются при вызове `AcceptChanges` метода набора данных или таблицы данных либо при вызове `Update` метода TableAdapter или адаптера данных.

Изменения записываются двумя способами в каждой строке данных:

- Каждая строка данных содержит сведения, связанные с ее (например,,, <xref:System.Data.DataRow.RowState%2A> <xref:System.Data.DataRowState.Added> <xref:System.Data.DataRowState.Modified> <xref:System.Data.DataRowState.Deleted> или <xref:System.Data.DataRowState.Unchanged> ).

- Каждая строка измененных данных содержит несколько версий этой строки ( <xref:System.Data.DataRowVersion> ), исходную версию (до изменений) и текущую версию (после изменений). В течение периода, когда ожидается изменение (время, когда вы можете ответить на <xref:System.Data.DataTable.RowChanging> событие), также доступна третья версия — предложенная версия.

<xref:System.Data.DataSet.HasChanges%2A>Метод набора данных возвращает `true` , если в наборе данных были внесены изменения. Определив, что измененные строки существуют, можно вызвать `GetChanges` метод <xref:System.Data.DataSet> или, <xref:System.Data.DataTable> чтобы вернуть набор измененных строк.

#### <a name="to-determine-if-changes-have-been-made-to-any-rows"></a>Определение того, были ли внесены изменения в строки

- Вызовите <xref:System.Data.DataSet.HasChanges%2A> метод набора данных для проверки измененных строк.

В следующем примере показано, как проверить возвращаемое значение метода, <xref:System.Data.DataSet.HasChanges%2A> чтобы определить, имеются ли измененные строки в наборе данных с именем `NorthwindDataset1` :

[!code-csharp[VbRaddataEditing#12](../data-tools/codesnippet/CSharp/edit-data-in-datasets_5.cs)]
[!code-vb[VbRaddataEditing#12](../data-tools/codesnippet/VisualBasic/edit-data-in-datasets_5.vb)]

## <a name="determine-the-type-of-changes"></a>Определение типа изменений
Можно также проверить, какие типы изменений были сделаны в наборе данных, передав значение из <xref:System.Data.DataRowState> перечисления в <xref:System.Data.DataSet.HasChanges%2A> метод.

#### <a name="to-determine-what-type-of-changes-have-been-made-to-a-row"></a>Определение типа изменений, внесенных в строку

- Передайте <xref:System.Data.DataRowState> значение в <xref:System.Data.DataSet.HasChanges%2A> метод.

В следующем примере показано, как проверить набор данных с именем `NorthwindDataset1` , чтобы определить, были ли добавлены новые строки.

[!code-csharp[VbRaddataEditing#13](../data-tools/codesnippet/CSharp/edit-data-in-datasets_6.cs)]
[!code-vb[VbRaddataEditing#13](../data-tools/codesnippet/VisualBasic/edit-data-in-datasets_6.vb)]

## <a name="to-locate-rows-that-have-errors"></a>Обнаружение строк с ошибками
При работе с отдельными столбцами и строками данных могут возникнуть ошибки. Можно проверить свойство, `HasErrors` чтобы определить, существуют ли ошибки в <xref:System.Data.DataSet> , <xref:System.Data.DataTable> или <xref:System.Data.DataRow> .

1. Проверьте `HasErrors` свойство, чтобы проверить наличие ошибок в наборе данных.

2. Если `HasErrors` свойство имеет значение `true` , выполните итерацию по коллекциям таблиц, а затем по строкам, чтобы найти строку с ошибкой.

[!code-csharp[VbRaddataEditing#23](../data-tools/codesnippet/CSharp/edit-data-in-datasets_7.cs)]
[!code-vb[VbRaddataEditing#23](../data-tools/codesnippet/VisualBasic/edit-data-in-datasets_7.vb)]

## <a name="see-also"></a>См. также раздел

- [Инструменты набора данных в Visual Studio](../data-tools/dataset-tools-in-visual-studio.md)
