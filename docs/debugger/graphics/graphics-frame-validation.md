---
title: Проверка кадров графики | Документация Майкрософт
ms.date: 03/02/2017
ms.topic: conceptual
f1_keywords:
- vs.graphics.FrameValidation
ms.assetid: 1e639182-1301-4e28-9c1e-b5df732f3f1b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 49248c6209f9e56e51551f6cd3d4af66ecac8b56
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72735500"
---
# <a name="graphics-frame-validation"></a>Проверка кадров графики
<!-- VERSIONLESS -->
Visual Studio 2017 и более поздних версий поддерживают средство **проверки кадров**.  В окне "Проверка кадров" отображаются ошибки и предупреждения, связанные со списком событий.  Чтобы открыть это окно, выберите меню **Представление > Проверка кадров**.

![Проверка кадра](media/gfx_diag_frame_validation.png)

Нажмите кнопку **Выполнить проверку** в верхнем левом углу, чтобы начать анализ.  В зависимости от сложности кадра выполнение проверки может занять несколько минут.  Данные, которые здесь появляются, представляют собой комбинацию из двух источников: сообщения, которые сам инструмент D3D испускает при включенном параметре [SDK Layers](/windows/desktop/direct3d11/overviews-direct3d-11-devices-layers) (Слои пакета SDK), и данные, которые собираются из собственного внутреннего отслеживания состояния инструмента. После завершения вы увидите несколько столбцов данных:

| **Столбец** | **Описание** |
|------------| - |
| Идентификатор события | Идентификатор, который сопоставляется с записью в окне [Список событий](graphics-event-list.md). |
| Серьезность | Повреждение, ошибка, предупреждение, информация или сообщение. |
| Категория | Определение приложений, различие, инициализация, очистка, компиляция, создание состояния, установка состояния, получение состояния, выполнение, обработка ресурсов, шейдер, избыточность и неиспользуемое. |
| Сообщение | Сообщение, связанное с событием. |
| событие | Событие, связанное с ошибкой или предупреждением. |

## <a name="see-also"></a>См. также
[Диагностика графики (отладка графики DirectX)](visual-studio-graphics-diagnostics.md)
<!-- /VERSIONLESS -->