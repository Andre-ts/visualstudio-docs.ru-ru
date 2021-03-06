---
title: Настройка пакета решения SharePoint с помощью целевых объектов MSBuild
titleSuffix: ''
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, packages
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 9845f755d184c18b6b5ade4c5504e393edae7b00
ms.sourcegitcommit: 9d2829dc30b6917e89762d602022915f1ca49089
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2020
ms.locfileid: "91585814"
---
# <a name="how-to-customize-a-sharepoint-solution-package-by-using-msbuild-targets"></a>Инструкции. Настройка пакета решения SharePoint с помощью целевых объектов MSBuild
  С помощью целевых объектов MSBuild в командной строке можно настроить, как Visual Studio будет создавать файлы пакетов SharePoint (*. wsp*). Например, можно настроить свойства MSBuild для изменения промежуточного каталога пакета и группы элементов MSBuild с перечисляемыми файлами.

## <a name="customize-and-run-msbuild-targets"></a>Настройка и запуск целевых объектов MSBuild
 При настройке целевых объектов BeforeLayout и AfterLayout можно выполнять задачи до компоновки пакета, например добавлять, удалять или изменять файлы, которые будут упакованы.

#### <a name="to-customize-the-beforelayout-target"></a>Настройка целевого объекта Бефорелайаут

1. Откройте текстовый редактор, например Блокнот, и добавьте следующий код.

   ```xml
   <Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
     <Target Name="BeforeLayout">
       <Message Importance="high" Text="In the BeforeLayout Target"></Message>
     </Target>
   </Project>
   ```

    Этот пример выводит сообщение перед упаковкой данного целевого объекта.

2. Присвойте файлу имя **кустомлайаут. SharePoint. targets**, а затем сохраните его в папке для проекта SharePoint.

3. Откройте проект, откройте его контекстное меню и выберите команду **Выгрузить проект**.

4. В **Обозреватель решений**откройте контекстное меню проекта, а затем выберите **изменить** * \<ProjectName> . vbproj* или **Edit** * \<ProjectName> . csproj*.

5. После строки `Import` в конце файла проекта добавьте следующую строку.

   ```xml
   <Import Project="CustomLayout.SharePoint.targets" />
   ```

6. Сохраните и закройте файл проекта.

7. В **Обозреватель решений**откройте контекстное меню проекта и выберите **Перезагрузить проект**.

   При публикации проекта сообщение выведется, прежде чем начнется упаковка.

#### <a name="to-customize-the-afterlayout-target"></a>Настройка целевого объекта Афтерлайаут

1. В строке меню выберите **файл**  >  **Открыть**  >  **файл**.

2. В диалоговом окне **Открытие файла** перейдите в папку проекта, выберите файл кустомлайаут. Target, а затем нажмите кнопку **Открыть** .

3. Непосредственно перед тегом `</Project>` добавьте следующий код:

   ```xml
   <Target Name="AfterLayout">
     <Message Importance="high" Text="In the AfterLayout Target"></Message>
   </Target>
   ```

    Этот пример выводит сообщение после того, как этот целевой объект упаковывается.

4. Сохраните и закройте файл targets.

5. Перезапустите среду Visual Studio и откройте проект.

   При публикации проекта сообщение BeforeLayout выведется, прежде чем начнется упаковка, а сообщение AfterLayout выведется после того, как упаковка завершится.

## <a name="see-also"></a>См. также
- [Упаковка и развертывание решений SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)
