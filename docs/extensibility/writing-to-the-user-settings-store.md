---
title: Запись в хранилище параметров пользователя | Документация Майкрософт
ms.date: 05/23/2019
ms.topic: how-to
ms.assetid: efd27f00-7fe5-45f8-9b97-371af732be97
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ec4d9cdda975d0f80e9d8523ec18a19c24c9418a
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "85906208"
---
# <a name="writing-to-the-user-settings-store"></a>Запись в хранилище параметров пользователя
Параметры пользователя — это доступные для записи параметры, такие как шаблоны в диалоговом окне **Сервис/параметры** , окна свойств и некоторые другие диалоговые окна. Расширения Visual Studio могут использовать их для хранения небольших объемов данных. В этом пошаговом руководстве показано, как добавить приложение "Блокнот" в Visual Studio как внешнее средство, читая данные из хранилища пользовательских параметров и записывая в него.

## <a name="writing-to-the-user-settings-store"></a>Запись в хранилище параметров пользователя

1. Создайте проект VSIX с именем Усерсеттингссторикстенсион, а затем добавьте пользовательскую команду с именем Усерсеттингссторекомманд. Дополнительные сведения о создании пользовательской команды см. в разделе [Создание расширения с помощью команды меню](../extensibility/creating-an-extension-with-a-menu-command.md) .

2. В UserSettingsStoreCommand.cs добавьте следующие директивы using:

    ```csharp
    using System.Collections.Generic;
    using Microsoft.VisualStudio.Settings;
    using Microsoft.VisualStudio.Shell.Settings;
    ```

3. В Менуитемкаллбакк удалите тело метода и получите хранилище параметров пользователя следующим образом:

    ```csharp
    private void MenuItemCallback(object sender, EventArgs e)
    {
        SettingsManager settingsManager = new ShellSettingsManager(ServiceProvider);
        WritableSettingsStore userSettingsStore = settingsManager.GetWritableSettingsStore(SettingsScope.UserSettings);
    }
    ```

4. Теперь выясните, является ли Блокнот уже установленным как внешний инструмент. Чтобы определить, имеет ли параметр Тулкмд значение «Notepad», необходимо выполнить итерацию по всем внешним инструментам:

    ```csharp
    private void MenuItemCallback(object sender, EventArgs e)
    {
        SettingsManager settingsManager = new ShellSettingsManager(ServiceProvider);
        WritableSettingsStore userSettingsStore = settingsManager.GetWritableSettingsStore(SettingsScope.UserSettings);

        // Find out whether Notepad is already an External Tool.
        int toolCount = userSettingsStore.GetInt32("External Tools", "ToolNumKeys");
        bool hasNotepad = false;
        CompareInfo Compare = CultureInfo.InvariantCulture.CompareInfo;
        for (int i = 0; i < toolCount; i++)
        {
            if (Compare.IndexOf(userSettingsStore.GetString("External Tools", "ToolCmd" + i), "Notepad", CompareOptions.IgnoreCase) >= 0)
            {
                hasNotepad = true;
                break;
            }
        }
    }

    ```

5. Если Блокнот не был установлен как внешний инструмент, установите его следующим образом:

    ```vb
    private void MenuItemCallback(object sender, EventArgs e)
    {
        SettingsManager settingsManager = new ShellSettingsManager(ServiceProvider);
        WritableSettingsStore userSettingsStore = settingsManager.GetWritableSettingsStore(SettingsScope.UserSettings);

        // Find out whether Notepad is already installed.
        int toolCount = userSettingsStore.GetInt32("External Tools", "ToolNumKeys");
        bool hasNotepad = false;
        CompareInfo Compare = CultureInfo.InvariantCulture.CompareInfo;
        for (int i = 0; i < toolCount; i++)
        {
            if (Compare.IndexOf(userSettingsStore.GetString("External Tools", "ToolCmd" + i), "Notepad", CompareOptions.IgnoreCase) >= 0)
            {
                hasNotepad = true;
                break;
            }
        }

        string message = (hasNotepad) ? "Notepad already installed" : "Installing Notepad";
         if (!hasNotepad)
        {
            userSettingsStore.SetString("External Tools", "ToolTitle" + toolCount, "&Notepad");
            userSettingsStore.SetString("External Tools", "ToolCmd" + toolCount, "C:\\Windows\\notepad.exe");
            userSettingsStore.SetString("External Tools", "ToolArg" + toolCount, "");
            userSettingsStore.SetString("External Tools", "ToolDir" + toolCount, "$(ProjectDir)");
            userSettingsStore.SetString("External Tools", "ToolSourceKey" + toolCount, "");
            userSettingsStore.SetUInt32("External Tools", "ToolOpt" + toolCount, 0x00000011);

            userSettingsStore.SetInt32("External Tools", "ToolNumKeys", toolCount + 1);
        }
    }
    ```

6. Протестируйте код. Помните, что он добавляет Блокнот как внешний инструмент, поэтому необходимо выполнить откат реестра перед повторным запуском.

7. Создайте код и начните отладку.

8. В меню **Сервис** выберите команду **вызвать усерсеттингссторекомманд**. Это приведет к добавлению Блокнота в меню **Сервис** .

9. Теперь вы должны увидеть Блокнот в меню Сервис/параметры, а затем щелкнуть **Блокнот** , чтобы открыть экземпляр блокнота.
