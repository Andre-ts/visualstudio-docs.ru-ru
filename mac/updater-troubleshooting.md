---
title: Сбой средства обновления при получении сведений
description: Инструкции по исправлению неполадок при появлении сообщения об ошибке получения сведений об обновлении в Visual Studio 2019 для Mac
ms.topic: troubleshooting
author: heiligerdankgesang
ms.author: dominicn
ms.date: 04/13/2019
ms.technology: vs-ide-install
ms.assetid: 31AF914A-C66B-4CD3-9429-39695E0E94AE
ms.openlocfilehash: 2ccef07a2889f66df3e7f217ea292b61ffc0008f
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "75405478"
---
# <a name="troubleshooting-updater-has-errors-retrieving-information"></a>Устранение неполадок: Сбой средства обновления при получении сведений

В редких случаях при попытке [обновить Visual Studio для Mac](update.md) может появиться сообщение об ошибке при получении сведений об обновлении. В этом случае попробуйте сделать следующее:

- Проверьте подключение к Интернету. Разорванное подключение — наиболее распространенная причина этой ошибки.
  - Если не удается скачать компонент, нажмите кнопку "Повторить" рядом с именем компонента, чтобы повторить попытку.
- Перезагрузите IDE.
- Если это сообщение об ошибке не исчезает, попробуйте выполнить обновление с помощью установщика, если на вашем компьютере есть файл **.dmg** (его можно скачать на сайте [visualstudio.com](https://visualstudio.microsoft.com/vs/mac/)).
  - Установщик обновит все установленные компоненты на компьютере.
  - Повторно запустив установщик, вы также сможете установить недостающие компоненты, которые не были установлены ранее.
- Кроме того, можно попробовать удалить скачанные кэшированные данные. Для этого удалите файл, расположенный в `~/Library/Caches/VisualStudio/8.0/TempDownload/index.xml`.
- Если вы работаете с более ранней версией Visual Studio для Mac, у вас могут быть другие номера версий в каталоге `VisualStudio`. Также удалите файл `index.xml` в этих путях.
