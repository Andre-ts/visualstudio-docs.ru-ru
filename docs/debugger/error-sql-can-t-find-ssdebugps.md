---
title: SQL не удается обнаружить компонент SSDEBUGPS | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: error-reference
f1_keywords:
- vs.debug.error.sqlde_cant_find_ssdebugps
dev_langs:
- CSharp
- VB
- FSharp
- C++
- SQL
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 50c8b6c2385879e4cf41c8cc2aea57715050b5e2
ms.sourcegitcommit: 062615c058d2ff44751e8d0c704ccfa3c5543469
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90851792"
---
# <a name="error-sql-can39t-find-ssdebugps"></a>Ошибка: SQL не удается обнаружить компонент SSDEBUGPS

Файл SSDEBUGPS.dll — компонент узла отладки SQL Server.

Эта ошибка возникает при попытке запустить отладку и указывает, что указанный файл не удается обнаружить на компьютере [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)]. Существуют две возможные причины этого: установка удаленной отладки не выполнялась или по каким-либо иным причинам файл был удален.

Существуют два способа разрешить эту проблему: повторное выполнение установки удаленной отладки и копирование файла на компьютер [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)].

Чтобы выполнить повторный запуск установки удаленной отладки, следуйте инструкциям в статье [Удаленная отладка](../debugger/remote-debugging.md).

Если есть возможность найти копию файла ssdebugps.dll, можно скопировать этот файл на компьютер [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)]. Этот файл должен быть в каталоге \Program Files\ Common Files\Microsoft Shared\SQL Debugging. Можно найти этот файл на другом компьютере [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] или на компьютере с установленной средой Visual Studio 2005.

Копирование файла SSDEBUGPS.dll на компьютер SQL Server 2005:

1. Скопируйте файл в каталог с тем же именем и путем на компьютер [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)].

2. Зарегистрируйте этот файл, запустив **Командную строку** и выполнив следующую команду:

    ```cmd
    regsvr32 ssdebugps.dll
    ```
