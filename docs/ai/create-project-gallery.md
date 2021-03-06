---
title: Создание проекта
description: Создание проекта с помощью образца из коллекции Машинного обучения Azure
keywords: ии, visual studio, машинное обучение azure
author: jillre
ms.author: jillfra
manager: jillfra
monikerRange: vs-2017
ms.date: 11/13/2017
ms.topic: how-to
ms.workload:
- multiple
ms.openlocfilehash: 4bcc1932bad5b34d9695257feb163654f6b99514
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "85371629"
---
# <a name="create-an-ai-project-from-the-azure-machine-learning-gallery-in-visual-studio"></a>Создание проекта ИИ с помощью коллекции машинного обучения Azure в Visual Studio

Машинное обучение Azure интегрировано с инструментами Visual Studio для сценариев ИИ. Вы можете использовать его для отправки заданий машинного обучения на удаленные целевые вычислительные ресурсы, например виртуальные машины Azure, кластеры Spark и т. д. 

После [установки инструментов Visual Studio для сценариев ИИ](installation.md) вы можете легко создать проект Python с помощью готовых рецептов из коллекции примеров машинного обучения Azure.

> [!NOTE]
> Необходимо установить Azure Machine Learning Workbench. 

1. Запустите Visual Studio. Откройте **обозреватель сервера**, открыв меню **Инструменты ИИ** и выбрав пункт **Выбрать кластер**

    ![Выбор кластера](media/create-project-gallery/select-cluster.png)

2. Войдите в свою подписку машинного обучения Azure. Для этого щелкните правой кнопкой мыши узел **Машинное обучение Azure** в обозревателе сервера, выберите **Войти** и следуйте указаниям.

    ![Вход](media/create-project-gallery/azureml-login.png)

3. Последовательно выберите **"Инструменты ИИ" > "Коллекция примеров машинного обучения Azure"** .

    ![Коллекция примеров](media/create-project-gallery/gallery.png)

4. Для этого краткого руководства выберите образец **MNIST using TensorFlow** и нажмите кнопку **Установить**. Укажите следующие сведения:

   - **Группа ресурсов**: группа ресурсов Azure, в которой будут храниться ваши метаданные
   - **Учетная запись**: учетная запись экспериментирования в машинном обучении Azure
   - **Рабочая область**: рабочая область машинного обучения Azure
   - **Тип проекта**: платформа машинного обучения. Для нашего случая выберите **TensorFlow**
   - **Добавить в решение**: определяет, следует ли добавлять образец в текущее решение Visual Studio или нужно создать и открыть новое решение
   - **Путь к проекту**: место, где будет сохранен код
   - **Имя проекта**: введите **TensorFlowMNIST**

   ![Итоговый проект при использовании шаблона приложения Python](media/create-project-gallery/new-AzureSampleProject.png)

5. Visual Studio создает файл проекта (файл `.pyproj` на диске) вместе с другими файлами, заданными в образце. В случае с шаблоном MNIST проект содержит несколько файлов.

    ![mnist](media/create-project-gallery/azml-mnist.png)

6. Отправьте задание в машинное обучение Azure.

    ![mnist](media/create-project-gallery/submit-azml.png)

7. Запустите его в контейнере Docker или на своем локальном компьютере

    ![mnist](media/create-project-gallery/azml-local.png)
